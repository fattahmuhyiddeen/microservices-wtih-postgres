## Running Jenkins
```bash
docker run --name myjenkins -p 8080:8080 -p 50001:50001 --restart=on-failure --env JENKINS_SLAVE_AGENT_PORT=50001 jenkins/jenkins:lts-jdk17
```



https://github.com/v1bh0r/spring-boot-local-dev-docker/?tab=readme-ov-file

https://github.com/v1bh0r/spring-boot-local-dev-docker/



# Demo App - Spring Boot Local Development on Docker

## Getting Started
### Install Docker
[https://docs.docker.com/get-docker/](https://docs.docker.com/get-docker/)

### Build and Run the code
```bash
docker-compose up --build
```

### Test
On visiting [http://localhost:8050/api/](http://localhost:8050/api/) in your browser

You should see "Hello Human"

Notice that you don't have to re-build the code when you make code changes. You can even enable automatic refresh on
Chrome by installing [LiveReload plugin](https://chrome.google.com/webstore/detail/livereload/jnihajbhpnppcggbcgedagnkighmdlei)

#### Test Database persistence
##### Create a record
```bash
curl --location --request POST 'http://localhost:8050/api/employees/' \
--header 'Content-Type: application/json' \
--data-raw '{
    "name": "John Doe"
}'
```
##### List all records
```bash
curl http://localhost:8050/api/employees/
```

## Reference Documentation
For further reference, please consider the following sections:

* [Official Apache Maven documentation](https://maven.apache.org/guides/index.html)
* [Spring Boot Maven Plugin Reference Guide](https://docs.spring.io/spring-boot/docs/2.5.5/maven-plugin/reference/html/)
* [Create an OCI image](https://docs.spring.io/spring-boot/docs/2.5.5/maven-plugin/reference/html/#build-image)
* [Spring Boot DevTools](https://docs.spring.io/spring-boot/docs/2.5.5/reference/htmlsingle/#using-boot-devtools)

## Troubleshooting
### Code changes are not automatically detected
[https://github.com/docker/for-win/issues/8479](https://github.com/docker/for-win/issues/8479)
