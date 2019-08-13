# What problems we are trying to solve
This document is intended to capture common ONNX converter issues and provide general recommendations for all converters to address them in a similar fashion.

# Issues and recommendations
| Issue ID | Issue description | Recommendation |
| -------------- |:------------------:|:------------------:|
|14|How to handle unsupported data types between ONNX and frameworks?|Provide an auto-cast level parameter as an optional user input. The default is "no cast", meaning unsupported data types will cause an exception and fail the conversion. The other levels are "upcast", for ex. float32 to float64, "downcast", and "upcast and downcast". We also recommend produce logging at the debug level whenever auto-cast occurs so that users could see clearly where the auto-cast is applied.|
