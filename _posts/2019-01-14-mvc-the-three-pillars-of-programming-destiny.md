---
layout: post
title: "The Three Pillars of Programming Destiny MVC"
categories: architecture
---


MVC is an architectural pattern that has been the foundation for many popular web apps. 
MVC stands for Model View Controller. It was invented in  by <a href="https://en.wikipedia.org/wiki/Trygve_Reenskaug">Trygve Reenskaug</a> in the 1970’s and became the holy arcticature it is today, like blues is to rock and roll??? 

Basically MVC says that an application should be broken down into three parts and each part has its own role to play in getting sh#{%raw %} * {%endraw%}t done. 

<img src="/assets/img/mvc.png" alt="mvc diagram">

<h3> MODEL </h3>
Is responsible for interacting with the persistence layer of the application. Did that make sense?? Possibly it did, but “give it to me in english doc”.... The model is responsible for saving information to the database or whatever system will keep the data for medium to long term use. Typical persistence layers include MySQL, MongoDB, Postgresql, etc... The model is the source and keeper of the information, as far as the application is concerned (a Librarian, if you remember them) .  When other parts of the application need data they ask the model to get it for them. Also when it is time to save information the model is your guy for the job. Some people will argue weather the model should be responsible for checking the information to make sure it is correct before saving it. In my opinion the model should check for simple things such as if the user is trying to save a string, when an integer is needed. As for more complex logic like coupon use, or a discount based on past purchases this logic should be somewhere else, such as a controller perhaps. The model’s primary job is to retrieve and store data in whatever persistence layer the application is using. One major benefit of using the pattern is that if you ever need to change what database you are using, then you only need to change the model. The rest of the application can remain the same. 

<h3> VIEW </h3>
I feel this is the simplest one to explain. The view is responsible for creating documents to the client to fulfill their request. You can think of a view as the webpage itself. For example say a user would like to view the “about us” page. The controller would look at the request and decide to ask the view to send the “about us” page content to the user. Views are what is going to be presented to the person viewing your site. 

<h3> CONTROLLER </h3>
The traffic cop of the your application…. Or teacher, administer, project manager…. Whatever person you feel  most comfortable with being in charge of stuff. In some examples the controller is the component that sits in the center of the pattern. It is responsible for taking requests from clients, and then deciding what steps should be taken the fulfill the users request. This could be as simple as serving up a static page such as a FAQ page. Or it could be asked to create an user account. It does not do all tasks by itself. The Controller delegates and manages tasks using the help of Views, Models and if needed other Controllers. For example serving a static FAQ page, the controller would see the request, and would pass the request along to a view that is assigned to creating the FAQ page. The view would then send the information to the user. In another example such as  creating a user account First the controller would need data from a registration form like the one below
<img src="/assets/img/register_page_example.png" alt="example customer register page">

One the above page We are asking for 
<ul>
	<li>Name </li>
	<li>Email</li>
	<li>Password</li>
	<li>Confirm Password</li>
</ul>

When a user fills out the form and hits submit typically the controller will get the first look at the data, server side that is. The controller would look at the information and decide if the data is valid, as in all the required fields were filled out. The controller will probably also check to see if the user already exists in the database. For this task the controller would take the email data point and ask the user model to check if this email already exists in the database.  The user model would do a check in the database and return something like true if the user already exists of false if it does not. The controller when then look at the result and decide what are the next steps. In the case that the user does not exist and the data is valid to save, the controller would take the data and make one more request to the user model to create the user. The model would then return the result of the user creation to the controller. Again the controller looks at the result sent to it from the model. If the user was created the controller will call the user created view to be sent to the client. If the user could not be created for some reason, the controller will ask the correct view to be sent to the user based on the error. Last possible out come of the user registering is if they already have an account. In that case the controller can call the login view to be sent to the user. 

<h3>of course there are Exceptions</h3>
This is the theory of this design. Not all applications build follow this pattern to it’s textbook version, although most try. Not all applications should follow this back and forth with the controller being the end all component in the middle of everything. One exception could be if a developer would like to skip sending data back to the controller if a user already exists, and they know they should be sent to the login screen. The model could ask the login view to be loaded,skipping sending the data back to the controller. Another example is the view could need data from the model tom complete the webpage before sending it to the user.  In our FAQ example the questions and answers could be stoed in the database. The view might need to ask the FAQ model for the content first and then loop though the data return from the model to complete it’s view and finally send it to the client. Exception like this are fine in a working application and things like this will happen. The controller does not always need to be informed of every out come and make every decision, just like your boss :). 

<h3> CONCLUSION </h3>
As you can se  some simple tasks that we take for granted on a daily basis can get very complicated quickly. The MVC structure gives us as web developers the ability to keep logic, and responsibilities separated so that we are not getting confused on how or where something is being done.




