
```dart
void main() {
  test();
}

Future<int> heavyFutureThatMultipliesByTwo(int a) {
  return Future.delayed(const Duration(seconds: 3), () => a * 2);  
}

void test() async{
  final result = await heavyFutureThatMultipliesByTwo(10);
  print(result);
}
```