# Coroutine

```cs
using System.Collections;
using UnityEngine;

public class Foo
{
  public IEnumerator Parent()
  {
    yield return StartCoroutine(Child());
  }

  private IEnumerator Child()
  {
    // ...
  }
}
```

Coroutine are methods that return an `IEnumerator`

- To start a coroutine, use `StartCoroutine(IEnumerator coroutine)`
- `StartCoroutine` returns an object that can be `yield return`, i.e.
  `StartCoroutine` can be used to start a child coroutine
- Objects yielded in coroutines must be subclass of `YieldInstruction`
