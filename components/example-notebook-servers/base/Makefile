TAG ?= $(shell git describe --tags --always --dirty)
REGISTRY ?= jeetdesai99

docker-build:
	docker build -t ${REGISTRY}/base:${TAG} --progress plain --no-cache -f Dockerfile .

docker-push:
	docker push ${REGISTRY}/base:${TAG}