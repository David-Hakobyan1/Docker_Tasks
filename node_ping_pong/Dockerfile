FROM node:20-slim
 
LABEL maintainer="David Hakobyan"
 
ARG USERNAME=David
 
ARG USER_UID=1001
 
ARG USER_GID=$USER_UID
 
ENV PORT=3000
 
WORKDIR /app
 
COPY package.json app.js ./
 
RUN groupadd --force --gid $USER_GID $USERNAME \
    && useradd --uid $USER_UID --gid $USER_GID -m $USERNAME \
    && apt-get update \
    && apt-get install -y sudo \
    && echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME \
    && chmod 0440 /etc/sudoers.d/$USERNAME \
    && apt-get clean && rm -rf /var/lib/apt/lists/*
 
RUN npm install
 
USER $USERNAME
 
EXPOSE $PORT
 
ENTRYPOINT ["node", "app.js"]
