FROM ubuntu:latest

# to run the container:
# - docker container run -it --rm --name spotify --device /dev/snd --net=host spotify:latest

# TODO: save user data
# TODO: media controls

# to run GUI application within the container
ENV DISPLAY :0

# install base packages
RUN apt update
RUN apt install curl gnupg -y

# add the spotify repo to the sources list
RUN curl -sS https://download.spotify.com/debian/pubkey_5E3C45D7B312C643.gpg | apt-key add -
RUN echo "deb http://repository.spotify.com stable non-free" | tee /etc/apt/sources.list.d/spotify.list

# install spotify package
RUN apt update
RUN apt install spotify-client -y

# launch the application
ENTRYPOINT ["spotify"]
