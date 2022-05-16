mkdir -p /docker_data/pypiserver
cd /docker_data/pypiserver
#계정 패스워드  생성
htpasswd -sc .htpasswd pyadmin
#패스워드 pyadmin

docker run -p 8180:8080 -v /docker_data/pypiserver/.htpasswd:/data/.htpasswd -v /docker_data/pypiserver/packages:/data/packages pypiserver/pypiserver:latest -P .htpasswd packages

