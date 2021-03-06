Symfony Demo Application with Elasticsearch
========================

The "Symfony Blog with Elasticsearch Application" is a reference application created to show how
to develop applications following the [Symfony Best Practices][1].

Requirements
------------

  * PHP 7.1.3 or higher;
  * PDO-SQLite PHP extension enabled;
  * and the [usual Symfony application requirements][2].

Installation
------------

```bash
$ composer create-project symfony/symfony-demo
```

Usage
-----

There's no need to configure anything to run the application. Just execute this
command to run the built-in web server and access the application in your
browser at <http://localhost:8000>:

```bash
$ cd symfony-elasticsearch/
$ php bin/console server:run
$ docker-compose up 😜
```

Elasticsearch run on http://localhost:9200/
Kibana runs on http://localhost:5601
Alternatively, you can [configure a web server][3] like Nginx or Apache to run
the application.

Everything is ready, we create the index with our IndexBuilder, then we send all the articles via ArticleIndexer
run this command

```bash
php bin/console elastic:reindex
```
You can go to Kibana and check that everything is in order:
Tests
-----

Execute this command to run tests:

```bash
$ cd symfony-demo/
$ ./bin/phpunit
```


[1]: https://symfony.com/doc/current/best_practices/index.html
[2]: https://symfony.com/doc/current/reference/requirements.html
[3]: https://symfony.com/doc/current/cookbook/configuration/web_server_configuration.html
