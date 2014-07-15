Googling
=========
Make requests
---------------
發送reguests的方法有很多以下舉例：

**1.
curl在的treminal環境下使用**

[可參考](http://rubylearning.com/blog/do-you-know-how-to-use-curl/)

[可參考](http://curl.haxx.se/docs/manpage.html)

**2.利用`gem instal _____`安裝gem, 舉例如下：**




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

整理程式
------------
解釋模組. class
