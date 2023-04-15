  What is a constructor in Python?
>     A constructor in Python is a special type of method (function) that is used to initialize members of an instance of a class.
>     
>     In C++ or Java, the constructor has the same name as its class, in Python the constructor is handled differently. It is used to create an
> object.
>     
>     There are two types of constructors:
>     
>     Parameterized constructor
>     Nonparametric constructor
>     The constructor definition is executed when we create an object of this class. The constructors also check that the object has enough
> resources to perform any startup task.
>     
>     Creating a Python constructor
>     In Python, the __init__() method simulates a class constructor. This method is called when creating an instance of the class. It takes
> the keyword self as the first argument, which allows access to the
> attributes or method of the class.
>     
>     We can pass any number of arguments during the creation of the class object, depending on the definition of __init __(). It is mainly
> used for.
>     

   

    class Employee:
    
    def __init__(self, name, id): 
        self.id = id 
        self.name = name 

 

    def display(self): 
        print("ID: %d nName: %s" % (self.id, self.name)) 

 
 

    emp1 = Employee("John", 101) 
    emp2 = Employee("David", 102) 

 
# accessing display() method to print employee 1 information 
 

    emp1.display() 

 
# accessing display() method to print employee 2 information 
emp2.display() 

> Exit:
> 
> ID: 101   Name: John  ID: 102   Name: David  Counting the number of
> class objects The constructor is called automatically when we create a
> class object. Consider the following example.

    class Student:   
        count = 0   
        def __init__(self):   
            Student.count = Student.count + 1   
    s1=Student()   
    s2=Student()   
    s3=Student()   
    print("The number of students:",Student.count) 

  

> Exit:
> 
> The number of students: 3  Nonparametric A nonparametric constructor
> is used when we don't want to manipulate a value, or a constructor
> that has only self as an argument. Let's take an example.

    class Student: 
        # Constructor - non parameterized 
        def __init__(self): 
            print("This is non parametrized constructor") 
        def show(self,name): 
            print("Hello",name) 
    student = Student() 
    student.show("John")   

  

> Parameterized Python Constructor A parameterized constructor has
> several parameters along with itself.
> 
> Example –

c

    lass Student: 
        # Constructor - parameterized 
        def __init__(self, name): 
            print("This is parametrized constructor") 
            self.name = name 
        def show(self): 
            print("Hello",self.name) 
    student = Student("John") 
    student.show()   

> Exit:
> 
> This is parametrized constructor  Hello John  Default Python
> Constructor When we don't include a constructor in a class or forget
> to declare it, it becomes the default constructor. It does not perform
> any tasks, but initializes objects. Consider an example.

    class Student: 
        roll_num = 101 
        name = "Joseph" 
     
        def display(self): 
            print(self.roll_num,self.name) 
     
    st = Student() 
    st.display() 

> Exit:
> 
> 101 Joseph  More than one constructor in one class Let's look at
> another scenario, what happens if we declare two identical
> constructors in a class.

    class Student: 
        def __init__(self): 
            print("The First Constructor") 
        def __init__(self): 
            print("The second contructor") 
     
    st = Student() 

> Exit:
> 
> The Second Constructor  In the above code, the st object called the
> second constructor, whereas both have the same configuration. The
> first method is not available for the st object. Internally, a class
> object will always call the last constructor if the class has multiple
> constructors.
> 
> Note. Constructor overloading is prohibited in Python.
> 
> Built-in Python class functions The built-in functions defined in the
> class are described in the following table.
> 
> SN Function Description 1 getattr(obj,name,default) is used to access
> the attribute of the object. 2 setattr(obj, name,value) It is used to
> set a specific value for a specific attribute of an object. 3 delattr
> (obj, name) is required to delete a specific attribute. 4 hasattr
> (obj, name) Returns true if the object contains a specific attribute.
> Example

    class Student: 
        def __init__(self, name, id, age): 
            self.name = name 
            self.id = id 
            self.age = age 

 
    # creates the object of the class Student 
    s = Student("John", 101, 22) 

 
# prints the attribute name of the object s 

    print(getattr(s, 'name')) 

 
# reset the value of attribute age to 23 

    setattr(s, "age", 23) 

 
# prints the modified value of age 

    print(getattr(s, 'age'))

 
 
# prints true if the student contains the attribute with name id 
 

    print(hasattr(s, 'id')) 

# deletes the attribute age 

    delattr(s, 'age') 

 
# this will give an error since the attribute age has been deleted 

    print(s.age) 

> Exit:
> 
> John  23  True  AttributeError: 'Student' object has no attribute
> 'age'  Built-in class attributes Along with other attributes, the
> Python class also contains some built-in class attributes that provide
> information about the class.
> 
> The built-in attributes of the class are shown in the table below.
> 
> SN Attribute Description 1 __dict__ Provides a dictionary containing
> information about the class namespace. 2 __doc__ Contains a string
> with class documentation. 3 __name__ Used to access the class name. 4
> __module__ It is used to access the module in which this class is defined. 5 __bases__ Contains a tuple that includes all base classes.
> Example –

    class Student:   
        def __init__(self,name,id,age):   
            self.name = name;   
            self.id = id;   
            self.age = age   
        def display_details(self):   
            print("Name:%s, ID:%d, age:%d"%(self.name,self.id))   
    s = Student("John",101,22)   
    print(s.__doc__)   
    print(s.__dict__)   
    print(s.__module__)   

> Exit: None  {'name': 'John', 'id': 101, 'age': 22} 
> __main__

