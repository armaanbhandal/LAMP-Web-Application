# LAMP Web Application

A LAMP stack (Linux, Apache, MySQL, PHP) setup assignment: an Apache virtual host serving a PHP site from its own document root.

## Files

The folders mirror where each file lives on the server.

- `etc/apache2/sites-available/armaanBhandal.conf` — Apache virtual host listening on port 87, with `DocumentRoot /var/www/armaanBhandal`
- `var/www/armaanBhandal/index.php` — PHP page confirming the site works

## Deploying on Ubuntu/Debian

```bash
sudo cp etc/apache2/sites-available/armaanBhandal.conf /etc/apache2/sites-available/
sudo mkdir -p /var/www/armaanBhandal
sudo cp var/www/armaanBhandal/index.php /var/www/armaanBhandal/
echo "Listen 87" | sudo tee -a /etc/apache2/ports.conf
sudo a2ensite armaanBhandal.conf
sudo systemctl reload apache2
```

Then visit `http://localhost:87`.
