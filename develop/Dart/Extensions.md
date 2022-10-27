Permite añadir funcionalidad adicional a una clase, se utiliza cuando la funcionalidad no es genérica de la clase, si no para un uso puntual

```dart
void main() {
  test();
}

void test() {
  final meow = Cat('Fluffers');
  print(meow.name);
  meow.run();
}

class Cat {
  final String name;
  Cat(this.name);
}  
  
extension Run on Cat {
  void run() {
    print('Cat $name is running');
  }  
}
```

Pueden hacerse extensions para propiedades get y set.