# Factory_Pattern_Design_Principle_Browsers
Factory design pattern is one of the most useful patterns. You can see the usage of this pattern everywhere. One such usage of Factory Design Principle in Frameworks is in the Log4j API. As we all know Log4j is a brilliant logging API.
Here you will notice that we are not directly creating a  Logger object by using the new keyword. We are calling another class called LogManager and on that class we have a static method called getLogger(). This getLogger method is responsible for returning us a Logger object instance. LogManager is based on the Factory pattern design principle, it is basically a factory that stores and provides different Logger objects for usage.

 
4
5
6
7
8
9
10
11
12
import org.apache.log4j.LogManager;
import org.apache.log4j.Logger;
 
public class run {
 
	public static void main(String[] args) {
 
		Logger logger = LogManager.getLogger(run.class);
 
		logger.debug("This is a random debug message");
	}
}

So what is a Factory pattern design principle?
A Factory pattern is used to encapsulate the complexity of creating an object. In the example above, LogManager has encapsulated the creation of Logger. As a result all we have to do is call the getLogger method on LogManager and get the Logger object. Below are the two important ideas behind Factory pattern:

Hide the logic of initializing an object inside the factory.
Refer to the object using a common interface instead of the concrete class.
Maintain/Cache the newly created object’s life time. This is not main responsibility of a factory pattern.
Lets understand how a Factory Pattern is beneficial while designing a Test framework.

 

Browser Factory
From our experience with frameworks we know that maintaining and passing around a WebDriver object across different tests is a delicate process. Also, the complexity increases when we have to maintain only one instance of a WebDriver through out the test run. To overcome the problem on instantiation of WebDriver and maintaining the instance of browser we can use create a small class called browser factory.
