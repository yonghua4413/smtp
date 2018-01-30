# smtp

smtp邮件 可用于阿里dm

```
$ composer require yonghua4413/smtp
```

```php
//引入
use YYHemail\smtp;

$mailto='接受者邮箱';
$mailsubject="邮件标题";
$mailbody= '邮件内容';
$smtpserver     = "smtpdm.aliyun.com";
$smtpserverport = 80;#端口

$smtpusermail   = "发信地址";
$smtpuser       = "发信地址";
$smtppass       = "smtp密码";

$mailsubject    = "=?UTF-8?B?" . base64_encode($mailsubject) . "?=";
$mailtype       = "HTML";
$smtp           = new smtp($smtpserver, $smtpserverport, true, $smtpuser, $smtppass);
$smtp->debug    = FALSE; 
$smtp->sendmail($mailto, $smtpusermail, $mailsubject, $mailbody, $mailtype);
```