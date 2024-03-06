# Day 3

## Notes

### Files

#### General files

GeneratedPluginRegistrant file in each folder

README.md

pubspec.yaml

Showcase of folder and files in the android folder in a flutter app

#### Android

android/app/src/build.gradle

android/app/src/gradle

#### IOS

GeneratedPluginRegistrant.h (c++)

GeneratedPluginRegistrant.m

info.plist (perms)

#### Linux

GeneratedPluginRegistrant.h

GeneratedPluginRegistrant.cc

#### Macos


#### Windows

CMakeLists.txt (c++)

### Test

Flutter test (in terminal)

github actions

integration test (auto test)

unit test, widget test, integration test

### Widget

Like angular components??

Alot of child widgets

Widget is weird.

Widget idea was taken from React

https://docs.flutter.dev/ui

All ui in flutter is build with widgets

Some widgets can hold one widget, Others widgets can hold more widgets

### Widget Tree



### Flutter info
Flutter Block Model.


#### Flutter Docs
https://docs.flutter.dev

Docs have alot of code examples. 

```dart
import 'package:flutter/material.dart';

void main() {
  runApp(
    const Center(
      child: Text(
        'Hello, world!',
        textDirection: TextDirection.ltr,
      ),
    ),
  );
}
```

Total widgets in code above = 3 | widgets = Center, Text and TextDirection.

#### Scaffold and Widgets
All apps start with scaffold

Drawers, snack bars, bottom sheets, app bars and so on.

https://api.flutter.dev/flutter/material/Scaffold-class.html

```dart
import 'package:flutter/material.dart';

/// Flutter code sample for [Scaffold].

void main() => runApp(const ScaffoldExampleApp());

class ScaffoldExampleApp extends StatelessWidget {
  const ScaffoldExampleApp({super.key});

  @override
  Widget build(BuildContext context) {
    return const MaterialApp(
      home: ScaffoldExample(),
    );
  }
}

class ScaffoldExample extends StatefulWidget {
  const ScaffoldExample({super.key});

  @override
  State<ScaffoldExample> createState() => _ScaffoldExampleState();
}

class _ScaffoldExampleState extends State<ScaffoldExample> {
  int _count = 0;

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text('Sample Code'),
      ),
      body: Center(child: Text('You have pressed the button $_count times.')),
      floatingActionButton: FloatingActionButton(
        onPressed: () => setState(() => _count++),
        tooltip: 'Increment Counter',
        child: const Icon(Icons.add),
      ),
    );
  }
}
```

Scaffold example (widget)

StatelessWidget. Doesn't know anything.

Is always emutable, cuz cant hold State.

emutable(cant change when created) (gets put down and started up again)

Cant contain values.


```dart
class ScaffoldExampleApp extends StatelessWidget {
  const ScaffoldExampleApp({super.key});

  @override
  Widget build(BuildContext context) {
    return const MaterialApp(
      home: ScaffoldExample(),
    );
  }
}
```
Return value
```dart
return const MaterialApp()
```


StateFull Widget can hold state( exprects a widget it can start up)

StateFull Has to Select widget.


ScaffoldEcample extents StatefulWidget that can hold a State,
```dart
Class ScaffoldExample extends StatefulWidget
```

Has CreateState() => _ScaffoldExampleState();
```dart
State<ScaffoldExample> createState() => _ScaffoldExampleState();
```

```dart
class _ScaffoldExampleState extends State<ScaffoldExample> 
```

#### Stateful and Stateless Widgets

Has to override build function
```dart
class ScaffoldExampleApp extends StatelessWidget {
  const ScaffoldExampleApp({super.key});

  @override
  Widget build(BuildContext context) {
    return const MaterialApp(
      home: ScaffoldExample(),
    );
  }
}
```

```dart
@override
  Widget build(BuildContext context) {
    return const MaterialApp(
      home: ScaffoldExample(),
    );
  }
```


#### Stateful widget

Has ascces to some fuctions beacause they're stateful

OnPressed: () => SetState: () => _count++

Redraws widget after above is run.

Breaks SOLID. ( Single Responsible)



### Pub.dev

Website where you can get packages for flutter/dart apps.

Not all publishers are verified



## Structur

Lib
  
components

Handlers

models

providers

screens

widgets

main.dart

```md
├── lib
│   ├── components
│   │   ├── 
│   ├── handlers
│   │   ├── 
│   ├── models
│   │   ├── 
│   ├── providers
│   │   ├── 
│   ├── screens
│   │   ├── 
│   ├── widgets
│   │   ├── 
│   └── main.dart
└── 
```


## Opgaver

### Deincrement

Make a deincrement button in our flutter app (when a new app is made, a app with a counter is used as a template)

Button on other side

can only deincrement to 0 and not to negative numbers

Shows a snackbar every modulus 3 == 0 (var % 3 == 0)


### Provider?

initialCounterValue
increment
Increment and Decrement with provider

same layout

provider Extends from ChangeNotifer

buttonType: OwnButtonType.Increment and other

Consumer<CounterProvider>(builder: (context, countProvider))

enum OwnButtonType{
increment, decrement
}

class OwnButton Extends StatelessWidget {
  const ownButton

  @ovveride
  WidgetBuild
}


switch (buttonType) {
  ownButtonType.increment = provider.increment();
  ownButtonType.decrement = provider.decrement();
}

`Provider:` https://pub.dev/packages/provider




## Later in the week


### State Management?



## Remember

Context.read<Provider>

Future<void> name() aysnc {}

notifyListeners();

Return Scaffold(
  appBar:
  body: child: column(children:[])
)

Consumer (decrease) / Producer (add)

_ = ignore child

provider.counter!.counter.toString(),


CirculerProgressIndicator