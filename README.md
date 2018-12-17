[![Biko2](https://www.biko2.com/wp-content/uploads/web/logo.png)](https://www.biko2.com)

# Drupal Dev Precommit

### Install
| Plugin | Command |
| ------ | ------ |
| php_codesniffer | composer require "squizlabs/php_codesniffer=*" |
| drupal/coder | composer require drupal/coder |
| phpcodesniffer | composer require dealerdirect/phpcodesniffer-composer-installer |
| phpmd | composer require phpmd/phpmd] |

### Configure
    php vendor/bin/phpcs --config-set installed_paths vendor/drupal/coder/coder_sniffer

### Activate
    cd .git/hooks
    ln -s ../../git_hooks/pre-commit pre-commit
