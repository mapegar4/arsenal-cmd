# bookstack

% services, web, bookstack

#platform/linux #target/server #cat/ADMIN #cat/WEB

## Update BookStack (Git & Composer)
```
sudo -u nginx git pull origin release
sudo -u nginx composer install --no-dev --no-interaction --prefer-dist
sudo -u nginx php artisan migrate --force
```

## Clear BookStack Caches (All)
```
sudo -u nginx php artisan cache:clear
sudo -u nginx php artisan config:clear
sudo -u nginx php artisan view:clear
```

## Fix Permissions (Nginx Owner)
```
chown -R nginx:nginx /var/www/bookstack
```

## Restart Web Services
```
systemctl restart php-fpm nginx
```

## Monitor Laravel Logs
```
tail -f /var/www/bookstack/storage/logs/laravel.log
```

## Send Test Email
```
php artisan bookstack:send-test-email --email=<email>
```

## Enable Network Connection (SELinux)
```
setsebool -P httpd_can_network_connect on
```

## Check SELinux Status
```
getenforce
```

## Run Backup Script
```
/usr/local/sbin/backup_bookstack.sh
```

## Manage Fail2Ban
```
nano /etc/fail2ban/jail.local
systemctl restart fail2ban
```

## Check Swap Usage
```
swapon --show
free -h
```
