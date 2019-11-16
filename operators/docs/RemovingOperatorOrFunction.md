# Removing operator and function
There are a lot of reasons for removing ONNX operator or function, such us being replaced with different operator or can be decomposed by a set of operators. This document describes the criteria for removing an existing ONNX operator from the standard.

## Removing operator
Any operator in ONNX was added because it was required by a model and/or framework. In order to deprecate such an operator we need to specify its replacement.
* Operator can’t be deprecated unless there is a replacement.
    * Replacement can be a more general operator that supersedes the old one.
    * Or a set of primitive operators that together can implement the same functionality and behavior of the deprecated operator (Function).
* If the deprecated operator can be decomposed by existing operators then it must be converted to a function.
* If replacement isn’t in ONNX standard yet, then add the replacement operator or set of operators first.
* No grace period is needed for deprecated operators.

## Removing function
Function, by definition, is composed of ONNX primitives; however, function could have been accelerated by framework or runtime that support ONNX. So, removing function is not recommended, with the exception of adding another single function which supersede its functionality.

## Document removing operator or function
To make sure everyone is aware of the deprecation, the following need to happen:
* Any removed operator or function from ONNX need to be mentioned in the release note.
* Their old documentation needs to be updated to show the new replacement and the mapping between the old to the new.
    * Only `def.cc` need to be remove, `old.cc` will remain.
    * `old.cc` need to be updated with the mapping to the replacement.
* ONNX checker need to be updated to error with a proper message.
* All removed operators need to be appended at the end of the `operator.md` file.
