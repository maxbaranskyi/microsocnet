# microsocnet

This is a project for building a tiny Twitter-like social network for learning purpose. The result of this project is going to be an API for using for different types of UI (web application, mobile application, desktop application) 



### Project pecification

| Technology  | Version                      |
|-------------|------------------------------|
| PHP         | 8.2                          |
| Laravel     | 10                           |
| PostgreSQL  | 15                           |
| Minio       | RELEASE.2023-02-10T18-48-39Z |
| Redis       |                              |
| Meilisearch | 1.0.1                        |

> :warning: Once again, the purpose of this project is to learn how to use technologies and some of them can be not relevant for this specific project

### Set up

This project uses Laravel Sail for . To run the project you need to be sure you have installed Docker on your machine. After that you can execute this command for a first run.

```bash
docker run --rm \
    -u "$(id -u):$(id -g)" \
    -v "$(pwd):/var/www/html" \
    -w /var/www/html \
    laravelsail/php82-composer:latest \
    composer install --ignore-platform-reqs
```

for next time you can use this command (you need to be on the project direcotry) for running the project 

```bash
vendor/bin/sail up
```

### Database

Here is a [link to ERD diagram](https://drive.google.com/file/d/1jVS6_rPuXVjGYLW9I0pOE48n1H8yXAho/view?usp=sharing) (Read only) of microsocnet project with whole diagram of database architecture

### Documentation

Here is a [link to documentation](https://docs.google.com/document/d/1PirQ_dMVsC228_E8qrA2dHGsA4j2EEy6LrQpwiIc9hw/edit?usp=sharing) (Read only) 