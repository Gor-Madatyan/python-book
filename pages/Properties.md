- there are 2 ways to write a property
	- ```python
	  #!/bin/python
	  class A:
	      def get_p(self):
	          return self.__p
	  
	      def set_p(self, val):
	          if not isinstance(val, str):
	              raise TypeError()
	          if not val:
	              raise ValueError()
	  
	          self.__p = val
	  
	      p = property(get_p, set_p)
	  
	  a.p = "awdaw"
	  print(a.p)
	  
	  ```
		- By the way, the `get_p` and `set_p` should be defined above
	- ```python
	  #!/bin/python
	  class A:
	      @property
	      def p(self):
	          return self.__p
	  
	      @p.setter
	      def p(self, val):
	          if not isinstance(val, str):
	              raise TypeError()
	          if not val:
	              raise ValueError()
	  
	          self.__p = val
	  
	  a = A()
	  
	  a.p = "awdaw"
	  print(a.p)
	  
	  ```
		- same applies here