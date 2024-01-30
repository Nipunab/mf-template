# Humana Module Federation Template

This repository holds the skeleton templates for building HMF compliant VueJS applications. For a full list of examples, please reference [the official examples](https://github.com/module-federation/module-federation-examples).

## Getting Started

If you have not already done so, you will need to make sure your NPM can authenticate with JFrog, please reference [this guide](https://experience-wiki-app-exp-dev.npii-aks.dhp-east2us-npe.humana.com/docs/nucleus/connecting-to-the-feed).

Create a new repository in your desired system and update the remote url of this repository.

## Developing locally

### Install the modules using the CI commaind

```
npm ci
```

### Start the relevant dev servers

```
npm run serve
```

### Run your unit tests

```
npm run test:unit
```

### Lints and fixes files

```
npm run lint
```

### Create a release

```

npm run version
git push --follow-tags

```

## Build and Release

- Run the version command with your initial version `npm run version --release-as 0.0.1`
- Push the tagged repository to your chosen system `git push --follow-tags`
- Create a build pipeline in ADO using the `azure-pipelines.yml` file as a template
- Create a release pipeline in ADO using the `azure-release.json` file as a template
- Update the Agent Job pool to Linux-NextGen_DockerOnly
- Attach the artifact from your build pipeline to the release
- Add the `dhp-infra-admin-sp` and `dha-dhp-artifact` variable groups
