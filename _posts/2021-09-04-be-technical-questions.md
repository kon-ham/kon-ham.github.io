### What is the difference between Array#map and Array#each?
Whenever you finish iterating over your elements, Array#each will return the original array while Array#map will return a new array. Both iterative methods iterate. Array#map actually incorporates the Array#each method while transforming the values of the array in a new array.

### Name 4 ruby enumerables excluding each and map and give a brief example of what’s unique about each.
- Enumerable#all? method iterates through each element of the collection and returns true if the included argument is never false or nil.
```
array = ['cat', 'bat', 'sat']

array.all? { | word | word.length == 3 } => true

array.all? { |word | word.length == 0 } => false
```

- Enumerable#count method iterates through each element in the collection and returns the total amount of elements inside of the collection.
```
array = ['john', 'ny', 'apple', 'seed']
array.count => 4
```

- Enumerable#drop(n) will iterate through each element of the collection and drop the (n) number of elements in the collection, starting from the first element. It will return the rest of the elements in the array
```
array = [1, 2, 3, 4, 5]

array.drop(1) => [2, 3, 4, 5]
```

- Enumerable#include? will iterate through each element and return true if any of the elements match the argument. 
```
array = [1, 2, 3, 4, 5, 6, 7]

array.include? 9000 => false
```
### In as much detail as possible, describe the request-response cycle.
### What’s a module in Ruby? What’s the difference between a class and a module? What are some good use cases for modules?
### What are a few ways to optimize a Rails application?
One example would be to utilize Active Record methods when making database queries. For example, `.length` is not actually an ActiveRecord method - but rather a Ruby method. While this would work, it technically is not very good practice. Instead of `.length`, you can utilize `.size`, which is much faster and efficient in terms of memory usage.

Another way is the utilization of well-known or widely appreciated Ruby gems like the `Bullet gem`, which address the `N+1` problem. Usually this could mean that in a one-to-many relationship, a database will often times make a query for the parent database as well as a query for each child database of that parent. In a larger scale application, this can lead to your database being overrun with queries. Sometimes this redundancy can be hard to see so gems like `Bullet gem` can help us to reduce the total number of `N+1` problems.

You could also utilize indexes in a database, which act as placeholders for a query. Since a database has to check every individual cell to grab the information needed from a request, a large database would get very tedious for your Rails application. 

And another way is to utilize caching: [https://guides.rubyonrails.org/v3.2/caching_with_rails.html#page-caching](https://guides.rubyonrails.org/v3.2/caching_with_rails.html#page-caching)
### What is HTTP and give a brief definition?
HTTP stands for hyper-text transfer protocol. We can understand protocol as a system of rules by which information or data is exchanged between computers. Usually a client, which we can understand as a web browser, will send out messages to another computer or server, which we call requests. Then that computer (server) will then respond with its own messages which we call a response. 

### What are three tools or strategies you use to prevent shipping unstable code to production?
### What’s a background worker? When would we want to use a background worker?
### What’s the difference between a session and a cookie?
The biggest difference between a session and a cookie is that a cookie is data that is stored on a user's browser, whereas a session involves storing a user's data on a server. 

A cookie's maximum allowed data is 4KB whereas on a session the amount of data we can store for each user is unlimited. Cookies are set to be destroyed at a given amount of lifetime whereas sessions are usually deleted whenever a user logs out or closes the browser. 
### Explain a git merge workflow vs a git rebase workflow


### What’s the difference between authentication and authorization? What tools have you used to set up auth in the past?
### What is TDD and give a brief definition?
TDD is an acronym for test driven development. This is a method of development in which unit test cases are built before the code is developed. It is iterative, or repeated over and over again, combining programming, creation of unit tets, and refactoring.

This process is sometimes reflected in the phrase "red-green-refactor":

- Red: Build tests. Run tests. Tests are failing.  
- Green: Build code to pass test. Run tests. Code is built. Tests are passing.
- Refactor: Optimize code. Run tests. Tests are passing. 
### What does API stand for and how do you define it?
### What does it mean to compile code?
### Tell me two advantages of testing your code
### How would you describe the prototype in Javascript?
### Here at Turing you have used two types of testing Minitest and RSpec. Please give your opinion/comparison of the two.
### My production and development environments are using large sets of data. What are some ways to optimize my tests to run quickly, but be thorough?
### What is a Mock vs. a Stub in testing? When would you use each?
### What is yield in Ruby? What is it useful for? Give an example of where you would put it.
### Describe each of the four fundamental concepts of object-oriented programming.
### An enumerable by any other name still behaves the same. Give the other name for these 3 Ruby enumerables Detect, Select, Collect
### In as much detail as possible, describe DNS.
### What does it mean for a function to be deprecated?
### What does CORS stand for and what issue does it address?
### What is the difference between synchronous vs. asynchronous?
### What is the difference between a function declaration vs a function expression
### In as much detail as possible, tell me about JSON Web Tokens