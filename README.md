# Triển khai Web Application bằng Docker Compose (Sử dụng Image có sẵn)

## Giới thiệu
Dự án này triển khai một ứng dụng web hoàn chỉnh bằng Docker Compose.  
Tất cả các thành phần (Backend, Frontend, Database) đã được build sẵn thành Docker image và lưu trữ trên Docker Registry(Docker Hub).

---

## Công nghệ sử dụng
- Docker
- Docker Compose
- MySQL
- Docker Images (Backend, Frontend)

---

## Yêu cầu hệ thống
Cần cài đặt:
- [Download Docker](https://docs.docker.com/get-docker/)
- [Docker Compose Guide](https://docs.docker.com/compose/)

Kiểm tra:
```bash
docker -v
docker-compose -v
```

---

## Hướng dẫn cài đặt và chạy

1. Clone Repository
```bash
git clone https://github.com/TheAnh-05-UIT/Deploy-Web-Application-with-Docker-Basic.git
cd Deploy-Web-Application-with-Docker-Basic
```

---

2. Tạo file .env
Tạo file .env trong thư mục gốc và cấu hình như sau:
```bash
# Cấu hình chung cho Backend
APP_PORT=8000
DB_HOST=mysqldb
DB_USER=your_db_user
DB_PASSWORD=your_db_password
DB_NAME=your_db_name

# Cấu hình Database
MYSQL_ROOT_PASSWORD=your_db_password
MYSQL_DATABASE=your_db_name

# Cấu hình cổng truy cập Web
WEB_PORT=8080
```

Cấu trúc thư mục
```plaintext
. 
├── docker-compose.yml 
├── .env 
├── .gitignore
└── README.md
```

Lưu ý:
- DB_HOST phải trùng với tên service database trong docker-compose.yml (ví dụ: mysqldb)

--- 

3. Pull image từ Docker Registry
```bash
docker-compose pull
```

--- 

4. Chạy ứng dụng
```bash
docker-compose up -d
```

Truy cập ứng dụng
- Frontend: http://localhost:${WEB_PORT}
- Backend API: http://localhost:${APP_PORT}
- Database: localhost:3306

---

Tổng quan docker-compose.yml
Các service chính:

- frontend → giao diện người dùng
- backend → API server
- mysqldb → MySQL database

----

Tác giả:

- [Link Github](https://github.com/TheAnh-05-UIT)
- [Link image Docker Hub](https://hub.docker.com/repositories/24520115)
