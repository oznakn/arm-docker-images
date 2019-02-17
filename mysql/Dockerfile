# https://github.com/hypriot/rpi-mysql

FROM oznakn/debian-qemu

RUN apt-get update && apt-get install -y perl --no-install-recommends

RUN apt-get update && apt-get install -y mysql-server*

VOLUME /var/lib/mysql

COPY entrypoint.sh /
ENTRYPOINT ["/entrypoint.sh"]

EXPOSE 3306
CMD ["systemctl start mysqld"]