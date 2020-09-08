### F.A.Q.

## 1. docker-compose exited with code 0
A: 
- Add ```tty: true``` to ```docker-compose.yml``` to web. (https://github.com/docker/compose/issues/3896). 
- About tty in docker (https://www.quora.com/What-does-the-t-or-tty-do-in-Docker)

## 2. docker-compose can't create ```IMAGE_NAME``` image (on server), because port is exists.
A: 
- Open running processes on server with terminal command: ```ps -aux``` (https://www.cyberciti.biz/faq/how-to-check-running-process-in-ubuntu-using-command-line/). 
- Then find process and stop it with command: ```kill YOUR_PROCESS_PID```.
- Start docker compose again in background with: ```docker-compose up -d```

## 3. Frontend (react) can't connect to backend (node) with env in ```docker-compose.yml```
A: 
- Rename env ```API_ROOT``` to ```REACT_APP_API_ROOT```
- Open ```agent.js``` in frontend app and rename in ```process.env.API_ROOT``` to ```process.env.REACT_APP_API_ROOT```

### on local app:
- Create ```.env.local``` in root folder with: ```API_ROOT=http://api:3000/api```
- Rename enviroment in ```docker-compose.yml```: ```API_ROOT=http://api:3000/api``` to ```REACT_APP_API_ROOT=${API_ROOT}```

### on server:
- Clone repo with new env with command: ```git clone https://github.com/Leitirion/Realworld-react-node-docker.git```
- Create .env with command: ```echo "API_ROOT=http://devmates.me:3000/api" > .env```
- Delete all old images for mongo and api with command: ```docker rm IMAGE_ID```
- Create and start new images: ```docker-compose up --build -d```

## 4. Change http to https:
A: 
{TBD}

## 5. How to use postman with newman to create api tests:
A:
- Create some tests in postman. You cna use some env.
- Export your tests from postman app to file with ```YOUR-POSTMAN-PROJECT-TESTS,json``` format.
- Export ypur env to file with ```YOUR-POSTMAN-PROJECT-ENV,json``` format.
- Save this two files to your project.
- install newmman with command: ```npm i -g newman```.
- Create command in your ```package.json``` in scripts: ```"test": "newman run ./YOUR-POSTMAN-PROJECT-TESTS.json -e ./YOUR-POSTMAN-PROJECT-ENV,json"```
- run tests with command: ```npm run test.
