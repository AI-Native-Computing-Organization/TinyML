
![Quantization](https://github.com/AI-Native-Computing-Organization/TinyML/blob/testing/src/quantization.png)

When we're talking about reducing the precision, what we mean  is that we're going to take a value that's expressed in float 32-bits, which takes 4 bytes, and compress that value down into an int8.
An int8 is only 1 byte. So immediately, if you do that, you get a 4x reduction. You go from 4 bytes down to 1 byte. That sounds wonderful.

![Quantization](https://github.com/AI-Native-Computing-Organization/TinyML/blob/testing/src/quant.png)

But where do we apply quantization?

We apply them in weights because weights play a major role in terms of storage, for instance, because those are the things that you actually physically store inside your flash memory.
![image](https://github.com/user-attachments/assets/d88aaf2f-bda9-4551-93d7-a0e99fa2af9f)

Now earlier, I showed you this graph on the left, which is showing you the weight distribution, the values for all the weights across all those neurons across the entire network. And what you're seeing is that there's limited range. 
That's a first point.
Second is that you can actually quantixze these values without losing the general representation of that space. So the values in the right graph are quantized values. 
![image](https://github.com/user-attachments/assets/ace162bd-3368-4dc2-957b-7710e633aa0e)
Quantization effectively means, again, binning the floating point ranges
into little buckets.We'll talk about that more. But effectively, if you look at the graph on the left, and you look at the graph on the right, you discretizing the data. But can you still help the same trend?
Yes.
You still have those two big lumps. And you have that tailing effect in the second lump. So how can we go further with this then?
![image](https://github.com/user-attachments/assets/028a56c1-d515-4913-91cd-38ff32309375)
Effectively, what's happening is that when you are taking those original weight values, which are in floating point representation, you are then binning them into an 8-bit encoding scheme.
Remember, because we are using 8-bit integer values, we have 2 to the 8, or 256 potential values, including 0 all the way up to 255. That's 256 values. So we discretize that long floating point range. And we took those values and we bucket them. We hash them into this 8-bit range that we have.

Then when we are ready to do the computation again-- 
![image](https://github.com/user-attachments/assets/e3367793-db21-420f-b7e9-f5f85715408f)

now that the network is actually 8 bits in the middle stage, you save it.
Then when you start running it, what you want to do is you take the 8-bit values and you reconstruct them into a 32-bit floating point value. And you can run it. Surely there are drawbacks!

When you quantize, yes, the network is smaller. Yes, you can run the network faster.
But then you end up losing accuracy. That's the critical trade-off you're going to make. What this graph is showing you is that you're able to take a point on accuracy versus latency and move that point to the left, which means you have
decreased the latency of the network. But then you see that it's also a little lower, which means you have dropped the accuracy.

![image](https://github.com/user-attachments/assets/36e34fa1-173e-4ec7-8ebe-be43c3e34230)

Also, once quantization is applied to other things of a neural network, it might have different drawbacks.
