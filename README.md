# Suspenders (私家版)

[thoughtbot](http://thoughtbot.com/community)が公開している
[Suspenders](https://github.com/thoughtbot/suspenders)をForkして自分用にカスタマイズしています。


## インストール方法

```
$ git clone git@github.com:bojovs/suspenders.git
$ gem install suspenders-1.1.5.gem
```


## 使い方

```
$ suspenders projectname
```

上記コマンドを実行すると `projectname` という名前の Rails 3.2 なアプリケーションが生成されます。


## やっていること

* 標準でインストールしたいgemsをGemfileに追加
  * インストール内容は[template/Gemfile_additions](/bojovs/suspenders/blob/master/templates/Gemfile_additions)を見てください。
* Override recipient emails in staging environment.
* Rails' flashes set up and in application layout.
* A few nice time formats set up for localization.
* [Heroku-recommended asset pipeline
  settings](https://devcenter.heroku.com/articles/rails3x-asset-pipeline-cedar/).


Heroku
------

You can optionally create Heroku staging and production apps:

    suspenders app --heroku true

This has the same effect as running:

    heroku create app-staging --remote staging
    heroku create app-production --remote production

Github
------

You can optionally create a Github repository:

    suspenders app --github organization/project

This has the same effect as running:

    hub create organization/project

Clearance
---------

You can optionally not include Clearance:

    suspenders app --clearance false

Capybara Webkit
---------------

You can optionally not include Capybara Webkit (which depends on QT being
installed on your machine):

    suspenders app --webkit false

Dependencies
------------

Some gems included in Suspenders have native extensions. You should have GCC installed on your
machine before generating an app with Suspenders.

Use [OS X GCC Installer](/kennethreitz/osx-gcc-installer/) for Snow Leopard
(OS X 10.6).

Use [Command Line Tools for XCode](https://developer.apple.com/downloads/index.action)
for Lion (OS X 10.7) or Mountain Lion (OS X 10.8).

We use [Capybara Webkit](/thoughtbot/capybara-webkit) for full-stack Javascript
integration testing. It requires QT. Instructions for installing QT are
[here](/thoughtbot/capybara-webkit/wiki/Installing-Qt-and-compiling-capybara-webkit).

PostgreSQL needs to be installed and running for the `db:create` rake task.

Issues
------

If you have problems, please create a [Github Issue](/thoughtbot/suspenders/issues).

Contributing
------------

Please see CONTRIBUTING.md for details.

Credits
-------

![thoughtbot](http://thoughtbot.com/images/tm/logo.png)

Suspenders is maintained and funded by [thoughtbot, inc](http://thoughtbot.com/community)

The names and logos for thoughtbot are trademarks of thoughtbot, inc.

License
-------

Suspenders is Copyright © 2008-2012 thoughtbot. It is free software, and may be
redistributed under the terms specified in the LICENSE file.
