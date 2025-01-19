# payload-db-setup

Sets up a mongoDB database for payload using docker compose for local development.

## Usage

1. Prerequisite: Your Payload 3 project should be setup.
   Set up to use MongoDB.
   Ignore db connection string, as it will be overwritten by this script.

2. Download the script
   for the moment, you can download it using curl:
   (This is not secure, but it's a trial. Don't @ me.)

   ```
   curl --create-dirs -o ./scripts/payload-db-setup.js \
   https://raw.githubusercontent.com/matiasbaldanza/payload-db-setup/refs/heads/main/scripts/payload-db-script.js
   ```

3. Run the script

   ```
   node ./scripts/payload-db-setup.js
   ```

   It will create a docker-compose.yml file in your project root (renaming the existing one.)
   It will create a .env file in your project root with the correct environment variables.
   It will add scripts to package.json to:

   - start the db
- stop the db
- wipe the db
- remove all containers and volumes related to the db

This first version will hardcode a mongoDB container.
Support for Postgres is coming soon.
