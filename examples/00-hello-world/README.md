# Hello world

Clean and simple single-file example of main GraphQL concepts originally proposed and
implemented by [Leo Cavalcante](https://github.com/leocavalcante).

### Run local test server

```bash
php -S localhost:8080 graphql.php
```

### Alternatively, running with Docker from the current directory:
```bash
# Install composer dependencies if they haven't been yet
docker run --rm --interactive --tty --volume $PWD/../..:/app --user $(id -u):$(id -g) composer install

# Run the application
docker run --rm -v $PWD/../..:/app -w /app -p 8080:80 php:8-cli php -S 0.0.0.0:80 examples/00-hello-world/graphql.php
```

### Try query

```bash
curl -d '{"query": "query { echo(message: \"Hello World\") }" }' -H "Content-Type: application/json" http://localhost:8080
```

### Try mutation

```bash
curl -d '{"query": "mutation { sum(x: 2, y: 2) }" }' -H "Content-Type: application/json" http://localhost:8080
```
