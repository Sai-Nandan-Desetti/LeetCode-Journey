**`is` vs `==`**:

* `a is b` compares the *identities* of the objects, `a` and `b`.
    * It returns `True` if and only if the two objects have the same identity.
    * You can get the identity of an object by using [`id()`](https://docs.python.org/3/library/functions.html#id).
        * CPython implementation treats the address of the object as its identity.
    * `is` cannot be overloaded.

* `a == b` compares the *values* of the two objects.
    * It returns `True` if and only if the two objects have the same value.
    * What do you mean by the *value* of a object?
        * This is largely implementation-specific.
        * For some types, like `int`, `strings`, `lists`, it's straightforward.
        * For some others, like a custom `class`, it isn't well-defined.
            * You need to specify what exactly needs to be compared when you execute `a == b`.
            * Each object comes with a built-in method where you can define that.
    * `__eq__()`:
        * When you execute `a == b`, actually `a.__eq__(b)` is called.
        * Now, it so happens that the default behaviour of `__eq__()` is (see [here](https://stackoverflow.com/a/57900009))...
        ```
        def __eq__(self, other):
            return self is other
        ```
        ...to compare the identities!
        * But this can be overloaded, and it's good practice to do so in order to meet the needs of your specific context.
        

* `is None`:
    * Typically, to check if an object is None or not, we check `if obj` or `while obj`.
    * But the recommended way to check is `if obj is not None`.
    * Suppose, `obj` is a boolean object/variable. Then `obj` is not `None` but `if obj` evaluates to `False`!

* Generally, when you want to compare `nodes` in a linked list or a tree, for example, you want to compare their *identities*. So, use `is`. And, if you want to check if a `node` is `None`, use the `is (not) None` clause.

**Further Reading**:
* [The `is` operator behaves unexpectedly with non-cached integers](https://stackoverflow.com/questions/34147515/the-is-operator-behaves-unexpectedly-with-non-cached-integers/34147516#34147516)
* ['is' operator behaves unexpectedly with floats](https://stackoverflow.com/questions/38834770/is-operator-behaves-unexpectedly-with-floats/38835030#38835030)
