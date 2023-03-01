# Vector Sizes

There are many different functions increase or decrease a vector's size. Here are some useful fuctions included with vectors.

## Get vector size
### .size()

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

## Decrease size
### .pop_back()

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

## Changing the size

### .resize()
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

