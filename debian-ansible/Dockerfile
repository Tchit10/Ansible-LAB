FROM debian

RUN apt update && apt upgrade -y \
&&  DEBIAN_FRONTEND=noninteractive \
&&  apt install -y apt --no-install-recommends openssh-server python nano \
&&  sed -i 's/#PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config \
&&  echo 'root:toor' | chpasswd \
&&  mkdir /run/sshd \
&&  apt clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* 

EXPOSE 22
CMD ["/usr/sbin/sshd", "-D"]
