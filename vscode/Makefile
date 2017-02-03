.PHONY: help
help:
	@echo "Please use any of the following targets:"
	@echo "    build owner=   Build the dockerfile. Tag it with {owner}/vscode."
	@echo "    run owner=     Run the image '{owner}/vscode' in a container."
	@echo "                   This container destroys itself after you quit vscode."

.PHONY: build
build:
	docker build -t ${owner}/vscode .

.PHONY: run
run:
	docker run -d --rm \
	-v /tmp/.X11-unix:/tmp/.X11-unix \
	-v ${HOME}:/home/user \
	-e DISPLAY=unix${DISPLAY} \
	--device /dev/dri \
	${owner}/vscode

