# Provider App

### Link to my GitHub Repo
Link:   
https://github.com/PandaOnCaffeine/Provider-App/tree/main


## Description
### Make a Flutter Counter app
Make a Flutter Counter app using Providers

We have to make a Counter app where the app look something like the picture below.  
Where we have a increment button and a decrement button.

Where it show the number go up when you click the increment button and down when you click the decrement button.

And a SnackBar/Alert that shows up when the count modulus 3 == 0

Modulus check Example:
```dart
void CheckModulus(){
    if(count % 3 == 0){
        //Show Snackbar
    }
}
```

![Picture](/DeincrementOpg.png)

### App includes:

Increment button.

Decrement button.

Using a Provider class.

A number that goes up and down.

#### Install Provider Package:

[Click Here](https://pub.dev/packages/provider) For link to pub.dev provider package

Type the command below in the terminal of your flutter app to install the provider package.

```cmd
flutter pub add provider
```

Insert the code below into the file where you make your provider class

```dart
import 'package:provider/provider.dart';
```


Example of my provider class: 
```dart
// Note:
// I'm missing a bit of the assignment
// The SnackBar Part
import 'package:flutter/material.dart';
import 'package:flutter/foundation.dart';

class CounterProvider with ChangeNotifier {
  int _count = 0;

  int get count => _count;

  void initCount() {
    _count = 0;
    notifyListeners();
  }

  void increment() {
    _count++;
    notifyListeners();
  }

  void decrement() {
    if (_count >= 0) {
      _count--;
    }
    notifyListeners();
  }
}
```

## Tips:

### Main.dart

In the void main() that is in the main.dart file. you can change it to the example below to use your provider with ChangeNotifer.

And i'll just input a few example of what of the original flutter app thing i have changed

#### void main()
```dart
void main() {
  runApp(
    ChangeNotifierProvider(
      create: (context) => CounterProvider(),
      child: const MyApp(),
    ),
  );
}
```


#### class MyApp extends StatelessWidget
```dart
class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Provider Demo',
      theme: ThemeData(
        colorScheme: ColorScheme.fromSeed(seedColor: Colors.deepPurple),
        useMaterial3: true,
      ),
      home: const MyHomePage(title: 'Increment/Decrement'),
    );
  }
}
```


#### class _MyHomePageState extends State<MyHomePage>
```dart
class _MyHomePageState extends State<MyHomePage> {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        backgroundColor: Theme.of(context).colorScheme.inversePrimary,
        title: Text(widget.title),
      ),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: <Widget>[
            const Text(
              'You have pushed the button this many times:',
            ),
            Consumer<CounterProvider>(
              builder: (context, value, child) {
                return Text('${value.count}');
              },
            ),
            Row(
              mainAxisAlignment: MainAxisAlignment.center,
              children: [
                FloatingActionButton(
                  // onPressed: () => counterProvider.increment(),
                  // onPressed: () => context.read<CounterProvider>().increment(),
                  // onPressed: () => counterProvider.increment(),
                  onPressed: () {
                    var provider = context.read<CounterProvider>();
                    provider.increment();
                  },
                  tooltip: 'Increment',
                  child: const Icon(Icons.add),
                ),
                FloatingActionButton(
                  // onPressed: () => counterProvider.decrement(),
                  // onPressed: () => context.read<CounterProvider>().decrement(),
                  // onPressed: () => counterProvider.decrement(),
                  onPressed: () {
                    var provider = context.read<CounterProvider>();
                    provider.decrement();
                  },
                  tooltip: 'Decrement',
                  child: const Icon(Icons.remove),
                )
              ],
            ),
          ],
        ),
      ),
    );
  }
}
```


#### Hope it helps a bit :)
