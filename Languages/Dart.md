# Main Function

```Dart
    void main(){
        var name = "prince";
    // final is used when we dont know the value like user input or api responce
        final age = 25;
    // const is compile time variable 
        const isOpen = true;
        print("My name is " + name);
        print("You can also do this $name");
    // and if it is a property of a object then  
        print("This is the property ${person.name}")
    }
```

# Data Types 

```Dart
        String name = "prince"; 
        int age = 17;
        bool isOpen = true;
        double averageRating = 6.9;
        // If you want the variable to be empty (null) you can't do it caus dart have null saftey so you have to do this 
        String? lastName;
```

# Function 

```Dart 
    void main(){
        final greeting = greet("Prince", 17);
        print(greeting)
    }

    greet(name, age){
        return "Hi, my name is $name and I am $age";
    }
```

- ##  With types
```Dart 
    String greet(String name, int age){
        return "Hi, my name is $name and I am $age";
    }
```

- ## Positional Arrguments 
```Dart
    void main(){
        final greeting = greet(name: "Prince", age: 17);
        print(greeting);
    }

    String greet({String? name, required int age}){
        return "Hi, my name is $name and I am $age";
    }
    // String? tells that name is not neccery arrgument 
    // required tells that age is necessary

```

# Lists  

```Dart 
    void main(){
        // Dynamic datatype list 
        var scores =[50, 43, 345, 35];

        List<int> rollno = [23, 2345, 234, 32, 2345];
        print(rollno[2]);
        rollno.add(100);
        rollno.remove(2345); // only removes the first instence
        rollno.removeLast(2345);
        rollno.shuffle();
        print(rollno.indexOf(32)); 
        print(rollno.lenght);
    }
```

# Sets 

```Dart

    void main(){
        // Dynamic datatype list 
        var names = {"mario", "luigi", "peach", "luigi"};

        Set<String> name = {"mario", "luigi", "peach", "luigi"}; 
    }

```

# For Loop

```Dart
    for(int i = 0; i < 5; i++){
        print("The current value of i is $i")
    }
```
- ## For in Loop
  
```Dart
    List<int> rollno = [23, 2345, 234, 32, 2345];
    for(int no in rollno){
        print("The roll no is $no")
    }
```

- ## Where method 
```Dart
    List<int> rollno = [23, 2345, 234, 32, 2345];
    for(int no in rollno.where((e)=> e > 32)){
        print("The roll no is $no")
    }
```

# Map

```Dart 
    void main(){
        var planets = {"first": "mercury","second": "venus"};

        Map<int, String> planets = {
            1:"mercury",
            2:"venus",
            3:"earth",
        };

        print(planets[3]);
// Add element
        planets[6]= "uranus";

        planets.containsKey(6);
        planets.containsValues("Earth");
        planets.remove(3);
    }
```

# Classes 

```Dart 
    void main(){
        var noodles = MenuItem('veg noodles', 9.99);
        var pizza = MenuItem('volcano pizzaw', 15.69);
    }

    class MenuItem {
        String type = 'food';
        String title;
        double price;

        // Class counstructor 
        MenuItem(this.title, this.price);

        String format(){
            return "The $title is Rs  $price"
        }
    }
```

- ## Inheritence
```Dart 
    class Pizza exetends MenuItem{
        List<String> toppings;
        Pizza(this.toppings)
    }

```
