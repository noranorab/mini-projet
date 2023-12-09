FROM debian:stable-slim

LABEL maintainer="@Nora"
LABEL version="1.0"
LABEL description="Spring boot app"

RUN apt-get update && \
    apt-get install -y openjdk-17-jdk \
    libtasn1-6 \
    dpkg \
    zlib1g \
    libldap-common \
    default-libmysqlclient-dev \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /app
COPY target/ .

RUN mvn clean install \
    && rm -rf /root/.m2 /app/src

EXPOSE 8080

CMD ["java", "-jar", "backend-0.0.1-SNAPSHOT.jar", "--spring.config.location=classes/application.properties"]