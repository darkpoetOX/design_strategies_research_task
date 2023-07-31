# Software design methodologies


### What do we mean by coupling and cohesion when discussing structured design?

Coupling refers to how dependent one piece of a software programme is on another. For example, in java, the degree to how one class needs another in order to function accurately. If you can change things in one class and it does not significantly affect other classes it may depend on or that may depend on it, it is referred to as low coupling. If such a change impacts other classes to a large extent, then the classes are said to be high coupling. Imagine a class, Teacher, dependent on another class, WorkingDay, to describe a teacher's working days at a school:

public class Teacher {
    
    private String id;
    private String department;

    public WorkingDay workingDay;
}

public class WorkingDay {
    
    private String day;
    private int workHours;

    public WorkingDay(String day, int workHours){
        this.day = day;
        this.workHours = workHours;
        }
    public String getDay(){
        return this.day = day;
    }
    public void setDay(String day){
        this.day = day;
    }
    public int getWorkHours(){
        return this.workHours = workHours;
    }
    public void setWorkHours(int workHours){
        this.workHours = workHours;
    }
}

The WorkingDay class serves as a template for days worked not just for a teacher but also for a cleaner, dinner lady etc at the same school. This allows for code reusability. In addition, any changes to the WorkingDay class will not affect the teacher class and as such, allows isolation of a potential bug to the smalest possible component. Consequently, the relationship bewteen the Teacher and WorkingDay class is of loose coupling. This coupling can also be looser if an interface is used instead of a concrete class. In contrast, an instance of a WorkingDay object had to be created inside the Teacher class to use it, this would be an example of high coupling.

The concept of cohesion is slightly different. It means that all methods and procedures within a component or class of the programme should be linked to one behaviour. In the example above, day and workHours methods are linked because it gives information on a teacher's working day and hours worked in that day. The WorkingDay methods are not entirely unrelated in the Teacher class, however, it will not be as cohesive. In cohesion, little dependency and high internal relation is required as it makes code look logical, easy to maintain and localises functional issues to that component or class.

</br>


### What is the difference between top-down and bottom-up design? Which best describes a function oriented design?

The top-down approach starts with an overarching design for a programme and is then split into smaller parts. The bottom-up design does the opposite, whereby little components which perform specific functions are firstly focused on before bringing the parts together to form the whole. Function-oriented design, like the name suggests, prioritises function and the building of the little components first, focusing on how each  component can be independent and cohesive for ease of use with other parts of the programme. Hnece, it is clear to see that this design approach is congruent with the bottom-up methodology.

</br>

### In which design methodology would a class diagram be most useful?

Given that a class is a template for an object in java, the object-oriented design would benefit most from the use of class diagrams. As earlier mentioned, function-oriented design focuses on the specific functionality and so it is logical that a more appropriate diagram would be one that illustrates the chronology of each of the functions or procedures. In addition, a class diagram in the object-oriented design shape would ideally have functions represented by methods in the diagram.

</br>

### What are the four pillars of object oriented programming? Give a single-sentence description of each.

- Abstraction - the process of hiding data not needed for a user to use a programme.

- Encapsulation - involves putting both the attributes and functions of data into one component like a a java class, such that other parts of the programme does not see it, limiting unintentional modification.

- Inheritance - is when a class inherits all the attributes and functions of another class, allowing code extention without having to rewrite it.

- Polymorphism - is the concept of many classes being related by inheritance under another class, allowing an implementation of a mehtod to take on different shapes or for a given method to be overloaded (same method, different inputs).

</br>

### What is the strategy pattern? How would its implementation differ between a functional and object oriented system?

The strategy pattern is a style of programming where related classes, implementing different algorithms, are bundled under often one interface called a strategy. It is made up of two main parts: Strategy objects and a delegator class. 

For example, a diet food delivery company may come up with a strategy to have varying proportions of weight loss superfood, based on a customer's body max index (BMI). The strategy can be called FoodDietStrategy and it would be an interface, taking BMI as input. The FoodDietStrategy is called the strategy interface. One can then have various classes implementing the interface function. Each class would be named differently based on BMI and output various proportions of the superfood i.e. one BMI class outputs 50% of superfood to be delivered while another BMI class outputs 90% of the superfood to be delivered. These classes would be the different strategies. After the various classes are defined, a separate class is defined which is repsonsible for calling the entire strategy group at runtime - this class is referred to as the delegator class.

In the object-oriented system, the implementation of each strategy is executed by classes using the 'implements' keyword while in the functional-oriented system, what are referred to as pointer functions are used to represent each strategy and then these functions are passed as inputs to the delegator class.

</br>

### Imagine creating a new online payment system. To gain maximum market share, it cannot be tied to a particular sector - needs to work just as well when ordering a takeaway as when buying a new coat. Which design methodology would you suggest?

I would opt for the object-oriented design as this is what I am more familiar with from the BNTA course so far. On the course, I have had practice with inheritance and polymorphism and for a non-sector-specific solution, it appears that the payment system would benefit from the ability for an object to change shape, such as afforded by method overloading. Abstract methods would also be useful as one can have a base method for payment in a parent class, but depending on what sector, can have different bodies, thus different outputs in each of the child classes. Furthermore, each new sector can be linked to common interfaces, which would mean each new component is loosely coupled. This would allow for flexibility and scalability.













