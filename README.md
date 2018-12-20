[![Biko2](https://www.biko2.com/wp-content/uploads/web/logo.png)](https://www.biko2.com)

# Drupal Dev Precommit

Este hook de git (pre-commit) nos revisará los ficheros que se han añadido al commit que cumplan con este patrón:
- *.php
- *.theme
- *.module
- _Están ignorados todos los ficheros que se encuentran en las carpetas "vendor" y "contrib"_

### Install

Descargar fichero pre-commit en la carpeta de tu proyecto "private/git_hooks".

Esta carpeta puede cambiar según el proyecto (acquia, pantheon, custom)

Hacer executable el fichero pre-commit (chmod)

    chmod +x pre-commit

| Plugin | Command |
| ------ | ------ |
| php_codesniffer | composer require "squizlabs/php_codesniffer=*" |
| drupal/coder | composer require drupal/coder |
| phpcodesniffer | composer require dealerdirect/phpcodesniffer-composer-installer |
| phpmd | composer require phpmd/phpmd |

### Configure
    php vendor/bin/phpcs --config-set installed_paths vendor/drupal/coder/coder_sniffer

#### Configuración de PHPMD (PHP Mess Detector):
El fichero "phpmd.xml" define las reglas para analizar.

En el fichero "pre-commit" está configurada la ruta "private/git_hooks/phpmd.xml" (adaptar si es necesario)

### Activate
    cd .git/hooks
    ln -s ../../private/git_hooks/pre-commit pre-commit
