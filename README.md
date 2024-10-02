
# Flutter Responsive Screen

A comprehensive and flexible solution for building responsive layouts in Flutter applications, handling various screen sizes with ease. This package allows you to create dynamic UIs that adapt to mobile, tablet, and desktop breakpoints.

## Table of Contents

- Features
- Installation
- Usage
- Example
- Methods
- License
- Contributing
- Acknowledgments

## Features

- **Breakpoint Handling**: Adapts layouts between mobile, tablet, and desktop breakpoints.
- **Dynamic Padding**: Easily apply padding based on the current screen size.
- **Responsive Font Size**: Automatically adjusts font size to match the device dimensions.
- **Grid Layout Management**: Customize the number of grid columns based on screen size.
- **Percentage Sizing**: Adjust widget width and height as a percentage of the screen size.

## Installation

Add the following dependency to your `pubspec.yaml` file:

```yaml
  dependencies:
  flutter:
    sdk: flutter
```

## Usage

1. Import the `Responsive` Class:

```dart
import 'path/to/your/responsive.dart';
```

2. Initialize Responsive for Your Widgets:

```dart
final responsive = Responsive(context);
```

3. Example Usage in Widgets:

 ```dart
 @override
Widget build(BuildContext context) {
  final responsive = Responsive(context);

  return Scaffold(
    appBar: AppBar(
      title: Text(
        'Responsive Layout',
        style: TextStyle(fontSize: responsive.responsiveFontSize()),
      ),
    ),
    body: Padding(
      padding: responsive.responsivePadding(),
      child: GridView.builder(
        gridDelegate: SliverGridDelegateWithFixedCrossAxisCount(
          crossAxisCount: responsive.responsiveGridColumns(),
        ),
        itemBuilder: (context, index) => Card(
          child: Center(child: Text('Item $index')),
        ),
      ),
    ),
  );
}
```

## Example

A quick example of how the `Responsive` class works for adaptive layouts:

```dart
class MyResponsiveWidget extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    final responsive = Responsive(context);

    return Scaffold(
      body: Column(
        children: [
          Container(
            width: responsive.responsiveWidth(0.8),  // 80% of screen width
            height: responsive.responsiveHeight(0.5),  // 50% of screen height
            child: Text(
              'Responsive Container',
              style: TextStyle(fontSize: responsive.responsiveFontSize()),
            ),
          ),
          Padding(
            padding: responsive.responsivePadding(),
            child: Text('Responsive Padding'),
          ),
        ],
      ),
    );
  }
}

```

## Methods

- `responsiveFontSize([double factor])`: Dynamically adjusts the font size based on the screen size.
- `responsivePadding([double factor])`: Provides padding that adapts to screen size (mobile, tablet, desktop).
- `responsiveWidth(double percentage)`: Sets the widget's width as a percentage of the screen width.
- `responsiveHeight(double percentage)`: Sets the widget's height as a percentage of the screen height.
- `responsiveGridColumns()`: Determines the number of grid columns based on the current screen size.

## Used By

This project is proudly being used by:

- [Hisaab Rakho](https://github.com/AmmarSAA/Hisaab-Rakho-2.0) - A Simple solution for your finances.

## License

This project is licensed under the [MIT](LICENSE) License.

## Contributing

Contributions are always welcome!
If you have ideas or improvements, feel free to open an issue or submit a pull request.
