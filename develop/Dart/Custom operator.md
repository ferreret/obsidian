```dart
class Cat extends Object {
  final String name;
  
  Cat(this.name);
  
  @override
  bool operator ==(covariant Cat other) => other.name == name;
  
  @override
  int get hashCode => name.hashCode;
}
```