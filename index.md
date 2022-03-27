---
layout: default
title: Home
---

# Hi! Kon here.

This is where I write about everything.

Use the top right panel to navigate through my pages. Use the links below to navigate through the home page. Thanks for visiting!

### Table of Contents: 

 - #### [Announcements](#announcements-link) 
 - #### [My Recent Posts](#my-recent-posts-link) 
 - #### [My Current Coding Projects](#my-current-coding-projects-link)
 - #### [My Past Coding Projects](#my-past-coding-projects-link) 
 - #### [Contact Me](#contact-me-link)

---

### Announcements: <a name="announcements-link"></a>

<p class="message">
<strong>My LinkedIn is currently hibernating.</strong>
<br>If you need to reach out - feel free to <a href="mailto:info.konham@gmail.com">email me</a>. (info.konham@gmail.com)
<br><br>
<strong>I'm currently mentoring about about 20 students learning either Ruby on Rails or 'Intro to Programming'.</strong><br>This not-for-profit organization focuses on teaching tech skills to people from diverse backgrounds (underrepresented, historically exluded, and/or folks from immigrant backgrounds) - all for free and powered by volunteers like me (and perhaps you)! It's a great mission that is very close to my heart. Check out <a href="https://codethedream.org">Code the Dream!</a>
</p>
---

### My Recent Posts: <a name="my-recent-posts-link"></a>
<ul>
  {% for post in site.posts limit: 10 %}
  <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
        <!-- <time  datetime="{{ post.date | date_to_xmlschema }}"  class="post-date">{{ post.date | date_to_string }}</time> -->
        <!-- {{ post.content | truncatewords: 120 }} -->
  </li>
  {% endfor %}
</ul>

---

### My Current Coding Project(s): <a name="my-current-coding-projects-link"></a>

 - **Learning Python**. I'm exploring Python via ['100 Days of Python'](https://www.udemy.com/course/100-days-of-code/). 
 
   Here's the Github [link](https://github.com/kon-ham/100_days_of_python).

 - **KnewHarvest** is a web-application that tracks a user's plant crops from seed to harvest. Authors of this application work closely in collaboration with end-user by implementing Agile methodology. MVP and sprint runs are utilized. End-user provides feedback with each sprint-run. Features are built incrementally. All authors work remotely and are located in three separate timezones. 

    This project is a practice in building an application in which goals and final deadlines are unknown. The authors of this application build small, iteratively, and collaboratively. Deliberate practice in async communications for standups and check-ins. Project board utilized to track user stories as well as progress of tasks and features. 

    We're currently using: Tailwind CSS and Rails.

    Check out the current status of this project [here](https://github.com/wdk3)!

---

### My Past Coding Projects: <a name="my-past-coding-projects-link"></a>

 - **Pawty-Trainer** is a web-application to track your dog’s training. Manage a training schedule via calendar. Users can customize dogs through name, breed, age. CRUD functionality. Earn badges for completed your dog's training. Experiment with utilizing a new technology: GraphQL

    - Link to the front-end Github repository: [here](https://github.com/Pawty-Trainer/pawty-trainer)
    - Link to the back-end Github repository: [here](https://github.com/Pawty-Trainer/pawty-trainer-api)
    - Link to the live site: [here](https://pawty-trainer.github.io/pawty-trainer)

 - **Find My City** is a city finding web application that allows users to search and sort cities by criteria they find most important. Get scores for major cities. Save your favorite cities. Deliberate exercise in learning to work with a front end and a back end team. Utilized consumption of third party APIs and regenerating necessary information into applications own unique JSON object utilizing JSON serializers. 

	 - Link to the front-end Github repository:  [here](https://github.com/NoahZinter/find_my_city_fe).  
     - Link to the back-end Github repository:  [here](https://github.com/NoahZinter/find_my_city_be).
     - Link to the live site:    [here](https://helpmefindmycity.herokuapp.com).  
     
 - **Sweater Weather** is an API-only application. Find weather data for the city you are traveling to. Know what the weather will be like whether you arrive three hours later or three days later. Deliver an API key for users to use. Consume third party APIs. Exclusively back-end only application. Utilize Postman to verify application returns appropriate responses through third party client. 

	- Link to the Github repository: [here](https://github.com/kon-ham/sweater_weather).

---

### Contact Me <a name="contact-me-link"></a>
My email is: [info.konham@gmail.com](mailto:info.konham@gmail.com)    
My Github is: [github.com/kon-ham](https://github.com/kon-ham)