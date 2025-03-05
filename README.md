# Dispersion Device

## Overview

## Technical

[High Level Design Doc](https://docs.google.com/document/d/13tRIg-ery4yuNY8-GabsWyR-y-mVJbLYWCKS7MwkBQo/edit?usp=sharing)

## Releases

> **NOTE**
> The following process is targeting a major or minor release, if you are doing a hotfix you can skip the release management section, pick a commit hash from the branch of the base major.minor version you are hotfixing, and then start the release process.

### Naming

Releases follow [semantic versioning](https://semver.org/). So the first release name will be v1.0.0.

### Release Management

- a milestone is created for each foreseeable release with the name associated with the release (ie v1.0.0)
- a release project is created for each foreseeable release with the name associated with the release (ie v1.0.0)
- all issues targeting a milestone should be linked to the milestone
- all tasks not created through the issue infrastructure should go in the release project
- once all tasks and issues in the project and milesone are complete, the associated commit can begin the release process

### Release Process

Assuming a git hash is selected, the hash must complete the entire process to be turned into a release. Failure at any point results in the hash not becoming a release.

- all automated tests pass
- all manual tests cases pass and are documented in the repo wiki pages
- a git tag of the semantic version (ie v1.0.0) is applied and pushed to the remote
- if the tag is not a hotfix version change, create a branch based on the major.minor version (ie v1.0)
- if the tag is not a hotfix version change, close the release project
- if the tag is not a hotfix version change, mark milestone as done
- create a github release for the above tag. release title should be the semantic version (ie v1.0.0) and all executed test plan documents should be linked.

## Contributing

### Documentation

There are a few types of documentation:

1. actively discussed design concepts that require async engagement from multiple people
1. developer facing code design documentation
1. end user facing documentation

**Type 1: Active Design Discussions**

All documentation in this category belong in google drive in the [design docs folder](https://drive.google.com/drive/folders/1usFVFsNC5s3LDBOTIhIMigCr1eJ5Gkz9?usp=drive_link). A new sub folder should be created with a unique id and descriptive name. The template is <id> - <description> (ie "1 - System Architecture"). We typically just add one to the largest numbered project in the folder to get the unique id.

**Type 2: Developer Facing**

All documentation in this category should be a readme in the repo, preferably in the root of the associated code module. If necessary link out to documents or images in the google drive folders create per the expectation for type 1 documentation above.

**Type 3: End User Facing**

All documentation in this category should be in markdown files in the /docs folder for this repo.

> **NOTE**
> We decided to do this over using the github wiki so that documentation changes can be version controlled in association the relevant development.

### Code Standards

- Follow Rust's [official style guide](https://doc.rust-lang.org/nightly/style-guide/), use `rustfmt` to format your code.
- Use `clippy` to lint your code.
- Maintain 80% test coverage.
- When adding new features, update the public documentation in the `docs/` directory, and module-level documentation as neccessary.
