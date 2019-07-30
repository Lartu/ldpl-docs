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
template<typename T>
struct ldpl_map {
    unordered_map<string, T> inner_collection;

    T& operator [] (const string& i) {
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

