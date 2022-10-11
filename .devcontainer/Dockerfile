#-----------------------------------------------------------------------------------------
# Copyright (c) Fortinet Corporation. All rights reserved.
# Licensed under the MIT License. See LICENSE in the project root for license information.
#-----------------------------------------------------------------------------------------

FROM hashicorp/terraform
USER root

RUN apk add screen

RUN /usr/bin/ssh-keygen -A
RUN echo 'root:secretpassword' | chpasswd
RUN sed -i 's/#PermitRootLogin prohibit-password/PermitRootLogin yes/g' /etc/ssh/sshd_config 
RUN sed -i 's/#PasswordAuthentication yes/PasswordAuthentication yes/g' /etc/ssh/sshd_config 
# RUN echo "#Legacy changes" >> /etc/ssh/sshd_config
# RUN echo "KexAlgorithms diffie-hellman-group1-sha1" >> /etc/ssh/sshd_config
# RUN echo "Ciphers aes128-cbc" >> /etc/ssh/sshd_config

EXPOSE 22