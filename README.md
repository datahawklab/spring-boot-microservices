# spring-boot-microservices

```bash
git clone -b 1-spring-cloud-config https://github.com/datahawklab/spring-boot-microservices.git 1-spring-cloud-config
```

## initialize a local git repo 

```bash
cd ~/1-spring-cloud-config/git-localconfig-repo
git init && git add -A && git commit -m "initial commit"
```

git-localconfig-repo folder contains 3 property files

![git-localconfig-repo-img](https://user-images.githubusercontent.com/91769455/178094236-c92e857f-4b62-4d03-bfdb-7dd201d7b2fc.png)

each property file has the same variables with different values

```bash
restfulwebservices.minimum=4
restfulwebservices.maximum=996
```

## run a Spring Cloud Config server

All thats required is a spring initilaizer project with just one dependency: Config Server
~/1-spring-cloud-config/spring-cloud-config-server is an example that you can use. 

cd to ~/1-spring-cloud-config/spring-cloud-config-server

in spring-boot-microservices/spring-cloud-config-server/src/main/resources/application.properties set the following paramaters pointing to the local git repo previously initialized. 

```bash
spring.application.name=spring-cloud-config-server
server.port=8888
spring.cloud.config.server.git.uri=file:///home/swapanc/springboot-udemy/spring-boot-microservices/git-localconfig-repo   
```

in spring-cloud-config-server/src/main/java/com/swapan/microservices/springcloudconfigserver/SpringCloudConfigServerApplication.java, the @EnableConfigServer annotation was added.

![image](https://user-images.githubusercontent.com/91769455/179668266-c70719bf-6a66-4418-9c34-a86a668b742f.png)
