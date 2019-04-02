# Continuous Delivery to Kubernetes with [jib](https://github.com/GoogleContainerTools/jib#what-is-jib), [skaffold](https://skaffold.dev/docs/getting-started/#installing-skaffold) and [ktor](https://github.com/ktorio/ktor)  


##### preconditions
- [kubernetes](https://kubernetes.io/) / [minikube](https://kubernetes.io/docs/setup/minikube/) / [docker](https://www.docker.com/)
- [skaffold](https://skaffold.dev/docs/getting-started/#installing-skaffold)
- [ktor](https://ktor.io/) / [kotlin](https://kotlinlang.org/)
- [gradle](https://gradle.org/) / [jib](https://github.com/GoogleContainerTools/jib)

#### continuous delivery
```
skaffold dev
# access ktor web app on 'http://127.0.0.1:8080/'
# change the ktor app and reload 'http://127.0.0.1:8080/' 
```

##### screencast:
[![Ktor App Continuous Delivery](http://img.youtube.com/vi/T-Ed_tbi1f8/0.jpg)](https://www.youtube.com/watch?v=T-Ed_tbi1f8 "Ktor App Continuous Delivery")

#### run application with jib & docker
```
./gradlew jibDockerBuild && docker run --rm -p 8080:8080 ktor01:1.0-SNAPSHOT
# specify docker image name
./gradlew jibDockerBuild --image=myimagename && docker run --rm -p 8080:8080 myimagename
```

#### run application

```
./gradlew run
```

#### test application

```
./gradlew test
```

#### clean up
```
./gradlew clean
docker rmi $(docker images -q)
```

#### blog post
[_Kotlin Continuous Delivery to Kubernetes_ on lotharschulz.info](https://www.lotharschulz.info/2019/02/17/Kotlin-Continuous-Delivery-to-Kubernetes/)

#### further reading
- [Jib 1.0.0 is GA—building Java Docker images has never been easier](https://cloud.google.com/blog/products/application-development/jib-1-0-0-is-ga-building-java-docker-images-has-never-been-easier)
- [What is Jib?](https://github.com/GoogleContainerTools/jib#what-is-jib)
- [Containerize your Gradle Java project](https://github.com/GoogleContainerTools/jib/tree/master/jib-gradle-plugin)
- [Containerize a Ktor application with Jib](https://github.com/GoogleContainerTools/jib/tree/master/examples/ktor)

