# Define converter
    An ONNX converter is a software component that converts models from a ML/DNN framework (or backend?) to the ONNX format, or vice versa.

# List of converters
| Framework(/Backend?)        | Exporter (to ONNX)  | Importer (to framwork) |
| -------------- |:------------------:|:------------------:|
|Caffe||https://github.com/MTlab/onnx2caffe|
|Caffe2|https://github.com/pytorch/pytorch/tree/master/caffe2/python/onnx|https://github.com/pytorch/pytorch/tree/master/caffe2/python/onnx|
|Chainer|https://github.com/chainer/onnx-chainer||
|Cognitive Toolkit (CNTK)|https://docs.microsoft.com/en-us/cognitive-toolkit/setup-cntk-on-your-machine|https://docs.microsoft.com/en-us/cognitive-toolkit/setup-cntk-on-your-machine|
|CoreML (Apple)|https://github.com/onnx/onnx-coreml|https://github.com/onnx/onnx-coreml|
|Keras|https://github.com/onnx/keras-onnx||
|LibSVM|https://github.com/onnx/onnxmltools||
|LightGBM|https://github.com/onnx/onnxmltools||
|MATLAB|https://www.mathworks.com/matlabcentral/fileexchange/67296-deep-learning-toolbox-converter-for-onnx-model-format|https://www.mathworks.com/matlabcentral/fileexchange/67296-deep-learning-toolbox-converter-for-onnx-model-format|
|Menoh|https://github.com/pfnet-research/menoh/releases||
|ML.NET|https://www.nuget.org/packages/Microsoft.ML/|https://www.nuget.org/packages/Microsoft.ML/|
|MXNet (Apache)|http://mxnet.incubator.apache.org/api/python/contrib/onnx.html|http://mxnet.incubator.apache.org/api/python/contrib/onnx.html|
|NCNN||https://github.com/Tencent/ncnn|
|NNL (Sony)|https://nnabla.readthedocs.io/en/latest/python/file_format_converter/file_format_converter.html|https://nnabla.readthedocs.io/en/latest/python/file_format_converter/file_format_converter.html|
|PaddlePaddle|https://github.com/PaddlePaddle/paddle-onnx||
|PyTorch|https://pytorch.org/docs/master/onnx.html||
|SAS|https://github.com/sassoftware/python-dlpy|https://github.com/sassoftware/python-dlpy|
|Scikit-Learn|https://github.com/onnx/sklearn-onnx||
|SIGNA (Apache)|https://github.com/apache/incubator-singa/blob/master/doc/en/docs/installation.md|https://github.com/apache/incubator-singa/blob/master/doc/en/docs/installation.md|
|SNPE (Qualcomm)||https://developer.qualcomm.com/docs/snpe/model_conv_onnx.html|
|Spark ML|https://github.com/onnx/onnxmltools||
|Tensorflow|https://github.com/onnx/tensorflow-onnx|https://github.com/onnx/onnx-tensorflow|
|Windows ML||https://docs.microsoft.com/en-us/windows/ai/windows-ml/release-notes|
|XGBoost|https://github.com/onnx/onnxmltools||

# List of non-converters (convert ONNX to run on backend)

| Backend        | Convert to execute on backend |
| -------------- |:------------------:|
|Habana|https://habana.ai/wp-content/uploads/2019/06/Habana-Offers-Gaudi-for-AI-Training.pdf|
|Onnx Runtime|https://github.com/microsoft/onnxruntime|
|TensorRT|https://github.com/onnx/onnx-tensorrt|
|ONNX.js|https://github.com/microsoft/onnxjs|
