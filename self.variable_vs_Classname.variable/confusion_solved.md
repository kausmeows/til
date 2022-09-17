```py
class Employee:
	num_of_emps = 0
	raise_amount = 1.04

	def __init__(self, first, last, pay):
		self.first = first
		self.last = last
		self.pay = pay
		self.email = first + '.' + last + '@company.com'

		Employee.num_of_emps += 1

		self.num_of_emps = self.num_of_emps + 1 # understand the difference between these two -> self.variable and Classname.variable

	def full_name(self):
		return '{} {}'.format(self.first, self.last)

	def apply_raise(self):
		self.pay = int(self.pay + self.raise_amount)

print(Employee.num_of_emps)

emp_1 = Employee("kaus", "mos", 50000)
emp_2 = Employee("kausiii", "mosiiiii", 60000)

# print(emp_1.num_of_emps)

print(Employee.num_of_emps)
```



# Example to explain the difference between these two -> self.variable and Classname.variable


`emp1` is an instance of the class employee. Each instance has its own set of variables, 
called instance variables. These are the ones assigned as `self.var` = `...` inside methods of the class.
If you try accessing `emp1.var` and this instance variable is not assigned, Python looks for a var variable 
attached to the class of emp1, meaning it looks up `employee.var`. These kind of variable are called a class 
variable, and they are defined the way you have defined `count=0` at the top of your class.

Now, in your example, `self.count=self.count+1`, the left-hand side assigns to the instance, 
so you are creating an instance variable called count. The right-hand side, however, 
looks up `self.count`, which does not yet exist as an instance variable, so `employee.count` is really used instead. 
This confusing behavior is avoided if you do not use the same variable name for both an
instance variable and a class variable.


```py
class employee:
    count=0
    def __init__(self,x):
        self.x=x
        self.count = self.count+1
        print ("this method is executed")
        print (self.count)
        print (employee.count)
emp1=employee("John")  
``` 






