# Schema Definition Language

Same as the Hello world example, but shows how to use schema definition language
and wire up some resolvers as plain functions.

### Run local test server

```bash
php -S localhost:8080 graphql.php
```

### Alternatively, running with Docker from the current directory:
```bash
# Install composer dependencies if they haven't been yet
docker run --rm --interactive --tty --volume $PWD/../..:/app composer install

# Run the application
docker run --rm -v $PWD/../..:/app -w /app -p 8080:80 php:8-cli php -S 0.0.0.0:80 examples/02-schema-definition-language/graphql.php
```

### Try query

```bash
curl -d '{"query": "query { echo(message: \"Hello World\") }" }' -H "Content-Type: application/json" http://localhost:8080
```

### Try mutation

```bash
curl -d '{"query": "mutation { sum(x: 2, y: 2) }" }' -H "Content-Type: application/json" http://localhost:8080
```
