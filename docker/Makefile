localnet-down:
	docker-compose -p localnet \
		-f docker-compose-localnet.yaml \
		-f ipfs-image.yaml \
		-f powergate-build-context.yaml \
		down
.PHONY: localnet-down

localnet: 
	BIGSECTORS=true docker-compose -p localnet \
		-f docker-compose-localnet.yaml \
		-f ipfs-image.yaml \
		-f powergate-build-context.yaml \
		up --build -V
.PHONY: localnet


up: down
	LOTUS_IMAGE_TAG=v1.1.2 \
	docker-compose \
		-p mainnet \
		-f docker-compose.yaml \
		-f ipfs-image.yaml \
		-f powergate-build-context.yaml \
		up --build 
.PHONY: up

down:
	LOTUS_IMAGE_TAG=v1.1.2 \
	docker-compose \
		-p mainnet \
		-f docker-compose.yaml \
		-f ipfs-image.yaml \
		-f powergate-build-context.yaml \
		down
.PHONY: down

