---
layout: default
title: Home
---

# Hi! Kon here.

Use the top right panel to navigate through the site or use the links below to navigate through the home page.  

Thanks for visiting!

### Table of Contents: 

 - #### [Announcements](#announcements-link) 
 - #### [My Latest Coding Projects](#my-latest-coding-projects-link) 
 - #### [My Recent Posts](#my-recent-posts-link) 
 - #### [Contact Information](#contact-information-link)

---

### Announcements: <a name="announcements-link"></a>

<p class="message">

<strong>I'm looking to join a great team.</strong><br>
Do you know of any junior-mid level openings? Here's my <a
href="https://github.com/kon-ham/kon-ham.github.io/blob/main/kon-ham-resume.pdf">resume.</a>
</p>

---

### My Latest Coding Projects: <a name="my-latest-coding-projects-link"></a>

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



### Contact Information: <a name="contact-information-link"></a>
My email is: [contact@konkham.com](mailto:contact@konkham.com) or [info.konham@gmail.com](mailto:info.konham@gmail.com)  
My Github is: [github.com/kon-ham](github.com/kon-ham)  
My LinkedIn is: [linkedin.com/in/kon-ham](linkedin.com/in/kon-ham)  