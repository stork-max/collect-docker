From alpine

RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.aliyun.com/g' /etc/apk/repositories && apk update && \
    apk add  ca-certificates bash coreutils sed tcpdump rsync tzdata curl strace iproute2 logrotate tree screen && \
    echo "Asia/Shanghai" > /etc/timezone && \
    cp -r -f /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && apk del tzdata && \
    echo -e "alias ls='ls --color=auto'\n alias ll='ls -la'\n PS1='[\\u@\\H:\\w]# '" >> /root/.bashrc && \
    echo -e "export SHELL='/bin/bash'\nsource ~/.bashrc" > /etc/profile.d/bash.sh && \
    echo -e "/bin/sh\n/bin/bash" > /etc/shells && \
    sed -ri "s~/bin/ash~/bin/bash~" /etc/passwd && \
    rm -rf /var/cache/apk/*

WORKDIR /

CMD ["/bin/bash"]
