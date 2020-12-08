Welcome to DOCKER
====================
Link full docs: https://docs.google.com/document/d/13jmbBC0mbOIYtSDtJuXzbxpPcOkd8nKwyyOarO6Iujo/edit?usp=sharing


## Docker 04

- Chia se du lieu giua 2 container:
    ```
    docker run -it --name C2 --volumes-from C1 <imageId>
    ```
- Kiem tra danh sach o dia:
    ```
    docker volume ls
    ```
 - Tao o dia moi:
    ```
    docker volume create <name>
    ```
    vd: Tao o dia ten la D1
    ```
    docker volume create D1
    ```
- Kiem tra thong tin o dia
    ```
    docker volume inspect <name>
    ```
vd: Kiem tra thong tin o dia D1
```
docker volume inspect D1
```
Xoa o dia
```
docker volume rm <name>
```
Anh xa o dia vao container
```
docker run -it --name <name_container> --mount source=<name_disk>,target=<path_container> <image_id>
```
Tao o dia anh xa den thu muc trong may host
```
docker create --opt device=<path_host> --opt type=none --opt o=bind <name_disk>
```
Anh xa o dia tu host vao container
```
docker run -it -v <name_disk>:<path_container> <image_id>
```

## Docker 05

Tao container voi -rm, sau khi ket thuc container se tu xoa
```
docker run -it --rm <image>
```
Liet ke danh sach network
```
docker network ls
```
Kiem tra cac container dang ket noi toi network
```
docker network inspect <name_network>
```
vd:
```
docker network inspect bridge
```
Anh xa cong cua container toi host (truy cap cac container)
```
docker run -it  --name <name_container> -p <port_host>:<port_container> <image>    
```

Tao network 
```
docker network create --driver <driver_type> <name_network>
```
vd:
```
docker network create --driver bridge network1
```
Xoa network
```
docker network rm <name_network>
```
Ket noi container voi 1 network chi dinh
```
docker run -it --name <name_container> --network name_network> <image>
```
Gan container dang chay ket noi toi network chi dinh
```
docker network connect <name_network> <name_container>
```
