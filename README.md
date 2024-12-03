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
