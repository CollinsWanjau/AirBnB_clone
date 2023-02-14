# 0x00. AirBnB clone - The console

* Description of the project

# [explanation](file_storage.py)

* This a python class called `File storage` that represents an abstracted
storage engine, it has the following attributes:

* `__file_path`: A private class variable that represents the name of the
file to save objects to.The default value is "file.json".

* `__objects`: A private class variable that represents a dictionary of
instantiated objects.The default value is as empty dictionary

* It has the following methods:

1. `all()`: A method that returns the `__objects` dictionary.

2. `new(obj)`

-> A method that sets the object `obj` in the `__objects` dictionary with
a key of `<obj_class_name>.id`, where `obj_class_name` of the object's
class and `id` is the object's id attribute.

```
def new(self, obj):
        """Set in __objects obj with key <obj_class_name>.id"""
        ocname = obj.__class__.__name__
        FileStorage.__objects["{}.{}".format(ocname, obj.id)] = obj
```

* To do this, the method first gets the class name of the object using
the `__class.name` attribute.It then constructs a key for the `objects`
dictionary by concatenating the class name, a period, and the object's
id attribute.

* Finally it sets the object in the `__objects` dictionary using the
constructed key.

* This method is used to add objects to the `__objects` dictionary of the
`FileStorage` class, which is later used to serialize the object to a file
using

* `ocname = obj.__class__.__name__`
-> Retrieves the name of the class of the object `obj`.It does this by
using the `__class__` attr of the `obj` to get the class, and then
calling the `__name__` attr of that class to get the name of the class as
a string.

* `FileStorage.__objects["{}.{}".format(ocname, obj.id)] = obj`
-> Adds the object `obj` to the `__objects` dictionary of the `FileStorage`
class using the key constructed from the `ocname` and `obj.id`

-> The `__objects` dictionary is used to keep track of all objects that
have been instantiated and allows the `FileStorage` class to save and
load these objects to and from a file.

3. `save()`

-> a method that serializes the `__objects` dictionary to the JSON file
specified in `__file_path`.

* Description of the command interpreter
1. How to start it
2. How to use it
