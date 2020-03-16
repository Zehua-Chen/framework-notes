# Properties

- Interpolate:
  - `Interpolate`: creates smooth movement, but lags a bit
  - `Extrapolate`: used for faster movements, but not as smooth

# Movement and Rotation

When a rigidbody is used and `interpolate` enabeld, calling
`void MovePosition(this, Vector3)` of rigidbodies in `void FixedUpdate(this)`
methods would yield smoother movements, compared to using
`Transform.Translate(this)`

```cs
void FixedUpdate()
{
  _rigidbody.MovePosition(transform.position + delta * Time.fixedDeltaTime);
}
```

The same also applies to rotation
