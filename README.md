# MyBatis-Plus 学习路线

## 1. MyBatis-Plus 简介

- **MyBatis-Plus 是什么？**
  - MyBatis-Plus (MP) 是一个 MyBatis 的增强工具，在 MyBatis 的基础上只做增强不做改变，为简化开发、提高效率而生。
- **为什么使用 MyBatis-Plus？**
  - 极简开发：CRUD 操作只需继承 `BaseMapper` 即可拥有。
  - 无侵入：只做增强不做改变，引入它不会对现有项目造成任何影响。
  - 强大的功能：内置代码生成器、分页插件、逻辑删除、自动填充等。
- **核心特性**
  - `BaseMapper`：提供常用的 CRUD 方法。
  - 条件构造器：灵活构建 SQL 查询条件。
  - 代码生成器：快速生成常用代码。
  - 分页插件：轻松实现分页功能。
  - 逻辑删除：数据软删除。
  - 自动填充：创建时间、更新时间等自动填充。

## 2. 环境搭建

- **Maven/Gradle 依赖**
  - 在 `pom.xml` 或 `build.gradle` 中添加 MyBatis-Plus 和数据库驱动依赖。
- **Spring Boot 集成**
  - 在 Spring Boot 项目中配置数据源和 MyBatis-Plus。
- **数据库配置**
  - 配置 `application.yml` 或 `application.properties` 中的数据库连接信息。

## 3. 基本 CRUD 操作

- **`BaseMapper` 接口**
  - 创建 Mapper 接口并继承 `BaseMapper<T>`。
- **实体类定义**
  - 创建与数据库表对应的实体类，使用 `@TableName`、`@TableId` 等注解。
- **插入、删除、修改、查询**
  - 使用 `BaseMapper` 提供的 `insert()`, `deleteById()`, `updateById()`, `selectById()`, `selectList()` 等方法。

## 4. 条件构造器 (Wrapper)

- **`QueryWrapper` 和 `LambdaQueryWrapper`**
  - 学习两种条件构造器的使用场景和语法。
- **常用查询方法**
  - `eq`, `ne`, `gt`, `ge`, `lt`, `le` (等于、不等于、大于、大于等于、小于、小于等于)
  - `like`, `notLike`, `likeLeft`, `likeRight` (模糊查询)
  - `in`, `notIn` (in 查询)
  - `between`, `notBetween` (区间查询)
  - `isNull`, `isNotNull` (判空)
  - `or`, `and` (逻辑连接)
- **排序、分组、聚合**
  - `orderByAsc`, `orderByDesc`
  - `groupBy`
  - `select` (选择特定字段)

## 5. Service 层封装

- **`IService` 接口**
  - 创建 Service 接口并继承 `IService<T>`。
- **常用 Service 方法**
  - 使用 `IService` 提供的 `save()`, `removeById()`, `updateById()`, `getById()`, `list()` 等方法。

## 6. 代码生成器 (AutoGenerator)

- **配置数据源**
  - 配置 `AutoGenerator` 的数据源信息。
- **生成实体、Mapper、Service、Controller**
  - 根据需求配置生成策略，快速生成项目基础代码。

## 7. 分页插件

- **配置 `PaginationInnerInterceptor`**
  - 在 MyBatis-Plus 配置类中添加分页拦截器。
- **使用 `Page` 对象进行分页查询**
  - 通过 `IPage<T> page = new Page<>(current, size);` 创建分页对象，并传入 `selectPage()` 方法。

## 8. 逻辑删除

- **配置逻辑删除字段**
  - 在实体类中添加逻辑删除字段，并使用 `@TableLogic` 注解。
- **使用逻辑删除**
  - MyBatis-Plus 会自动处理逻辑删除字段，无需手动修改 SQL。

## 9. 枚举类型处理

- **`@EnumValue` 注解**
  - 在枚举类中使用 `@EnumValue` 标记数据库存储的值。
- **`IEnum` 接口**
  - 实现 `IEnum` 接口，自定义枚举值和描述。

## 10. 性能优化

- **批量操作**
  - `saveBatch()`, `updateBatchById()` 等批量方法。
- **二级缓存**
  - 了解 MyBatis 的二级缓存机制，并在 MyBatis-Plus 中配置使用。

## 11. 高级特性

- **乐观锁**
  - 使用 `@Version` 注解实现乐观锁，解决并发问题。
- **自动填充**
  - 实现 `MetaObjectHandler` 接口，自动填充创建时间、更新时间等字段。
- **多租户**
  - 配置多租户拦截器，实现数据隔离。
- **自定义 SQL**
  - 当 `BaseMapper` 和条件构造器无法满足需求时，使用 XML 或注解编写自定义 SQL。

## 12. 整合其他框架

- **Spring Security**
- **Redis**
- **Swagger/Knife4j**

## 13. 实战项目

- **构建一个简单的管理系统**
  - 将所学知识应用于实际项目，加深理解和掌握。
