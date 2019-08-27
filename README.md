# lua-class
Implementation of class in Lua

Supports inheritance;
If you have a method for the class called 'init', the code will automatically execute when you call class:new() 

## Usage:
```lua
require("Class.lua")

--===========================

cAnimal=setclass("Animal")

function cAnimal.methods:init(action, cutename) 
	self.superaction = action
	self.supercutename = cutename
end

--==========================

cTiger=setclass("Tiger", cAnimal)

function cTiger.methods:init(cutename) 
	self:init_super("HUNT (Tiger)", "Zoo Animal (Tiger)")
	self.action = "ROAR FOR ME!!"
	self.cutename = cutename
end

--==========================

Tiger1 = cAnimal:new("HUNT", "Zoo Animal")
Tiger2 = cTiger:new("Mr Grumpy")
Tiger3 = cTiger:new("Mr Hungry")

print("CLASSNAME FOR TIGER1 = ", Tiger1:classname())   
print("CLASSNAME FOR TIGER2 = ", Tiger2:classname()) 
print("CLASSNAME FOR TIGER3 = ", Tiger3:classname()) 
print("===============")
print("SUPER ACTION",Tiger1.superaction)
print("SUPER CUTENAME",Tiger1.supercutename)
print("ACTION        ",Tiger1.action)
print("CUTENAME",Tiger1.cutename)
print("===============")
print("SUPER ACTION",Tiger2.superaction)
print("SUPER CUTENAME",Tiger2.supercutename)
print("ACTION        ",Tiger2.action)
print("CUTENAME",Tiger2.cutename)
print("===============")
print("SUPER ACTION",Tiger3.superaction)
print("SUPER CUTENAME",Tiger3.supercutename)
print("ACTION        ",Tiger3.action

```


## Credits to:

Based on original class implementation made by __Christian Lindig__ (https://github.com/lindig) with some changes from dontspamme_sam_lie2000@yahoo.com. Obtained at http://lua-users.org/wiki/ClassesAndMethodsExample
