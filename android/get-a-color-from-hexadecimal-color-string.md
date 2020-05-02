# Get a Color from hexadecimal Color String
Use Color.parseString
```java
int myColor = Color.parseColor("#3F51B5");
myView.setBackgroundColor(myColor);
```
Note that the String must start with a #. Both RRGGBB and AARRGGBB formats are supported.

## Color from int
```java
int myColor = 0xFF3F51B5;
myView.setBackgroundColor(myColor);
```

## Color from XML
```java
int myColor = ContextCompat.getColor(context, R.color.my_view_background_color);    
myView.setBackgroundColor(myColor);
````

## Android Predefined colors
```java
int myColor = Color.BLUE;
myView.setBackgroundColor(myColor);
```

[source](https://stackoverflow.com/a/42103610)
