FROM kalilinux/kali-last-release

RUN apt-get update && apt-get install evilginx2 ca-certificates -y --fix-missing && update-ca-certificates 

COPY microsoft365.yaml /usr/share/evilginx2/phishlets

ENTRYPOINT ["evilginx2", "-p", "/usr/share/evilginx2/phishlets", "-t", "/usr/share/evilginx2/redirectors", "-developer", "-debug"]