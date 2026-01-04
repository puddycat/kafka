#
# kafka/containers/Dockerfile
#
# raymondstrose@hotmail.com
#
#   Create a Kafka Docker image.
#
#   docker build -f Dockerfile  \
#       --build-arg BASE_IMAGE="apache/kafka" \
#       --build-arg BASE_IMAGE_TAG="4.0.0" \
#       --build-arg KAFKA_VERSION="4.0.0" \
#       -t raymondstrose/kafka:4.0.0 .
#

ARG	BASE_IMAGE="apache/kafka"
ARG	BASE_IMAGE_TAG="4.0.0"
ARG	KAFKA_VERSION="4.0.0"

FROM $BASE_IMAGE:$BASE_IMAGE_TAG
LABEL MAINTAINER=raymondstrose@hotmail.com

ARG	KAFKA_VERSION
ENV APP_VERSION="${KAFKA_VERSION}" \
    BITNAMI_APP_NAME="kafka" \
    IMAGE_REVISION="2" \
    JAVA_HOME="/opt/bitnami/java" \
    PATH="/opt/bitnami/java/bin:/opt/bitnami/kafka/bin:$PATH"

COPY opt /opt

EXPOSE 9092

USER 1001

ENTRYPOINT [ "/opt/kafka/entrypoint" ]
CMD [ "/opt/kafka/run" ]
