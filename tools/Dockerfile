FROM local/archlinux:latest

# RUN rm -rf /etc/pacman.d/gnupg
# RUN pacman-key --init
# RUN echo "allow-weak-key-signatures" >> /etc/pacman.d/gnupg/gpg.conf
# RUN pacman-key --populate 

# RUN pacman -Sy --noconfirm archlinux-keyring
# RUN pacman-key --populate
# # RUN pacman-key --refresh-keys
# # RUN pacman -Syyu --noconfirm
# RUN pacman-db-upgrade
# RUN update-ca-trust

# Sort mirrors by speed
# RUN pacman --sync --refresh --noconfirm \
#         reflector \
#     && reflector \
#         --save /etc/pacman.d/mirrorlist \
#         --protocol https \
#         --latest 20 \
#         --sort rate

RUN pacman --sync --refresh --noconfirm \
        ansible \
        diffutils \
        docker \
        git \
        graphviz \
        curl \
        helm \
        kubectl \
        kustomize \
        libisoburn \
        make \
        mdbook \
        neovim \
        openssh \
        p7zip \
        python \
        python-jinja \
        python-kubernetes \
        python-netaddr \
        python-pip \
        python-rich \
        sudo \
        terraform

RUN mkdir -p /usr/local/lib/docker/cli-plugins
RUN curl -SL https://github.com/docker/compose/releases/download/v2.28.1/docker-compose-linux-x86_64 -o /usr/local/lib/docker/cli-plugins/docker-compose
RUN chmod +x /usr/local/lib/docker/cli-plugins/docker-compose

# # TODO https://github.com/ansible-collections/community.docker/issues/216
# RUN pip install docker-compose
