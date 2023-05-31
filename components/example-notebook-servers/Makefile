#TAG ?= $(shell git describe --tags --always --dirty)
TAG ?= v1.6.1-new
REGISTRY ?= jeetdesai99

.PHONY: docker-build
docker-build: build-codeserver-python
		@echo "\nAll notebook-server images have been successfully built...\n"

.PHONY: build-codeserver-python
build-codeserver-python:
	@echo "\nBuilding codeserver-python image...\n"
	$(MAKE) docker-build -C codeserver-python TAG=${TAG}

.PHONY: docker-push
docker-push:
	@echo "\nPushing base image...\n"
	$(MAKE) docker-push -C base

	@echo "\nPushing codeserver image...\n"
	$(MAKE) docker-push -C codeserver

	@echo "\nPushing codeserver-python image...\n"
	$(MAKE) docker-push -C codeserver-python 

	@echo "\nAll notebook-server images have been successfully pushed...\n"
