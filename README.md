# cat-system
一个以网站形式展示的app，用于宠物电商的宣传和管理
[README.md](https://github.com/user-attachments/files/29192946/README.md)
# 宠物售卖系统

本工作区按前后端分离方式组织：

- `backend/`：Spring Boot 3 后端，提供客户端 `/api/v1/**` 与管理端 `/api/admin/v1/**` 接口。
- `frontend/`：宠物售卖系统客户端，React 18 + TypeScript + Vite。
- `admin-frontend/`：管理后台前端。

## 后端数据库

后端只使用 MySQL 8.0。启动前请先创建数据库：

```sql
CREATE DATABASE IF NOT EXISTS petshop
  DEFAULT CHARACTER SET utf8mb4
  DEFAULT COLLATE utf8mb4_unicode_ci;
```

默认连接参数：

- `DB_URL=jdbc:mysql://localhost:3306/petshop?useUnicode=true&characterEncoding=utf8&serverTimezone=Asia/Shanghai&useSSL=false&allowPublicKeyRetrieval=true`
- `DB_USERNAME=root`
- `DB_PASSWORD=root`

也可以通过环境变量覆盖：

```powershell
$env:DB_URL="jdbc:mysql://localhost:3306/petshop?useUnicode=true&characterEncoding=utf8&serverTimezone=Asia/Shanghai&useSSL=false&allowPublicKeyRetrieval=true"
$env:DB_USERNAME="root"
$env:DB_PASSWORD="root"
```

## 启动

后端：

```powershell
cd backend
& "C:\Program Files\apache-maven-3.9.5\bin\mvn.cmd" spring-boot:run
```

客户端：

```powershell
cd frontend
npm install
npm run dev -- --host 0.0.0.0 --port 5175
```

管理后台：

```powershell
cd admin-frontend
npm install
npm run dev -- --host 0.0.0.0 --port 5174
```

访问地址：

- 客户端：http://localhost:5175
- 管理后台：http://localhost:5174
- 客户端 API：http://localhost:8080/api/v1
- 管理端 API：http://localhost:8080/api/admin/v1
- Swagger：http://localhost:8080/swagger-ui.html

演示账号：

- 客户端：`138000in` / `admin123`00000` / `123456`
- 管理端：`adm

## 构建验证

```powershell
cd backend
& "C:\Program Files\apache-maven-3.9.5\bin\mvn.cmd" -q clean package -DskipTests

cd ..\frontend
npm run build
```
