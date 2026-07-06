---
title : "Cài đặt Docker và Docker Compose"
date : 2024-01-01
weight : 2
chapter : false
pre : " <b> 5.5.2 </b> "
---
1. Bước này mình sẽ lần lượt chạy các câu lệnh sau để cài đặt Docker vào hệ thống.
```
sudo dnf update -y

sudo dnf install docker -y

sudo systemctl start docker

sudo systemctl enable docker

sudo mkdir -p /usr/local/lib/docker/cli-plugins
sudo curl -SL https://github.com/docker/compose/releases/download/v2.31.0/docker-compose-linux-x86_64 -o /usr/local/lib/docker/cli-plugins/docker-compose
sudo chmod +x /usr/local/lib/docker/cli-plugins/docker-compose

docker compose version

```
![overview](../../../images/5-Workshop/5.5-ec2/53.png)
2. Sau khi cài thành công mình lại tiếp tục tạo thư mục làm việc và tạo 2 file docker-compose.yml và .env
```
sudo mkdir -p /home/ssm-user/engexam
cd /home/ssm-user/engexam
sudo nano docker-compose.yml
```
3. Thêm nội dung file compose
```
services:  engexam:
    image: pdtuan04/engexam    container_name: engexam
    depends_on:      engexam-mq:
        condition: service_healthy
    environment:
        - ASPNETCORE_ENVIRONMENT=Production        
        - ASPNETCORE_URLS=http://+:8080
        - ConnectionStrings__EngExamConnection=Server=${DB_SERVER};Database=${DB_NAME_WRITE};User Id=${DB_USER};Password=${DB_PASS};Encrypt=False;TrustServerCertificate=True;
        - ConnectionStrings__EngExamReadDBConnection=Server=${DB_SERVER};Database=${DB_NAME_READ};User Id=${DB_USER};Password=${DB_PASS};Encrypt=False;TrustServerCertificate=True;
        - ConnectionStrings__RedisCache=${REDIS_CONNECTION}
        - JWTKey__ValidAudience=${JWT_AUDIENCE}
        - JWTKey__ValidIssuer=${JWT_ISSUER}
        - JWTKey__Secret=${JWT_SECRET}
        - ExternalAuth__GoogleAuthOptions__ClientId=${GOOGLE_CLIENT_ID}
        - ExternalAuth__GoogleAuthOptions__ClientSecret=${GOOGLE_CLIENT_SECRET}
        - StorageOptions__StorageType=${STORAGE_TYPE}
        - StorageOptions__S3Options__Region=${S3_REGION}
        - StorageOptions__S3Options__BucketName=${S3_BUCKET_NAME}
        - StorageOptions__S3Options__CloudFrontDomain=${S3_CLOUDFRONT_DOMAIN}
        - EmailSetting__Provider=${EMAIL_PROVIDER}
        - EmailSetting__SMTPOptions__Host=${SMTP_HOST}
        - EmailSetting__SMTPOptions__Port=${SMTP_PORT}
        - EmailSetting__SMTPOptions__Username=${SMTP_USER}
        - EmailSetting__SMTPOptions__Password=${SMTP_PASS}
        - MessageBrokerSetting__Host=${MQ_HOST}
        - MessageBrokerSetting__UserName=${MQ_USER}
        - MessageBrokerSetting__Password=${MQ_PASS}
        - AIModel__ModelType=${AI_MODEL_TYPE}
        - FrontEndOptions__BaseUrl=${FRONTEND_URL}
    volumes:
        - images_data:/app/wwwroot/uploads/images
    networks:
      - engexam-network
    restart: always
  engexam-mq:
    image: rabbitmq:3-management
    container_name: engexam-mq
    restart: always
    ports:
      - "5672:5672"
    volumes:
      - rabbitmq_data:/var/lib/rabbitmq
    environment:
      RABBITMQ_DEFAULT_USER: ${MQ_USER}
      RABBITMQ_DEFAULT_PASS: ${MQ_PASS}
    healthcheck:
      test: ["CMD", "rabbitmq-diagnostics", "-q", "ping"]
      interval: 10s
      timeout: 5s
      retries: 5
      start_period: 30s
    networks:
      - engexam-network
  engexamui:
    image: pdtuan04/engexamui:latest
    container_name: engexamui
    restart: always
    ports:
      - "8082:8082"
    depends_on:
      engexam:
        condition: service_started
    networks:
      - engexam-network
volumes:
  images_data:
  rabbitmq_data:
networks:
  engexam-network:
    driver: bridge
```
4. Lần này mình cần lấy chuỗi kết nối của RDS và Elastic Cache đã tạo ở bước trước thay vào chỗ DB_SERVER= và REDIS_CONNECTION= trong file .env bên dưới
5. Tiếp tục `sudo nano .env` những chỗ "..." điền secret của riêng mình vào
```
DB_SERVER="..."
DB_NAME_WRITE=ENG_WRITE
DB_NAME_READ=ENG_READ
DB_USER=admin
DB_PASS=111AAAaaa
REDIS_CONNECTION="..."
MQ_HOST=amqp://engexam-mq:5672
MQ_USER=guest
MQ_PASS=guest
JWT_AUDIENCE=http://localhost:7262
JWT_ISSUER=http://localhost:7262
JWT_SECRET=MY-SUPER-SECRET-KEY-PDTUAN04-ENGEXAM
GOOGLE_CLIENT_ID="..."
GOOGLE_CLIENT_SECRET="..."
STORAGE_TYPE=S3
S3_REGION=ap-southeast-1
S3_BUCKET_NAME="..."
S3_CLOUDFRONT_DOMAIN="..."
EMAIL_PROVIDER=SMTP
SMTP_HOST=smtp.gmail.com
SMTP_PORT=587
SMTP_USER="..."
SMTP_PASS="..."
```
6. Sau khi tạo xong mình tiến hành pull về và chạy lên thử <br>
`sudo docker compose pull`
 <br>
`sudo docker compose up -d`
![overview](../../../images/5-Workshop/5.5-ec2/54.png)