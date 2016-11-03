Instructions:

- Add your answers inline to the markdown file.
- Use your own words.
- Come up with an answer from memory. Write it down, even if the answer is "I don't know."
- Then, we will go over the answers in class. Write down your revised answer below your original answer.
- There are two intermissions. We will go over the answers to the previous parts during those times.
- Finally, submit all of your answers in a file to canvas. This is so Lloyd and I can get a sense of your understanding.

---
### Part 1: Servers - 20 minutes

1. What is a server? What does a server do?

a server is a file where you (the maker of the site) link certain files together, and get the site working.

2. What is Node.js?

a program that runs files, similar to ruby.

3. What is express?

an application you use to create routes on node.js, I guess in ruby-terms it would be ruby on rails.

4. What is a client? What does a client do?

client is a computer that makes requests (eg. show this or that page)

5. How do the server and the client communicate?

the client makes a request, the server gives a response.

6. Debugging:
- 6a. How do you view server logs?

I don't know

- 6b. How do you view client logs?

in the console, using morgan

---
### Part 2: HTTP Requests - 15 minutes

1. What is an HTTP Request?



2. GET Requests
- 2a. What is a GET request?
a request from the client to get a webpage from a server
- 2b. When do you use GET requests?
the client uses it when it wants to view a webpage
- 2c. How do you send data in a GET request?
app.get('/extension', data)

3. POST Requests
- 3a. What is a POST request?
a request to post something on a webpage
- 3b. When do you use POST requests?
eh filling in a form, leaving you email-adress.
- 3c. How do you send data in a POST request?
app.post(...data...) (not sure yet)

---

### Intermission

---
### Part 3: Ajax - 15 minutes

1. Ajax
- 1a. What is Ajax?
an application that the server requires, but I'm still in the dark as to what it really does
- 1b. When should you use Ajax?
see previous answer
2. Given the following code snippet:

```js
console.log("A");
$('#map').click(function(event) {
	console.log("B");
	var coordinates = convertMouseCoordinatesToGeoCoordinates(event);

	console.log("C");
	$.get('/map', { lat: coordinates.x, lon: coordinates.y }, function(response, status) {
		console.log("D");
		mapDisplay.update(response);
	});

	console.log("E");
});
console.log("F");
```

- 2a. Describe what seems to be happening.

the code prints "A" in the console, then it uses jquery, so that when the mouse clicks on the Id "map", the console prints "B". then the variable "coordinates" get defined as a callback function. console prints "C".  then jquery gets a file displaying a map (I guess) the forementiones function converts the mouse coordinates to geographical coordinates (I trust the function is defined elsewhere) the function is called when the latitudeXlongitude coordinates are clicked on, and it responds with the status (?). "D" is printed in the console.  and "E" and "F".

- 2b. In what order is `A` through `F` printed?

A - F - B - C - E - D

- 2c. Describe the events that happen between each letter. When does the server get hit?

"A" and "F" are called regardless, B-E are called when the function runs (click)
---

### Intermission

---
### Part 4: Jade - 20 minutes

1. Jade
- 1a. What is Jade?

(now pug) is a mark up language for html

- 1b. Why should we use Jade?

cleaner code, easy to snippet down (eg. seperate navbar, you can include in each pug file) and easier to connect with javascript.

2. Explain the difference between 'server side' JavaScript and 'client side' JavaScript.

serverside is back end, it makes all the routes work, client side is front end, makes the site work

3. Given this example `index.jade` file:

```js
doctype html
html
	head
		script(src='boop.js')
		script.
			var x = 1;
	body
		- var y = 2;
		h2= z + y
```

- 3a. Is `x` executed server side or client side? Does the client ever see `x`?

x is in the head, the client won't see it so it's client side

- 3b. Is `y` executed server side or client side? Does the client ever see `y`?

I don't know what the dash means in pug, but I think the client won't see this because it has no "p" or "h6" or anything like that before the formula.

- 3c. Is `z` executed server side or client side? Does the client ever see `z`?

z is nowhere defined in this code, maybe it is defined in boop.js. I don't know

- 3d. When is `boop.js` executed? Does the client ever see `boop.js`?

I don't think so.

---
### Part 5: Request Lifecycle - 15 minutes

5. Given the following code snippet in an express application:

```js
app.get('/home', function (request, response) {
	response.render('index', { z: 3 } );
});
```

- 5a. List the complete order of events, starting from the browser making a `GET` request to `/home`. Assume that 	`index` refers to the Jade file in Part 4. Be sure to describe when each JavaScript statement (`x`, `y`, `z`, and `boop.js`) gets executed.

(wild guess, because I'm not confident on the subject)
the the client makes a get request to get the "/home" page the server responds with rendering the index.js file, defining the value of "z" as 3. first X is executed, in the header, then Y, the Z.

- 5b. What is displayed on the page?

"5" in h2 size ? (I'm not sure this will actually happen though)

- 5c. What is visible from 'view page source'?

I don't know
