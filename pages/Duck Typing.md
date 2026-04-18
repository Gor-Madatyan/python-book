- When many classes don't inherit from the same class but implement the same interface that strategy can be called `duck typing`
- for more runtime convenience(to use `isinstance`)
	- you can use `.register()` (inheriting from `ABC` required)
	  logseq.order-list-type:: number
		- ```python
		  #!/bin/python
		  from abc import ABC, abstractmethod
		  
		  class A(ABC):
		    	@abstractmethod
		      def a(self):
		          ...
		  
		  class B:
		      def a(self):
		          print("AAA")
		  
		  A.register(B)
		  
		  print(isinstance(B(),A))
		  
		  ```
	- or `Protocol` from typing `from typing import Protocol, runtime_checkable`
	  logseq.order-list-type:: number
		- ```python
		  #!/bin/python
		  from typing import Protocol, runtime_checkable
		  
		  @runtime_checkable
		  class A(Protocol):
		      def a(self):
		          ...
		  
		  class B:
		      def a(self):
		          print("AAA")
		  
		  
		  print(isinstance(B(),A))
		  
		  ```