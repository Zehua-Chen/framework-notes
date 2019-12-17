# Tensors

Tensors are the equivalent of `numpy`'s `ndarray`, and they can be computed on
GPU

## Factory Functions

`torch.empty(sizes..., dtype)`

Create a **uninitialized** tensor with `sizes` as shape

- `dtype`: type of data in the tensor

Note that because the tensor is **unitialized**, it is very likely it will
contain garbage values

`torch.zeros(sizes..., dtype)`

Create a tensor filled with zeros

- Same parameters as `torch.empty(sizes..., dtype)`

`torch.rand(sizes..., dtype)`

Create a tensor filled with random values

- Same parameters as `torch.empty(sizes..., dtype)`

## Shape

### View and Reshape

`torch.Tensor.view(self, sizes...)` provides a view into a tensor with its shape
changed to what's defined by `sizes...`

- The returned tensor shares the same data with the old tensor

`torch.Tensor.reshape(self, sizes...)` creates a copy of `self` with its shape
changed

- The returned tensor owns different data with the old tensor

# Operations

Operations on pytorch tensors can be written in the same was as regular python
object operations, but with the operation spread to all of the torch's elements

```py
import torch

x = ...  # type: torch.Tensor
y = ...  # type: torch.Tensor

z = x * y
```

## Note on Assignment Operation

```py
import torch

x = torch.zeros(7, 7)
x = 100.0
```

**Here `x` would just be a float**, rather than `torch.Tensor` object.

To fill a tensor with a scalar value, use `torch.Tensor.fill_(self, value)`
method instead
