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

A user types in a request utilizing their client which we call a browser. The request eventually will make its way through the servers to our Rails `routes.rb` file. Our `routes.rb` file will then determine the closest match with the URL and HTTP request and match it with the controllers and action in our Rails application. Then the view is generated and the response is sent back to the user. 

### What’s a module in Ruby? What’s the difference between a class and a module? What are some good use cases for modules?

A module is a collection of methods and constants (otherwise known as a library of methods). Unlike classes, modules cannot generate an instance of an object. Classes can have instance variables and objects. 

Modules may not inherit anything whereas a class can inherit from another class. 

Modules are great for augmenting a class's functionality. 

### What are a few ways to optimize a Rails application?

One example would be to utilize Active Record methods when making database queries. For example, `.length` is not actually an ActiveRecord method - but rather a Ruby method. While this would work, it technically is not very good practice. Instead of `.length`, you can utilize `.size`, which is much faster and efficient in terms of memory usage.  

Another way is the utilization of well-known or widely appreciated Ruby gems like the `Bullet gem`, which address the `N+1` problem. Usually this could mean that in a one-to-many relationship, a database will often times make a query for the parent database as well as a query for each child database of that parent. In a larger scale application, this can lead to your database being overrun with queries. Sometimes this redundancy can be hard to see so gems like `Bullet gem` can help us to reduce the total number of `N+1` problems.  

You could also utilize indexes in a database, which act as placeholders for a query. Since a database has to check every individual cell to grab the information needed from a request, a large database would get very tedious for your Rails application.  

And another way is to utilize caching: [https://guides.rubyonrails.org/v3.2/caching_with_rails.html#page-caching](https://guides.rubyonrails.org/v3.2/caching_with_rails.html#page-caching)

### What is HTTP and give a brief definition?

HTTP stands for hyper-text transfer protocol. We can understand protocol as a system of rules by which information or data is exchanged between computers. Usually a client, which we can understand as a web browser, will send out messages to another computer or server, which we call requests. Then that computer (server) will then respond with its own messages which we call a response.

### What are three tools or strategies you use to prevent shipping unstable code to production? 

- The use of continuous integration which would catch any potential errors before the code is shipped to production.

- The use of clear workflow between developers as well as adequate code review integrated in the Git workflow. 

- The practice of releasing smaller production code often as opposed to releasing a large set of code with down time inbetween each shipping interval. 

### What’s a background worker? When would we want to use a background worker?

A background worker is a job that extends beyond the typical request a client could make to our application. Sometimes we don't want an job to be completed instantaneously or we need a feature to do work once a user completes a task, which could take longer than the usual instantaneous response we'd expect. Sometimes the advantange of this background worker is that it enables you to queue work to be done at a later time. This also allows for us to retry work if sometimes the work fails the first time.  

This means that we do not have to rely upon the User to act as a catalyst for events.

### What’s the difference between a session and a cookie?

The biggest difference between a session and a cookie is that a cookie is data that is stored on a user's browser, whereas a session involves storing a user's data on a server.  

A cookie's maximum allowed data is 4KB whereas on a session the amount of data we can store for each user is unlimited. Cookies are set to be destroyed at a given amount of lifetime whereas sessions are usually deleted whenever a user logs out or closes the browser.

### Explain a git merge workflow vs a git rebase workflow

A git merge workflow allows for a timeline of events. It is also non-destructive as in existing branches are not changed in any way. However, if your `main` branch is very active, you may have a lot of extra data that you'd not be very interested in. Utilizing git rebase allows for a much more cleaner git history interface. We can see commits happen in a history of time-line by feature rather than by commits. This also allows for you to avoid having to merge to main. 

As long as we can utilize the Golden Rule of Rebase, which is to never rebase on public branches, rebase can be a workflow for specific uses!

### What’s the difference between authentication and authorization? What tools have you used to set up auth in the past?

Authentication is making sure that the user is actually who they say they are. Authorization is giving someone access once authentication has been made.

An example of this is when you go to a venue that sells alcohol. Perhaps there is a bouncer at the front door. You know the deal. You must show your ID to the bouncer. The bouncer checks the ID (or pretends to check it) and looks at your face. They are happy with your ID and facial recognition. You've now been authenticated.  

The bouncer then allows you to enter the venue. This is now authorization. You have user authorization to enter the venue. Happy drinking!

We've utilized authentication by creating a User's controller in which a user must provide email and password. Once the account is created, we then confirm the user has the correct password and then give the user authorization to access the site. 

### What is TDD and give a brief definition?

TDD is an acronym for test driven development. This is a method of development in which unit test cases are built before the code is developed. It is iterative, or repeated over and over again, combining programming, creation of unit tets, and refactoring.  

This process is sometimes reflected in the phrase "red-green-refactor":

- Red: Build tests. Run tests. Tests are failing.

- Green: Build code to pass test. Run tests. Code is built. Tests are passing.

- Refactor: Optimize code. Run tests. Tests are passing.

### What does API stand for and how do you define it?

An API is short for application programming interface. APIs are a convenient means to allow users to access only very specific portions of data that exists on your server. An API is a type of software interface, which means that an API is a software designed to talk to another software. Users do not usually consume raw API data. It is usually converted into useful data that humans can digest easily. A very common format of an API is JSON. GraphQL is a competitor to JSON. 

### What does it mean to compile code?

Compiling code means that you take the source code, which we can refer to as human readable language, and it then translates source code into machine code. Machine code is known as binary code which reflects the transistor state of computers. Essentially on and off switches. Since it's not very useful for humans to know binary, we can utilize a compiler to translate the hard work of taking human readable language into machine code.

This is unlike Ruby or JavaScript, which is what we call an interpreted language. This means that the language is interpreted into machine code without the use of a compiler. There are pros and cons to each approach, of which I will not get into here.

### Tell me two advantages of testing your code

- I know that potentially the code will run without errors in production

- Testing my code allows me to overcome bias in my own assumptions about what I expect my code to do

### How would you describe the prototype in Javascript?

### Here at Turing you have used two types of testing Minitest and RSpec. Please give your opinion/comparison of the two.

### My production and development environments are using large sets of data. What are some ways to optimize my tests to run quickly, but be thorough?

### What is a Mock vs. a Stub in testing? When would you use each?

### What is yield in Ruby? What is it useful for? Give an example of where you would put it.

### Describe each of the four fundamental concepts of object-oriented programming.

### An enumerable by any other name still behaves the same. Give the other name for these 3 Ruby enumerables Detect, Select, Collect

### In as much detail as possible, describe DNS.

DNS solves the problem of translating domain names like `google.com` into actual IP addresses. IP addresses are how client requests are directed to go to the exact server.  

For humans, IP addresses are not an ideal way form of data. It is much harder to remember `192.168.1.1` than it is to remember `google.com`. DNS solves this problem by giving humans a way to remember website names and conveniently acting as an interpreter for computers to direct the domain name to the actual corresponding IP address.

### What does it mean for a function to be deprecated?

Programming syntax or language evolves over time to reflect user and real world needs - this means that as version updates happen, certain functions may lose relevance or more robust functions eventually replace older functions. Deprecated means that the function is being phased out, or that it is in the process of being replaced by another function.

### What does CORS stand for and what issue does it address?

A website usually implements a security feature called same-origin policy, which means that the browser by default will restrict access of data for websites which have a different origin. By origin we mean protocol, domain name, and port number. Which this is a great feature for security as it keeps one website from attacking another website, sometimes we need to implement the sharing of data between two websites so that they are able to communicate back and forth for the benefit of a user.  

CORS is a solution to that problem. CORS is cross-origin resource sharing. While normally websites are restricted from resource sharing, CORS will specify to which origin a website is allowed access to another, while blocking off resource sharing from other origins. You can even set CORS to share with all origins on the internet, but this is generally considered bad practice since it's the equivalent of keeping your house door permanently open.

### What is the difference between synchronous vs. asynchronous?

We can refer to synchronous vs asynchronous as relating to work done. Synchronous work means that work is done in a specific order, whereas asynchronous work means that work is not done in a specific order. 

Synchronous work means that work is not done until a specific task is completed. Asynchronous work could mean the work is started immediately or not until some amount of time in the future. 

### What is the difference between a function declaration vs a function expression

Function declarations are loaded before any code is executed whereas function expressions are executed as the interpretor reaches that line of code. You may want to utilize a function expression if you are trying to avoid global scope. Function declaratives may be utilized if you need them more often than not. (Is it being needed often?)

### In as much detail as possible, tell me about JSON Web Tokens

A JSON webtoken is an open standard that allows for securely transmitted data between parties. It is sent as a JSON object and can be sent with a digital signature - sometimes an encryption or a key pair.

We normally use JSON web tokens to transmit information or to provide authorization for users.