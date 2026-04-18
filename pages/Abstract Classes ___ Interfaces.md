- ```pyton
  from abc import ABC, abstractmethod
  ```
- you inherit from `ABC` and annotate the **abstract** methods with  `abstractmethod`
	- if all methods are abstract the class is considered to be an interface
	- abstract methods can have default implementation
	- ```python
	  #!/bin/python
	  from abc import ABC, abstractmethod
	  
	  class A(ABC):
	      @abstractmethod
	      def a(self):
	          print("AAAA")
	  
	  
	  class B(A):
	      def a(self):
	          super().a()
	  
	  B().a()
	  
	  ```