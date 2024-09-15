# Spring Gateway 项目

## 项目简介
该项目是一个基于Spring Cloud Gateway的Reactive网关，旨在路由和保护多个微服务的API。集成了OAuth2资源服务器进行认证和授权，通过JWT验证用户的身份，并使用Spring Reactive Web进行非阻塞式的API请求处理。

## 技术栈
- **框架**: Spring Reactive Web, Spring Cloud Gateway
- **安全**: OAuth2 Resource Server (JWT)

## 功能
1. **API 路由**：
    - 路由到不同的微服务，具体配置如下：
        - `/api/v1/*/**` 路由到 [spring-6-rest-mvc](https://github.com/SaulGoodman-jl/spring-6-rest-mvc) 微服务（http://localhost:8081）
        - `/api/v2/*` 路由到 [spring-6-reactive](https://github.com/SaulGoodman-jl/spring-6-reactive) 微服务（http://localhost:8082）
        - `/api/v3/*` 路由到 [spring-6-reactive-mongo](https://github.com/SaulGoodman-jl/spring-6-reactive-mongo) 微服务（http://localhost:8083）

2. **认证与授权**：
    - 使用[OAuth2资源服务器](https://github.com/SaulGoodman-jl/spring-6-auth-server)对请求进行JWT验证，确保请求的安全性。
    - 配置了JWT的`issuer-uri`为`http://localhost:9000`。

## 安装步骤
1. 克隆项目到本地:
   ```bash
   git clone https://github.com/SaulGoodman-jl/spring-6-gateway.git
   ```
2. 启动应用：
   ```bash
   .\mvnw spring-boot:run
   ```

## 配置
如需修改API路由或JWT验证配置，可在[application.yml](src/main/resources/application.yml)文件中修改配置

## License
该项目基于MIT许可证，请参阅[LICENSE](./LICENSE)文件获取详细信息。