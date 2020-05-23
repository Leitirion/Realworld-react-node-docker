### How to deploy app

1. Create instance in ```scaleway```, choose OS images and hardware.
2. Create SSH-key with ```https://www.notion.so/Learning-sources-ffb80890fe114f40aef1225bf17bdd27#acb5fbfba5384ab9a87b5e80e34ceac4```
3. To start work on server, open terminal and paste ```ssh root@YOUR_IP```
4. Create project folder with command ```mkdir app/Realworld```
5. Go to app directory with command ```cd app/Realworld```
6. Clone example app with react+node from Realworld-react-node-docker repository github with command: ```git clone https://github.com/Leitirion/Realworld-react-node-docker.git```
7. Install docker with: ```apt  install docker.io```
8. Install docker compose with: ```apt  install docker-compose```
9. Run container with command: ```docker-compose up -d```, where -d starts the containers in the background and leaves them running.
10. Check app in browser: ```http://devmates.me```