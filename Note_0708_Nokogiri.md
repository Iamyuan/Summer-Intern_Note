[Nokogiri](http://nokogiri.org/)
=====

>Nokogiri 是 Ruby 上的一個 HTML, XML, SAX 的 parser(語法分析器), 他可以藉由 XPath or CSS3 selectors 來尋找 XML/HTML 中的 tag 功能強大，速度快速---轉自  [printf("I'm Eric Wang")-Nokogiri 簡介、教學](http://wwssllabcd.github.io/blog/2012/10/25/how-to-use-nokogiri/)


 Install
---------- 
  - 可參考[官網教學](http://nokogiri.org/tutorials/installing_nokogiri.html)
  - [個人推薦](https://blog.engineyard.com/2010/getting-started-with-nokogiri/)

HTML結構
------

    <html> 
       <head>
          <title>Hello!</title>
       </head>
       <body id="uniq">
          <h1>Hello World!</h1>
       </body>
    </html>

可知

Reponse.code
----

[reference](http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html)

Code
----
```
require 'nokogiri'

require 'open-uri'

doc = Nokogiri::HTML(open('response["location"]'))
 doc.css('h3 a').each do |node|
      puts node.text #title
      puts node.body
      puts node['href'] 
end
```


.class

\#id


['href']

[css](http://www.w3schools.com/css/)


[heroku](https://dashboard.heroku.com/apps)

http://ruby.bastardsbook.com/chapters/html-parsing/

http://www.freeformatter.com/html-formatter.html#ad-output


