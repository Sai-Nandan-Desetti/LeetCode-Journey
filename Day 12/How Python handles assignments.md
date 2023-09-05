**Assignment**:
    * The assignment operator never creates new *values*, and it never *copies* data. It simply facilitates creating a new reference for the value.
        * "Reference", here, simply means a name used to *refer* to something. Don't start analysing it from a C++ perspective.
        * Maybe a better word is "binding".
    * There's a smart (read crazy) way to create an exception to the above generalization. Read [here](https://gist.github.com/jamalex/5997735).

    * Further Reading:
        * [Facts and myths about Python names and values](https://nedbatchelder.com/text/names.html)

**Shallow vs Deep copy**:
    * Assignment doesn't create even a shallow copy of the value. NO COPIES.
    * To create a copy, shallow or deep, you've to use the `copy` module.
    ```
    The difference between shallow and deep copying is only relevant for compound objects (objects that contain other objects, like lists or class instances):

    A shallow copy constructs a new compound object and then (to the extent possible) inserts references into it to the objects found in the original.

    A deep copy constructs a new compound object and then, recursively, inserts copies into it of the objects found in the original.
    ```
    * Further Reading:
        * Python docs: [copy](https://docs.python.org/3/library/copy.html) module.

![Shallow copy vs Deep copy (Generated using [pythontutor](https://pythontutor.com/render.html#mode=display))]('Shallow copy vs Deep copy.png')
