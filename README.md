# php-buddy
Пакет необходимых инструментов анализа и тестирования php кода

Включает в себя:
* https://github.com/phingofficial/phing
* https://github.com/sebastianbergmann/phpunit
* https://github.com/JakubOnderka/PHP-Parallel-Lint
* https://github.com/phpmd/phpmd
* https://github.com/pdepend/pdepend
* https://github.com/sebastianbergmann/phploc
* https://github.com/sebastianbergmann/phpcpd
* https://github.com/squizlabs/PHP_CodeSniffer
* https://github.com/itmh/coding-standard-php
* https://github.com/itmh/cyclophp
* https://github.com/mayflower/PHP_CodeBrowser
* https://github.com/phpstan/phpstan

### Установка

После установки пакета, следует скопировать файл `build.xml.example` в корень проекта и настроить под свои требования. Также необходимо добавить секцию `scripts` в свой `composer.json`:
```
"scripts": {
  "build": "./vendor/bin/phing build",
  "build:strict": "BUILD_STRICT=1 ./vendor/bin/phing build",
  "test": "./vendor/bin/phing test"
}
```
А также добавить хук на пуш для гита:
```shell
cat > .git/hooks/pre-push << EOF
#!/bin/sh
composer build:strict
EOF
```
И убедиться что у него есть права на запуск
```shell
chmod +x .git/hooks/pre-push
```
