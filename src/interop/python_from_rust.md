# Calling Python from Rust

## Running code

The simplest way to do this is `VirtualMachine::run_code_string`.
This requires a scope, which can be created with `VirtualMachine::new_scope_with_builtins`
```rust
let scope = vm.new_scope_with_builtins();
vm.run_code_string(scope, "print('hello')", "<embedded>").unwrap();
```

If your code is from a path, consider using `VirtualMachine::run_script`

```rust
let scope = vm.new_scope_with_builtins();
vm.run_code_string(scope, "hello.py").unwrap();
```

### Compilation
```rust
vm.compile("print('hello')", vm::compiler::Mode::Exec, "<embedded>".to_owned())
```
once compiled, the code can be called any number of times with
```rust
let scope = vm.new_scope_with_builtins();
vm.run_code_obj(code_obj, scope)?;
```

## Calling specific code
TODO.
