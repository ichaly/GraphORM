# GraphORM

GraphORM 是一个基于 GraphQL 的 ORM 库，用于简化 Go 语言应用程序与 PostgreSQL 数据库之间的数据交互。它提供了一组工具来定义
GraphQL Schema 和 Resolvers，并自动生成 SQL 查询语句并执行。

## 特性

- **🚀基于 GraphQL 的 API**: 通过使用 GraphQL Schema 和 Resolvers，您可以轻松地将数据库操作公开为 GraphQL API。
- **🤖自动生成 SQL 查询语句**: GraphORM 根据 GraphQL 查询自动生成 SQL 查询语句，从而减少手动编写 SQL 查询语句的工作量。
- **🔍支持多种类型字段**: 除了可自动处理标量类型字段外，GraphORM 还支持对象类型、接口类型、输入对象类型等复杂类型字段。
- **🧬易于扩展**: GraphORM 允许您按自己的需求扩展 Resolvers 和查询功能。

## 安装

```bash
go get github.com/ichaly/GraphORM
```

## 使用指南

### 配置数据库连接：

```go
package main

import (
	"github.com/ichaly/graphorm"
)

func main() {
	// 初始化 GraphORM 配置信息
	graphorm.Config = &graphorm.Config{
		Host:     "localhost",
		Port:     5432,
		User:     "postgres",
		Password: "password",
		Database: "my_database",
	}
}
```

### 执行查询

```go
params := graphql.Params{
Schema:        schema,
RequestString: `{ product(id: 1) { id, name } }`,
}
result := graphorm.ExecuteQuery(params)
fmt.Println(result.Data)
```

## 贡献

欢迎您为 GraphORM 做出贡献！如果您发现任何问题或错误，请提交 Issue 或 Pull Request。我们非常感谢您的帮助，使 GraphORM 成为更好的
ORM 库。

## 许可证

GraphORM 基于 MIT 许可证发布。详情请参见 LICENSE 文件。