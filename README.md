# Solution proposal for 1dv032

This repo is a solution proposal for the exercise https://github.com/1dv032/exercise-docker-compose-ror-dev

How to get it running:
First we need two volumes:
```bash
docker volume create --name todo-postgres
docker volume create --name todo-redis
```
Then we need to get the containers setup by running `docker-compose up`, this will ta some time.
Since the database isn't configured you will get an error like `solutionexercisedockercomposerordev_todo_1 exited with code 1`, exit out witch `Ctrl + c`and run the database setup commands:
```bash
docker-compose run todo rake db:reset
docker-compose run todo rake db:migrate
```
Now you should be able to run `docker-compose up` without errors and be able to access http://localhost:8000

## Pull requests are welcome
