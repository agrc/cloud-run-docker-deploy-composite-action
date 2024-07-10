# Changelog

## [2.0.2](https://github.com/agrc/cloud-run-docker-deploy-composite-action/compare/v2.0.1...v2.0.2) (2024-07-10)


### Dependencies

* bump docker/build-push-action in the ci-dependencies group ([c01f487](https://github.com/agrc/cloud-run-docker-deploy-composite-action/commit/c01f4874e8a17f4e3f6e5958b1d42f42bd2abe86))

## [2.0.1](https://github.com/agrc/cloud-run-docker-deploy-composite-action/compare/v2.0.0...v2.0.1) (2024-04-15)


### 🐛 Bug Fixes

* use image id instead of latest ([bbd7b44](https://github.com/agrc/cloud-run-docker-deploy-composite-action/commit/bbd7b449981e7589c8586bddae79cf3025373b58))


### 🌲 Dependencies

* bump the ci-dependencies group with 2 updates ([06d3f9b](https://github.com/agrc/cloud-run-docker-deploy-composite-action/commit/06d3f9bf4c77a515ad1422132d1609848c65f2c0))

## [2.0.0](https://github.com/agrc/cloud-run-docker-deploy-composite-action/compare/v1.1.2...v2.0.0) (2023-10-11)


### ⚠ BREAKING CHANGES

* Requires creation of artifact registry in the associated GCP project.

### 🐛 Bug Fixes

* migrate from container to artifact registry ([dcd9621](https://github.com/agrc/cloud-run-docker-deploy-composite-action/commit/dcd96210f5e069ed1160c1f8e0992ccefd854d06)), closes [#23](https://github.com/agrc/cloud-run-docker-deploy-composite-action/issues/23)


### 🌲 Dependencies

* bump the ci-dependencies group with 5 updates ([c8510e1](https://github.com/agrc/cloud-run-docker-deploy-composite-action/commit/c8510e1be9e89f8ddfa963c53344abea96a1d1ba))
* bump the ci-dependencies group with 5 updates ([fda11e1](https://github.com/agrc/cloud-run-docker-deploy-composite-action/commit/fda11e1b5fa3fb8d3c8d5221adc161efcda7a5c0))

## [1.1.2](https://github.com/agrc/cloud-run-docker-deploy-composite-action/compare/v1.1.1...v1.1.2) (2023-01-25)


### 🐛 Bug Fixes

* disable SLSA provenance since GCR doesn't support it ([3c4c196](https://github.com/agrc/cloud-run-docker-deploy-composite-action/commit/3c4c196049b22d6c1352bf6a0f1e9fc69048d3dd)), closes [#13](https://github.com/agrc/cloud-run-docker-deploy-composite-action/issues/13)

## [1.1.1](https://github.com/agrc/cloud-run-docker-deploy-composite-action/compare/v1.1.0...v1.1.1) (2022-12-10)


### 🐛 Bug Fixes

* December dependency bumps 🌲 ([738853d](https://github.com/agrc/cloud-run-docker-deploy-composite-action/commit/738853d8b70a625fb2ffa2e703c01abc17a1ace3))

## [1.1.0](https://github.com/agrc/cloud-run-docker-deploy-composite-action/compare/v1.0.0...v1.1.0) (2022-10-12)


### 📖 Documentation Improvements

* fix syntax and switch to v1 in example ([7e7184b](https://github.com/agrc/cloud-run-docker-deploy-composite-action/commit/7e7184b5bfe60f8fe1bdebbbf28872c944436388))


### 🚀 Features

* add docker-context and docker-file input parameters ([f4a0394](https://github.com/agrc/cloud-run-docker-deploy-composite-action/commit/f4a03943fe405cb8892ffde6558fc09662d20d58))

## 1.0.0 (2022-10-06)


### 🐛 Bug Fixes

* add checkout step ([fbd4bdf](https://github.com/agrc/cloud-run-docker-deploy-composite-action/commit/fbd4bdf6b2a208c69cdc168f469e88349d58d8ad))
* add repo-token input ([335eb7e](https://github.com/agrc/cloud-run-docker-deploy-composite-action/commit/335eb7e79eb2698ed3ab709be5d4bc58d7adea51))
* input syntax ([9bb6524](https://github.com/agrc/cloud-run-docker-deploy-composite-action/commit/9bb6524271d4715d37d7beedfba7505f25644a1a))
* steps syntax ([9f9c937](https://github.com/agrc/cloud-run-docker-deploy-composite-action/commit/9f9c93712c6c2a476a6839d7b5fc7b5fe58450df))


### 🚀 Features

* add docker build args and cloud run secrets ([409b34c](https://github.com/agrc/cloud-run-docker-deploy-composite-action/commit/409b34cb161c37d1e0011c19cf12d12cf9abed27))
* add release action ([0e93f77](https://github.com/agrc/cloud-run-docker-deploy-composite-action/commit/0e93f77cbca0aaf23f7a030eaf5f514fbabcca41))
* initial commit ([2aad473](https://github.com/agrc/cloud-run-docker-deploy-composite-action/commit/2aad4737df9f7e612318213ea97a2b57d1e97704))


### 📖 Documentation Improvements

* fix syntax ([e95b3ff](https://github.com/agrc/cloud-run-docker-deploy-composite-action/commit/e95b3ffb0395a6d3da866a11be6e8bfd2c27062f))
* update for more options ([b7f4d28](https://github.com/agrc/cloud-run-docker-deploy-composite-action/commit/b7f4d28dae843bfca53cb63a301cf752c0d660f8))
