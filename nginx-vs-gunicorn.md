## WHY BOTH NGINX & GUNICORN

Nginx is where requests from the internet arrive first. It can handle them very quickly, and is usually configured to only let those requests through, which really need to arrive at your web application.

Gunicorn translates requests which it gets from Nginx into a format which your web application can handle, and makes sure that your code is executed when needed.


### Nginx
web server and reverse proxy.

- domain name routing

- Serve static files

- Handle lots of requests coming in at once

- Handle slow clients

- Forwards requests which need to be dynamic to Gunicorn

- Terminate SSL (https happens here)

- Save computing resources (CPU and memory) compared to your Python code

- load balancing, caching etc

### Gunicorn
A Web Server Gateway Interface (WSGI) server implements the web server side of the WSGI interface for running Python web applications.

- Running a pool of worker processes/threads (executing your code!)

- Translates requests coming in from Nginx to be WSGI compatible

- Translate the WSGI responses of your app into proper http responses

- Actually calls your Python code when a request comes in

- Gunicorn can talk to many different web servers


#### Sources
- https://vsupalov.com/gunicorn-and-nginx/
- https://www.fullstackpython.com/wsgi-servers.html
