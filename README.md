设置依赖
```bash
go mod init
```
安装Gin框架
```bash
go get github.com/gin-gonic/gin

```
启动Gin服务器
```bash
go run main.go
```

获取请求
**GET** `[http://127.0.0.1:8080/books](http://127.0.0.1:8080/books)` 获取所有书本信息
返回格式
```json
[
    {
        "id": "1",
        "title": "In Search of Lost Time",
        "author": "Marcel Proust",
        "quantity": 2
    },
    {
        "id": "2",
        "title": "The Great Gatsby",
        "author": "F. Scott Fitzgerald",
        "quantity": 5
    },
    {
        "id": "3",
        "title": "War and Peace",
        "author": "Leo Tolstoy",
        "quantity": 6
    }
]
```

**POST** `[http://127.0.0.1:8080/books](http://127.0.0.1:8080/books)` 添加书本
请求体
```json
{
  "id": "4",
  "title": "Hamlet",
  "author": "William Shakespeare",
  "quantity": 2
}
```
**GET** `[http://127.0.0.1:8080/books/2](http://127.0.0.1:8080/books/2)` 
返回格式
```json
{
    "id": "2",
    "title": "The Great Gatsby",
    "author": "F. Scott Fitzgerald",
    "quantity": 5
}
```
查询并不存在的数据

**GET**`http://127.0.0.1:8080/books/5`
返回格式
```json
{
    "message": "Book not found."
}
```

**PATCH** `[http://127.0.0.1:8080/checkout?id=2](http://127.0.0.1:8080/checkout?id=2)` 每次调用此API，书本数量减一
返回格式
```json
{
    "id": "2",
    "title": "The Great Gatsby",
    "author": "F. Scott Fitzgerald",
    "quantity": 3
}
```
数量小于等于0
```json
{
    "message": "Book not available."
}
```

**PATCH**`[http://127.0.0.1:8080/return?id=2](http://127.0.0.1:8080/return?id=2)` 增添书本数量
```json
{
    "id": "2",
    "title": "The Great Gatsby",
    "author": "F. Scott Fitzgerald",
    "quantity": 7
}
```
