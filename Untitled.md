### Scope Resolution Operator (`::`)

The **scope resolution operator** is used in C++ to:

1. **Access class members** defined **outside** the class.
2. **Differentiate** between local and global variables when they have the same name.
3. Access **static members** of a class.
4. Use functions or variables from **namespaces**.

Let’s go over each of these concepts:

### 1. **Class Functions Defined Outside the Class**

While you can define class member functions inside the class definition, it is often good practice to define them outside the class using the scope resolution operator (`::`).

Here’s an example:
``` 
class MyClass {
public:
    void display();
};

// Define the function outside the class using `::`
void MyClass::display() {
    cout << "This is a function defined outside the class!" << endl;
}

```
In this case, `MyClass::display` means that the `display` function belongs to the `MyClass` class.

### 2. **Accessing a Global Variable with the Same Name as a Local Variable**

Sometimes, you may have a **global** variable and a **local** variable with the same name. To access the global variable inside a function, you use the scope resolution operator.

Example
```
int x = 10;  // Global variable

void func() {
    int x = 20;  // Local variable
    cout << "Local x: " << x << endl;
    cout << "Global x: " << ::x << endl;  // Access the global variable
}

```
In this case:

- `x` refers to the local variable.
- `::x` refers to the global variable.

### 3. **Accessing Static Members**

**Static members** belong to the class itself, rather than any specific instance (object) of the class. You can access them using the scope resolution operator.

Example:
```
class MyClass {
public:
    static int count;

    void increment() {
        count++;
    }
};

// Define the static member outside the class
int MyClass::count = 0;  // Initialize the static variable

int main() {
    MyClass obj1, obj2;
    
    obj1.increment();
    obj2.increment();

    // Access the static member using the scope resolution operator
    cout << "Count: " << MyClass::count << endl;
    return 0;
}

```
