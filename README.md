# PMysql

> Java MySQL 操作工具类

## 开发信息

- 作者：欧阳鹏
- 开发日期：2022年12月14日
- 官网：https://apee.top

## 使用方式

1. 导入 `PMysql.jar`
2. `import` 引入

    ```java
    import top.apee.PMysql.PMysql;
    ```

## API 实例

- 连接到数据库

    ```java
    // 创建数据库操作对象
    PMysql pmysql = new PMysql();
    // 设置数据库密码
    pmysql.password = "12345678";
    // 设置数据库名称
    pmysql.database = "ponconsoft";
    // 连接到数据库
    pmysql.connect();
    ```

- 执行 SELECT 查询

    ```java
    ResultSet resultSet = pmysql.executeQuery("SELECT * FROM `my_table`");
    ```

- 游标移动

    ```java
    pmysql.resultNext(resultSet);
    ```

- 获取查询结果的内容
  - 获取一条

    ```java
    // 移动游标到下一条记录
    pmysql.resultNext(resultSet);
    // 字符串
    String string = (String) mysql.getValue(resultSet, "title");
    // 数字
    int age = (int) pmysql.getValue(resultSet, "age");
    ```

  - 获取所有

    ```java
    while (pmysql.result.next(resultSet)) {
        String string = (String) pmysql.getValue(resultSet, "title");
        System.out.println(string);
    }
    ```
