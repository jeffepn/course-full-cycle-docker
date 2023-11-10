### course-full-cycle-docker
Curso para imersão em docker - Full Cycle

#### Clone o projeto em sua máquina

```bash
git clone https://github.com/jeffepn/course-full-cycle-docker.git
```

#### Criação das imagens
##### Laravel e Nginx

```bash
cd course-full-cycle-docker

docker build -t jeffepn/laravel:prod laravel/ -f laravel/Dockerfile.prod

 docker build -t jeffepn/nginx:prod nginx/ -f nginx/Dockerfile.prod
```
#### Criação da rede compartilhada

```bash
 docker network create laranet
```

#### Execução dos containers

```bash
docker run -d  --network laranet --name laravel jeffepn/laravel:prod

docker run -d --network laranet --name nginx -p 8080:80 jeffepn/nginx:prod
```
