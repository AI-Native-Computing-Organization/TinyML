The overall TensorFlow ecosystem can be represented using a diagram like this -- with the left side of the diagram showing the architecture and APIs that can be used for training models. 

![TF architecture](https://github.com/AI-Native-Computing-Organization/TinyML/blob/testing/src/tf_arch.png)

In the center is the architecture for saving a model, called TensorFlow SavedModel. You can learn more about it at: https://www.tensorflow.org/guide/saved_model

On the right are the ways that models can be deployed.

- The standard TensorFlow models that you’ve been creating this far, trained without any post-training modification can be deployed to Cloud or on-Premises infrastructures via a technology called **TensorFLow Serving**, which can give you a REST interface to the model so inference can be executed on data that’s passed to it, and it returns the results of the inference over HTTP.  You can learn more about it at https://www.tensorflow.org/tfx/guide/serving
- **TensorFlow Lite** is a runtime that is optimized for smaller systems such as Android, iOS and embedded systems that run a variant of Linux, such as a Raspberry Pi. You’ll be exploring that over the next few videos. TensorFlow Lite also includes  a suite of tools that help you convert and optimize your model for this runtime. https://www.tensorflow.org/lite
- **TensorFlow Lite Micro** built on top of TensorFlow Lite and can be used to shrink your model even further to work on microcontrollers and is a core enabling technology for TinyML. https://www.tensorflow.org/lite/microcontrollers
- **TensorFlow.js** provides a javascript-based library that can be used both for training models and running inference on them in JavaScript-based environments such as the Web Browsers or Node.js. https://www.tensorflow.org/js.

**Here is a basica CNN code using tensorflow**

```import tensorflow as tf

data = tf.keras.datasets.mnist

(training_images, training_labels), (val_images, val_labels) = data.load_data()

training_images  = training_images/255.0

val_images = val_images /255.0

model = tf.keras.models.Sequential([tf.keras.layers.Flatten(input_shape=(28,28)),

tf.keras.layers.Dense(20, activation=tf.nn.relu),

tf.keras.layers.Dense(10, activation=tf.nn.softmax)])

model.compile (optimizer='adam',

loss='sparse_categorical_crossentropy',

metrics=['accuracy'])

model.fit(training_images, training_labels, epochs=20, validation_data=(val_images, val_labels))```
