

## PHP

### 简介

这些函数允许你通过不同的方式来使用和操作数组。数组是存储、管理和操作变量组的必不可少的工具。

PHP 支持简单数组和多维数组，数组可由用户自己创建也可以由其它函数创建。有很多特殊的数据库处理函数可以从数据库查询中返回数组以及一些返回数组的函数。

###  预定义常量

下列常量作为 PHP 核心的一部分总是可用的。

CASE_LOWER (integer)

> CASE_LOWER 用在 array_change_key_case() 中将数组的键名转换成小写字母。这也是 array_change_key_case() 的默认值。

CASE_UPPER (integer)

> CASE_UPPER 用在 array_change_key_case() 中将数组的键名转换成大写字母。
> 排序顺序标识：

SORT_ASC (integer)

> SORT_ASC 用在 array_multisort() 函数中，使其升序排列。

SORT_DESC (integer)

> SORT_DESC 用在 array_multisort() 函数中，使其降序排列。

- 排序类型标识：用于各种排序函数

SORT_REGULAR (integer)

> SORT_REGULAR 用于对对象进行通常比较。

SORT_NUMERIC (integer)

> SORT_NUMERIC 用于对对象进行数值比较。

SORT_STRING (integer)

> SORT_STRING 用于对对象进行字符串比较。

SORT_LOCALE_STRING (integer)

> SORT_LOCALE_STRING 基于当前区域来对对象进行字符串比较。PHP 4.4.0 和 5.0.2 新加。

COUNT_NORMAL (integer)

COUNT_RECURSIVE (integer)

EXTR_OVERWRITE (integer)

EXTR_SKIP (integer)

EXTR_PREFIX_SAME (integer)

EXTR_PREFIX_ALL (integer)

EXTR_PREFIX_INVALID (integer)

EXTR_PREFIX_IF_EXISTS (integer)

EXTR_IF_EXISTS (integer)

EXTR_REFS (integer)

###  对数组进行排序

PHP 有一些用来排序数组的函数

主要区别有：

- 有些函数基于 array 的键来排序， 而其他的基于值来排序的：$array['key'] = 'value';。
- 排序之后键和值之间的关联关系是否能够保持， 是指排序之后数组的键可能 会被重置为数字型的（0,1,2 ...）。
- 排序的顺序有：字母表顺序， 由低到高（升序）， 由高到低（降序），数字排序，自然排序，随机顺序或者用户自定义排序。
- 注意：下列的所有排序函数都是直接作用于数组本身， 而不是返回一个新的有序的数组。
- 以下函数对于数组中相等的元素，它们在排序后的顺序是未定义的。 （也即相等元素之间的顺序是不稳定的）。

| 函数名称          | 排序依据 | 数组索引健保持                   | 排序的顺序               | 相关函数      |
| ----------------- | -------- | -------------------------------- | ------------------------ | ------------- |
| array_multisort() | 值       | 键值关联的保持，数字类型的不保持 | 第一个数组或者由选项指定 | array_walk()  |
| asort()           | 值       | 是                               | 由低到高                 | arsort()      |
| arsort()          | 值       | 是                               | 由高到低                 | asort()       |
| krsort()          | 键       | 是                               | 由高到低                 | ksort()       |
| ksort()           | 键       | 是                               | 由低到高                 | asort()       |
| natcasesort()     | 值       | 是                               | 自然排序，大小写不敏感   | natsort()     |
| natsort()         | 值       | 是                               | 自然排序                 | natcasesort() |
| rsort()           | 值       | 否                               | 由高到低                 | sort()        |
| shuffle()         | 值       | 否                               | 随机                     | array_rand()  |
| sort()            | 值       | 否                               | 由低到高                 | rsort()       |
| uasort()          | 值       | 是                               | 由用户定义               | uksort()      |
| uksort()          | 键       | 是                               | 由用户定义               | uasort()      |
| usort()           | 值       | 否                               | 由用户定义               | uasort()      |

###  数组函数

array_change_key_case — 将数组中的所有键名修改为全大写或小写

array_chunk — 将一个数组分割成多个

array_column — 返回数组中指定的一列

array_combine — 创建一个数组，用一个数组的值作为其键名，另一个数组的值作为其值

array_count_values — 统计数组中所有的值

array_diff_assoc — 带索引检查计算数组的差集

array_diff_key — 使用键名比较计算数组的差集

array_diff_uassoc — 用用户提供的回调函数做索引检查来计算数组的差集

array_diff_ukey — 用回调函数对键名比较计算数组的差集

array_diff — 计算数组的差集

array_fill_keys — 使用指定的键和值填充数组

array_fill — 用给定的值填充数组

array_filter — 用回调函数过滤数组中的单元

array_flip — 交换数组中的键和值

array_intersect_assoc — 带索引检查计算数组的交集

array_intersect_key — 使用键名比较计算数组的交集

array_intersect_uassoc — 带索引检查计算数组的交集，用回调函数比较索引

array_intersect_ukey — 用回调函数比较键名来计算数组的交集

array_intersect — 计算数组的交集

array_key_exists — 检查数组里是否有指定的键名或索引

array_key_first — Gets the first key of an array

array_key_last — Gets the last key of an array

array_keys — 返回数组中部分的或所有的键名

array_map — 为数组的每个元素应用回调函数

array_merge_recursive — 递归地合并一个或多个数组

array_merge — 合并一个或多个数组

array_multisort — 对多个数组或多维数组进行排序

array_pad — 以指定长度将一个值填充进数组

array_pop — 弹出数组最后一个单元（出栈）

array_product — 计算数组中所有值的乘积

array_push — 将一个或多个单元压入数组的末尾（入栈）

array_rand — 从数组中随机取出一个或多个单元

array_reduce — 用回调函数迭代地将数组简化为单一的值

array_replace_recursive — 使用传递的数组递归替换第一个数组的元素

array_replace — 使用传递的数组替换第一个数组的元素

array_reverse — 返回单元顺序相反的数组

array_search — 在数组中搜索给定的值，如果成功则返回首个相应的键名

array_shift — 将数组开头的单元移出数组

array_slice — 从数组中取出一段

array_splice — 去掉数组中的某一部分并用其它值取代

array_sum — 对数组中所有值求和

array_udiff_assoc — 带索引检查计算数组的差集，用回调函数比较数据

array_udiff_uassoc — 带索引检查计算数组的差集，用回调函数比较数据和索引

array_udiff — 用回调函数比较数据来计算数组的差集

array_uintersect_assoc — 带索引检查计算数组的交集，用回调函数比较数据

array_uintersect_uassoc — 带索引检查计算数组的交集，用单独的回调函数比较数据和索引

array_uintersect — 计算数组的交集，用回调函数比较数据

array_unique — 移除数组中重复的值

array_unshift — 在数组开头插入一个或多个单元

array_values — 返回数组中所有的值

array_walk_recursive — 对数组中的每个成员递归地应用用户函数

array_walk — 使用用户自定义函数对数组中的每个元素做回调处理

array — 新建一个数组

arsort — 对数组进行逆向排序并保持索引关系

asort — 对数组进行排序并保持索引关系

compact — 建立一个数组，包括变量名和它们的值

count — 计算数组中的单元数目，或对象中的属性个数

current — 返回数组中的当前单元

each — 返回数组中当前的键／值对并将数组指针向前移动一步

end — 将数组的内部指针指向最后一个单元

extract — 从数组中将变量导入到当前的符号表

in_array — 检查数组中是否存在某个值

key_exists — 别名 array_key_exists

key — 从关联数组中取得键名

krsort — 对数组按照键名逆向排序

ksort — 对数组按照键名排序

list — 把数组中的值赋给一组变量

natcasesort — 用“自然排序”算法对数组进行不区分大小写字母的排序

natsort — 用“自然排序”算法对数组排序

next — 将数组中的内部指针向前移动一位

pos — current 的别名

prev — 将数组的内部指针倒回一位

range — 根据范围创建数组，包含指定的元素

reset — 将数组的内部指针指向第一个单元

rsort — 对数组逆向排序

shuffle — 打乱数组

sizeof — count 的别名

sort — 对数组排序

uasort — 使用用户自定义的比较函数对数组中的值进行排序并保持索引关联

uksort — 使用用户自定义的比较函数对数组中的键名进行排序

usort — 使用用户自定义的比较函数对数组中的值进行排序

### echo、print、print_r、var_dump 区别

> `echo`和`print`是语言结构、`print_r`和`var_dump`是普通函数

- echo：输出一个或多个字符串

- print：输出字符串

- print_r：打印关于变量的易于理解的信息

- var_dump：打印关于变量的易于理解的信息(带类型)

拓展阅读 [《echo、print、print_r、var_dump区别》](./03.echo、print、print_r、var_dump区别.md)

### 单引号和双引号的区别

双引号可以被分析器解析，单引号则不行

### isset 和 empty 的区别

isset：检测变量是否已设置并且非 NULL

empty：判断变量是否为空，变量为 0/false 也会被认为是空；变量不存在，不会产生警告

### static、self、$this 的区别

static：static 可以用于静态或非静态方法中，也可以访问类的静态属性、静态方法、常量和非静态方法，但不能访问非静态属性

self：可以用于访问类的静态属性、静态方法和常量，但 self 指向的是当前定义所在的类，这是 self 的限制

$this：指向的是实际调用时的对象，也就是说，实际运行过程中，谁调用了类的属性或方法，$this 指向的就是哪个对象。但 $this 不能访问类的静态属性和常量，且 $this 不能存在于静态方法中

### include、require、include_once、require_once 的区别

require 和 include 几乎完全一样，除了处理失败的方式不同之外。require 在出错时产生 E_COMPILE_ERROR 级别的错误。换句话说将导致脚本中止而 include 只产生警告（E_WARNING），脚本会继续运行

include_once 语句在脚本执行期间包含并运行指定文件。此行为和 include 语句类似，唯一区别是如果该文件中已经被包含过，则不会再次包含。如同此语句名字暗示的那样，只会包含一次

### 常见数组函数

array_count_values — 统计数组中所有的值

array_flip — 交换数组中的键和值

array_merge — 合并一个或多个数组

array_multisort — 对多个数组或多维数组进行排序

array_pad — 以指定长度将一个值填充进数组

array_pop — 弹出数组最后一个单元(出栈)

array_push — 将一个或多个单元压入数组的末尾(入栈)

array_rand — 从数组中随机(伪随机)取出一个或多个单元

array_keys — 返回数组中部分的或所有的键名

array_values — 返回数组中所有的值

count — 计算数组中的单元数目，或对象中的属性个数

sort — 对数组排序

### Cookie 和 Session

Cookie：PHP 透明的支持 HTTP cookie 。cookie 是一种远程浏览器端存储数据并以此来跟踪和识别用户的机制

Session：会话机制(Session)在 PHP 中用于保持用户连续访问Web应用时的相关数据

### 预定义变量





```text
$GLOBALS — 引用全局作用域中可用的全部变量
$_SERVER — 服务器和执行环境信息
$_GET — HTTP GET 变量
$_POST — HTTP POST 变量
$_FILES — HTTP 文件上传变量
$_REQUEST — HTTP Request 变量
$_SESSION — Session 变量
$_ENV — 环境变量
$_COOKIE — HTTP Cookies
$php_errormsg — 前一个错误信息
$HTTP_RAW_POST_DATA — 原生POST数据
$http_response_header — HTTP 响应头
$argc — 传递给脚本的参数数目
$argv — 传递给脚本的参数数组
```

- 超全局变量

PHP 中的许多预定义变量都是“超全局的”，这意味着它们在一个脚本的全部作用域中都可用。在函数或方法中无需执行 global $variable; 就可以访问它们

超全局变量：$GLOBALS、$\_SERVER、$\_GET、$\_POST、$\_FILES、$\_COOKIE、$\_SESSION、$\_REQUEST、$\_ENV

### 传值和传引用的区别

传值导致对象生成了一个拷贝，传引用则可以用两个变量指向同一个内容

### 构造函数和析构函数

构造函数：PHP 5 允行开发者在一个类中定义一个方法作为构造函数。具有构造函数的类会在每次创建新对象时先调用此方法，所以非常适合在使用对象之前做一些初始化工作

析构函数：PHP 5 引入了析构函数的概念，这类似于其它面向对象的语言，如 C++。析构函数会在到某个对象的所有引用都被删除或者当对象被显式销毁时执行

### 魔术方法

\_\_construct()， \_\_destruct()， \_\_call()， \_\_callStatic()， \_\_get()， \_\_set()， \_\_isset()， \_\_unset()， \_\_sleep()， \_\_wakeup()， \_\_toString()， \_\_invoke() 等方法在 PHP 中被称为"魔术方法"（Magic methods）

### public、protected、private、final 区别

对属性或方法的访问控制，是通过在前面添加关键字 public（公有），protected（受保护）或 private（私有）来实现的。被定义为公有的类成员可以在任何地方被访问

PHP 5 新增了一个 final 关键字。如果父类中的方法被声明为 final，则子类无法覆盖该方法。如果一个类被声明为 final，则不能被继承

### 客户端/服务端 IP 获取，了解代理透传 实际IP 的概念

客户端IP: $\_SERVER['REMOTE_ADDR']

服务端IP: $\_SERVER['SERVER_ADDR']

客户端IP(代理透传): $\_SERVER['HTTP_X_FORWARDED_FOR']

### 类的静态调用和实例化调用

- 占用内存

静态方法在内存中只有一份，无论调用多少次，都是共用的

实例化不一样，每一个实例化是一个对象，在内存中是多个的

- 不同点

静态调用不需要实例化即可调用

静态方法不能调用非静态属性，因为非静态属性需要实例化后，存放在对象里

静态方法可以调用非静态方法，使用 self 关键字。php 里，一个方法被 `self::` 后，自动转变为静态方法

调用类的静态函数时不会自动调用类的构造函数

### PHP 不实例化调用方法

静态调用、使用 PHP 反射方式

### php.ini 配置选项

- 配置选项

|名字|默认|备注|
|-|-|-|
|short_open_tag|"1"|是否开启缩写形式(`<? ?>`)|
|precision|"14"|浮点数中显示有效数字的位数|
|disable_functions|""|禁止某些函数|
|disable_classes|""|禁用某些类|
|expose_php|""|是否暴露 PHP 被安装在服务器上|
|max_execution_time|30|最大执行时间|
|memory_limit|128M|每个脚本执行的内存限制|
|error_reporting|NULL|设置错误报告的级别 `E_ALL` & ~`E_NOTICE` & ~`E_STRICT` & ~`E_DEPRECATED`|
|display_errors|"1"|显示错误|
|log_errors|"0"|设置是否将错误日志记录到 error_log 中|
|error_log|NULL|设置脚本错误将被记录到的文件|
|upload_max_filesize|"2M"|最大上传文件大小|
|post_max_size|"8M"|设置POST最大数据限制|

```shell
php -ini | grep short_open_tag //查看 php.ini 配置
```

- 动态设置

```php
ini_set(string $varname , string $newvalue);

ini_set('date.timezone', 'Asia/Shanghai'); //设置时区
ini_set('display_errors', '1'); //设置显示错误
ini_set('memory_limit', '256M'); //设置最大内存限制
```

### php-fpm.conf 配置

|名称|默认|备注|
|-|-|-|
|pid||PID文件的位置|
|error_log||错误日志的位置|
|log_level|notice|错误级别 alert:必须立即处理、error:错误情况、warning:警告情况、notice:一般重要信息、debug:调试信息|
|daemonize|yes|设置 FPM 在后台运行|
|listen|ip:port、port、/path/to/unix/socket|设置接受 FastCGI 请求的地址|
|pm|static、ondemand、dynamic|设置进程管理器如何管理子进程|
|request_slowlog_timeout|'0'|慢日志记录阀值|
|slowlog||慢请求的记录日志|

### 502、504 错误产生原因及解决方式

#### 502

502 表示网关错误，当 PHP-CGI 得到一个无效响应，网关就会输出这个错误

- `php.ini` 的 memory_limit 过小
- `php-fpm.conf` 中 max_children、max_requests 设置不合理
- `php-fpm.conf` 中 request_terminate_timeout、max_execution_time 设置不合理
- php-fpm 进程处理不过来，进程数不足、脚本存在性能问题

#### 504

504 表示网关超时，PHP-CGI 没有在指定时间响应请求，网关将输出这个错误

- Nginx+PHP 架构，可以调整 FastCGI 超时时间，fastcgi_connect_timeout、fastcgi_send_timeout、fastcgi_read_timeout

#### 500

php 代码问题，文件权限问题，资源问题

#### 503

超载或者停机维护

### 如何返回一个301重定向

```php
header('HTTP/1.1 301 Moved Permanently');
header('Location: https://blog.maplemark.cn');
```

### PHP 与 MySQL 连接方式

#### MySQL

```php
$conn = mysql_connect('127.0.0.1:3306', 'root', '123456');
if (!$conn) {
    die(mysql_error() . "\n");
}
mysql_query("SET NAMES 'utf8'");
$select_db = mysql_select_db('app');
if (!$select_db) {
    die(mysql_error() . "\n");
}
$sql = "SELECT * FROM `user` LIMIT 1";
$res = mysql_query($sql);
if (!$res) {
    die(mysql_error() . "\n");
}
while ($row = mysql_fetch_assoc($res)) {
    var_dump($row);
}
mysql_close($conn);
```

#### MySQLi

```php
$conn = @new mysqli('127.0.0.1:3306', 'root', '123456');
if ($conn->connect_errno) {
    die($conn->connect_error . "\n");
}
$conn->query("set names 'utf8';");
$select_db = $conn->select_db('user');
if (!$select_db) {
    die($conn->error . "\n");
}
$sql = "SELECT * FROM `user` LIMIT 1";
$res = $conn->query($sql);
if (!$res) {
    die($conn->error . "\n");
}
while ($row = $res->fetch_assoc()) {
    var_dump($row);
}
$res->free();
$conn->close();
```

#### PDO

```php
$pdo = new PDO('mysql:host=127.0.0.1:3306;dbname=user', 'root', '123456');
$pdo->exec("set names 'utf8'");
$sql = "SELECT * FROM `user` LIMIT 1";
$stmt = $pdo->prepare($sql);
$stmt->bindValue(1, 1, PDO::PARAM_STR);
$rs = $stmt->execute();
if ($rs) {
    while ($row = $stmt->fetch(PDO::FETCH_ASSOC)) {
        var_dump($row);
    }
}
$pdo = null;
```

### MySQL、MySQLi、PDO 区别

#### MySQL

- 允许 PHP 应用与 MySQL 数据库交互的早期扩展
- 提供了一个面向过程的接口，不支持后期的一些特性

#### MySQLi

- 面向对象接口
- prepared 语句支持
- 多语句执行支持
- 事务支持
- 增强的调试能力

#### PDO

- PHP 应用中的一个数据库抽象层规范
- PDO 提供一个统一的 API 接口，无须关心数据库类型
- 使用标准的 PDO API，可以快速无缝切换数据库

### 数据库持久连接

把 PHP 用作多进程 web 服务器的一个模块，这种方法目前只适用于 Apache。

对于一个多进程的服务器，其典型特征是有一个父进程和一组子进程协调运行，其中实际生成 web 页面的是子进程。每当客户端向父进程提出请求时，该请求会被传递给还没有被其它的客户端请求占用的子进程。这也就是说当相同的客户端第二次向服务端提出请求时，它将有可能被一个不同的子进程来处理。在开启了一个持久连接后，所有请求 SQL 服务的后继页面都能够重用这个已经建立的 SQL Server 连接。

### 代码执行过程

PHP 代码 => 启动 php 及 zend 引擎，加载注册拓展模块 => 对代码进行词法/语法分析 => 编译成opcode(opcache) => 执行 opcode

> PHP7 新增了抽象语法树(AST)，在语法分析阶段生成 AST，然后再生成 opcode 数组

### base64 编码原理

![base64](./assets/php-base64.png)

### ip2long 实现

![ip2long](./assets/php-ip2long.png)


```
124.205.30.150=2093817494

list($p1,$p2,$p3,$p4) = explode(',','124.205.30.150');

$realNum = $p1<<24+$p2<<16+$p3<<8+$p4;
```

### MVC 的理解

MVC 包括三类对象。模型 Model 是应用对象，视图 View 是它在屏幕上的表示，控制器 Controller 定义用户界面对用户输入的响应方式。不使用 MVC，用户界面设计往往将这些对象混在一起，而 MVC 则将它们分离以提高灵活性和复用性

### 主流 PHP 框架特点

#### Laravel

易于访问，功能强大，并提供大型，强大的应用程序所需的工具

- 简单快速的路由引擎
- 强大的依赖注入容器
- 富有表现力，直观的数据库 ORM
- 提供数据库迁移功能
- 灵活的任务调度器
- 实时事件广播

#### Symfony

- Database engine-independent
- Simple to use, in most cases, but still flexible enough to adapt to complex cases
- Based on the premise of convention over configuration--the developer needs to configure only the unconventional
- Compliant with most web best practices and design patterns
- Enterprise-ready--adaptable to existing information technology (IT) policies and architectures, and stable enough for long-term projects
- Very readable code, with phpDocumentor comments, for easy maintenance
- Easy to extend, allowing for integration with other vendor libraries

#### CodeIgniter

- 基于模型-视图-控制器的系统
- 框架比较轻量
- 全功能数据库类，支持多个平台
- Query Builder 数据库支持
- 表单和数据验证
- 安全性和 XSS 过滤
- 全页面缓存

#### ThinkPHP

- 采用容器统一管理对象
- 支持 Facade
- 更易用的路由
- 注解路由支持
- 路由跨域请求支持
- 验证类增强
- 配置和路由目录独立
- 取消系统常量
- 类库别名机制
- 模型和数据库增强
- 依赖注入完善
- 支持 PSR-3 日志规范
- 中间件支持
- 支持 Swoole/Workerman 运行

### 对象关系映射/ORM

#### 优点

- 缩短编码时间、减少甚至免除对 model 的编码，降低数据库学习成本
- 动态的数据表映射，在表结构发生改变时，减少代码修改
- 可以很方便的引入附加功能(cache 层)

#### 缺点

- 映射消耗性能、ORM 对象消耗内存
- SQL 语句较为复杂时，ORM 语法可读性不高(使用原生 SQL)

### 链式调用实现

类定义一个内置变量，让类中其他定义方法可访问到

### 异常处理

set_exception_handler — 设置用户自定义的异常处理函数

使用 try / catch 捕获


### 多进程同时写一个文件

加锁、队列

### PHP 进程模型，进程通讯方式，进程线程区别

消息队列、socket、信号量、共享内存、信号、管道

### PHP 支持回调的函数

array_map、array_filter、array_walk、usort

is_callable + callbacks + 匿名函数实现

### 发起 HTTP 请求有哪几种方式，它们有何区别

cURL、file_get_contents、fopen、fsockopen

### php for while foreach 迭代数组时候，哪个效率最高

### 弱类型变量如何实现

PHP 中声明的变量，在 zend 引擎中都是用结构体 zval 来保存，通过共同体实现弱类型变量声明

### PHP 拓展初始化


#### 编译安装

```shell
php编译安装
$ cd extname
$ phpize
$ ./configure
$ make
# make install
```

### 如何获取扩展安装路径

### 垃圾回收机制

引用计数器

### Trait

自 PHP 5.4.0 起，PHP 实现了一种代码复用的方法，称为 trait

### yield 是什么，说个使用场景 yield、yield 核心原理是什么

一个生成器函数看起来像一个普通的函数，不同的是普通函数返回一个值，而一个生成器可以yield生成许多它所需要的值

### traits 与 interfaces 区别 及 traits 解决了什么痛点

### 如何 foreach 迭代对象、如何数组化操作对象 $obj[key]、如何函数化对象 $obj(123);

### Swoole 适用场景，协程实现方式

那你知道swoole的进程模型

### PHP 数组底层实现 （HashTable + Linked list）

### Copy on write 原理，何时 GC

### 如何解决 PHP 内存溢出问题

### ZVAL

### HashTable

### PHP7 新特性

标量类型声明、返回值类型声明、通过 define() 定义常量数组、匿名类、相同命名空间类一次性导入

### PHP7 底层优化

ZVAL 结构体优化，占用由24字节降低为16字节

内部类型 zend_string，结构体成员变量采用 char 数组，不是用 char*

PHP 数组实现由 hashtable 变为 zend array

函数调用机制，改进函数调用机制，通过优化参数传递环节，减少了一些指令

### PSR 介绍，PSR-1, 2, 4, 7

### Xhprof 、Xdebug 性能调试工具使用

### 字符串、数字比较大小的原理，注意 0 开头的8进制、0x 开头16进制

### BOM 头是什么，怎么除去

### 模板引擎是什么，解决什么问题、实现原理（Smarty、Twig、Blade）

##  PHP 反射详解

面向对象编程中对象被赋予了自省的能力，而这个自省的过程就是反射。
反射，直观理解就是根据到达地找到出发地和来源。比如，一个光秃秃的对象，我们可以仅仅通过这个对象就能知道它所属的类、拥有哪些方法。
反射是指在PHP运行状态中，扩展分析PHP程序，导出或提出关于类、方法、属性、参数等的详细信息，包括注释。这种动态获取信息以及动态调用对象方法的功能称为反射API。
如何使用反射API

###  如何使用反射 API

```php
class person
{
	public $name;
	public $gender;
	public function say(){
		echo $this->name," \tis ",$this->gender,"\r\n";
	}
	public function set($name, $value)
	{
		echo "Setting $name to $value \r\n";
		$this->$name= $value;
	}
	public function get($name)
	{
		if(!isset($this->$name)){
			echo '未设置';　
			$this->$name="正在为你设置默认值";
		}
  		return $this->$name;
	}
}
$student = new person();
$student->name = 'Tom';
$student->gender = 'male';
$student->age = 24;
```

现在，要获取这个student对象的方法和属性列表该怎么做呢？

```php
// 获取对象属性列表
$reflect = new ReflectionObject($student);
$props　= $reflect->getProperties();
foreach ($props as $prop) {
	print $prop->getName() ."\n";
}
// 获取对象方法列表
$m = $reflect->getMethods();
foreach ($m as $prop) {
	print $prop->getName() ."\n";
}
```

也可以不用反射API，使用class函数，返回对象属性的关联数组以及更多的信息：

```php
// 返回对象属性的关联数组
var_dump(get_object_vars($student));
// 类属性
var_dump(get_class_vars(get_class($student)));
// 返回由类的方法名组成的数组
var_dump(get_class_methods(get_class($student)));
```

假如这个对象是从其他页面传过来的，怎么知道它属于哪个类呢？

```php
// 获取对象属性列表所属的类
echo get_class($student);
```

反射API的功能显然更强大，甚至能还原这个类的原型，包括方法的访问权限等

```php
// 反射获取类的原型
$obj = new ReflectionClass('person');
$className = $obj->getName();
$Methods = $Properties = array();
foreach($obj->getProperties() as $v)
{
	$Properties[$v->getName()] = $v;
}
foreach($obj->getMethods() as $v)　　
{
	$Methods[$v->getName()] = $v;
}
echo "class {$className}\n{\n";
is_array($Properties) && ksort($Properties);
foreach($Properties as $k => $v)
{
	echo "\t";
	echo $v->isPublic() ? ' public' : '',$v->isPrivate() ? ' private' : '',
	$v->isProtected() ? ' protected' : '',
	$v->isStatic() ? ' static' : '';
	echo "\t{$k}\n";
}
echo "\n";
if(is_array($Methods)) ksort($Methods);
foreach($Methods as $k => $v)
{
	echo "\tfunction {$k}(){}\n";
}
echo "}\n";
```

输出如下

```php
class person
{
	public gender
	public name
	function get(){}
	function set(){}
	function say(){}
}
```

不仅如此，PHP手册中关于反射API更是有几十个，可以说，反射完整地描述了一个类或者对象的原型。反射不仅可以用于类和对象，还可以用于函数、扩展模块、异常等

###  反射有什么作用

反射可以用于文档生成。因此可以用它对文件里的类进行扫描，逐个生成描述文档。
既然反射可以探知类的内部结构，那么是不是可以用它做hook实现插件功能呢？或者是做动态代理呢？

```php
class mysql
{
	function connect($db) {
		echo "连接到数据库${db[0]}\r\n";
	}
}
class sqlproxy
{
	private $target;  
	function construct($tar) { 
		$this->target[] = new $tar();
	}
	function call($name, $args) {
		foreach ($this->target as $obj) {
			$r = new ReflectionClass($obj);
			if ($method = $r->getMethod($name)) {
				if ($method->isPublic() && !$method->isAbstract()) {
					echo "方法前拦截记录LOG\r\n";
					$method->invoke($obj, $args);
					echo "方法后拦截\r\n";
				}
			}
		}
	}
}
$obj = new sqlproxy('mysql');
$obj->connect('member');
```

在平常开发中，用到反射的地方不多：一个是对对象进行调试，另一个是获取类的信息。在MVC和插件开发中，使用反射很常见，但是反射的消耗也很大，在可以找到替代方案的情况下，就不要滥用。

PHP有Token函数，可以通过这个机制实现一些反射功能。从简单灵活的角度讲，使用已经提供的反射API是可取的。

很多时候，善用反射能保持代码的优雅和简洁，但反射也会破坏类的封装性，因为反射可以使本不应该暴露的方法或属性被强制暴露了出来，这既是优点也是缺点。



2.MyISAM索引与InnoDB索引的区别？
InnoDB索引是聚簇索引，MyISAM索引是非聚簇索引。
InnoDB的主键索引的叶子节点存储着行数据，因此主键索引非常高效。
MyISAM索引的叶子节点存储的是行数据地址，需要再寻址一次才能得到数据。
InnoDB非主键索引的叶子节点存储的是主键和其他带索引的列数据，因此查询时做到覆盖索引会非常高效。

聚簇索引：将数据存储与索引放到了一块，找到索引也就找到了数据
非聚簇索引：将数据存储于索引分开结构，索引结构的叶子节点指向了数据的对应行，myisam通过key_buffer把索引先缓存到内存中，当需要访问数据时（通过索引访问数据），在内存中直接搜索索引，然后通过索引找到磁盘相应数据，这也就是为什么索引不在key buffer命中时，速度慢的原因

3.索引的优缺点
索引的优点
可以大大加快数据的检索速度，这也是创建索引的最主要的原因。
通过使用索引，可以在查询的过程中，使用优化隐藏器，提高系统的性能。
索引的缺点
时间方面：创建索引和维护索引要耗费时间，具体地，当对表中的数据进行增加、删除和修改的时候，索引也要动态的维护，会降低增/改/删的执行效率；
空间方面：索引需要占物理空间。

4.最左前缀匹配原则，非常重要的原则，mysql会一直向右匹配直到遇到范围查询(>、<、between、like)就停止匹配，比如a = 1 and b = 2 and c > 3 and d = 4 如果建立(a,b,c,d)顺序的索引，d是用不到索引的，如果建立(a,b,d,c)的索引则都可以用到，a,b,d的顺序可以任意调整。

```
- 表级锁：开销小，加锁快，不会出现死锁。锁定粒度大，发生锁冲突的概率最高，并发量最低

- 行级锁：开销大，加锁慢，会出现死锁。锁力度小，发生锁冲突的概率小，并发度最高
```


#### 超全局变量

超全局变量 — 超全局变量是在全部作用域中始终可用的内置变量

```http
$_GET ----->get传送方式
$POST ----->post传送方式
$REQUEST ----->可以接收到get和post两种方式的值
$GLOBALS ----->所有的变量都放在里面
$FILE ----->上传文件使用
$SERVER ----->系统环境变量
$SESSION ----->会话控制的时候会用到
$COOKIE ----->会话控制的时候会用到
```

### http

```
HTTP中POST、GET、PUT、DELETE方式的区别?

    HTTP定义了与服务器交互的不同的方法，最基本的是POST、GET、PUT、DELETE，与其比不可少的URL的全称是资源描述符，我们可以这样理解：url描述了一个网络上资源，而post、get、put、delete就是对这个资源进行增、删、改、查的操作！

表单中get和post提交方式的区别?

	get是把参数数据队列加到提交表单的action属性所指的url中，值和表单内各个字段一一对应，从url中可以看到；post是通过HTTPPOST机制，将表单内各个字段与其内容防止在HTML的head中一起传送到action属性所指的url地址，用户看不到这个过程
	对于get方式，服务器端用Request.QueryString获取变量的值，对于post方式，服务器端用Request.Form获取提交的数据
	get传送的数据量较小，post传送的数据量较大，一般被默认不受限制，但在理论上，IIS4中最大量为80kb，IIS5中为1000k，
	get安全性非常低，post安全性较高
	
常见的HTTP状态码：
200 : 请求成功，请求的数据随之返回。
301 : 永久性重定向。
302 : 暂时行重定向。
401 : 当前请求需要用户验证。
403 : 服务器拒绝执行请求，即没有权限。
404 : 请求失败，请求的数据在服务器上未发现。
500 : 服务器错误。一般服务器端程序执行错误。
503 : 服务器临时维护或过载。这个状态时临时性的。

HTTP状态码分类:
1** - 信息，服务器收到的请求，需要请求者继续执行操作
2** - 成功，操作被成功接收并处理
3** - 重定向，需要进一步的操作以完成请求
4** - 客户端错误，请求包含语法错误或者无法完成请求
5** 服务器错误，服务器在处理请求的过程	
	
```

#### php
```
CGI 、FAST_CGI 、PHP_FPM
```

```
了解XSS攻击吗？如何防止？

XSS是跨站脚本攻击，首先是利用跨站脚本漏洞以一个特权模式去执行攻击者构造的脚本，然后利用不安全的Activex控件执行恶意的行为。
使用htmlspecialchars()函数对提交的内容进行过滤，使字符串里面的特殊符号实体化。

SQL注入漏洞产生的原因？如何防止？

SQL注入产生的原因：程序开发过程中不注意规范书写sql语句和对特殊字符进行过滤，导致客户端可以通过全局变量POST和GET提交一些sql语句正常执行。
防止SQL注入的方式：
开启配置文件中的magic_quotes_gpc 和 magic_quotes_runtime设置
执行sql语句时使用addslashes进行sql语句转换
Sql语句书写尽量不要省略双引号和单引号。
过滤掉sql语句中的一些关键词：update、insert、delete、select、 * 。
提高数据库表和字段的命名技巧，对一些重要的字段根据程序的特点命名，取不易被猜到的。
Php配置文件中设置register_globals为off,关闭全局变量注册
控制错误信息，不要在浏览器上输出错误信息，将错误信息写到日志文件中。

PHP网站的主要攻击方式有哪些？

命令注入(Command Injection)
eval 注入(Eval Injection)
客户端脚本攻击(Script Insertion)
跨网站脚本攻击(Cross Site Scripting, XSS)
SQL 注入攻击(SQL injection)
跨网站请求伪造攻击(Cross Site Request
Forgeries, CSRF)
Session 会话劫持(Session Hijacking)
Session 固定攻击(Session Fixation)
HTTP 响应拆分攻击(HTTP Response Splitting)
文件上传漏洞(File Upload Attack)
目录穿越漏洞(Directory Traversal)
远程文件包含攻击(Remote Inclusion)
动态函数注入攻击(Dynamic Variable
Evaluation)
URL 攻击(URL attack)
表单提交欺骗攻击(Spoofed Form
Submissions)
HTTP 请求欺骗攻击(Spoofed HTTP Requests)
```

#### PHP数组
```
一、数组操作的基本函数

1 array_values($arr);       //获得数组的值
2 array_keys($arr);         //获得数组的键名
3 array_flip($arr);         //数组中的值与键名互换（如果有重复前面的会被后面的覆盖）
4 array_search('PHP',$arr); //检索给定的值，加true则是严格类型检查
5 array_reverse($arr);      //将数组中的元素翻转
6 in_array("apple", $arr);  //在数组中检索apple
7 array_key_exists("apple", $arr); // 检索给定的键名是否存在数组中
8 array_count_values($arr);        // 统计数组中所有值出现的次数
二、数组的分段和填充

1 array_slice($arr, 0, 3);    //将数组中的一段取出，此函数忽略键名（数组的分段）
2 array_splice($arr, 0, 3，array("black","maroon"));    //将数组中的一段取出，返回的序列从原数组中删除
3 array_chunk($arr, 3, TRUE);   //将一个数组分割成多个，TRUE为保留原数组的键名（分割多个数组）
四、数组与栈，列队

1 array_push($arr, "apple", "pear");    //将一个或多个元素压入数组栈的末尾（入栈），返回入栈元素的个数
2 array_pop($arr);    // 将数组栈的最后一个元素弹出（出栈）
3 array_shift($arr);   //数组中第一个元素移出并返回（长度减1，其他元素向前移动一位，数字键名改为从零计数，文字键名不变）
4 array_unshift($arr,"a",array(1,2));  //在数组的开头插入一个或多个元素
六、数组的排序

1 sort($arr);       //由小到大，忽略键名       
2 rsort($arr);      //由大到小，忽略键名
3 asort($arr);     //由小到大，保留键名       
4 arsort($arr);    // 由大到小，保留键名
5 ksort($arr);     //按照键名正序排序           
6 krsort($arr);   // 按照键名逆序排序
七、数组的计算

1 array_sum($arr);   //对数组内部的所有元素做求和运算（数组元素的求和）
2 array_merge($arr1, $arr2); //合并两个或多个（相同字符串键名，后面覆盖前面，相同的数字键名，后面的附加到后面）
3  
4 array_diff($arr1, $arr2);           //返回差集结果数组   array_diff_assoc($arr1, $arr2, $arr3);  //返回差集结果数组，键名也做比较
5 array_intersect($arr1, $arr2);  //返回交集结果数组    array_intersect_assoc($arr1, $arr2);   //返回交集结果数组，键名也做比较 
八、其他的数组函数

1 array_unique($arr);   //移除数组中重复的值，新的数组中会保留原始的键名
2 shuffle($arr);  
```

#### 面向对象
```
权限修饰符 private protected public
子类继承抽象类使用 extends，子类实现接口使用 implements。
静态方法 static
```
#### 一些编译php时的configure 参数
```
./configure  
–prefix=/usr/local/php                      php 安装目录  
–with-apxs2=/usr/local/apache/bin/apxs  
–with-config-file-path=/usr/local/php/etc      指定php.ini位置  
–with-mysql=/usr/local/mysql           mysql安装目录，对mysql的支持  
–with-mysqli=/usr/local/mysql/bin/mysql_config    mysqli文件目录,优化支持  
–enable-safe-mode                              打开安全模式  
–enable-ftp                                 打开ftp的支持  
–enable-zip                                 打开对zip的支持  
–with-bz2                    打开对bz2文件的支持  
–with-jpeg-dir                                 打开对jpeg图片的支持  
–with-png-dir                                 打开对png图片的支持  
–with-freetype-dir              打开对freetype字体库的支持  
–without-iconv                关闭iconv函数，种字符集间的转换  
–with-libxml-dir                 打开libxml2库的支持  
–with-xmlrpc              打开xml-rpc的c语言  
–with-zlib-dir                                 打开zlib库的支持  
–with-gd                                    打开gd库的支持  
–enable-gd-native-ttf               支持TrueType字符串函数库  
–with-curl                      打开curl浏览工具的支持  
–with-curlwrappers                 运用curl工具打开url流  
–with-ttf                      打开freetype1.*的支持，可以不加了  
–with-xsl            打开XSLT 文件支持，扩展了libxml2库 ，需要libxslt软件  
–with-gettext                      打开gnu 的gettext 支持，编码库用到  
–with-pear            打开pear命令的支持，php扩展用的  
–enable-calendar             打开日历扩展功能  
–enable-mbstring                  多字节，字符串的支持  
–enable-bcmath                  打开图片大小调整,用到zabbix监控的时候用到了这个模块  
–enable-sockets                  打开 sockets 支持  
–enable-exif                      图片的元数据支持  
–enable-magic-quotes               魔术引用的支持  
–disable-rpath                     关闭额外的运行库文件  
–disable-debug                  关闭调试模式  
–with-mime-magic=/usr/share/file/magic.mime      魔术头文件位置  
cgi方式安装才用的参数  
–enable-fpm                     打上php-fpm 补丁后才有这个参数，cgi方式安装的启动程序  
–enable-fastcgi                  支持fastcgi方式启动php  
–enable-force-cgi-redirect             同上 ,帮助里没有解释  
–with-ncurses                     支持ncurses 屏幕绘制以及基于文本终端的图形互动功能的动态库  
–enable-pcntl           freeTDS需要用到的，可能是链接mssql 才用到  
mhash和mcrypt算法的扩展  
–with-mcrypt                     算法  
–with-mhash                     算法  
–with-gmp  
–enable-inline-optimization  
–with-openssl           openssl的支持，加密传输时用到的  
–enable-dbase  
–with-pcre-dir=/usr/local/bin/pcre-config    perl的正则库案安装位置  
–disable-dmalloc  
–with-gdbm                    dba的gdbm支持  
–enable-sigchild  
–enable-sysvsem  
–enable-sysvshm  
–enable-zend-multibyte              支持zend的多字节  
–enable-mbregex  
–enable-wddx  
–enable-shmop  
–enable-soap  
PHP配置选项完整列表  
数据库选项  
–with-dbplus  
包括 dbplus 的支持。  
–with-adabas[=DIR]  
包括 Adabas D 的支持。DIR 是 Adabas 的基本安装目录，默认为 /usr/local。  
–with-sapdb[=DIR]  
包括 SAP DB 的支持。DIR 是 SAP DB 的基本安装目录，默认为 /usr/local。  
–with-solid[=DIR]  
包括 Solid 的支持。DIR 是 Solid 的基本安装目录，默认为 /usr/local/solid。  
–with-ibm-db2[=DIR]  
包括 IBM DB2 的支持。DIR 是 DB2 的基本安装目录，默认为 /home/db2inst1/sqllib。  
–with-empress[=DIR]  
包括 Empress 的支持。DIR 是 Empress 的基本安装目录，默认为 $EMPRESSPATH。自 PHP4 起，本选项仅支持 Empress 8.60 及以上版本。  
–with-empress-bcs[=DIR]  
包括 Empress Local Access 的支持。DIR 是 Empress 的基本安装目录，默认为 $EMPRESSPATH。自 PHP4 起，本选项仅支持 Empress 8.60 及以上版本。  
–with-birdstep[=DIR]  
包括 Birdstep 的支持。DIR 是 Birdstep 的基本安装目录，默认为 /usr/local/birdstep。  
–with-custom-odbc[=DIR]  
包 括用户自定义 ODBC 的支持。DIR 是 ODBC 的基本安装目录，默认为 /usr/local。要确认定义了 CUSTOM_ODBC_LIBS 并且在 include 目录中有某个 odbc.h。例如，对于 QNX 下的 Sybase SQL Anywhere 5.5.00，在运行 configure 脚本之前应该先定义以下环境变量： CPPFLAGS=”-DODBC_QNX -DSQLANY_BUG” LDFLAGS=-lunix CUSTOM_ODBC_LIBS=”-ldblib -lodbc”.  
–with-iodbc[=DIR]  
包括 iODBC 的支持。DIR 是 iODBC 的基本安装目录，默认为 /usr/local。  
–with-esoob[=DIR]  
包括 Easysoft OOB 的支持。DIR 是 OOB 的基本安装目录，默认为 /usr/local/easysoft/oob/client。  
–with-unixODBC[=DIR]  
包括 unixODBC 的支持。DIR 是 unixODBC 的基本安装目录，默认为 /usr/local。  
–with-openlink[=DIR]  
包括 OpenLink ODBC 的支持。DIR 是 OpenLink 的基本安装目录，默认为 /usr/local。这和 iODBC 一样。  
–with-dbmaker[=DIR]  
包括 DBMaker 的支持。DIR 是 DBMaker 的基本安装目录，默认为最新版 DBMaker 安装的目录（例如 /home/dbmaker/3.6）。  
–disable-unified-odbc  
取消对 unified ODBC 的支持。仅适用于激活了 iODBC，Adabas，Solid，Velocis 或用户自定义 ODBC 界面。仅能用于 PHP 3！  
图像选项  
–without-gd  
禁用 GD 支持。仅用于 PHP 3！  
–with-imagick  
Imagick 扩展被移到 PEAR 中的 PECL 中去了，可以在这里找到。PHP 4 中的安装指示可以在 PEAR 站点中找到。  
只用 –with-imagick 仅在 PHP 3 中支持，除非依照 PEAR 站点的指示去做。  
–with-ming[=DIR]  
包括 ming 支持。  
杂类选项  
–enable-force-cgi-redirect  
激活服务器内部重定向的安全检查。如果是在 Apache 中以 CGI 方式使用 PHP 则应该使用此选项。  
–enable-discard-path  
使用此选项可以使 PHP 的 CGI 可执行程序安全地放置在 web 目录树以外的地方，并且别人也不能绕过 .htaccess 的安全设置。  
–with-fastcgi  
将 PHP 编译成 FastCGI 应用程序。  
–enable-debug  
编译时加入调试符号。  
–with-layout=TYPE  
设置安装后的文件布局。TYPE 可以是 PHP（默认值）或者 GNU。  
–with-pear=DIR  
将 PEAR 安装在 DIR 目录中（默认为 PREFIX/lib/php）。  
–without-pear  
不安装 PEAR。  
–enable-sigchild  
激活 PHP 自己的 SIGCHLD 句柄。  
–disable-rpath  
禁止传递附加的运行时库搜索路径。  
–enable-libgcc  
激活显式 libgcc 连接。  
–enable-php-streams  
包含试验的 PHP 流。除非是测试源代码，否则不要使用！  
–with-zlib-dir=<DIR>;  
定义 zlib 的安装路径。  
–with-aspell[=DIR]  
包含 ASPELL 支持。  
–with-ccvs[=DIR]  
包含 CCVS 支持。  
–with-cybercash[=DIR]  
包含 CyberCash 支持。DIR 是 CyberCash MCK 的安装目录。  
–with-icap[=DIR]  
包含 ICAP 支持。  
–with-ircg-config  
ircg-config 脚本的路径。  
–with-ircg  
包含 ircg 支持。  
–enable-mailparse  
包含 mailparse 支持。  
–with-muscat[=DIR]  
包含 muscat 支持。  
–with-satellite[=DIR]  
激活通过 Satellite（试验性质）的 CORBA 支持。DIR 是 ORBit 的主目录。  
–enable-trans-sid  
激活透明的 session id 传播。  
–with-regex[=TYPE]  
使用系统 regex 库（不赞成）。  
–with-vpopmail[=DIR]  
包含 vpopmail 支持。  
–with-tsrm-pthreads  
使用 POSIX 线程（默认值）。  
–enable-shared[=PKGS]  
编译共享库 [default=yes]。  
–enable-static[=PKGS]  
编译静态库 [default=yes]。  
–enable-fast-install[=PKGS]  
为快速安装而优化 [default=yes]。  
–with-gnu-ld  
假定 C 编译器使用 GNU ld [default=no]。  
–disable-libtool-lock  
避免锁死（可能会破坏并行编译）。  
–with-pic  
尝试只使用 PIC/non-PIC 对象 [default=use both]。  
–enable-memory-limit  
编译时加入内存限制支持。  
–disable-url-fopen-wrapper  
禁止通过 URL 的 fopen wrapper，不能通过 HTTP 或 FTP 访问文件。  
–enable-versioning  
仅输出所需要的符号。更多信息见 INSTALL 文件。  
–with-imsp[=DIR]  
包含 IMSp 支持（DIR 是 IMSP 的 include 目录和 libimsp.a 目录）。仅用于 PHP 3！  
–with-mck[=DIR]  
包含 Cybercash MCK 支持。DIR 是 cybercash mck 编译目录，默认为 /usr/src/mck-3.2.0.3-linux。帮助见 extra/cyberlib。仅用于 PHP 3！  
–with-mod-dav=DIR  
包含通过 Apache 的 mod_dav 的 DAV 支持。DIR 是 mod_dav 的安装目录（仅用于 Apache 模块版本！）仅用于 PHP 3！  
–enable-debugger  
编译入远程调试函数。仅用于 PHP 3！  
–enable-versioning  
利用 Solaris 2.x 和 Linux 提供的版本控制与作用范围的优势。仅用于 PHP 3！  
PHP 选项  
–enable-maintainer-mode  
激活将编译规则和未使用的（以及一些混淆的）依赖文件放入临时安装中。  
–with-config-file-path=PATH  
设定 php.ini 所在的路径，默认为 PREFIX/lib。  
–enable-safe-mode  
默认激活安全模式。  
–with-exec-dir[=DIR]  
安全模式下只允许此目录下执行程序。默认为 /usr/local/php/bin。  
–enable-magic-quotes  
默认激活 magic quotes。  
–disable-short-tags  
默认禁止简写的 PHP 开始标记 <?。  
服务器选项  
–with-aolserver=DIR  
指定已安装的 AOLserver 的路径。  
–with-apxs[=FILE]  
编译共享 Apache 模块。FILE 是可选的 Apache 的 apxs 工具的路径，默认为 apxs。确保指定的 apxs 版本是安装后的文件而不是 Apache 源程序中包中的。  
–with-apache[=DIR]  
编译 Apache 模块。DIR 是 Apache 源程序的最高一级目录。默认为 /usr/local/apache。  
–with-mod_charset  
激活 mod_charset 中的传递表（Apache 中）。  
–with-apxs2[=FILE]  
编译共享的 Apache 2.0 模块。FILE 是可选的 Apache 的 apxs 工具的路径，默认为 apxs。  
–with-fhttpd[=DIR]  
编译 fhttpd 模块。DIR 是 fhttpd 的源代码路径，默认为 /usr/local/src/fhttpd。  
–with-isapi=DIR  
将 PHP 编译为 ISAPI 模块用于 Zeus。  
–with-nsapi=DIR  
指定已安装的 Netscape 服务器路径。  
–with-phttpd=DIR  
暂无信息。  
–with-pi3web=DIR  
将 PHP 编译为用于 Pi3Web 的模块。  
–with-roxen=DIR  
将 PHP 编译为一个 Pike 模块。DIR 是 Roxen 的根目录，通常为 /usr/local/roxen/server。  
–enable-roxen-zts  
编译 Roxen 模块，使用 Zend Thread Safety。  
–with-servlet[=DIR]  
包含 servlet 支持。DIR 是 JSDK 的基本安装目录。本 SAPI 需要 java 扩展必须被编译为共享的 dl。  
–with-thttpd=SRCDIR  
将 PHP 编译为 thttpd 模块。  
–with-tux=MODULEDIR  
```





1.看看简历，会问一些过去做的项目的用户量、pv、吞吐量、相关难点和解决方法等
2.数据库设计经验,为什么进行分表? 分库?
一般多少数据量开始分表? 分库? 分库分表的目的? 什么是数据库垂直拆分? 水平拆分? 分区等等？可以举例说明
3.数据库优化有哪些? 分别需要注意什么?
4.web开发方面会遇到哪些缓存? 分别如何优化?
5.给你256M的内存,对10G的文件进行排序(文件每行1个数字),如何实现？
  对10G的文件进行查找如何实现？
  统计10G文件每个关键字出现的次数如何实现？
6.假如你现在是12306火车订票的设计师,你该如何设计满足全国人民订票?
7.假如有1亿用户的访问量,你的服务器架构是怎样的? 用户信息的存储方案如何设计?
8.如果你是技术组长,所带团队任务进度无法完成你该如何解决?
  如果在进度排满的前提下插入任务,你该如何保证总进度不延期?
  如果有的工程师今天预定任务没有完成,你该如何解决?
9.从你的经验方面谈一下如何构建高性能web站点? 需要哪些环节? 步骤? 每个步骤需要注意什么如何优化等?

10. 为什么要对数据库进行主从分离?
11. 如何处理多服务器共享session?
12. 一个10G的表,你用php程序统计某个字段出现的次数,思路是?
13. 会告诉你一个nginx日志例子,用你认为最佳的编程语言统计一下http响应时间超过1秒的前10个url?
14. 给你一个mysql配置文件,用你认为最佳的编程语言解析该文件?
15. 给你两个路径a和b,写一个算法或思路计算a和b差距几层并显示a和b的交集?
16. 给你一个url,在nginx配置一下rewrite指定到某个具体路径?
17. 一个php文件的解释过程是? 一般加速php有哪些? 提高php整体性能会用到哪些技术?
18. session和cookie生存周期区别? 存储位置区别?
19. require、include、require_once、include_once区别? 加载区别? 如果程序按需加载某个php文件你如何实现?

include() 将会产生一个警告，不影响后续程序的执行。require() 将会产生一个致命错误，后续程序停止执行。
require () 和 require_once () 执行同样的任务，除了第二个函数在执行前检查 PHP 脚本是否已经包含。

20. chrome号称为多线程的,所以多线程和多进程的区别为?
21. php在2011年底出现hash碰撞,hash碰撞原理为? 如何进行修复?
22. web不安全因素有哪些? 分别如何防范?
sql注入
xss攻击  
csrf攻击


php5与php7之间的区别：

1、性能提升：PHP7比PHP5.0性能提升了两倍。

2、以前的许多致命错误，现在改成抛出异常。

3、PHP 7.0比PHP5.0移除了一些老的不在支持的SAPI（服务器端应用编程端口）和扩展。

4、PHP 7.0比PHP5.0新增了空接合操作符。

5、PHP 7.0比PHP5.0新增加了结合比较运算符。

6、PHP 7.0比PHP5.0新增加了函数的返回类型声明。

7、PHP 7.0比PHP5.0新增加了标量类型声明。

8、PHP 7.0比PHP5.0新增加匿名类。

9、错误处理和64位支持


1.变量存储字节减小，减少内存占用，提升变量操作速度

2、改善数组结构，数组元素和hash映射表被分配在同一块内存里，降低了内存占用、提升了 cpu 缓存命中率

3、改进了函数的调用机制，通过优化参数传递的环节，减少了一些指令，提高执行效率




23. 假如两个单链表相交,写一个最优算法计算交点位置,说思路也可以?
24. 假如你是技术组长? 如何提高团队效率?
25. nginx负载均衡有哪些? 如果其中一台服务器挂掉,报警机制如何实现?
26. 不优化前提下,apache一般最大连接数为? nginx一般最大连接数为? mysql 每秒insert ? select ? update ? delete?
27. mysql 数据类型有哪些 ? 分别占用多少存储空间 ?
28. nginx设置缓存js、css、图片等信息,缓存的实现原理是?
29. 如何提高缓存命中率? 如何对缓存进行颗粒化?
30. php的内存回收机制是?
31. 我的所有问题都问完了,你有什么问题问我没有？





面向对象的 关键字  final  const  static



1.redis 和 memache 缓存的区别（**）
1.数据类型
redis支持多种数据类型（5种）：hash string list set zset
memcache 只支持key-value
2.持久性（**）
redis 支持两种持久化方式 RDB、AOF
memcache 不支持持久化
3.分布式存储
redis支持master-slave复制模式
memcache可以使用一致性hash做分布式
4.value大小不同
memcache是一个内存缓存，key的长度小于250字符，单个item存储要小于1M，不适合虚拟机使用
5.线程模型
memcache是master+worker的线程模型，其中master完成网络监听后投递到worker线程，由worker线程处理
redis是单进程单线程模型，即单个线程完成所有的事情
这两种实现造成下面的差异，即redis更容易实现多种数据结构，类似列表，集合，hash，有序集合等，由于是单线程的，如果单实例部署redis，不能全面用到服务器多核的优势，通常部署时，都会通过多实例的方式去部署
6.内存管理
redis：redis没有自己得内存池，而是直接使用时分配，即什么时候需要什么时候分配，内存管理的事交给内核，自己只负责取和释放，直接malloc和free即可。内存管理没有什么特殊的算法，通过使用google的jmalloc库来做内存管理（申请，释放）
memcache：memcached是有自己得内存池的，即预先分配一大块内存，然后接下来分配内存就从内存池中分配，这样可以减少内存分配的次数，提高效率，这也是大部分网络服务器的实现方式，只不过各个内存池的管理方式根据具体情况而不同。使用了类似linux的内存管理，即slab内存管理方式。
7.其他
redis支持事务，频道（发布-订阅），集群；memcache不支持

apche 和 nginx 的优缺（*）
nginx轻量级，比apache占用更少的内存及资源，抗并发
nginx处理请求是异步非阻塞的，而apache 则是阻塞型的，在高并发下nginx 能保持低资源低消耗高性能。
apache 相对于nginx 的优点：
rewrite比nginx 的rewrite 强大，少bug，稳定。（需要性能用nginx，求稳定就apache）

什么是内存管理？（**）
内存管理主要是指程序运行时对计算机内存资源的分配、使用和释放等技术，内存管理的目标是高效、快速地分配内存同时及时地释放和回收内存资源。内存管理主要包括是否有足够的内存供程序使用，从内存池中获取可用内存，使用后及时销毁并重新分配给其他程序使用。
在PHP开发过程中，如果遇到大数组等操作，那么可能会造成内存溢出等问题。一些常见的处理方法如下：
1）通过ini_set(‘memory_limit’,‘64M’)方法重置php可以使用的内存大小，一般在远程主机上是不能修改php.ini文件的，只能通过程序设置。注：在safe_mode（安全模式）下，ini_set会失效。
2）另一方面可以对数组进行分批处理，及时销毁无用的变量，尽量减少静态变量的使用，在需要数据重用时，可以考虑使用引用（&）。同时对于数据库、文件操作完要及时关闭，对象使用完要及时调用析构函数等。
3）及时使用unset()函数释放变量，使用时需要注意以下两点：
① unset()函数只能在变量值占用内存空间超过256字节时才会释放内存空间。
② 只有当指向该变量的所有变量都销毁后，才能成功释放内存。

共享Session的方式（**）
1）基于NFS的Session共享。NFS（Network File System）最早由Sun公司为解决Unix网络主机间的目录共享而研发。仅需将共享目录服务器mount到其他服务器的本地session目录即可。
2）基于数据库的Session共享。
3）基于Cookie的Session共享。原理是将全站用户的Session信息加密、序列化后以Cookie的方式，统一种植在根域名下（如：.host.com），利用浏览器访问该根域名下的所有二级域名站点时，会传递与之域名对应的所有Cookie内容的特性，从而实现用户的Cookie化Session 在多服务间的共享访问。
4）基于缓存（Memcache）的Session共享。Memcache是一款基于Libevent多路异步I/O技术的内存共享系统，简单的key + value数据存储模式使得代码逻辑小巧高效，因此在并发处理能力上占据了绝对优势，目前能达到2000/s平均查询，并且服务器CPU消耗依然不到10%。

memcache或redis雪崩如何解决？（*）
造成原因：通常，在一个网站里，mysql数据库处理的请求比较少（20%），负载80%，缓存技术处理大多数请求（80%）
如果memcache或redis挂掉，所有请求都会在mysql处理，数据库的处理能力不足会直接宕机。这时候就算重启缓存和mysql也是无济于事的，因为缓存重启后，数据已经丢失，数据请求还是会走mysql，mysql还是会死掉（死循环）
解决方法：
缓存预热
1：先启动缓存，再启动数据库。（但是此时不提供对外服务）
2：通过一个PHP脚本把常用的key写入缓存中
3：开放对外服务【热点数据已经缓存，请求会被缓存处理，减轻mysql压力】


Redis持久化的方式？（*）
1.Aof(append only file)
redis执行命令时，会把我们执行的命令通过日志形式进行追加。安全性高，但是影响性能。
2.Rdb
按照制定规则进行持久化
save 900 1 (900s内1次redis操作 会做一次持久化)
save 300 10 (300s内10次redis操作 会做一次持久化)
save 60 10000 (60s内10000次redis操作 会做一次持久化)
但是可能会存在数据丢失，比如：12:00做过一次持久化，正常的话，12:15会再做持久化，如果12:14缓存死掉，那么14分钟的数据会丢失。不大安全，但是性能比aof好很多



Linux系统中，进程间通信的方式。(*)
管道：
管道分为有名管道和无名管道
无名管道是一种半双工的通信方式,数据只能单向流动,而且只能在具有亲缘关系的进程间使用.进程的亲缘关系一般指的是父子关系。无明管道一般用于两个不同进程之间的通信。当一个进程创建了一个管道,并调用fork创建自己的一个子进程后,父进程关闭读管道端,子进程关闭写管道端,这样提供了两个进程之间数据流动的一种方式。
有名管道也是一种半双工的通信方式,但是它允许无亲缘关系进程间的通信。
消息队列：
消息队列是消息的链表,存放在内核中并由消息队列标识符标识.消息队列克服了信号传递信息少,管道只能承载无格式字节流以及缓冲区大小受限等特点.消息队列是UNIX下不同进程之间可实现共享资源的一种机制,UNIX允许不同进程将格式化的数据流以消息队列形式发送给任意进程.对消息队列具有操作权限的进程都可以使用msget完成对消息队列的操作控制.通过使用消息类型,进程可以按任何顺序读信息,或为消息安排优先级顺序.
信号：
信号是一种比较复杂的通信方式,用于通知接收进程某个事件已经发生.
信号量：
信号量是一个计数器,可以用来控制多个线程对共享资源的访问.,它不是用于交换大批数据,而用于多线程之间的同步.它常作为一种锁机制,防止某进程在访问资源时其它进程也访问该资源.因此,主要作为进程间以及同一个进程内不同线程之间的同步手段.
共享内存：
共享内存就是映射一段能被其他进程所访问的内存,这段共享内存由一个进程创建,但多个进程都可以访问.共享内存是最快的IPC(进程间通信)方式,它是针对其它进程间通信方式运行效率低而专门设计的.它往往与其他通信机制,如信号量,配合使用,来实现进程间的同步与通信.
socket：
可用于不同及其间的进程通信
文件，互斥量等，不过我在swoole源码中看到了通过eventfd这种方式做进程通信的

两台mysql服务器，其中一台挂了，怎么让业务端无感切换，并保证正常情况下讲台服务器的数据是一致的
不是核心业务的话，先停写，把备机拉起来，查看两台机器的日志，进行数据补偿，开写。
如果是核心业务的话，现在所有的写操作都在正常的状态机器上。把好的这台机器的备机拉起来，当主机。
备机的数据不一致怎么办？
你要勇敢怼回去，你们每秒多少写入操作。按照百万级表，每秒1000的写入效率，正常的设计是，分布在2台机器上每台500。这个级别的数据同步，出现差异的概率 可以忽略不计的。有一台出现问题，另一台也可以抗住。


redis是如何进行同步的，同步的方式，同步回滚怎么办，数据异常怎么办（**）
redis 集群主从同步的简单原理
Redis的复制功能是基于内存快照的持久化策略基础上的，也就是说无论你的持久化策略选择的是什么，只要用到了Redis的复制功能，就一定会有内存快照发生
　　当Slave启动并连接到Master之后，它将主动发送一个SYNC命令( 首先Master会启动一个后台进程，将数据快照保存到文件中[rdb文件] Master 会给Slave 发送一个
Ping命令来判断Slave的存活状态 当存活时 Master会将数据文件发送给Slave 并将所有写命令发送到Slave )。Slave首先会将数据文件保存到本地之后再将数据加载到内存中。
　　当第一次链接或者是故障后，重新连接都会先判断Slave的存活状态再做全部数据的同步，之后只会同步Master的写操作(将命令发送给Slave)
问题：
　　当 Master 同步数据时 若数据量较大 而Master本身只会启用一个后台进程 来对多个Slave进行同步 ， 这样Master就会压力过大 ， 而且Slave 恢复的时间也会很慢！
redis 主从复制的优点：
(1)在一个Redis集群中，master负责写请求，slave负责读请求，这么做一方面通过将读请求分散到其他机器从而大大减少了master服务器的压力，另一方面slave专注于提供
读服务从而提高了响应和读取速度。
　　(2)在一个Redis集群中，如果master宕机，slave可以介入并取代master的位置，因此对于整个Redis服务来说不至于提供不了服务，这样使得整个Redis服务足够安全。
　　(3)水平增加Slave机器可以提高性能


如何解决跨域(*)
JSONP
添加响应头，允许跨域
代理的方式

什么是服务容器、控制反转（IoC）、依赖注入（DI）

服务容器是用来管理类依赖与运行依赖注入的工具。Laravel框架中就是使用服务容器来实现 控制反转 和 依赖注入 。
控制反转(IoC) 就是说把创建对象的 控制权 进行转移，以前创建对象的主动权和创建时机是由自己把控的，而现在这种权力转移到第三方，也就是 Laravel 中的容器。
依赖注入（DI）则是帮助容器实现在运行中动态的为对象提供提依赖的资源。


Composer自动加载原理（*）

composer加载核心思想是通过composer的配置文件在引用入口文件(autoload.php)时,将类和路径的对应关系加载到内存中,最后将具体加载的实现注册到spl_autoload_register函数中.最后将需要的文件包含进来.


一个请求到PHP，Nginx的主要过程。完整描述整个网络请求过程，原理。（*）
1)、FastCGI进程管理器php-fpm自身初始化，启动主进程php-fpm和启动start_servers个CGI 子进程。主进程php-fpm主要是管理fastcgi子进程，监听9000端口。fastcgi子进程等待来自Web Server的连接。
2)、当客户端请求到达Web Server Nginx是时，Nginx通过location指令，将所有以php为后缀的文件都交给127.0.0.1:9000来处理，即Nginx通过location指令，将所有以php为后缀的文件都交给127.0.0.1:9000来处理。
3）FastCGI进程管理器PHP-FPM选择并连接到一个子进程CGI解释器。Web server将CGI环境变量和标准输入发送到FastCGI子进程。
4)、FastCGI子进程完成处理后将标准输出和错误信息从同一连接返回Web Server。当FastCGI子进程关闭连接时，请求便告处理完成。
5)、FastCGI子进程接着等待并处理来自FastCGI进程管理器（运行在 WebServer中）的下一个连接。


PHP的魔术方法（*）
__set() // 在给不可访问属性赋值时，__set()会被调用
__get() // 读取不可访问属性的值时，__get()会被调用
__isset() //当对不可访问属性调用isset()或empty()，__isset()会被调用
__unset() // 当对不可访问属性调用unset()时，__unset()会被调用
__call() // 在对象中调用一个不可访问方法时，__call()会被调用
__callStatic() // 在静态上下文中调用一个不可访问的方法时，__callStatic会被调用
__construct() // 构造函数的类会在每次创建新对象时先调用此方法，所以非常适合在使用对象之前做一些初始化工作。

__destruct() // 析构函数会在到某个对象的所有引用都被删除或者当对象被显式销毁时执行。
__sleep() // serialize()函数会检查类中是否存在一个魔术方法__sleep()，如果存在，该方法会先被调用，然后再执行序列化操作。此功能可以用于清理对象，并返回一个包含对象中所有应被序列化的变量名称的数组。如果该方法未返回任何内容，则 NULL 被序列化，并产生一个 E_NOTICE 级别的错误。
__wakeup() // unserialize()函数会检查是否存在一个__wakeup()方法，如果存在，则会先调用该方法，然后再执行反序列化操作。__wakeup() 经常用在反序列化操作中，例如重新建立数据库连接，或执行其它初始化操作。


MySQL默认的排序方式是什么
MyIsam存储引擎：在没有任何删除，修改的操作下，执行select不带order by那么会按照插入的顺序下进行排序。
InnDB存储引擎：在相同的情况下，select不带order by会根据主键来排序，从小到大。

OSI七层网络模型（*）
物理层：建立、维护、断开物理连接
数据链路层：建立逻辑链接、进行硬件地址寻址、差错校验等功能（SDLC、HDLC、PPP、STP）
网络层：进行逻辑地址寻址，实现不同网络之间的路径选择（IP、IPX、OSPF）
传输层：定义传输数据的协议端口号，以及流程和差错校验（TCP,UDP）数据包一旦离开网卡即进入网络传输层
会话层：建立、管理、终止会话
表示层：数据的表示、安全、压缩
应用层：网络服务与最终用户的一个接口；协议有：HTTP、FTP、TFTP、SMTP、DNS、TELNET、HTTPS、POP3、DHCP


LRU算法
如果一个 数据在最近一段时间没有被访问到，那么在将来它被访问的可能性也很小


找出数组中出现一次的元素。10 10 11 11 12 13 12 13 16 只出现一次的数字。要求时间复杂度尽可能低
// 方法一
function onlyOne($arr) {
	$res = 0;
	for ($i = 0; $i < count($arr); $i++) {
		$res ^= $arr[$i];
	}
	
   return $res;
}
// 方法二
function onlyOne2($arr) {
	$m = array_count_values($arr);
	foreach ($m as $k => $v) {
	  if ($v == 1) {
		return $k;
	  }
	}
	return 0;
}

php八种数据类型
数据类型分为三种：
标量数据类型：boolean、string、integer、double
复合数据类型：array、object
特殊数据类型：resource、null


php进程模型，php怎么支持多个并发
守护进程模型：https://www.jianshu.com/p/542935a3bfa8

nginx的进程模型，怎么支持多个并发
https://www.zhihu.com/question/22062795

php-fpm各配置含义，fpm的daemonize模式
http://www.4wei.cn/archives/1002061







#### 存放 session 的三种方法

```php
1、如果你能修改到服务器配置文件，那就打开打开php.ini
修改下面两项：
    session.save_handler = memcache
    session.save_path = "tcp://127.0.0.1:11211"
2、修改网站根目录下的.htaccess文件
    php_value session.save_handler "memcache"
    php_value session.save_path  "tcp://127.0.0.1:11211"
3、最常用的方法  在程序代码中修改（推荐）
    ini_set("session.save_handler", "memcache");
    ini_set("session.save_path", "tcp://127.0.0.1:11211");
```



## http 请求的流程？
```http
1. 域名解析 
2. 发起TCP的3次握手 
3. 建立TCP连接后发起http请求 
4. 服务器端响应http请求，浏览器得到html代码 
5. 浏览器解析html代码，并请求html代码中的资源 
6. 浏览器对页面进行渲染呈现给用户

1、浏览器向 DNS 服务器请求解析该 URL 中的域名所对应的 IP 地址;
2、解析出 IP 地址后，根据该 IP 地址和默认端口 80，和服务器建立TCP连接;
3、浏览器发出读取文件(URL 中域名后面部分对应的文件)的HTTP 请求，该请求报文作为 TCP 三次握手的第三个报文的数据发送给服务器;
4、服务器对浏览器请求作出响应，并把对应的 html 文本发送给浏览器;
5、释放 TCP连接;
6、浏览器将该 html 文本并显示内容; 
```

## [nginx响应504的超时问题及php的慢日志事宜](http://www.04007.cn/article/488.html)

* **原因**

  - 程序在处理大量数据，导致等待超时。
  - 程序中调用外部请求，而外部请求响应超时。
  - 连接数据库失败而没有停止，死循环重新连。

* **解决方法**

  - 开启php慢日志功能(找到php-fpm.conf配置文件，或者如果有加载*.conf文件，需要找一下对应目录下的配置文件，我这里在php-fpm.d文件夹中有www.conf文件)

  ```
  # 将上面这行配置去除前面的分号并改为以下内容：
  slowlog = var/log/$pool.slow.log
  # 将上面这行配置去除前面的分号并改为以下内容：
  request_slowlog_timeout = 5
  ```

---

## [array_multisort](https://www.cnblogs.com/pyspang/p/10573256.html)

```
<?php

 假设， $arr 是一个二维数组, $arg1是取出的字段1， $arg2是取出的字段2， 需要多少个字段拿多少个！


// 先用 内置函数 array_column 取出其中一个字段

array_multisort(array_column($arr, $arg1), SORT_ASC, array_column($arr, $arg2), SORT_DESC, $arr);

这样既可得到根据两个字段来排序的功能，简单快捷！
```

---

## [php获取post方法payload(json)形式参数的方法](https://blog.csdn.net/cominglately/article/details/80393335)

- 场景

  ```
  vue-resource发送了一个post请求，在后台$_POST都获取不到数据
  ```

- 分析

  ```
  研究完参数 发现参数是通过payload json方式传递的,  这种方式是没有办法从$_POST中获取的,
  只有x-www-form-data multipart/form-data 这两种形式的payload才会填充$_POST, 而application/json则填充 php://input
  ```

- 解决

  ```
  $request_body = file_get_contents('php://input');
  $data = json_decode($request_body, true);
  ```

---

## [PHP中三点（…）的含义](https://codingdict.com/questions/31333)

函数声明中的参数列表中包含...运算符，它的基本含义是“ …以及其他所有内容都应放入$
strings中”。您可以向该函数传递2个或多个参数，第二个及后续参数将添加到$ strings数组中

```
function concatenate($transform, ...$strings) {
    $string = '';
    foreach($strings as $piece) {
        $string .= $piece;
    }
    return($transform($string));
}

echo concatenate("strtoupper", "I'd ", "like ", 4 + 2, " apples");
// 输出结果：
// I'D LIKE 6 APPLES
```

# 