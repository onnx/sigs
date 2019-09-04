# What problems we are trying to solve
This document is intended to capture common ONNX converter issues and provide general recommendations for all converters to address them in a similar fashion.

# Issues and recommendations
| Issue ID | Issue description | Recommendation |
| -------------- |:------------------:|:------------------:|
|14|How to handle unsupported data types between ONNX and frameworks?|Provide an auto-cast level parameter as an optional user input. The default is "no cast", meaning unsupported data types will cause an exception and fail the conversion. The other levels are "upcast", for ex. float32 to float64, and "upcast and downcast". We also recommend produce logging at the debug level whenever auto-cast occurs so that users could see clearly where the auto-cast is applied.|
|18|How to handle deprecated operators?|Frontend converters: Do not add deprecated ops, with respect to the target opset version, into onnx graph. Use the new/replacement op instead. Backend converters: Run ONNX checker before conversion, the default behavior in Backend.prepare(...), which will throw an error message indicating the deprecated op. If the converter doesn't use checker, it should handle the op with the previous definition and print out a warning message state that this op is deprecated at this opset version and advise user to use the "new" op to replace this in the future.|
