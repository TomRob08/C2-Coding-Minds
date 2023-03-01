# Vector Sizes

There are many different functions increase or decrease a vector's size. Here are some useful fuctions included with vectors.

## Get vector size
### .size()
Returns the amount of elements in the vector.
```
#include <iostream>
#include <vector>
using namespace std;

int main() 
{
  vector<int> nums (10, 4);

  cout << nums.size() << endl;

  return 0;
}
```

### Exercise
__1.__ Use ```.size()``` in a for loop to print all of the elements in the vector above.


## Increase size
### .push_back()
Adds a new element at the end of the vector containing a given value.
```
#include <iostream>
#include <vector>
using namespace std;

int main() 
{
  vector<float> nums = {3.14, 5.9, 1.45};

  nums.push_back(7.29);

  for(int i = 0; i < nums.size(); i++)
  {
    cout << nums[i] << " ";
  }
  cout << endl;

  return 0;
}
```

__Output__
```
3.14 5.9 1.45 7.29
```

### .insert()
Adds a new element at a specific place in the vector containing a given value.
```
#include <iostream>
#include <vector>
using namespace std;

int main() 
{
  vector<float> nums = {3.14, 5.9, 1.45};

  nums.insert(nums.begin(), 7.29);

  for(int i = 0; i < nums.size(); i++)
  {
    cout << nums[i] << " ";
  }
  cout << endl;

  return 0;
}
```

__Output__
```
7.29 3.14 5.9 1.45
```

```.begin()``` references the first element in the vector so in this case 7.29 gets inserted at the first element of the vector. Values can also be inserted at different indexes by doing ```.begin() + index```. An example of this would be let's say you want to insert 4.27 into the vector above at index 2 so that means we would do ```nums.insert(nums.begin + 2, 4.27)``` and then the vector would be ```{7.29, 3.14, 4.27, 5.9, 1.45}```.

```.index()``` also has a third optional argument for how many elements should be inserted into the vector and that would look like this: ```vector.insert(num.begin, number_of_elements, element_value)```. 
Here is an example of inserting 3 elements with the values of 9.18 into the nums vector: ```nums.insert(nums.begin, 3, 9.18)```

### Exercises
__1.__ What would be the sequence be if we inserted ```48``` at index 3 into this vector: ```{12,67,30,76,83}```?

__2.__ Write a program to do what was in the previous problem.

__3.__ Using 8 random numbers, ```.push_back()``` each number to a vector.

## Decrease size
### .pop_back()
Similar to ```.push_back()```. Deletes an element at the end of the vector.
```
#include<iostream>
#include<vector>
using namespace std;

int main()
{
  vector<char> chars = {'a', 'b', 'c', 'd', 'e'};

  chars.pop_back();

  for(int i = 0; i < chars.size(); i++)
  {
    cout << chars[i] << " ";
  }
  cout << endl;
  
  return 0;
}
```

__Output__
```
a b c d
```

### .erase()
Similar to ```.insert```. Delete an element at a specific place in the vector.
```
#include<iostream>
#include<vector>
using namespace std;

int main()
{
  vector<char> chars = {'a', 'b', 'c', 'd', 'e'};

  chars.erase(chars.begin()+1);

  for(int i = 0; i < chars.size(); i++)
  {
    cout << chars[i] << " ";
  }
  cout << endl;
  
  return 0;
}
```

__Output__
```
a c d e
```

### .clear()
Removes all elements in a vector
```
#include<iostream>
#include<vector>
using namespace std;

int main()
{
  vector<char> chars = {'a', 'b', 'c', 'd', 'e'};

  chars.clear();

  for(int i = 0; i < chars.size(); i++)
  {
    cout << chars[i] << " ";
  }
  cout << endl;
  
  return 0;
}
```

__Output__
```

```

### Exercises
__1.__ Using the vector: ```{"up", "up", "down", "down", "left", "right", "left", "right", "B", "A", "Start"}``` remove the last element from the vector.

__2.__ Using the vector for the previous exercise, remove the first from the vector.

__3.__ Using the vector for the previous exercise, remove any element if it equals "right".

__4.__ There is a concept called FIFO (First In, First Out) we can apply to vectors where there is a priority to how values are inserted and removed from a vector. The first value in will be the first value out and it will continue to have this behavior for all values in the vector. Let's use FIFO for a vector of people waiting in line for concert tickets. Declare a vector and push the names Jared, Delilah, and Owen. A ticket booth opened so Jared can be removed from the vector. Stacy decided to also join the line so add her to the vector. Two ticket booths opened so remove Delilah and Owen from the vector. Finally, Stacy also can go to an open ticket booth.  

## Changing the size

### .resize()
Resizes the amount of elements in a vector. If the vector is resized to a smaller size, all elements past the new size are removed.
```
#include<iostream>
#include<vector>
using namespace std;

int main()
{
  vector<char> chars = {'a', 'b', 'c', 'd', 'e'};
  cout << "Chars original size: " << chars.size() << endl;

  chars.resize(10);
  cout << "Chars size after resizing to 10: " << chars.size() << endl;

  for(int i = 0; i < chars.size(); i++)
  {
    cout << chars[i] << " ";
  }
  cout << endl;

  chars.resize(3);
  cout << "Chars size after resizing to 3: " << chars.size() << endl;

  for(int i = 0; i < chars.size(); i++)
  {
    cout << chars[i] << " ";
  }
  cout << endl;
  
  return 0;
}
```

__Output__
```
Chars original size: 5
Chars size after resizing to 10: 10
a b c d e      
Chars size after resizing to 3: 3
a b c
```

### Exercises
__1.__ Resize this vector to have 6 elements: {'s', 'y', 's', 't', 'e', 'm', 'a', 't', 'i', 'c'}

__2.__ Create 2 vectors with 10 elements each containing random numbers between 1 and 50 for the values. Print out all the numbers they have in common.

