
### Ejemplo raro

Lista que puede ser null, con valores String que pueden ser null

```dart
List<String?>? names = ['Foo', 'Bar', null];
```

### ?? Operator

```dart
  const String? firstName = null;
  const String? middleName = null;
  const String? lastName = null;
  
  // Código ....
  
  const firstNonNullable = firstName ?? middleName ?? lastName;
```

### ??= Operator

Asigna a la izquierda el valor de la derecha si el de la izquierda no es null y el de la derecha tampoco

```dart
  String? firstName;
  String? name;
  
  // Código
  
  name ??= firstName;
```

