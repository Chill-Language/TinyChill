# TinyChill
The TinyChill Programming Language

TinyChill is a Tiny of Chill Programming Language.

The TinyChill Interpreter is build on [CVM](https://github.com/CVM-Projects/CVM).

## Usage

*This project is building.*

## Documentation

[Documentation](documentation\README.md)

## Feature

- Conveniently Embedded in C/C++
- Binding with types, variables, functions..
- Lightweight and Quick-Startup
- Easy Customization

## Example

```c++
void print_value(int value) {
	std::printf("%d\n", value);
}
void print_string(const char *value) {
	std::printf("%s\n", value);
}

void init_vm(TinyChill::VM &vm) {
	vm.bind_type<int>(TinyChill::T_Integer);
	vm.bind_type<const char*>(TinyChill::T_String);
	vm.insert_bind_func("print", print_value);
	vm.insert_bind_func("print", print_string);
}
void do_shell(TinyChill::VM &vm, const std::string &script) {
	const char *word = "Hello World!";
	vm.bind_variable("word", &word);
	vm.run_script(script);

	std::printf("%s\n", word);  // Hi TinyChill!
}
```

```
(print 5)     ; 5
(print word)  ; Hello World!
(set word "Hi TinyChill!") ; Modify the value of variable 'word'.
(print word)  ; Hi TinyChill!
```
