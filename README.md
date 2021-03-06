[![Build Status](http://doyuni-devops.duckdns.org/jenkins/job/demo/badge/icon)](http://doyuni-devops.duckdns.org/jenkins/job/demo)
[![App Status](http://doyuni-argo.duckdns.org/api/badge?name=covid-demo&revision=true)](http://doyuni-argo.duckdns.org/applications/covid-demo)

# k8s-pipeline
Experience CI/CD pipeline with kubernetes 

- CI 
  - GitHub Actions
    - Check PR (build docker image)
    <img width="1009" alt="github_action1" src="https://user-images.githubusercontent.com/46062199/98458523-df6a4880-21d4-11eb-88cf-cf63d601c318.png">
    <img width="999" alt="github_action2" src="https://user-images.githubusercontent.com/46062199/98458354-fd36ae00-21d2-11eb-98b1-df04baada3f7.png">
  - Jenkins 
    - Loacal Host + Docker + ngrok   
     problem: different URL whenever restarting -> It's annoying to register github webhook every time.
    - Google Cloud + Kubernetes
    - Covid demo app Jenkins pipeline
    <img width="1220" alt="jenkins" src="https://user-images.githubusercontent.com/46062199/98458341-dc6e5880-21d2-11eb-8b45-35c1a1a523a3.png">
 
- Continuous Delivery
  - Nexus repository
  
- CD (Continuous Deployment)
  - Deploy on k8s with Argo CD
  <img width="1281" alt="argocd" src="https://user-images.githubusercontent.com/46062199/98458345-e1cba300-21d2-11eb-96a9-df8e802b1725.png">
  
  - Performance Test
    - nGrinder
       - Test scenario
    <img width="1275" alt="ngrinder-1000" src="https://user-images.githubusercontent.com/46062199/98464744-2c1b4700-2208-11eb-8488-bad360f39123.png">
  
       - Test Report 
         - virtual user: 99      
    <img width="1356" alt="ngrinder" src="https://user-images.githubusercontent.com/46062199/98464735-1efe5800-2208-11eb-8ca4-b6fa84861578.png">     

- virtual user: 1000 (default: DB maxconnection = 151, wait_timeout = 28800)
 <img width="1359" alt="ngrinder-test" src="https://user-images.githubusercontent.com/46062199/98464745-2de50a80-2208-11eb-9c98-713e4ee08dcd.png">    
          
- virtual user: 1000 (Modify: DB maxconnection = 500, wait_timeout = 60)      
 <img width="1281" alt="n1" src="https://user-images.githubusercontent.com/46062199/98465539-f462ce00-220c-11eb-85dc-1031e77b96ad.png">     
    
    
- APM
  - Grafana(Visualizing) & Prometheus
    - k8s monitoring
  <img width="1269" alt="Grafana" src="https://user-images.githubusercontent.com/46062199/98458457-3e7b8d80-21d4-11eb-9e54-13addd309dcc.png">
            
    - Monitoring during testing with nGrinder
<img width="1165" alt="스크린샷 2020-11-08 오후 9 53 06" src="https://user-images.githubusercontent.com/46062199/98465597-51f71a80-220d-11eb-9166-f99c9a71b7f3.png">
<img width="1174" alt="스크린샷 2020-11-08 오후 9 53 13" src="https://user-images.githubusercontent.com/46062199/98465598-53284780-220d-11eb-89dc-ed35d9e6f40b.png">
