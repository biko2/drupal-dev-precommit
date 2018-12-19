[![Biko2](https://www.biko2.com/wp-content/uploads/web/logo.png)](https://www.biko2.com)

# Drupal Dev Precommit

Este hook de git (pre-commit) nos revisará los ficheros que se han añadido al commit que cumplan con este patrón:
- *.php
- *.theme
- *.module
- _Están ignorados todos los ficheros que se encuentran en las carpetas "vendor" y "contrib"_

#### Nota importante con la librería phpmd (mess detector):
En algunos fichero de drupal se necesita utilizar variables con barras bajas (_), por ejemplo: $form_state

En estas ocasiones lo recomendable es poner en el comentario del fichero: "@SuppressWarnings(PHPMD)"

    /**
     * Ejemplo para ignorar phpmd en este fichero
     *
     * @SuppressWarnings(PHPMD)
     */

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

### Activate
    cd .git/hooks
    ln -s ../../private/git_hooks/pre-commit pre-commit
