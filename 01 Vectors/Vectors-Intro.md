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

## Declare a vector with elements
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
__1.__ 
