## SIG Compiler Meeting 04/04/2023

### Attendance:
Alex, Gong, Haruki, Kiyo, Nathaniel, Philip, Soren, Tung,   

## Agenda:

### Goals of SIG Compiler
- Philip: Provide a compiler focus to the ONNX Specs, with a focus on how to make them lean and expressive. 
- Soren: has practical suggestions (ranked in order of importance).
  - Clarify ambiguities. For example, rules about type conversions are not alwasy clear (rounding modes). To find answer, we often have to look at what ORT is doing de facto.
  - Provide a way to verify an op, shape inference, type. Spoke about the possiblilty of a formal description that can be used to verify an implementation.
  - Fix specs (scalar, inconsitencies). Issue with this is that since we aim to maintain backward compatibility, it may not simplify the task of the compiler writers.
- Alex: should be more proactive with the operator committee to "proof" new ops before they come in the standard. Discussion ensued on how to do this, how relatively easy it is to generate a PR against the ONNX specs.

#### Practical steps:
- review new ops, look for ambiguities
- may organize followup meeting among folks interested int this.
  
### Discussion on OpenXLA
- Alexandre: goal of discussion is to see if OpenXLA is responding to a need that should also be addressed in ONNX.
- Philip: ONNX customers like the fact that ONNX models are stable, and that the PyTorch to ONNX is well supported within PyTorch. Currently the path from PyTorch to StableHLO is less direct. StableHLO aim to provide stability for the OpenXLA project.
