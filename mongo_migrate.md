# mongodb的数据迁移

* 备份数据

  * 工具mongodump
  * 定义`mongodump <options>`
  * 参数
    * -h 主机名（可IP可URL）
    * -d 数据库名
    * -o 备份目的地的目录地址
    * -c collection名（非必须）

* 恢复数据

  * 工具mongorestore

  * 定义`mongorestore <options> <directory or file to restore>`

  * 参数

    * -h 主机名（可IP可URL）
    * -d 数据库名（非必须）
    * -c collention名（非必须）

  * > 特殊的，若指定了-d 或者-c 选项。则必须在最后指定file而不是directory

* 例子

  * 备份

    ```bash
    mongodump -h 127.0.0.1 -d databasename -o /Users/ap010gi2e/Documents/mongodb_migrate -c collection
    ```

    > 将备份CasinoLady的数据到/Users/ap010gi2e/Documents/mongodb_migrate文件夹，并会自动建立一个-d选项所指定的名称的文件夹。

  * 恢复

    ```bash
    mongorestore -h ***.***.com /Users/ap010gi2e/Documents/mongodb_migrate
    ```

    或者

    ``` bash
    mongorestore -h ***.***.com -d bees -c CasinoLady /Users/ap010gi2e/Documents/mongodb_migrate/collection.bson
    ```

    > 差别在于是否指定了-d 或 -c 选项。

    ​
