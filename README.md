#!/usr/bin/env punki

print "Welcome to Punki language"

# A function definition
f: x = x*x + 2*x + 1

# A function call
a = sqrt 2.0

# Function call nesting
# Python: fun1(a,fun2(b, c, fun3(d)),e)
fun1 a (fun2 b c (fun3 d)) e

# A more complex series of calls and formulations
b = 2 * sqrt 7 + 3 * golden 2 5 + a  
# or b = 2 * (sqrt 2) + 3 * (golden 2 5) + a

# Imports. look like a function calls

import random
import math

# Class definitions

Person:
    __init__: self name age occupation = 
        self.name = name
        self.age = age
        self.occupation = occupation
        
    breathe: self = 
        print self.name "breathes... he's alive and kicking..."
        
    celebrate: self reason = 
        if reason == "birthday":
            self.age += 1
            print "Happy birthday" self.name ", happy birthday to you!"
        elif reason == "promotion":
            print "I got promoted honey, now we can afford a new car!"

# I like the '/' class inheritance construct, don't judge me! :-)
#  We use that symbol for nesting directory namespaces, why not for classes?

Employee / Person:
    __init__: self name age salary occupation position = 
        (Person self).__init__ name age occupation
        self.position = position
        self.salary = salary
        self.tasks = []
        
    assign: self task = 
        if task in self.tasks:
            raise (Exception "More work?")
        self.tasks.append task
        
    work: self = 
        for task in self.tasks:
            dt = random.int 1 8
            task.advance dt self
            
# A Multiple inheritance would be:
Tank / (Weapon Vehicle):
    pass
    
Borg:
    # I am going to be hated for this, I can almost anticipate it :)
    _state = [ 'world'=42 'other'='whatever' ]
    
    __init__: self = 
        self.__dict__ = Borg._state

# Class instantation and object usage        
joe = Person "Joe Average" 23 "college student"
joe.celebrate "party!"
joe.breathe

b = Borg
print b.world b.other

# type_of operator. 
# when you need class-as-an-object instead of class instantiation
the_borg_class = ?Borg

# In this case, you must instantiate instead of refer to the class Borg's properties
print (Borg).world
print (Borg).other

# Arrays/Dictionaries reference, instantation and usage
eat: me food_item = 
    print me.name "eats a" (str food_item) ". Very tasty"
    
fruits = [ "apple" "orange" "banana" ]
eat (Person "Boril") fruits#1

vocabulary = {
    'insult;standard': 'fuck you' 'curse;standard': 'damn it!'
    'surprise;standard': 'oh shit!' "amazement;standard':'daaaaaaym!'
    'famous-last-words': 'Meh, it\'s always gonna work'
}

# Default parameters
say: something who?"Joe Random" =
    print who "says" (str something)

# I am considering also '$' or '@' for the type_of operator

# That's it! 
# It's only a syntax replacement for Python, not a complete language so all 
#  Python code should be 100% translatable
# I tried it to be like what Python is For C or Java
# I also tried to preserve "Do not surprise me" motto of Python

