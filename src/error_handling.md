# Error Handling

Most errors are considered `PyResult`s, this is re-exported as `rustpython_vm::PyResult`.

The error in a `PyResult` is a `PyBaseExceptionRef`, which is a reference to a base error (documented as `PyBaseException`).

It contains methods that return more information.
