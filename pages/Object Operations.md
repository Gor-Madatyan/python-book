# Constructor
- the `__new__(cls, *args, **kwargs)`
  creates the object
- ```python
  ...
  def __new__(cls, *args, **kwargs):
          if cls._instance is None:
              # Create the instance only if it doesn't exist
              cls._instance = super().__new__(cls)
          return cls._instance
  ...
  ```
- # Destructor
- responsible for the final cleanup of resources right before clearing the object
- ```python
  ...
  def __del__(self):
          # This code runs when the object is destroyed
          print(f"File {self.filename} is being closed.")
  ...
  ```
- # Selector
- the regular boring getter
- # Mutator
- the regular boring setter
- # Iterator
- Is used to `iterate` over the components of a composite class
- can be implemented as `__iter__(self)`
- You can create lazy iterators by calling yield in a function
	- > This syntax is called generator function
	- ```python
	  #!/bin/python
	  
	  class A:
	      def __init__(self,l):
	          self.l = l
	  
	  
	      def __iter__(self):
	          yield from self.l # the same as to yield in a loop
	  
	  
	  for i in A([1,2,3,4,5,10000]):
	      print(i)
	  
	  ```