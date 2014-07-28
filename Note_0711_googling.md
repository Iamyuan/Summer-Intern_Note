Googling
=========
Make requests
---------------

**發送reguests的方法有很多以下舉例：**

  **1.
curl在的treminal環境下使用**

[可參考](http://rubylearning.com/blog/do-you-know-how-to-use-curl/)

[可參考](http://curl.haxx.se/docs/manpage.html)

  **2.利用`gem instal _____`安裝[gems], 舉例如下：**

[gems]:https://rubygems.org/
[rest-client](https://github.com/rest-client/rest-client)

[gem install rest-client](https://rubygems.org/gems/rest-client)

    require 'rest_client'
    
    RestClient.get 'http://example.com/resource'
    
    response = RestClient.get 'http://example.com/resource'

  **3.net::HTTP(ruby std-lib)**
    
    require "net/https"

    uri = URI.parse("https://www.google.com/search?q=#{@keywords}") 
    # ↑get the url that we need to post to
    http = Net::HTTP.new(uri.host, uri.port)
    http.use_ssl = true  #
    request = Net::HTTP::Get.new(uri.request_uri)
    @response = http.request(request) 
    # ↑Net::HTTPResponse object
    
    
Nokogiri
------------
可參考[Nocogiri]

refactor
------------
make the code easier to write and mantain.

[Gem](https://rubygems.org/gems/googling)
------
於完成後可製作成gem, 首先在rubygems.org辦一個帳號，上傳到GitHub, 安裝以下套件, 並且上傳。

1. ```gem install bundler```
 It can install all the gem you need.

2. ```gem install rake```
類似 Make 的 Builder 工具, 安裝後可在googling看到[rakefile](https://github.com/Iamyuan/googling/blob/master/Rakefile), 就是將測試的內容以ruby語法寫成。 並且會看到[gemfile](https://github.com/Iamyuan/googling/blob/master/Gemfile)以及 [googling.gemspec](https://github.com/Iamyuan/googling/blob/master/googling.gemspec), gemspec可以設定gem的一些資料和敘述

3. 之後如果有更新，便按以下步驟執行：

   在googling/lib/[version.rb]更新版本

[version.rb]:https://github.com/Iamyuan/googling/blob/master/lib/googling/version.rb

   (terminal)
        
    git add . 

    git commit -m "   "

    rake push 

    rake release →將新版本發佈到rubygems.org