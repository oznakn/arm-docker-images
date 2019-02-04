FROM balenalib/odroid-xu4-debian:stretch

COPY qemu-arm-static /usr/bin

RUN apt update -qq && apt upgrade -y && apt-get install -y --no-install-recommends \
		ca-certificates \
		curl \
		netbase \
		wget \
	&& rm -rf /var/lib/apt/lists/*