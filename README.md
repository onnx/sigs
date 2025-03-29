<!--- SPDX-License-Identifier: Apache-2.0 -->

# SIGs - Special Interest Groups

As described in the ONNX [governance](https://github.com/onnx/onnx/tree/main/community#sig---special-interest-groups), Special Interest Groups (SIGs) are persistent groups responsible for specific parts of the project. SIGs have open and transparent proceedings to develop goals and implement code contributions. SIGs are also responsible for ongoing maintenance of the code in their areas.

SIG artifacts, including membership list and meeting notes, are stored in this repository.

## Participating
If you are interested in participating, please [join the discussion](https://lfaifoundation.slack.com/archives/C016UBNDBL2") in the respective slack channel.

You can find the schedule of SIG meetings on the [LFX calendar](https://zoom-lfx.platform.linuxfoundation.org/meetings/lfai-onnx?view=month)

## SIG members
The current list of Contributors and Approvers in the SIGs are listed in the [CONTRIBUTORS](CONTRIBUTORS) file. The file also describes the process for updating the list.

## Current SIGs

| Name      | Responsibilities    |
| ------------------ | ------------- |
| [Architecture & Infra](infra) | Defining and maintaining the core ONNX format, the build and CI/CD systems for ONNX repositories, publishing release packages for ONNX, the onnx-docker repository, and creating tools to help integrate with and test against the ONNX standard. This SIG is also the defacto owner of files in the main ONNX repository unless explicitly owned by another SIG. |
| [Compilers](compilers) | Developing and maintaining core compiler technology for optimizing and lowering ONNX format. |
| [Converters](converters) | Developing and maintaining the various converter repositories under ONNX. |
| [Models and tutorials](models-tutorials) | Providing a comprehensive collection of state of the art ONNX models from a variety of sources and making it easy for users to get started with ONNX and the ecosystem around it. |
| [Optimizations](optimizations) | Developing and maintaining solutions to optimize ONNX models, including model compression techniques (e.g. quantization, pruning, distillation, etc.) |
| [Operators](operators) | Determining the operators that are part of the ONNX spec (ONNX and ONNX-ML domains), ensuring high quality operator definitions and documentation, establishing criteria for adding new operators, managing ops domains and compliance tiers, and enforcing versioning mechanisms. |
