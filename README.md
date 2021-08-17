Docker Imap Migrator
====================

## Automatic imap mail migration

## TODO ENGLISH

Go to the deploy_migrator folder, 
copy the 
## docker-compose.sample.yml 
file to 
## docker-compose.yml 
and change the environment variables for mailbox migration 

You can create a container for each mailbox. 
If the container crashes just restart and the migration resumes where it was.

Uso
---

Once the compose file is fixed, launch it with

```bash
docker-compose up
```

At the end of the migration, you will get a message like this:

    Synchronization of 12571 messages finished, took 6:44:35.101650
