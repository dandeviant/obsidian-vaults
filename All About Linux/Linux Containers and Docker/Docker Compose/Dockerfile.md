```bash
# syntax=docker/dockerfile:1
FROM ubuntu:18.04
COPY . /app
RUN make /app
CMD python /app/app.py
```

Each instruction creates one layer:

-   `FROM` creates a layer from the `ubuntu:18.04` Docker image.
-   `COPY` adds files from your Docker client’s current directory.
-   `RUN` builds your application with `make`.
-   `CMD` specifies what command to run within the container.

---
**Currently used in Ubuntu VM fot phpMyAdmin Docker**
```bash
FROM phpmyadmin/phpmyadmin <--name of image used
```