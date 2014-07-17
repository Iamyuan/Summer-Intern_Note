[Nokogiri](http://nokogiri.org/)
=====

>Nokogiri 是 Ruby 上的一個 HTML, XML, SAX 的 parser(語法分析器), 他可以藉由 XPath or CSS3 selectors 來尋找 XML/HTML 中的 tag 功能強大，速度快速---轉自  [printf("I'm Eric Wang")-Nokogiri 簡介、教學](http://wwssllabcd.github.io/blog/2012/10/25/how-to-use-nokogiri/)


 Install
------------ 
  - 可參考[官網教學](http://nokogiri.org/tutorials/installing_nokogiri.html)
  - [個人推薦](https://blog.engineyard.com/2010/getting-started-with-nokogiri/)


Remember to require
-----------

`require 'nokogiri'`

`require 'open-uri'`


Fetch the documents 
--------

**從檔案**
    
    html_doc = Nokogiri::HTML( File.open("test.html") )
    xml_doc  = Nokogiri::XML( File.open("test.xml") )
    
**從URL**

    
    url = 'http://www.google.com/search?q=sparklemotion'
    doc = Nokogiri::HTML(open( url ))

P.S 利用ruby(gem or core)得到url


Parse the content
-------------------
    doc = Nokogiri::HTML( url )

可銜接以下不同編輯需求(有xpath及css兩種，在此以css為例)

**<取出標籤h1 以及 h3底下的a>**

* tag_h1 = doc.css('h1')

* h3_a =doc.css('h3 a')

**<分辨標籤底下的class和id>**

* h3.class → class用 . 表示

    x =doc.css('h3 a.x')

* h3\#id → id用 \# 表示

     y =doc.css('h3 a#y')

**<取出標題內容>**

title = doc.text

**<取出tag >**

link = doc['href']


Others
--------
1. 可用.map {|x| x }將每個結果做不同的編譯
2. 如果href 取出來並非以http://開頭，可用.to_s.sub!("欲替換的內容","")
3. 有關內容字體字型的編碼問題可參考[編碼學問大](http://blog.sammylin.tw/nokogiri-encoding/)
    → require 'iconv'  別忘記了
4. 可重複使用.css()以篩選欲編輯的內容  ex : doc.css('li.g').css('h3 a.k')
5. 當輸入任何內容欲[轉成url格式](http://stackoverflow.com/questions/6714196/ruby-url-encoding-string)時, `gem install uri_handler`  然後利用.to_uri即可 ex: a = "2*&^%$$".to_uri