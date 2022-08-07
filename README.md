# What is EJS and why use it?
EJS, short for Embedded JavaScript, is a simple templating language used for generating HTML using JavaScript. Sometimes we will need to dynamically render content on our website, which can be cumbersome with just JavaScript and HTML alone. What if we have to add data we get from our server and render it on our webpage? What if we have multiple routes to our webpages, can we make it less repetitive and make it more easy to render the pages?
These are one of the few reasons we use EJS. Functionally EJS templating is similar to React.

# Installing EJS
We can install the node module for ejs by `npm install ejs`

# Writing the server code
We first have to require the ejs node module which can be done by `const ejs = require("ejs");`

Our EJS files (i.e. the webpages we are rendering must be stored in a directory called views) and we have to set the view engine to ejs, by
`app.set("view engine", "ejs");`

As seen in the code, we render the 'home.ejs' when we perform a get request to "/" route. Along with that we are also passing the items array. The syntax followed is as such
<br />
`res.render('ejs_file', {'name_of_variable_in_ejs_file':'name_of_variable_in_server_file'});`
Using the same variable names, avoid confusion as to which variable name was used in which file.

# Writing the home.ejs file
The boilerplate for the file is same as our HTML page. We add a form that performs post request on "/" that adds an item to the item array.
Now we have to code the part where we render the data from item array.
<br />
The EJS syntax for it is like, wherever we use JS we enclose it in `<% %>` or something similar to this syntax (Refer Documentation for all the tags).
<br />
The tags used here are 
`<% %>`: We enclosed the looping of the items array in this to indicate that it is JS code and not HTML code.
<br />
`<%= %>`: We used this to output the value in items array in the template, i.e., as HTML.

# Working
Initially, when the server is running, the items array is empty and so nothing will be displayed after the title. But after we add an item using the form, then items array will contain an element and that renders the item below the title heading.