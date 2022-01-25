Specs
Get familiar with Rails command line basics. For this exercise, you should know at least how to:

Create a new Rails app
Launch a web server to open your app locally
Generate a new controller from the command line
Check your routes with the relevant rails command
Launch a rails server
Every web developer starts working by launching a server and opening a browser to test live the features they code. Go ahead:

launch a server in your terminal
open localhost:3000 in your favourite web browser! You should see Rails’ welcome page.
Every time you write some code in a file, save it and refresh your browser. You will get many error messages, but it is important to get familiar with them. This way, you will understand Rails’ execution flow and learn how to fix them!

Generate controller
First things first, let’s generate a QuestionsController we’ll use for our two pages. Remember the rails command to do that?

Display the form: /ask
We want to display a page with a <form> to our users at localhost:3000/ask. In Rails, this counts as a user story, so we need more than an HTML file to make it happen. For every user action in Rails, we need to code (i) a route, (ii) an action, and (iii) a view. Remember the MVC pattern?

Route

Write a simple route to serve the GET /ask HTTP request to the ask action of the questions controller. As a reminder, here is the pattern of a route coded in Rails:

verb "url", to: "controller#action"
Controller

After setting up the route, it’s time to code the action. Go ahead and add an ask action in your QuestionsController! Do we need to define an instance variable here? We’ll figure it out while coding the view!

Oh and by the way, do you remember how to display all your routes in the terminal?

View solution
View

Last step to display the form, let’s create a view! Do you remember in which folder it should be and how it should be named? That’s one of Rails’ conventions, the Action View convention. Refresh the page at localhost:3000/ask, if you named your file properly you should finally see a page without an error! For now it’s empty, let’s finally add the <form>. Remember the syntax?

<form action="???">
  <input type="text" name="???">
  <input type="submit" value="Ask!">
</form>
The native behaviour of a <form> tag is to generate the HTTP request defined by the method and action attributes.

the method attribute holds the HTTP verb (GET by default)
the action attribute holds the url of the request it triggers on submit
In the <input>, the name attribute enables you to set the key of the corresponding parameter.

Here we want the form to trigger our second user story: answer, which should be routed on /answer. Go ahead and replace the ??? above and try to submit the form.

You should get a routing error, let’s code the answer now!

Display the Coach’s Answer: /answer
Time to implement the logic in the answer action (second step of the user journey). For this second user story, follow the same methodology as in 1. Display the form:

code the route
code the action (in the controller)
code the view
And make sure you refresh your page frequently in your browser to let Rails’ execution flow drive your development!

The answer.html.erb will display the question you ask your coach as well as his answer. The controller will need to read the question from params and compute an instance variable @answer for the view to display. Here are two requests that you should be able to handle:

localhost:3000/answer?question=hello
localhost:3000/answer?question=what time is it?
If you don’t remember about the coach (poor) logic, here it is:

If the message is I am going to work, the coach will answer Great!
If the message has a question mark ? at the end, the coach will answer Silly question, get dressed and go to work!.
Otherwise the coach will answer I don't care, get dressed and go to work!

Backlink from /answer to /ask
Add a link to /ask on the answer.html.erb view using the link_to Rails helper.
