---
title:  "What Are Restful Routes?"
date:   2014-4-19 12:26:20 -0800
categories: routes
permalink: restful routes
image:
comments: true

---

There are 4 main commands, or 'HTTP verb' your browser can send to a web server.

They are
    
1. GET
2. POST
3. PUT
4. DELETE

If you are not working with a database, you will have little need to use POST, PUT, or DELETE.
Your browser will just GET pages and show them to a user.
Or maybe your website will have a contact form.
In that case, when the user presses the submit button, the browser will send a POST command to the server.

Other than that, restful routes are mainly useful when working with databases.

When you program your front-end (the javascript that gets loaded in the browser), 
you can make it send any combination of HTTP verb + URL you want back to the server.

Then, when you program your back end (the server), all you have to do is make it recognize the combination 
the user is sending from the front end, and respond accordingly.

If you just make up these combinations of VERB and ROUTE out of thin air, you are not using restful routes.
Other programmers will mock you and will refuse to help you with your project.

So 'restful routes' is merely a pattern you should follow.

The chart below shows the combinations you should use.
Consult the chart enough, and you will eventually have the routes memorized

    | ACTION                 | NON-RESTFUL ROUTES        | RESTFUL ROUTES    |
    |------------------------|---------------------------|-------------------|
    | Show all walnuts       | GET    /walnuts/show_all  | GET    /walnuts   |
    | Show walnut number 67  | GET    /walnuts/show/67   | GET    /walnuts/67|
    | Add a new walnut       | POST   /walnuts/add       | POST   /walnuts   |
    | Update walnut number 4 | POST   /walnuts/update/4  | PUT    /walnuts/4 |
    | Delete walnut number 2 | DELETE /walnuts/destroy/2 | DELETE /walnuts/2 |
    
Note that user `sign_in` and `sign_out` don't really fit nicely into this pattern.
People usually just use the routes `/sign_in`, `/sign_up`, and `/sign_out`.