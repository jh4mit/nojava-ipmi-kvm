REPO = jh4mit/nojava-ipmi-kvm
TAG = v0.9.2

.PHONY: build-java build-html5 build-all push-java push-html5 push-all

build-all: build-java build-html5

build-java:
	docker build -t $(REPO):$(TAG)-openjdk-7 -f Dockerfile_openjdk-7 .
	docker tag $(REPO):$(TAG)-openjdk-7 $(REPO):latest-openjdk-7

build-html5:
	docker build -t $(REPO):$(TAG)-html5 -f Dockerfile_html5 .
	docker tag $(REPO):$(TAG)-html5 $(REPO):latest-html5

push-all: push-java push-html5

push-java: build-java
	docker push $(REPO):$(TAG)-openjdk-7
	docker push $(REPO):latest-openjdk-7

push-html5: build-html5
	docker push $(REPO):$(TAG)-html5
	docker push $(REPO):latest-html5
