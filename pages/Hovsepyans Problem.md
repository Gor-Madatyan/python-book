- ```python
  #!/#!/bin/python
  
  class A:
      def __init__(self):
          print("A")
  
  class B:
      def __init__(self):
          print("calling from B to super")
          super().__init__()
  
  class G(B,A):
      def __init__(self):
          super().__init__()
  
  
  G()
  
  ```
- in `inheritance` like this the parent of `B` when accessed from `G` is `A` not `object`