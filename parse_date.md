Короткий способ.

```c++
#include <iostream>
#include <string>
#include <iterator>
#include <vector>
#include <sstream>

using namespace std;

int main()
{
    string test = "frst second   pepep";
    istringstream words_input(test);
    vector<string> vec_word{istream_iterator<string>(words_input), istream_iterator<string>()};
	cout << (vec_word.size() == 3 ? "good" : "fail");
return 0;
}
```

