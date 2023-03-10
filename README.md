"# codeigniter Rest API" 

Clone or Download project . Set on server.

"# Create Database Tables"

```
CREATE TABLE `users` (
 `id` int(11) NOT NULL AUTO_INCREMENT,
 `email` varchar(50) COLLATE utf8_unicode_ci NOT NULL,
 `password` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
 `confirm_password` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
 `phone` varchar(20) COLLATE utf8_unicode_ci DEFAULT NULL,
 `created` datetime NOT NULL,
 `modified` datetime NOT NULL,
 `status` tinyint(1) NOT NULL DEFAULT '1' COMMENT '1=Active | 0=Inactive ',
 PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
```

```
CREATE TABLE `keys` (
 `id` int(11) NOT NULL AUTO_INCREMENT,
 `user_id` int(11) NOT NULL,
 `key` varchar(40) NOT NULL,
 `level` int(2) NOT NULL,
 `ignore_limits` tinyint(1) NOT NULL DEFAULT '0',
 `is_private_key` tinyint(1) NOT NULL DEFAULT '0',
 `ip_addresses` text,
 `date_created` datetime NOT NULL,
 PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8;
```

Insert one default key to table

```
INSERT INTO `keys` (`id`, `user_id`, `key`, `level`, `ignore_limits`, `is_private_key`, `ip_addresses`, `date_created`) VALUES
(NULL, 1, 'stemword', 0, 0, 0, NULL, '2018-10-11 13:34:33');
```

List of APIs you will get:

http://localhost/codeigniter-rest-api-user-login-registration/index.php/authentication/login - POST

http://localhost/codeigniter-rest-api-user-login-registration/index.php/authentication/registration - POST

http://localhost/codeigniter-rest-api-user-login-registration/index.php/authentication/user/1 - GET 

http://localhost/codeigniter-rest-api-user-login-registration/index.php/authentication/user_edit - POST
