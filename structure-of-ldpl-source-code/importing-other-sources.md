# Importing other sources

You can import other LDPL source codes to your LDPL source by using the `INCLUDE` statement. For example, say you have two sources:

{% code-tabs %}
{% code-tabs-item title="firstSource.ldpl" %}
```coffeescript
procedure:
  call someSubprocedure
```
{% endcode-tabs-item %}
{% endcode-tabs %}

and

{% code-tabs %}
{% code-tabs-item title="included.ldpl" %}
```coffeescript
procedure:
  sub someSubprocedure
    display "Hi there!"
  end sub
```
{% endcode-tabs-item %}
{% endcode-tabs %}

You can import the second source into the first one in order to create one big source file like this:

{% code-tabs %}
{% code-tabs-item title="firstSource.ldpl" %}
```coffeescript
include "included.ldpl"
procedure:
  call someSubprocedure
```
{% endcode-tabs-item %}
{% endcode-tabs %}

The location where the included files are searched is relative to the file that includes them.

