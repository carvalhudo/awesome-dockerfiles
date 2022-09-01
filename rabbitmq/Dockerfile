FROM ubuntu:latest

# to run the container:
# - docker container run -p 15672:15672 -p 5672:5672 -it --rm --name rabbitmq rabbitmq:latest

RUN apt update
RUN apt install erlang rabbitmq-server -y

# install rabbitmq plugins
RUN rabbitmq-plugins enable rabbitmq_management
# to enable the guest user
# https://stackoverflow.com/questions/23669780/rabbitmq-3-3-1-can-not-login-with-guest-guest
RUN echo "[{rabbit, [{loopback_users, []}]}]." > /etc/rabbitmq/rabbitmq.config

 # rabbitmq port
EXPOSE 5672
# rabbitmq_management port
EXPOSE 15672

ENTRYPOINT ["rabbitmq-server", "start"]
