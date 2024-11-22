We can code complex codes using tensorflow but to use that on IoT devices or micro-controllers, we need to make the code small and compact. This can be done using **tensorflow lite**. But first we need to train a model using tensorflow. Then we need to convert it to a small model. It will do this by **prunning the model**(Basically removing unnecessary neurons)


![Prunning](https://github.com/AI-Native-Computing-Organization/TinyML/blob/testing/src/prunning.png)

It also applies  Quantization: Quantization is a technique used in various fields, including signal processing, machine learning, and data compression. It involves mapping a large set of values to a smaller set, often with a finite number of elements. This process can be thought of as rounding or approximating values to a lower precision.

![Quantization](https://github.com/AI-Native-Computing-Organization/TinyML/blob/testing/src/quant.png)

Here the range reduced from **float32 to  int8**.

Check out the [code](https://github.com/AI-Native-Computing-Organization/TinyML/blob/testing/TensorFlow/convert_code.ipynb)
