FROM openjdk:slim

RUN apt-get update && \
    apt-get install -y wget && \
    apt-get clean && rm -rf /var/lib/apt/lists /tmp /var/tmp

RUN wget https://s3.eu-central-1.amazonaws.com/dynamodb-local-frankfurt/dynamodb_local_latest.tar.gz && \
    mkdir -p /dynamodb /data && \
    tar -xvzf dynamodb_local_latest.tar.gz -C /dynamodb && \
    rm dynamodb_local_latest.tar.gz

WORKDIR /dynamodb

EXPOSE 8000
ENTRYPOINT ["java"]
CMD ["-Djava.library.path=./DynamoDBLocal_lib", "-jar", "DynamoDBLocal.jar", "-sharedDb", "-dbPath", "/data"]
