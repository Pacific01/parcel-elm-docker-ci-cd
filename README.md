

# Build image
```sh
docker build -t parcelm .
```

# Run go inside and run npm

# Go inside
## Linux
```sh
docker run --user "$(id -u):$(id -g)" -v `pwd`:/code -it parcelm /bin/sh
```

## Windows
Aviso: \`pwd\` se ha de sustituir por el path actual del proyecto.
```sh
docker run -v `pwd`:/code -it parcelm /bin/sh
```


# Install dependencies
```sh
npm install
```

# Build the project
```sh
npm run build
```

# Serve
```sh
docker run -it --name my-apache-app -p 8080:80 -v "$PWD/dist":/usr/local/apache2/htdocs/ httpd:2.4
```
