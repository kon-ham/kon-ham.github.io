---
layout: default
title: Home
---

# Hi! Kon here.

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
<strong>I'm currently mentoring about 10 students learning Ruby on Rails.</strong><br>This not-for-profit organization focuses on teaching tech skills to people from diverse backgrounds (underrepresented, historically exluded, and/or folks from immigrant backgrounds) - all for free and it is powered by volunteers like me! It's a great mission that is very close to my heart.<br><br>Check out <a href="https://codethedream.org">Code the Dream!</a><br><br>

<strong>I'm looking to join a great team.</strong><br>
Do you know of any junior-mid level openings? Here's my <a
href="https://github.com/kon-ham/kon-ham.github.io/blob/main/kon-ham-resume.pdf">resume.</a>
</p>

### My Recent Posts: <a name="my-recent-posts-link"></a>
<ul>
  {% for post in site.posts limit: 5 %}
  <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
        <!-- <time  datetime="{{ post.date | date_to_xmlschema }}"  class="post-date">{{ post.date | date_to_string }}</time> -->
        <!-- {{ post.content | truncatewords: 120 }} -->
  </li>
  {% endfor %}
</ul>
---

### My Current Coding Project(s): <a name="my-current-coding-projects-link"></a>

 - **KnewHarvest** is a web-application that tracks a user's plant crops from seed to harvest. Authors of this application work closely in collaboration with end-user by implementing Agile methodology. MVP and sprint runs are utilized. End-user provides feedback with each sprint-run. Features are built incrementally. All authors work remotely and are located in three separate timezones. 

    This project is a practice in building an application in which goals and final deadlines are unknown. The authors of this application build small, iteratively, and collaboratively. Deliberate practice in async communications for standups and check-ins. Project board utilized to track user stories as well as progress of tasks and features. 

    Check out the current status of this project [here](https://github.com/wdk3)!

### My Past Coding Projects: <a name="my-past-coding-projects-link"></a>

 - **Pawty-Trainer** is a web-application to track your dog’s training. Manage a training schedule via calendar. Users can customize dogs through name, breed, age. CRUD functionality. Earn badges for completed your dog's training.  

    - Link to the front-end Github repository: [here](https://github.com/Pawty-Trainer/pawty-trainer)
    - Link to the back-end Github repository: [here](https://github.com/Pawty-Trainer/pawty-trainer-api)
    - Link to the live site: [here](https://pawty-trainer.github.io/pawty-trainer)

 - **Find My City** is a city finding web application that allows users to search and sort cities by criteria they find most important. Get scores for major cities. Save your favorite cities.  

	 - Link to the front-end Github repository:  [here](https://github.com/NoahZinter/find_my_city_fe).  
     - Link to the back-end Github repository:  [here](https://github.com/NoahZinter/find_my_city_be).
     - Link to the live site:    [here](https://helpmefindmycity.herokuapp.com).  
     
 - **Sweater Weather** is an API-only application. Find weather data for the city you are traveling to. Know what the weather will be like whether you arrive three hours later or three days later.  

	- Link to the Github repository: [here](https://github.com/kon-ham/sweater_weather).

### Contact Me <a name="contact-me-link"></a>
My email is: [contact@konkham.com](mailto:contact@konkham.com) or [info.konham@gmail.com](mailto:info.konham@gmail.com)    
My Github is: [github.com/kon-ham](https://github.com/kon-ham)  
My LinkedIn is: [linkedin.com/in/kon-ham](https://www.linkedin.com/in/kon-ham)