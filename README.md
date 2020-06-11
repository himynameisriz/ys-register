# What is this?
A pretty simple cash register application

# Requirements to run this project
[Node14](https://nodejs.org/en/download/current/), or [Docker](https://www.docker.com/)

# How to build and run (Node)
- Clone the repository
- Go to a terminal to the repository
- Run in terminal `npm install`

For development purposes:
- Run in terminal `npm run start`

For production purposes: 
- Run in terminal `npm run build`
- Run in terminal `npm run serve`

The API is now accessible from port 3000.

# How to build and run (Docker)
- Clone the repository
- Go to a terminal to the repository
- Run in terminal `docker build -t register .`
- Run in terminal `docker run -p 49160:3000 -d register`
-- You can change 49160 to any port you want

The API is now accessible from port 49160 (unless you chose something else)
