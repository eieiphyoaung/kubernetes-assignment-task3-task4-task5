Task 4
- successfully deployed bookinfo microservices using your own images from AWS ECR (your image should not be able to pull from others, only yourself)

Task 5
- successfully deployed bookinfo microservices using your own choice of Container Registry (your image should not be able to pull from others, only yourself)

###
aws ecr create-repository --repository-name bookinfo/bookinfo-productpage-v1 --region=ap-southeast-1 --profile=master-programmatic-admin
aws ecr create-repository --repository-name bookinfo/bookinfo-details-v1 --region=ap-southeast-1 --profile=master-programmatic-admin
aws ecr create-repository --repository-name bookinfo/bookinfo-ratings-v1 --region=ap-southeast-1 --profile=master-programmatic-admin
aws ecr create-repository --repository-name bookinfo/bookinfo-reviews-v1 --region=ap-southeast-1 --profile=master-programmatic-admin
aws ecr create-repository --repository-name bookinfo/bookinfo-reviews-v2 --region=ap-southeast-1 --profile=master-programmatic-admin
aws ecr create-repository --repository-name bookinfo/bookinfo-reviews-v3 --region=ap-southeast-1 --profile=master-programmatic-admin

aws ecr get-login-password --region ap-southeast-1 --profile=master-programmatic-admin | docker login --username AWS --password-stdin 820242905231.dkr.ecr.ap-southeast-1.amazonaws.com

docker pull ei2000/bookinfo-productpage-v1:1.20.3
docker pull ei2000/bookinfo-details-v1:1.20.3
docker pull ei2000/bookinfo-ratings-v1:1.20.3
docker pull ei2000/bookinfo-reviews-v1:1.20.3
docker pull ei2000/bookinfo-reviews-v2:1.20.3
docker pull ei2000/bookinfo-reviews-v3:1.20.3

docker tag ei2000/bookinfo-productpage-v1:1.20.3 8820242905231.dkr.ecr.ap-southeast-1.amazonaws.com/bookinfo/bookinfo-productpage-v1:1.20.3
docker tag ei2000/bookinfo-details-v1:1.20.3 820242905231.dkr.ecr.ap-southeast-1.amazonaws.com/bookinfo/bookinfo-details-v1:1.20.3
docker tag ei2000/bookinfo-ratings-v1:1.20.3 820242905231.dkr.ecr.ap-southeast-1.amazonaws.com/bookinfo/bookinfo-ratings-v1:1.20.3
docker tag ei2000/bookinfo-reviews-v1:1.20.3 820242905231.dkr.ecr.ap-southeast-1.amazonaws.com/bookinfo/bookinfo-reviews-v1:1.20.3
docker tag ei2000/bookinfo-reviews-v2:1.20.3 820242905231.dkr.ecr.ap-southeast-1.amazonaws.com/bookinfo/bookinfo-reviews-v2:1.20.3
docker tag ei2000/bookinfo-reviews-v3:1.20.3 820242905231.dkr.ecr.ap-southeast-1.amazonaws.com/bookinfo/bookinfo-reviews-v3:1.20.3

docker push 820242905231.dkr.ecr.ap-southeast-1.amazonaws.com/bookinfo/bookinfo-productpage-v1:1.20.3
docker push 820242905231.dkr.ecr.ap-southeast-1.amazonaws.com/bookinfo/bookinfo-details-v1:1.20.3
docker push 820242905231.dkr.ecr.ap-southeast-1.amazonaws.com/bookinfo/bookinfo-ratings-v1:1.20.3
docker push 820242905231.dkr.ecr.ap-southeast-1.amazonaws.com/bookinfo/bookinfo-reviews-v1:1.20.3
docker push 820242905231.dkr.ecr.ap-southeast-1.amazonaws.com/bookinfo/bookinfo-reviews-v2:1.20.3
docker push 820242905231.dkr.ecr.ap-southeast-1.amazonaws.com/bookinfo/bookinfo-reviews-v3:1.20.3


kubectl create secret docker-registry my-secret --from-file=$HOME/.docker/config.json -n ecr


