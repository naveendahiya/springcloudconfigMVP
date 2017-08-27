1. git simple config-server and config-client from [http://kubecloud.io/guide-spring-cloud-config/]

In config-server : spring.cloud.config.server.git.uri property will have git location of centralized configurations

It is possible to have a local folder to serve as centralized location:

a. add following to bootstrap.yml
spring.profiles.include: native
# ${user.parent.dir} is set in main() to get the parent of ${user.dir}
spring.cloud.config.server.native.searchLocations: file://${user.parent.dir}/sample-config-repo

refer [https://github.com/checketts/config-server-example]

Server: http://localhost:8888/configclient/default

http://localhost:8888/config-service/default

Client: http://localhost:8000/

PS. Config server gets updates right away, to update client it requires a refresh [curl -d{} http://localhost:8000/refresh]

Tasks:

1. Use rabbitmq and spring config cloud bus to avoid the refresh endpoint

2. Check how to use @RefreshScope at one place rather then at everyclass which have properties

3. Use base application.yml which is being used by all other profile specific application's ymls

4. Create one application yml file with [---] to segregate different env properties(dev,tst,prd)



