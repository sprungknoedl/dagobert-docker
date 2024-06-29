FROM debian:12
WORKDIR /app

ADD https://github.com/Yamato-Security/hayabusa/releases/download/v2.16.0/hayabusa-2.16.0-linux-intel.zip /usr/src/hayabusa-2.16.0-linux-intel.zip

RUN apt update && apt install -y ca-certificates unzip
RUN unzip /usr/src/hayabusa-2.16.0-linux-intel.zip -d /app
RUN rm hayabusa-2.16.0-lin-x64-gnu && mv hayabusa-2.16.0-lin-x64-musl hayabusa && chmod +x hayabusa 
RUN ./hayabusa update-rules

ENTRYPOINT [ "/app/hayabusa" ]