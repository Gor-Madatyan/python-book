- First we are gonna talk about the data members and then about methods
- # Data Members
- When talking about the data members we can effectively classify them either as instance attributes or as class attributes. **We don't have static attributes**
- ## Instance Attribute
- ```python
  class A:
    def __init__(self, age):
      self.age = age
  ```
	- here the `age` is **instance attribute**
	- > When you assign something to self with syntax `self.smt = smt` it is always instance attribute but it is not necessary if we request value instead of assigning `print(self.smt)`
- ## Class Attributes
- ```python
  class Singleton:
    __instance = None
    def __new__(cls, *args, **kwargs):
      if not cls.__instance:
        cls.__instance = super().__new__(cls)
      return cls.__instance
  ```
	- here the `__instance` is **class attribute**
	- > when the object of the singleton assigns something to the `__instance` it automatically becomes instance attribute
- # Method Members
- It is instance member by default. If you annotate it with `@classmethod` or `@staticmethod` it becomes one
- ```python
  class A:
      @classmethod
      def do_smt(cls):
          print(f"{type(cls)}")
  
      @staticmethod
      def just_do_smt():
          print("doing smt")
  
  ```