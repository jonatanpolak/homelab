# Create a new directory somewhere to store this file, then store this file in it as "Dockerfile".
#
# Go to that directory and type:
# docker build -t "arch-updated" .
#
# Then, whenever you want to use this image, simply type:
# docker
#
# If it's been a while since you built the image, you can re-update by either running
# pacman -Syyu --noconfirm
# or you can just re-create the package.

FROM local/archlinux:latest

ENV LANG=en_US.UTF-8

RUN locale-gen
RUN pacman-key --init
RUN pacman -Sy --noconfirm archlinux-keyring
RUN pacman-key --populate
# RUN pacman-key --refresh-keys
RUN pacman -Syyu --noconfirm
RUN pacman-db-upgrade
RUN update-ca-trust

RUN pacman --sync --refresh --noconfirm \
        reflector \
    && reflector \
        --save /etc/pacman.d/mirrorlist \
        --protocol https \
        --latest 20 \
        --sort rate