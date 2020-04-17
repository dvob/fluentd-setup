.PHONY: build push

VERSION ?= 1.10.2
IMAGE ?= index.docker.io/dsbrng25b/fluentd:v$(VERSION)

build:
	cp Gemfile.tpl Gemfile
	echo "gem 'fluentd', '$(VERSION)'" >> Gemfile
	docker build -t $(IMAGE) --build-arg from=fluent/fluentd:v$(VERSION)-1.0 .

push:
	docker push $(IMAGE)
