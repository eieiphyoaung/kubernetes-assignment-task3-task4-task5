# jfrog artifactory

docker login -ueieiphyo.ycc@gmail.com trialvzqg22.jfrog.io
cmVmdGtuOjAxOjE3Nzg1MTI4ODI6Qlp4Z2Vpa2d4THdnSGFSQUdMTGl0aHU4THdl

docker pull trialvzqg22.jfrog.io/eep-productpage-docker/hello-world:latest

docker pull ei2000/bookinfo-productpage-v1:1.20.3
docker pull ei2000/bookinfo-details-v1:1.20.3
docker pull ei2000/bookinfo-ratings-v1:1.20.3
docker pull ei2000/bookinfo-reviews-v1:1.20.3
docker pull ei2000/bookinfo-reviews-v2:1.20.3
docker pull ei2000/bookinfo-reviews-v3:1.20.3

docker tag ei2000/bookinfo-productpage-v1:1.20.3 trialvzqg22.jfrog.io/eep-bookinfo-docker-local/bookinfo-productpage-v1:1.20.3
docker tag ei2000/bookinfo-details-v1:1.20.3 trialvzqg22.jfrog.io/eep-bookinfo-docker-local/bookinfo-details-v1:1.20.3
docker tag ei2000/bookinfo-ratings-v1:1.20.3 trialvzqg22.jfrog.io/eep-bookinfo-docker-local/bookinfo-ratings-v1:1.20.3
docker tag ei2000/bookinfo-reviews-v1:1.20.3 trialvzqg22.jfrog.io/eep-bookinfo-docker-local/bookinfo-reviews-v1:1.20.3
docker tag ei2000/bookinfo-reviews-v2:1.20.3 trialvzqg22.jfrog.io/eep-bookinfo-docker-local/bookinfo-reviews-v2:1.20.3
docker tag ei2000/bookinfo-reviews-v3:1.20.3 trialvzqg22.jfrog.io/eep-bookinfo-docker-local/bookinfo-reviews-v3:1.20.3


docker push trialvzqg22.jfrog.io/eep-bookinfo-docker-local/bookinfo-productpage-v1:1.20.3
docker push trialvzqg22.jfrog.io/eep-bookinfo-docker-local/bookinfo-details-v1:1.20.3
docker push trialvzqg22.jfrog.io/eep-bookinfo-docker-local/bookinfo-ratings-v1:1.20.3
docker push trialvzqg22.jfrog.io/eep-bookinfo-docker-local/bookinfo-reviews-v1:1.20.3
docker push trialvzqg22.jfrog.io/eep-bookinfo-docker-local/bookinfo-reviews-v2:1.20.3
docker push trialvzqg22.jfrog.io/eep-bookinfo-docker-local/bookinfo-reviews-v3:1.20.3

kubectl create ns jfrog
kubectl create secret docker-registry jfrog-secret --from-file=$HOME/.docker/config.json -n jfrog
kubectl apply -f bookinfo-jfrog.yaml -n jfrog
kubectl port-forward svc/productpage -n jfrog --address 0.0.0.0 9080:9080
watch kubectl get all -n jfrog
kubectl get secret jfrog-secret -n jfrog --output=yaml


trialvzqg22.jfrog.io/eep-bookinfo-docker-local/bookinfo-productpage-v1:1.20.3
trialvzqg22.jfrog.io/eep-bookinfo-docker-local/bookinfo-details-v1:1.20.3
trialvzqg22.jfrog.io/eep-bookinfo-docker-local/bookinfo-ratings-v1:1.20.3
trialvzqg22.jfrog.io/eep-bookinfo-docker-local/bookinfo-reviews-v1:1.20.3
trialvzqg22.jfrog.io/eep-bookinfo-docker-local/bookinfo-reviews-v2:1.20.3
trialvzqg22.jfrog.io/eep-bookinfo-docker-local/bookinfo-reviews-v3:1.20.3