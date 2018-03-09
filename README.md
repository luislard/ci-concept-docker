# Docker Main Project

Here you will find instructions on how to configure properly your setup in local and be able to ship to common CI environment
without creating conflict with other projects being pushed.

## Folder Structure (TODO)

## Developer Flux

1. Create ci-concept folder and go inside it. This folder will hold two main folders: Docker Stack configuration and Project Repo.

```bash
mkdir ci-concept && cd ci-concept
```

2. Download ci-concept-docker repo.

```bash
git clone git@gitlab.com:eng.luisrosales/ci-concept-docker.git
```

3. Download ci-concept-project repo.

```bash
git clone git@gitlab.com:eng.luisrosales/ci-concept-php.git
```

4. We have created a shell script that will help the developer, we need to make it executable.

```bash
chmod +x ci-concept-docker/develop
```

## Useful commands

Being inside the ci-concept-docker.

```bash
# Check if the stack is active (shortcut to docker-compose ps)
./develop

# Create the stack (shortcut to docker-compose up -d)
./develop up -d

## Note: If you want to change the default port to 90 instead of 80 do the following.
APP_PORT=90 ./develop up -d

# Install composer dependencies (shortcut to docker-compose exec php bash -c "composer install")
./develop composer install

# Run tests (shortcut to docker-compose exec -T php bash -c "./vendor/bin/phpunit <folder_name_with_tests>")
./develop t <folder_name_with_tests>

# example
./develop t tests

```
