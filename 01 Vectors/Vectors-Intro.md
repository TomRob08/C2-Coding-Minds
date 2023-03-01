# Vectors Intro

Vectors are similar to arrays because they both can store a sequence of data but vectors have the advantage due to using dynamically allocated memory for it's elements. What is dynamic memory? Dynamic memory in terms of vectors means it doesn't need a declared size and the size can change by either increasing or decreasing. Although, vectors are not magical and perfect because they also have disadvantages which are increased memory usage and reletivily less efficient in terms of performace compared to arrays.

## Declare an empty vector
```
#include <iostream>
#include <vector>
using namespace std;

int main() 
{
  vector<int> name;

  return 0;
}
```

In the code above we require ```#include <vector>``` and inside of ```main()``` a vector is declared with the data type within the ```<>``` and then the variable name comes after.

## Vector initialization
Vectors have multiple ways of being intitalized containing elements but let's look at the most faliliar and common ways.

### Brackets
```
#include <iostream>
#include <vector>
using namespace std;

int main() 
{
  vector<int> nums = {0,1,2,3,4};

  return 0;
}
```

### Fill
```
#include <iostream>
#include <vector>
using namespace std;

int main() 
{
  vector<int> nums (5, 10);

  return 0;
}
```

In this example the nums vector would be filled with 5 elements that are the value of 10 such as ```{10,10,10,10,10}```

### .assign()
```
#include <iostream>
#include <vector>
using namespace std;

int main() 
{
  vector<int> nums;

  nums.assign (3,100);

  return 0;
}
```

This example is similar to the one above since the vector will be assigned with 3 elements that rae the value of 100 such as ```{100,100,100}```

## Accessing elements
Vectors are indexed just like arrays so we are able to access their values similarly.

### Array style
```
#include <iostream>
#include <vector>
using namespace std;

int main() 
{
  vector<string> str = {"The", "dog", "ran", "very", "fast"};

  cout << str[1] << endl;

  return 0;
}
```

__Output__
```
dog
```

### .at()
```
#include <iostream>
#include <vector>
using namespace std;

int main() 
{
  vector<string> str = {"The", "sun", "is", "very", "bright"};

  cout << str.at(4) << endl;

  return 0;
}
```

__Output__
```
bright
```

### Exercises
__1.__ What values are in this vector and how many elements does it have? ```vector<int> nums(8,5);```

__2.__ Using this vector: ```vector<char> chars = {'a', 'e', 'i', 'o', 'u'}```, what value is at ```chars[2]```? 

__3.__ Write a program to initalize a vector with these values: ```{4,4,4,4,4,4,4}``` 

__4.__ Write a program to initalize a vector with these values: ```{"I", "got", "this"}``` 
