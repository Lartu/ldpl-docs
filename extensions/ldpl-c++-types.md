# LDPL C++ Types

{% code-tabs %}
{% code-tabs-item title="TEXT" %}
```cpp
//TEXT is just std::string
```
{% endcode-tabs-item %}
{% endcode-tabs %}

{% code-tabs %}
{% code-tabs-item title="NUMBER" %}
```cpp
#define ldpl_number double
```
{% endcode-tabs-item %}
{% endcode-tabs %}

{% code-tabs %}
{% code-tabs-item title="MAP" %}
```cpp
#include <unordered_map>
#include <string>
#include <sstream>
#include <iostream>
#define ldpl_number double

std::string to_ldpl_string(double x);

template<typename T>
struct ldpl_map {
    std::unordered_map<std::string, T> inner_collection;

    T& operator [] (const std::string& i) {
        return inner_collection[i];
    }

    T& operator [] (ldpl_number i) {
        return inner_collection[to_ldpl_string(i)];
    }
};
```
{% endcode-tabs-item %}
{% endcode-tabs %}

{% code-tabs %}
{% code-tabs-item title="LIST" %}
```cpp
template<typename T>
struct ldpl_list {
    vector<T> inner_collection;

    T& operator [] (ldpl_number i) {
        i = floor(i);
        if (i < 0 || i >= inner_collection.size()) {
            cerr << \"Runtime Error: LIST index \" << i << \" out of range [0, \"
                 << inner_collection.size() << \")\" << endl;
            exit(1);
        }
        return inner_collection[i];
    }
};
```
{% endcode-tabs-item %}
{% endcode-tabs %}

