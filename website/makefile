
SERVICE = masterconsole-website
DOCKER_IMAGE = klakegg/hugo:0.74.3-ext-alpine
DOCKER_RUN_CMD = --name ${SERVICE} --rm -p 1313:1313 -v ${CURDIR}/src:/src

UNAME := $(shell uname)
ifeq ($(UNAME), Linux)
	OPEN_CMD = xdg-open
else
	OPEN_CMD = open
endif

# all: devstart

# dockerenv:
# 	docker build -f dockerfile  . -t ${DOCKER_IMAGE}

bash:
	docker run --rm -it ${DOCKER_RUN_CMD} ${DOCKER_IMAGE} shell

dev:
	docker run ${DOCKER_RUN_CMD} ${DOCKER_IMAGE} server -D

# dist: dockerenv
# 	docker run -it ${DOCKER_RUN_CMD} ${DOCKER_IMAGE} mvn clean install appengine:deploy

# test: dockerenv
# 	docker run -it ${DOCKER_RUN_CMD} ${DOCKER_IMAGE} npm run test


.PHONY: dockerenv bash dev dist test