Use this comand:

```bash
	docker run --name postgres -p 5432:5432 -e POSTGRES_USER=admin -e POSTGRES_PASSWORD=admin -d postgres
```

Arguments breakdown:

- **name:** container name
- **p:** port to bind this container (in this case, this container is running and pointing to our maching in part 5432)
- **e:** use this to set environment variables
- **d:** image to use (in this case, **postgres**)