TAG ?= $(shell git describe --tags --always --dirty)
REGISTRY ?= jeetdesai99

docker-build-codeserver:
	$(MAKE) docker-build -C ../codeserver TAG=${TAG}

docker-build: docker-build-codeserver
	docker build -t ${REGISTRY}/codeserver-python:${TAG} --build-arg BASE_IMG=${REGISTRY}/codeserver:${TAG} --progress plain --no-cache -f Dockerfile . 

docker-push:
	docker push ${REGISTRY}/codeserver-python:${TAG}
