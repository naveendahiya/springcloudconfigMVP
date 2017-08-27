1. git simple config-server and config-client from [http://kubecloud.io/guide-spring-cloud-config/]
In config-server : spring.cloud.config.server.git.uri property will have git location of centralized configurations
It is possible to have a local folder to serve as centralized location:
a. add following to bootstrap.yml
spring.profiles.include: native
# ${user.parent.dir} is set in main() to get the parent of ${user.dir}
spring.cloud.config.server.native.searchLocations: file://${user.parent.dir}/sample-config-repo
refer [https://github.com/checketts/config-server-example]
