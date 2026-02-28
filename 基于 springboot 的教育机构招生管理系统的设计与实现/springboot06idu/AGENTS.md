# Repository Guidelines

## 项目结构与模块组织
- `src/main/java/com`: Spring Boot 主代码；常见包 `controller`、`service`、`dao`、`entity`、`config`、`interceptor`、`utils`。
- `src/main/resources`: 配置与资源；`application.yml` 运行配置，`mapper/` 为 MyBatis XML，`static/` 存放上传资源。
- `src/main/resources/admin/admin`: 管理端 Vue 工程；`src/` 源码，`dist/` 编译产物（后端直接加载）。
- `src/main/resources/front/front`: 前台静态页面与资源。
- `db/springboot06idu.sql` 为库结构/样例数据；`target/` 为 Maven 输出。

## 构建、测试与开发命令
- `.\mvnw.cmd spring-boot:run`（或 `mvn spring-boot:run`）：启动后端，默认 `http://localhost:8080/springboot06idu`。
- `.\mvnw.cmd test`：运行 JUnit 测试。
- `.\mvnw.cmd -DskipTests package`：打包 jar 到 `target/`。
- 管理端（进入 `src/main/resources/admin/admin`）：`npm install`、`npm run serve`、`npm run build`、`npm run lint`。

## 代码风格与命名规范
- Java 8 / Spring Boot 2.2.2；保持现有格式，不做无关重排版。
- 命名惯例：`*Controller`、`*Service`、`*Dao`、`*Entity`、`*View`、`*VO`；映射文件为 `*Dao.xml`。
- 接口返回统一使用 `com.utils.R`。

## 测试指南
- 使用 JUnit 5 + `@SpringBootTest`。
- 测试类以 `*Tests` 结尾（例：`src/test/java/com/SpringbootSchemaApplicationTests.java`）。
- 新增接口或复杂查询时尽量补充测试。

## 提交与 PR 要求
- 当前目录无 Git 历史，暂无既定提交规范可引用。
- 建议提交信息简短、动词开头（例：`Update admission labels`），必要时补充范围。
- PR 描述需包含可见改动、数据库/表结构调整；涉及 `admin` 或 `front` 页面时附截图。

## 配置与数据说明
- 数据库配置在 `src/main/resources/application.yml`（默认 MySQL `127.0.0.1:13306`）。
- 避免提交真实账号密码；按本地环境调整。
- 静态上传目录来自 `src/main/resources/static` 与 `static/`（见 `spring.resources.static-locations`）。

## 会话重点记录（本次）
- 系统名称统一改为“教育机构招生管理系统”，仅改名称不动功能字段。
- UI 文本“学校名称”改为“招生单位”，后端字段名与数据库结构未改。
- 页面入口：前台 `http://localhost:8080/springboot06idu/front/index.html`；后台 `http://localhost:8080/springboot06idu/admin/dist/index.html`。
- 编译后的 `admin/dist` 已同步更新；如未生效可尝试硬刷新。

## 会话记录维护
- 需要记录新的对话结论或变更时，请在对话中明确说明“写入 AGENTS.md”，我会追加到本节。
- 仅记录确认过的结论/改动，不写入敏感信息。
