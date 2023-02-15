<!--- SPDX-License-Identifier: Apache-2.0 -->

# ONNX Compiler Special Interest Group (SIG)

This is the working repo for the Compiler Special Interest Group (SIG), which is responsible for compiler solutions that optimizes and lower ONNX core format file to representations that are fed to further compilers, runtimes, or directly executed.
The compiler solutions investigated by this SIG predominantly consumes ONNX core files as defined by the Architecture & Infrastrucutre SIG and uses ONNX operations as defined by the Operator SIG.
This SIG is open to solutions developped in any relevant, open-sourced compiler-frameworks and may sponsor projects that work in specific compiler frameworks.
This SIG also invite discussions on making the ONNX standard more amendable to compiler technology.

This repo contains all the artifacts, materials, meeting notes, and proposals regarding the Compiler SIG.

Feedbacks and contributions are welcome.

## Slack channel
Please sign up at https://slack.lfai.foundation/ and join [onnx-compilers](https://lfaifoundation.slack.com/archives/C01B38FP2AV) channel.
<!--- slack channels to be created / renamed if proposal is accepted -->

## SIG Lead(s)

* Alexandre Eichenberger (IBM)
* Philip Lassen (Groq)

## Logistics

* SIG lead(s) will drive the monthly Compiler SIG meeting.
* Meeting annoucement will be posted in our Slack channel.
* Specific Compiler-SIG projects may meet at a higher frequency.
  * SIG lead(s) may delegate leadership of project meetings to their respective project technical lead(s).
  * Monthly Compiler SIG meetings may take place at the begining of a specific project meeting.
* Feedbacks and topic request are welcome by all.

## Discussion

* Slack channel https://lfaifoundation.slack.com/archives/C018Y2QG7V2
* Documents and artifacts: https://github.com/onnx/sigs/tree/main/compilers

## Meeting notes

* Compiler SIG meeting notes are kept in the [meeting](meetings) folder. 

## Current projects(s)

* Onnx-mlir: lowering ONNX representation to other MLIR representations, including representations for ingestion in the LLVM compiler.
  * Description: [High Level](https://www.onnx.ai/onnx-mlir), [GitHub](https://github.com/onnx/onnx-mlir).
  * Meeting [agenda and notes](https://github.com/onnx/onnx-mlir/wiki/Informal-meeting-agenda-and-notes).
  * Slack channel: [onnx-mlir](https://lfaifoundation.slack.com/archives/C01B38FP2AV)


