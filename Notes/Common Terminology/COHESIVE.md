- **Cohesion is the degree to which the elements inside a module belong together.** 
- Simply put, it means “the code that changes together, stays together”.
- A module with high cohesion contains elements that are tightly related to each other and united in their purpose.
- A module is said to have low cohesion if it contains unrelated elements.
- cohesion is closely related to the Single Responsibility Principle (SRP, one of [the SOLID principles](https://www.baeldung.com/solid-principles)) which states that a class should only have one responsibility.


## Advantages :
- Modules with single and well-defined purpose are **easy to understand and much more readable.**
- It is easier to make code changes since all the related code is within the module.
- It is easier to test the code since such modules do not depend on other modules for their purpose.

**Highly Cohesive modules reflect better quality of software design.**
#NOTE A module could be a class or a package or even a microservice. 






https://www.baeldung.com/cs/cohesion-vs-coupling#:~:text=Simply%20put%2C%20it%20means%20%E2%80%9Cthe,should%20represent%20the%20user%20behavior.