## QAT
There are two forms of quantization:
1) **Post-training quantization** (Used in [optimization folder ](TensorFlow/tensorflow_lite/optimization) where, as part of the conversion process, your model’s internal weights and ops get converted to int8 and uint8.
   It’s much easier to use this, and it’s a good way to get started.)
2) **Quantization Aware Technique (QAT)**: It is called an api but this process  is done prior to converting and all. We do it once we are running the training. [Read more](https://www.tensorflow.org/model_optimization/guide/quantization/training)

Note: The effects of quantization do not impact the accuracy that much.
For example, while using MobilenetV1 224, the nonquantized model gives an accuracy of 70.03%; the quantized  one gives an accuracy of 71.06%

Try (TFLite)[https://ai.google.dev/edge/litert/models/convert_to_flatbuffer]

