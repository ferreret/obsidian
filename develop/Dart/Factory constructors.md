```dart
void main() {
  
  test();
 
}

void test() {
  final person = Person('Foo Bar');
  person.run();
  person.breath();
  
  final fluffBall = Cat('Fluff ball');
  print(fluffBall.name);
}

class Person {
  
  final String name;
  
  Person(this.name);
  
  
  void run() {
    print('Running');
  }
  
  void breath() {
    print('Breathing');
  }
  
}

class Bomber extends Person
{
  Bomber(String name) : super(name);
  
}

class Cat {
  final String name;
  
  Cat(this.name);
  
  factory Cat.fluffBall() {
    return Cat('Fluff Ball');
  }
   
}
```