1. docker-compose exited with code 0
    A: add ```tty: true``` to ```docker-compose.yml``` to web. (https://github.com/docker/compose/issues/3896). About tty in docker (https://www.quora.com/What-does-the-t-or-tty-do-in-Docker)
2. docker-compose can't create IMAGE_NAME image (on server), because port is exists.
    A: open running processes on server with terminal command: ```ps -aux``` (https://www.cyberciti.biz/faq/how-to-check-running-process-in-ubuntu-using-command-line/). 
    Then find process and stop it with command: ```kill YOUR_PROCESS_PID```.
    Start docker compose again in background with: ```docker-compose up -d```
3. 