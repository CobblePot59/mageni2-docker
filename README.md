# mageni2-docker
Mageni provides a free, open-source cybersecurity vulnerability management solution.

It indicates potential or proven weaknesses on the machines tested. This includes, among others: services vulnerable to attacks allowing the machine to be taken over, access to sensitive information, denials of service, etc.

## Installation / Configuration
1) Download this project.
```
git clone https://github.com/CobblePot59/mageni2-docker.git
```
2) Modify docker-compose.yml arguments.
```
args:
  MAGENI_USERNAME: "admin"
  MAGENI_EMAIL: "admin@mageni.int"
  MAGENI_PASSWORD: "Password1"
```
3) Launch docker-compose to start the app.
```
docker compose up -d --build
```

## Preview
![alt text](https://raw.githubusercontent.com/CobblePot59/mageni2-docker/main/pictures/mageni2.png)
