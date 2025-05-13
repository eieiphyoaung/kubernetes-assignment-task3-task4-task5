Task 3
- successfully deployed bookinfo microservices using your own images from DockerHub


## original images

docker.io/istio/examples-bookinfo-productpage-v1:1.20.3
docker.io/istio/examples-bookinfo-details-v1:1.20.3
docker.io/istio/examples-bookinfo-ratings-v1:1.20.3
docker.io/istio/examples-bookinfo-reviews-v1:1.20.3
docker.io/istio/examples-bookinfo-reviews-v2:1.20.3
docker.io/istio/examples-bookinfo-reviews-v3:1.20.3

# productpage
docker pull istio/examples-bookinfo-productpage-v1:1.20.3
docker tag istio/examples-bookinfo-productpage-v1:1.20.3 ei2000/bookinfo-productpage-v1:1.20.3
docker push ei2000/bookinfo-productpage-v1:1.20.3

# details

docker pull istio/examples-bookinfo-details-v1:1.20.3
docker tag istio/examples-bookinfo-details-v1:1.20.3 ei2000/bookinfo-details-v1:1.20.3
docker push ei2000/bookinfo-details-v1:1.20.3

# ratings

docker pull istio/examples-bookinfo-ratings-v1:1.20.3
docker tag istio/examples-bookinfo-ratings-v1:1.20.3 ei2000/bookinfo-ratings-v1:1.20.3
docker push ei2000/bookinfo-ratings-v1:1.20.3

# reviews
docker pull istio/examples-bookinfo-reviews-v1:1.20.3
docker pull istio/examples-bookinfo-reviews-v2:1.20.3
docker pull istio/examples-bookinfo-reviews-v3:1.20.3


docker tag istio/examples-bookinfo-reviews-v1:1.20.3 ei2000/bookinfo-reviews-v1:1.20.3
docker tag istio/examples-bookinfo-reviews-v2:1.20.3 ei2000/bookinfo-reviews-v2:1.20.3
docker tag istio/examples-bookinfo-reviews-v3:1.20.3 ei2000/bookinfo-reviews-v3:1.20.3


docker push ei2000/bookinfo-reviews-v1:1.20.3
docker push ei2000/bookinfo-reviews-v2:1.20.3
docker push ei2000/bookinfo-reviews-v3:1.20.3


#### use own images
docker.io/ei2000/bookinfo-productpage-v1:1.20.3
docker.io/ei2000/bookinfo-details-v1:1.20.3
docker.io/ei2000/bookinfo-ratings-v1:1.20.3
docker.io/ei2000/bookinfo-reviews-v1:1.20.3
docker.io/ei2000/bookinfo-reviews-v2:1.20.3
docker.io/ei2000/bookinfo-reviews-v3:1.20.3

kubectl describe pod/details-v1-668f8ff5b8-f6l5f -n bookinfo

kubectl port-forward -n ko-lw-docker-image svc/productpage 9080:9080 --address=0.0.0.0