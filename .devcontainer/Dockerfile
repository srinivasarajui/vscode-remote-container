# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.177.0/containers/typescript-node/.devcontainer/base.Dockerfile

# [Choice] Node.js version: 16, 14, 12
ARG VARIANT="16-buster"
FROM mcr.microsoft.com/vscode/devcontainers/typescript-node:0-${VARIANT}


# [Optional] Uncomment this section to install additional OS packages.
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
     && apt-get -y install --no-install-recommends curl \
  gnupg \
  linuxbrew-wrapper \
  locales \
  zsh \
  wget \
  fonts-powerline \
  chromium \
  && su node -c "npm install -g @angular/cli@11.2.13 @aws-amplify/cli"

USER node
RUN wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | zsh || true \
  && git clone https://github.com/romkatv/powerlevel10k.git ~/.oh-my-zsh/custom/themes/powerlevel10k \
  && cd ~ && curl -fsSLO https://raw.githubusercontent.com/romkatv/dotfiles-public/master/.purepower

ENV TERM xterm
ENV CHROME_BIN=/usr/bin/chromium
ENV SHELL /bin/zsh
ADD .zshrc ~
