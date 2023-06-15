# OOP-in-Python
Self learning for OOP in Python

## Concepts
1. Isolated functions creataed with "def" are called functions, but when put inside a class shoule be called "methods".
2. Class Attribute vs. Instance Attribute
Class attributes are the variables defined directly in the class that are shared by all objects of the class.
Instance attributes are attributes or properties attached to an instance of a class. Instance attributes are defined in the constructor.
```
class Item:
    pay_rate = 0.8   # class attribute
    def __init__(self, name: str, price: float, quantity=0):
        self.name = name
        self.price = price
        self.quantity = quantity
        
    def apply_discount(self):
        self.price = self.price * self.pay_rate   # call pay_rate only will not work, if not specified by the instance will pull from the class

item1 = Item("Phone", 100, 1)
print(Item.pay_rate)  # access class attribute from the class level
print(Item1.pay_rate)   # access class attribute from the instance level
print(Item.__dict__)  # All the attribute for Class Level
print(Item1.__dict__) # All the attributes for Instance level (will not see pay_rate)

item3 = Item("Laptop", 1000, 3)
item2.pay_rate = 0.7    # item2 will not go to class level to find pay_rate, thus item1 will have pay_rate = 0.8 but item2 will be 0.7

```
The instance will try to bring the the attribute from the instance level at first, if not find, will try to bring the instance from the class level.
3. The "ALL" attribute that will give a list of all the created instances:
4. 
```
class Item:
    all = []
    def __init__(self, name: str, price: float, quantity=0):
        ...
        Item.all.append(self)
        
print(Item.all)
```
5. __repr__ representing the objects
change the way the objects are represented when using print
```
class Item:
    ...
    
    def __repr__(self):
        return f"Item('{self.name}', {self.price}, {self.quantity})"
```


## Sources
- [Design Patterns](https://www.oodesign.com/)




# Agile


## Sources
- [The Agile Coach](https://www.atlassian.com/agile#:~:text=The%20Agile%20methodology%20is%20a,planning%2C%20executing%2C%20and%20evaluating.)
