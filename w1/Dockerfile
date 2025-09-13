FROM ubuntu:22.04

RUN apt update && apt install -y \
    sudo

# Add nvp user
RUN useradd -m -s /bin/bash nvp \
    && echo "nvp:nguyenphuchntt" | chpasswd \
    && usermod -aG sudo nvp

ENV USER=nvp

# Set port
EXPOSE 22 5901

CMD ["/bin/bash"]