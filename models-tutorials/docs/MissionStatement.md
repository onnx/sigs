<!--- SPDX-License-Identifier: Apache-2.0 -->

# Priorities and Mission Statement
#### ONNX Model Zoo and Tutorials SIG
#### Vinitra Swamy

This document outlines the mission statement and core priorities of the ONNX Model Zoo and Tutorials Special Interest Group (SIG).

### Mission Statement

The Model Zoo and Tutorials SIG is responsible for the comprehensive collection of state of the art ONNX models from a variety of sources and making it easy for users to get started with ONNX and the ecosystem around it. Concretely, this SIG has ownership over the [onnx/tutorials](https://github.com/onnx/tutorials) and [onnx/models](https://github.com/onnx/models) repositories, as well as tutorials located in the [onnx/onnx-docker](https://github.com/onnx/onnx-docker) repository, instructive blog posts and conference participation.

We intend to focus on the following priorities in the new year.

## Model Zoo

### 1. Establish model entry guidelines

Delineate a set of rules and templates for what must be included with the proposal of a new model for the model zoo. Enforce these rules as part of the PR process.

### 2. CI testing for model zoo

Add continuous integration (CI) testing for the model zoo, so that models are tested regularly upon updates and additions. This has the added benefit of validating the current state of the ONNX models so we can identify which models are difficult for users to run out-of-the-box.

A successful CI pipeline has the base requirement of at least running the ONNX model checker to validate the models. In the ideal case, a CI pipeline includes unit tests for all the models through the input and output PB datapoints included with the model. We would also like to centralize the storage of models from each individual contributor’s server to Git LFS so the model binaries can be stored directly in the Github project.

### 3. Add more models

We currently have ~30 models in the ONNX model zoo. Over the last year, there has not been a dedicated effort into substantially increasing that number. One of the incentives for a new user to join ONNX is the ease of getting started with the state-of-the-art – this involves dedicating time to reach out to relevant model authors and sending requests to convert and publish their models.

### 4. Regulate model quality

Once the set of model entry guidelines are defined for the Model Zoo, we must enforce these rules by removing or revamping contributed models that do not fit the criteria. The CI tests will also be helpful in validating these checks.

### 5. Improve discoverability and organization of models

We need to have cohesive visuals with the onnx.ai website to improve the Model Zoo browsing experience. We should also link to model zoo from relevant websites and standardize the Github README page layout for an ONNX model. The categories the models have been classified into were refined earlier this year but could be revisited to improve user experience.


## Tutorials

### 6. Remove friction points for new ONNX users

Right now, the onboarding experience to ONNX is a little scattered. On the onnx/onnx README, a new user has to scroll down two page lengths and look through “Source” instructions to see the PyPi command for easy installation. There should be a quick start guide for new users earlier in the README with a link to the tutorials and the model zoo.

### 7. Improve discoverability and organization of tutorials

There are tutorials in the onnx/tutorials repository, others in the onnx/docker repository, and some in various company blogs and Jupyter notebooks. Most of these are linked from onnx/tutorials, but the organization structure of the README and the stored tutorials could be improved. We also need to expose tutorials on the onnx.ai website.

### 8. Establish tutorial entry guidelines

We need to create a set of requirements for addition of a new ONNX tutorial and enforce these guidelines with current tutorials. We should also set up a CI for tutorial notebooks – ideally, these notebooks should run end-to-end without breaking.
