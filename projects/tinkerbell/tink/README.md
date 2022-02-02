## **Tink**
![Version](https://img.shields.io/badge/version-v0.6.0-blue)

[Tink](https://github.com/tinkerbell/tink) consists of the tink-server, tink-worker, and tink-cli. The tink-worker and tink-server communicate over gRPC, and are responsible for processing workflows. The CLI is the user-interactive piece for creating workflows and their building blocks, templates and hardware data.

### Updating

1. Review commits upstream [repo](https://github.com/tinkerbell/tink) and decide on release tag to track. 
1. Update the `GIT_TAG` file to have the new desired tag based on upstream.
1. Verify the golang version has not changed. Currently the version 1.17 mentioned in the github workflows [ci.yaml](https://github.com/tinkerbell/tink/blob/main/.github/workflows/ci.yaml) is being used to build.
1. Verify no changes have been made to the Dockerfile for each image under [cmd/<image-name>](https://github.com/tinkerbell/tink/tree/main/cmd) looking specifically for added dependencies.
1. Update checksums and attribution using `make update-attribution-checksums-docker PROJECT=tinkerbell/tink` from the root of the repo.
1. Update the version at the top of this Readme.
1. Run `make generate` from the root of the repo to update the UPSTREAM_PROJECTS.yaml file.