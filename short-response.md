# Short Response Questions

Answer each question below in your own words. Aim for 3–5 sentences per answer. Be specific — use the exact terms and concepts from the lesson.

Your responses will each be evaluated out of 6 points. You can earn 3 points for writing quality and 3 points for the accuracy and precision of the technical content per question.

---

## Question 1: Express vs `node:http`

Express is described as a framework that "wraps" `node:http`. What does that mean? Compare how you would handle a `GET /api/users` request in `node:http` versus in Express. What does Express do for you automatically that you had to write manually with `node:http`?

**Your answer here**:

`Express.js` is described as wrapping the `Node.js` `node:http` module because it is built on top of it and simplifies how servers handle requests and responses. With `node:http`, you must manually create the server, check `req.method` and `req.url`, set headers, convert data to `JSON`, and end the response. In `Express`, routing is handled with methods like `app.get('/api/users')`, and you can send data using `res.json()`. `Express` automatically sets the correct headers, converts objects to `JSON`, and manages the response. This reduces boilerplate code and makes building APIs faster and easier.

## Question 2: Endpoints, Controllers, and Middleware

What are **controllers** and **middleware** in Express? What are each responsible for and how do they work together to handle incoming requests?

**Your answer here**:

In `Express.js`, **middleware** and **controllers** are functions that handle parts of a request. **Middleware** runs first and is responsible for tasks like logging, authentication, or modifying the `req` and `res` objects before passing **control** with `next()`. **Controllers** contain the main route logic, such as retrieving data and sending the response with `res.json()` or `res.send()`. **Middleware** prepares the request, and the **controller** sends the final response.

## Question 3: Query Strings and Route Parameters

How are **query strings** and **route parameters** similar? How are they different? In your answer, provide an example of when you would use each.

**Your answer here**:

**Query strings** and **route parameters** are both ways to send data from the client to the server in a `URL` in `Express.js`. Route parameters are part of the `URL` path and are used to identify a specific resource, like `/users/:id` to get one user. Query strings come after a `?` in the `URL` and are used for optional data like filtering or searching, such as `/users?name=alex`. **Route parameters** are accessed with `req.params`, while query strings are accessed with `req.query`.

## Question 4: Same-Origin Requests

For API fetch calls from a client-side application, explain the difference between fetching from endpoints with relative paths like `/api/quotes` and fetching from endpoints with a full URL like `https://dog.ceo/api/breeds/image/random`. Why do we not send a fetch using a url like `http://localhost:8080/api/quotes`?

**Your answer here**:

In client-side applications, a relative path like `/api/quotes` sends a request to the same server that the website is running on. A full URL like `https://dog.ceo/api/breeds/image/random` sends a request to an external API on a different server. We usually avoid using `http://localhost:8080/api/quotes` because the domain and port may change when the app is deployed. Using a relative path ensures the fetch works correctly no matter where the app is hosted.