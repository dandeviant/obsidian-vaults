```bash
version: "3.9"  # optional since v1.27.0
services:
  web:
    build: . #path to Dockerfile
    ports:
      - "5000:5000"
    volumes:
      - .:/code
      - logvolume01:/var/log
    links:
      - redis
  redis:
    image: redis
volumes:
  logvolume01: {}
```
---
**Currently used in Ubuntu VM for phpMyAdmin Docker**
```
version: "3.1"
services:
        phpmyadmin:
                image: phpmyadmin/phpmyadmin
                container_name: 'phpmyadmin'
                restart: always
                ports:
                        - "9999:80"
                environment:
                        - PMA_ARBITRARY=1
```
