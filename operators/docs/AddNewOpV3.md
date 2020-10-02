# Table of Contents
1. [New Operator or Function](#new_operator_or_function)
    1. [Step 1: Proposing a new operator/function](#step1_new_operator_or_function)
    2. [Step 2: Coding Conventions](#step2_coding_conventions)
    3. [Step 3: Submit PR](#step3_new_operator_or_function)
    4. [Step 4: PR Review by Operators SIG](#step4_new_operator_or_function)
    5. [Step 5: ONNX release](#step5_new_operator_or_function)

2. [Removing Operator or Function](#removing_operator_or_function)
    1. [Removing operator](#removing_operator)
    2. [Removing function](#removing_function)
    3. [Document removing operator or function](#document_removing_operator_or_function)

# Proposing and submitting a new operator or function to ONNX <a name="new_operator_or_function"></a>

Operators are the basic building blocks that define ONNX model. With a rich set of operators, ONNX can describe most DNN and ML models from various frameworks. Functions allow for composing complex operators from more primitive operators, without increasing the number of operators in ONNX. ONNX specification includes a core set of operators that enable many models. It is a non-goal to add all possible operators, however, more operators are added as needed to cover evolving needs.

In this document, we describe the process of accepting a new proposed operator and how to properly submit a new operator as part of ONNX standard. The goal is to improve on what we currently have based on our experience, learning and feedbacks we gathered from the community.

## 4 steps to add an operator <a name="steps_to_add_an_operator"></a>
1. Draft your proposal
2. Follow coding conventions
3. Submit PR for new operator/function
4. Review of PR by Operators SIG
5. Merging of PR and inclusion in next ONNX release

## Step 1: Proposing a new operator/function <a name="step1_new_operator_or_function"></a>
In order to propose a new operator/function, the following is needed:
1. If the operator can be composed by other ONNX operators, then it should be a function and not an operator.
2. If the operator can be split to new primitives, propose those primitives instead and make the operator a function.
3. The operator should be based on a popular model architecture to validate that this operator solves an actual problem. In case, the model is private or IP and can't be shared, the operator doesn't belong to the standard and should be implemented as custom OP.
4. The operator should be implemented by at-least one (well-known) framewor to validate the actual behavior of the operator and its usage.
5. Operator signature and behavior:
    1. If the operator is available in numpy, prefer numpy semantics.
    2. If the operator is available in more than one frameworks, make sure that your design is general and covers those frameworks.
6. Prefer attributes over inputs.

## Step 2: Codeing Conventions <a name="step2_codeing_conventions"></a>
To maintain consistency in operator signatures, follow these principles:
1. All attribute names should be lower case and use underscores when applicable
2. Any input/output represented by a single letter should be capitalized (i.e. X)
3. Any input/output represented by a full word or multiple words should be all lower case and uses underscores between 2 words as this helps with readability
4. Any input/output representing a bias tensor should utilize the name "B"
5. Any input/output representing a weight tensor should utilize the name “W”
6. “axes” should be used when an input, output or attribute represents multiple axes
7. “axis” should be used when an input, output or attribute represents a single axis

## Step 3: Submit PR <a name="step3_new_operator_or_function"></a>
Once the criteria of proposing new operator/function has been satisfied, submit a PR for the new operator/function. The PR should include the following (The reviewer is expected to verify the completeness of the PR before signoff).
1. Description:
    1. Write a detailed description about the operator, and its expected behavior. The description should be clear enough to avoid confusion between implementors.
    2. Add an example in the description to illustrate the usage.
    3. Add reference to the source of the operator in the original framework in the description.
    4. Write the mathematic formula or a pseudocode in the description. The core algorithm needs to be very clear.
2. Write a reference implementation in Python, this reference implementation should cover all the expected behavior of the operator. Only in extremely rare case (with approval from Operator SIG), this requirement will be waived.
3. Writing test:
    1. It should have the same coverage as the original framework.
    2. Generate the test data from the original framework operator, the submission needs to include the script that generated the test data and all its depencdencies. (where will this script be checked in?)
    3. The testing examples will be extracted to the doc.(explain this better? Its not clear what is expected here)
    4. We also generate binary data for it. (what is the action item for the PR author? )
    5. Example: https://github.com/onnx/onnx/blob/master/onnx/backend/test/case/node/abs.py (does this need to be as a separate bullet?)    
4. Operator version: check out the 
[versioning doc](https://github.com/fdwr/onnx/blob/master/docs/Versioning.md#operator-versioning)
5. Update the documentation and generate the test data.
    1. Running [the script](https://github.com/onnx/onnx/blob/master/tools/update_doc.sh)
to update the doc and generate the test data.
6. Test functions.
    1. In the case of functions, the test data generator generates two test instances from each test case,
    one for a model containing the function (call) and one for a model containing the function body.
    The test case containing the function body should be tested with an existing backend as a sanity
    check for the function-body definition. (Since the CI infrastructure does not currently use any
    backend or reference-implementation, this test needs to be done manually.)
7. Shape Inference function 
    1. Provide a shape inference function in cases where it is meaningful and applicable.
    2. In cases where shape inference is not possible, it must have logic to perform 
rank inference at the very least (adding right amount of dimensions to the output shape)
    3. Shape inference functions must be accompanied by unit tests (https://github.com/onnx/onnx/blob/master/onnx/test/shape_inference_test.py).
    4. You can refer to the shape inference function for the `TopK` operator while implementing your own function (https://github.com/onnx/onnx/blob/master/onnx/defs/math/defs.cc#L943)

### Example to Follow
[PR 1959](https://github.com/onnx/onnx/pull/1959) is a good example to follow.

## Step 4: PR Review by Operators SIG <a name="step4_new_operator_or_function"></a>
The [Operators SIG](https://github.com/onnx/sigs/tree/master/operators) is responsible for the operators/functions in the ONNX specification. The SIG regularly meets and reviews PRs.

### Sign-off
At least two sign-off from the Operators SIG [contributors](https://github.com/onnx/onnx/tree/master/community#community-roles).

## Step 5: ONNX release <a name="step5_new_operator_or_function"></a>
Once the PR is reviewed and signed off by the Operators SIG, it will be merged. Your new operator/function will be part of the master branch and available to anyone building from source. These are not official releases. ONNX periodically releases official new versions that are a snapshot of the master branch. Your new operator/function will be part of that release.

# Removing operator or function <a name="removing_operator_or_function"></a>
There are a lot of reasons for removing existing ONNX operator or function, such us being replaced with different operator or can be decomposed by a set of other operators. This document describes the criteria of removing an existing ONNX operator from the standard.

## Removing operator <a name="removing_operator"></a>
Any operator in ONNX was added because it was required by a model and/or framework. In order to deprecate such an operator we need to do the following.
* Operator can’t be deprecated unless there is a replacement.
    * Replacement can be a more general operator that supersedes the old one.
    * Or a set of primitive operators that together can implement the same functionality and behavior of the deprecated operator (Function).
* If the deprecated operator can be decomposed by existing operators then it must be converted to a function.
* If replacement isn’t in ONNX standard yet, then add the replacement operator or set of operators first.
* No grace period is needed for deprecated operators.

## Removing function <a name="removing_function"></a>
Function, by definition, is composed of ONNX primitives; however, function could have been accelerated by framework or runtime that support ONNX. So, removing function is not recommended, with the exception of adding another single function which supersede its functionality.

## Document removing operator or function <a name="document_removing_operator_or_function"></a>
To make sure everyone is aware of the deprecation, the following need to happen:
* Any removed operator or function from ONNX need to be mentioned in the release note.
* Their old documentation needs to be updated to show the new replacement and the mapping between the old to the new.
    * Only `def.cc` need to be remove, `old.cc` will remain.
    * `old.cc` need to be updated with the mapping to the replacement.
* ONNX checker need to be updated to error with a proper message.
* All removed operators need to be appended at the end of the `operator.md` file.