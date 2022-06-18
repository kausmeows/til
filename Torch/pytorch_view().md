## How To Use The PyTorch View Function

Simply put, the `view` function is used to reshape tensors.
To illustrate, let's create a simple tensor in PyTorch:

To illustrate, let's create a simple tensor in PyTorch:

```python
import torch
# tensor
some_tensor = torch.range(1, 36) # creates a tensor of shape (36,)
```

Since `view` is used to reshape, let's do a simple reshape to get an array of shape (3, 12).

```python
some_tensor_reshaped = some_tensor.view(3, 12) # creates a tensor of shape (3, 12)
```

![tensor shape](https://api.wandb.ai/files/ayush-thakur/images/projects/103390/6c2d7650.png)

Other shapes we can reshape `some_tensor` into are `(12, 3)`, `(6, 6)`, `(2, 18)` etc.

**But notice that you can reshape the given tensor to your desired tensor only because you know about the shape of the tensor to be reshaped.**

What if you don't know the shape of that tensor?

Remember our intro where we talked about negative values? This is where the -1 parameter is magical. 

```python
some_tensor_reshaped_1 = some_tensor.view(3, -1) # creates a tensor of shape (3, 12)
some_tensor_reshaped_2 = some_tensor.view(-1, 12) # creates a tensor of shape (3, 12)
```

The  `-1` parameter **automatically computes one dimension of your output tensor!** This is useful while building a model in PyTorch as you have to specify the input and output shape for each layer, which might be an issue for complex networks. 