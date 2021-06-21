# what is Component ?
>> Components are independent and reusable bits of code. They serve the same purpose as JavaScript functions, but work in isolation and return HTML via a render() function. Components come in two types, Class components and Function components, in this tutorial we will concentrate on Class components.

----------

>Object-oriented view
A component is viewed as a set of one or more cooperating classes. Each problem domain class (analysis) and infrastructure class (design) are explained to identify all attributes and operations that apply to its implementation. It also involves defining the interfaces that enable classes to communicate and cooperate.

>Conventional view
It is viewed as a functional element or a module of a program that integrates the processing logic, the internal data structures that are required to implement the processing logic and an interface that enables the component to be invoked and data to be passed to it.

>Process-related view
In this view, instead of creating each component from scratch, the system is building from existing components maintained in a library. As the software architecture is formulated, components are selected from the library and used to populate the architecture.
* > A user interface (UI) component includes grids, buttons referred as controls, and utility components expose a specific subset of functions used in other components.

* > Other common types of components are those that are resource intensive, not frequently accessed, and must be activated using the just-in-time (JIT) approach.

* > Many components are invisible which are distributed in enterprise business applications and internet web applications such as Enterprise JavaBean (EJB), .NET components, and CORBA components.
![alt](https://www.tutorialspoint.com/software_architecture_design/images/principles_of_component_based_design.jpg) .

###### Advantages

1. > Ease of deployment − As new compatible versions become available, it is easier to replace existing versions with no impact on the other components or the system as a whole.

2. > Reduced cost − The use of third-party components allows you to spread the cost of development and maintenance.

3. > Ease of development − Components implement well-known interfaces to provide defined functionality, allowing development without impacting other parts of the system.

4. > Reusable − The use of reusable components means that they can be used to spread the development and maintenance cost across several applications or systems.

5. > Modification of technical complexity − A component modifies the complexity through the use of a component container and its services.

6. > Reliability − The overall system reliability increases since the reliability of each individual component enhances the reliability of the whole system via reuse.

7. > System maintenance and evolution − Easy to change and update the implementation without affecting the rest of the system.

8. > Independent − Independency and flexible connectivity of components. Independent development of components by different group in parallel. Productivity for the software development and future software development.


----------------------

### What is Props?

> **React is a component-based library which divides the UI into little reusable pieces. In some cases, those components need to communicate (send data to each other) and the way to pass data between components is by using props.**
> *“Props” is a special keyword in React, which stands for properties and is being used for passing data from one component to another.*



######  How are props used in React?

1. > Firstly, define an attribute and its value(data)
2. > Then pass it to child component(s) by using Props
3. >Finally, render the Props Data
   

`class ParentComponent extends Component {  
  render() {
    return (
      <h1>
        I'm the parent component.
        <ChildComponent />
      </h1>
    );
  }
}`


###### It always renders the same string again and again:

![alt](https://miro.medium.com/max/700/1*rzX4l1-rJn4c4_yeqooFbQ.png))


> *React has a different approach to data flow & manipulation than other frameworks, and that’s why it can be difficult at the beginning to understand some concepts like props, state and so on.*
