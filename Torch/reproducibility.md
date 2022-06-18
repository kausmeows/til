## Reproducibility

> ML experiments may be very hard to reproduce. You have a lot of hyperparameters, different dataset splits, different ways to preprocess your data, bugs, etc. Ideally, you should log data split (already preprocessed), all hyperparameters (including learning rate scheduling), the initial state of your model and optimizer, random seeds used for initialization, dataset shuffling and all of your code. 

> Your GPU also should be in deterministic mode (which is not the default mode). For every single model run. This is a very hard task. Different random seed can significantly change your metrics and even GPU-induced randomness can be important. We're not solving all of these problems, but we need to address at least what we can handle.

> However, there are some steps you can take to limit the number of sources of nondeterministic behavior for a specific platform, device, and PyTorch release. First, you can control sources of randomness that can cause multiple executions of your application to behave differently. Second, you can configure PyTorch to avoid using nondeterministic algorithms for some operations, so that multiple calls to those operations, given the same inputs, will produce the same result.

## Controlling sources of randomness

### PyTorch random number generator

You can use [torch.manual_seed()](https://pytorch.org/docs/stable/generated/torch.manual_seed.html#torch.manual_seed) to seed the RNG for all devices (both CPU and CUDA):

```python
import torch
torch.manual_seed(0)
```
### Random number generators in other libraries

If you or any of the libraries you are using rely on NumPy, you can seed the global NumPy RNG with:

```python
import numpy as np
np.random.seed(0)
```


