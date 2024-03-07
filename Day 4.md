# Day 4

## Notes

```dart
context.watch<CounterPorvider>().state.count.toString()
context.read<CounterProvider>().increment()//Providers Function
```


### POJO / POFO / PODO

```dart
/* Plain Old Java Objects (POJO) */
/* Plain Old Flutter Objects (POFO) */
/* Plain Old Dart Objects (PODO) */
```

### Provider:

```dart
/* Provider Design with Consumer. */
/* Provider Design without Consumer. */
```

CounterPorvider providers increment and decrement   
MultiProvider and not Multiprovider     
pub.dev Provider gives access to MultiProvider      


### Consumer:

Consumer<CounterProvider> listens for when notifyListeners(); is called in the CounterProvicer

child in Builder is required.

_ in builder if you know it needs a widget but doesn't want to use one.     
Like Discard in c#

null cant be used as indentifier, because it a keyword

Only updates what is in the build method.   
##### Best Practice:      
Consumer: `put as little data inside build method as possible`

# Navigation in flutter app

## Flutter Navigator

Push and Popv functions.

Flutter PopGet

Screen UI elements on top of eachother like in a stack.     

Pop Then Push, is not best practice.

### MaterialPageRoute Example:
```dart
// Within the `FirstRoute` widget
onPressed: () {
  Navigator.push(
    context,
    MaterialPageRoute(builder: (context) => const SecondRoute()),
  );
},

// Within the SecondRoute widget
onPressed: () {
  Navigator.pop(context);
}
```

### MaterialApp Route Example
```dart
MaterialApp(
  title: 'Named Routes Demo',
  // Start the app with the "/" named route. In this case, the app starts
  // on the FirstScreen widget.
  initialRoute: '/',
  routes: {
    // When navigating to the "/" route, build the FirstScreen widget.
    '/': (context) => const FirstScreen(),
    // When navigating to the "/second" route, build the SecondScreen widget.
    '/second': (context) => const SecondScreen(),
  },
)
```

MaterialApp, if there's no child, Route has to be assigned.         
Route has (Path, Context, Point to Screen to open(widget))

path '/' = const FirstScreen();     
path '/second' = const SecondScreen();


### To Go To SecondScreen:
```dart
// Within the `FirstScreen` widget
onPressed: () {
  // Navigate to the second screen using a named route.
  Navigator.pushNamed(context, '/second');
}
```

### To Go back:
```dart
// Within the SecondScreen widget
onPressed: () {
  // Navigate back to the first screen by popping the current route
  // off the stack.
  Navigator.pop(context);
}
```

## Go_Router

flutter.dev package: go_router 13.2.0
https://pub.dev/packages/go_router

### Go_Router Example:
```dart
import 'package:flutter/material.dart';
import 'package:go_router/go_router.dart';

/// This sample app shows an app with two screens.
///
/// The first route '/' is mapped to [HomeScreen], and the second route
/// '/details' is mapped to [DetailsScreen].
///
/// The buttons use context.go() to navigate to each destination. On mobile
/// devices, each destination is deep-linkable and on the web, can be navigated
/// to using the address bar.
void main() => runApp(const MyApp());

/// The route configuration.
final GoRouter _router = GoRouter(
  routes: <RouteBase>[
    GoRoute(
      path: '/',
      builder: (BuildContext context, GoRouterState state) {
        return const HomeScreen();
      },
      routes: <RouteBase>[
        GoRoute(
          path: 'details',
          builder: (BuildContext context, GoRouterState state) {
            return const DetailsScreen();
          },
        ),
      ],
    ),
  ],
);

/// The main app.
class MyApp extends StatelessWidget {
  /// Constructs a [MyApp]
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp.router(
      routerConfig: _router,
    );
  }
}

/// The home screen
class HomeScreen extends StatelessWidget {
  /// Constructs a [HomeScreen]
  const HomeScreen({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: const Text('Home Screen')),
      body: Center(
        child: ElevatedButton(
          onPressed: () => context.go('/details'),
          child: const Text('Go to the Details screen'),
        ),
      ),
    );
  }
}

/// The details screen
class DetailsScreen extends StatelessWidget {
  /// Constructs a [DetailsScreen]
  const DetailsScreen({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: const Text('Details Screen')),
      body: Center(
        child: ElevatedButton(
          onPressed: () => context.go('/'),
          child: const Text('Go back to the Home screen'),
        ),
      ),
    );
  }
}
```

### Deep links

Link to certain widget on website.

Example:    
Link in a mail to a certain widget in the app or site.

### From pub.dev package example:
```dart
/// The buttons use context.go() to navigate to each destination. On mobile
/// devices, each destination is deep-linkable and on the web, can be navigated
/// to using the address bar.
```


## Bloc (State Management)
### MVVM?

### on event Increment
```dart
On
```


# Flutter

### Future
```dart
Future<void> function(){
  // Async
}
```

### FutureOr
```dart
FutureOr<void> function(CounterEvent even, Emitter<int> emit) async {

}
```

# Assignments

Flutter app navigation

### Later on:
```dart
//Welcome Screen:
    //Burger Menu elements:
        // Stateful (Flutter Startup App Code, Almost)
        // Provider
        // Bloc
        // Future
        // Stream
```

### From Dosc:
```dart
// 1. Create two screens. (widgets)
// 2. Define the routes.
// 3. Navigate to the second screen using Navigator.pushNamed().
// 4. Return to the first screen using Navigator.pop().
```

## Assignment Burger Menu
```dart
// 1. Create Welcome Screen
// 2. Make a burger Menu
// 3. Navlink to a second Screen
```



## Assignment Bloc Counter


# Research

### What is the difference between flutter models and flutter porviders?
### Android Deep Links

