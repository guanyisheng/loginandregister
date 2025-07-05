

# 用户登录与注册系统

这是一个基于 PHP 和 MySQL 的简单用户登录与注册系统，采用 Tailwind CSS 进行页面样式设计，为用户提供了便捷的登录和注册功能。

## 项目概述
本系统包含三个主要页面：
- `login.php`：用户登录页面，支持使用用户名或邮箱进行登录。
- `register.php`：用户注册页面，用户可以创建新的账户。
- `logout.php`：用户注销页面，用于清除会话并将用户重定向到登录页面。

## 安装与配置

### 1. 克隆项目


### 2. 数据库配置
在 `login.php` 和 `register.php` 文件中，找到数据库连接部分，根据你的 MySQL 配置修改以下信息：
```php
$auth_host = "localhost";
$auth_dbname = "";
$auth_username = "";
$auth_password = "";
```
确保数据库中存在名为 `users` 的表，表结构至少包含以下字段：
- `id`：用户 ID，自增主键
- `username`：用户名
- `email`：用户邮箱
- `password`：用户密码

### 3. 页面依赖
项目使用了 Tailwind CSS 和 Font Awesome 图标库，通过 CDN 引入，确保网络连接正常即可。

## 使用说明

### 注册
访问 `register.php` 页面，输入用户名、邮箱和密码，点击“创建账户”按钮完成注册。如果用户名已存在，系统将提示错误信息。

### 登录
访问 `login.php` 页面，输入用户名或邮箱以及密码，点击“登录”按钮进行登录。如果密码不正确或用户不存在，系统将提示相应的错误信息。

### 注销
访问 `logout.php` 页面，系统将清除会话并将用户重定向到登录页面。

## 修改登录后跳转页面
在 `login.php` 文件中，找到以下代码：
```php
// 重定向到用户主页或其他页面
header("Location: dashboard.php");
exit();
```
将 `dashboard.php` 替换为你想要跳转的页面文件名，例如 `home.php`：
```php
// 重定向到用户主页或其他页面
header("Location: home.php");
exit();
```

## 注意事项
- 本系统取消了密码的哈希加密和验证，直接使用明文密码进行存储和比较，这在实际生产环境中存在安全风险，请根据需求添加适当的加密和验证机制。
- 确保服务器支持 PHP 和 MySQL，并且配置正确。

## 贡献
如果你发现任何问题或有改进建议，请提交 Issue 或 Pull Request。

## 许可证
本项目采用 [MIT 许可证](https://opensource.org/licenses/MIT)。

