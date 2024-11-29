
# Static 
1) A variable 
	
 ```cpp
 include <iostream>
		using namespace std;
		int main() {
			int a // statically declearing a variable 
		}
```
2)  A object

```cpp
#include <iostream>
class myclass{};

int main() {
myclass obj; // Staticakly creates a  object for class
}
```

 3) Arrays
```cpp
int arr[5] = {1, 2, 3, 4, 5};  // Static array
```

### Dynamic Initialization:

Dynamic variables are allocated on the heap at runtime, typically using pointers.

- **For primitive types:**
    
	
```cpp
    
    Copy code
    
    `int* p = new int(5);  // Dynamic allocation delete p;  // Don't forget to free the memory`
    ```
    
  
- **For arrays:**
    ```cpp
    int* arr = new int[5];  // Dynamic array allocation 
    // Initialize the array    
   for(int i = 0; i < 5; i++) {     arr[i] = i + 1; } delete[] arr;  // Free Memory
```

- **For objects:**
    ```cpp
    MyClass* obj = new MyClass(10);  // Dynamically allocated object delete obj;  
```


### 1. **Dynamically Created Object:**

When you create an object dynamically, you're allocating memory on the **heap** for the object itself, and you use a pointer to reference that memory. The pointer points to the memory address where the object resides.

```cpp
MyClass* objPtr = new MyClass(10);  // Dynamically create an object

```


## Difference Between Dynamic and Static Memory Allocation

| **Aspect**                 | **Static Memory Allocation**                          | **Dynamic Memory Allocation**                          |
|----------------------------|-------------------------------------------------------|--------------------------------------------------------|
| **Memory Location**         | Memory is allocated from the **stack**.               | Memory is allocated from the **heap**.                 |
| **Allocation Time**         | Occurs at **compile-time** (when the program is compiled). | Occurs at **run-time** (when the program is running).  |
| **Size Determination**      | The size must be known at compile-time (fixed size).  | The size can be determined at run-time (flexible size). |
| **Lifetime**                | Variables are automatically destroyed when they go out of scope. | Memory persists until it is manually deallocated with `delete` (C++) or `free()` (C). |
| **Efficiency**              | Faster allocation and deallocation due to stack nature. | Slower allocation and deallocation due to heap management. |
| **Control**                 | No explicit control over memory allocation and deallocation. | Programmer has explicit control over allocation and deallocation. |
| **Syntax**                  | Uses regular variable declaration, e.g., `int x;`.    | Uses `new` and `delete` in C++, e.g., `int* p = new int;`. |
| **Memory Limit**            | Limited by the size of the stack (usually smaller).   | Can allocate large amounts of memory (limited by system memory). |
| **Example**                 | ```cpp int arr[10]; ```                              | ```cpp int* arr = new int[10]; ```                     |
| **Risk of Memory Leaks**    | No risk of memory leaks.                             | Risk of memory leaks if `delete` is not called after use. |

---

