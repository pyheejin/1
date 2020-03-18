---
title: "상속(polymorphism)"
date: 2020-03-18
categories: class
---

# 상속 polymorphism
* In inheritance(상속), the same instance method of objects from different classes results in different behaviors.

```python
class Animal:
    def eat(self):
        print('eat something')

class Lion(Animal):
    def eat(self):
        print('eat meat')

class Deer(Animal):
    def eat(self):
        print('eat grass')

class Human(Animal):
    def eat(self):
        print('eat meat and grass')


# test code
if __name__=='__main__':
    animals=[]
    animals.extend((Lion(), Deer(), Human()))
    
    for animal in animals:
        animal.eat() # polymorphism code
```
