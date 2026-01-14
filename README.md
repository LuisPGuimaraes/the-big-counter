# The Big Counter
A simple web application that implements a counter with increment and reset operations, built with a Clojure (Pedestal) backend and a TypeScript/React frontend.


## Docker
This repo has a Docker Compose configuration to make running and development easier.

* For run all systems:
```sh
docker compose up
```

* For run only back-end:
```sh
docker compose up backend
```

* For run only front-end:
```sh
docker compose up frontend
```


* For run only datomic db:
```sh
docker compose up --build datomic
```

Connect from the backend:
- Host: `localhost`
- Port: `4334`
