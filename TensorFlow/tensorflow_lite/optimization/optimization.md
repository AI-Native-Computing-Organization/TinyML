# Optimization

After convering, we can optimize it here  for size or,inference time or, both (default). This will reduce the size (From 9 MB to 2-3 MB)

```converter.optimizations = [tf.lite.Optimize.DEFAULT]```


# Representative Data/ Quantization
We'll start by taking a sample of our test data
from the data set that we originally used to train and test the model.
The goal is to have a representative sample of the type of data
that the model would expect to see, so that the model can be calibrated
for the ranges of data expected.
This is then wrapped in a function that returns its input values.
This type of function is typically called a Data Generator,
so here, the function name is Representative Data Generator.
Now that you have a Data Generator that can
provide a good example of what type of data
the model is expected to run inference on,
we can tell the converter to use that as the representative
data set for the model.
And then we can tell the model that the supported_ops
should be INT8 by setting the supported_ops property like this 


```def representative_data_gen():                          
#     for input_value, _ in test_batches.take(100):
#         yield [input_value]
# converter.representative_dataset = representative_data_gen
# converter.target_spec.supported_ops = [tf.lite.OpsSet.TFLITE_BUILTINS_INT8]```
