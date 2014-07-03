Install-[Ruby](https://www.ruby-lang.org/en/installation/#homebrew)
============

目前最新的穩定版本是 2.1.2。

安裝順序： XCode → HomeBrew → ROR → etc(SSH...)

1. XCode
-------
Open the Mac App Store to buy and download apps.

[APP介紹](https://itunes.apple.com/us/app/xcode/id497799835?mt=12)


2. HomeBrew(套件管理工具)
--------
在commend line 輸入

`ruby -e "$(curl -fsSL https://raw.github.com/mxcl/homebrew/go/install)`

安裝Git(版本管理)`brew install git`

安裝wget(抓網路檔案的工具)`brew install wget`

安裝ImageMagick(縮圖用)`brew install imageMagick`

安裝MySQL(DataBase)`brew install mysql`

設定MySQL

3.RVM
--------------------------
管理及切換不同版本的ruby

`$ curl -L https://get.rvm.io | bash -s stable`

接著重開命令列或者重新登入
([rbven]也可以)

4.  ROR
--------
安裝ruby`rvm install ruby-版本 `

安裝ruby gem`rvm rubygems current`

安裝rails`gem install rails`

Further Explanation
---------------
  * [Ruby on Rails 開發環境建置 for Mac]


[Ruby on Rails 開發環境建置 for Mac]: http://www.slideshare.net/marsz330/ruby-on-rails-for-mac
[rbven]:https://www.ruby-lang.org/en/installation/#rbenv