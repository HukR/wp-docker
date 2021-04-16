# Wordpress Docker Environment

php7.4-fpm + xDebug \
NGINX \
phpMyAdmin \
MySQL 8.0.23 \
MailHog

## Setup 

update variables in .env
```
docker-compose up -d
```

### for MailHog add this to functions.php:
```
add_action( 'phpmailer_init', 'mailhog_setup' );

function mailhog_setup( PHPMailer $phpmailer ) {
    $phpmailer->Host = 'mailhog';
    $phpmailer->Port = 1025;
    $phpmailer->IsSMTP();
}
```