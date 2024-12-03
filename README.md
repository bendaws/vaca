# Stal
Stal is an interpreted language The name comes from a mix of **Sta**ck and **L**ua.

## Code Sample
```lua
type Person:
  name: str
  age: num
  height: num

  func say(text: str):
    print(me.name + " says: " + text)
  ;

func newPerson(nname: str, nage: num, nheight: num):
  newPerson: Person = nname, nage, nheight
  return newPerson
;

me: Person = newPerson("Ben", 14, 165)
me.say("I like pizza")
print(str.convert(me.age))
```

## Standard Library
The standard library is imported by default and contains a pretty good amount of libraries to use. Most are direct translations from Lua but some are custom-written.

### Libraries
> Any ``?`` represents an optional argument that is optional.
> Any other variable not containing ``?`` before it is required.

#### str
| Function           | Arguments  | Description                                                                                              | Returns          |
|--------------------|------------|----------------------------------------------------------------------------------------------------------|------------------|
| ``str.convert()``  | ``(any)``  | Converts another variable to a string. Accepts numbers and booleans. Returns ``null`` if not convertable | ``str``/``null`` |
| ``str.replace()``  | ``(string, occur, replace)``  | Replaces all instances of substring ``occur`` with ``replace``. | ``str`` |
| ``str.upper()``  | ``(string)``  | Makes all characters in the string uppercase. | ``str`` |
| ``str.lower()``  | ``(string)``  | Makes all characters in the string lowercase. | ``str`` |
| ``str.match()``  | ``(string, occur)``  | Returns true if substring ``occur`` is found inside of the string, returns false if otherwise. | ``true``/``false`` |

#### math
| Function           | Arguments  | Description                                                                                              | Returns          |
|--------------------|------------|----------------------------------------------------------------------------------------------------------|------------------|
| ``math.big()``  | ``none``  | Returns a very big number. | ``num`` |
| ``math.small()``  | ``none``  | Returns a very little number. | ``num`` |
| ``math.pi()``  | ``(?rto)``  | Returns the estimated value of pi. ``rto`` is the decimal place to round to which is any number under 1000. | ``num`` |
| ``math.round()``  | ``(number, ?decimal)``  | Returns the rounded value of ``number``. ``decimal`` signifies the decimal place to round to if not a whole number. | ``num`` |
| ``math.slope()``  | ``(point1X, point1Y, point2X, point2Y)``  | Returns the slope of the linear equation that connects through (``point1X``, ``point1Y``) and (``point2X``, ``point2Y``). | ``num`` |
| ``math.sslope()``  | ``(point1X, point1Y, point2X, point2Y)``  | Returns the y-intercept format of the linear equation that connects through (``point1X``, ``point1Y``) and (``point2X``, ``point2Y``). Example: ``y=1x+0`` | ``str`` |
| ``math.even()``  | ``(number)``  | Returns ``true`` if the given number is even. | ``true``/``false`` |

#### io
| Function           | Arguments  | Description                                                                                              | Returns          |
|--------------------|------------|----------------------------------------------------------------------------------------------------------|------------------|
| ``io.write()``  | ``(string)``  | Prints the given string with no newline character. | ``null`` |
| ``io.clear()``  | ``(none)``  | Clears the terminal the script is currently executing from. | ``null`` |

#### Included standard library
| Function           | Arguments  | Description                                                                                              | Returns          |
|--------------------|------------|----------------------------------------------------------------------------------------------------------|------------------|
| ``print()``  | ``(string)``  | Prints the given string including ``\n``. | ``null`` |
| ``read()``  | ``(none)``  | Reads a string from the terminal. | ``str`` |
| ``type()``  | ``(any)``  | Returns the given type of ``any`` in string format. | ``str`` |
| ``import()``  | ``(string)``  | Require a module from file ``string``. | ``module``/``error`` |
| ``warn()``  | ``(string)``  | Prints the given string including ``\n`` in orange color. | ``null`` |
| ``error()``  | ``(string)``  | Prints the given string including ``\n`` in red color and closes the program with exit code ``1``. | ``null`` |
