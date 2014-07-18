[Sinatra](https://github.com/sinatra/sinatra)
===========
[bin](https://github.com/Iamyuan/googling/blob/master/bin/googling)
-------
於整理程式之後，將module.md放在[googling/lib/googling]，使用時務必'require' for example:


    module Googling
      class Result
    attr_reader :title, :link, :description
    
    def initialize(attributes = {})
      @title = attributes[:title]
      @link = attributes[:link]
      @description = attributes[:description]
    end
      end
    end


將最後執行檔放入googling/bin的資料夾(重新建立)

    \#!/usr/bin/env ruby →language
    
    \# The command line Googling tool. → function
    
    $LOAD_PATH.unshift File.dirname(__FILE__) + '/../lib' → LOAD_PATH
    require 'googling' → 執行時的名稱
    \# ↓以下為真正執行的內容
    results = Googling.search(ARGV.join('+'))
    results.each do |result|
      puts ">>>> "
      puts result.title
      puts result.link
      puts result.description
    end
    

在設置bin之後，若要在terminal觀看結果，必須輸入 `ruby -I ./ filename.rb`, 以表示執行的LOAD_PATH


install
------
編輯sinatra檔案，然後在github設置一個相同名稱的repo

```gem install sinatra```

and run with

```ruby filename.rb```

可得一個localhost，即可檢查結果。


Start
--------

以下是主要的內容，包含了已寫完的googling,然後erb :search也

    require 'sinatra'
    require 'googling'

    get '/search' do 
      @q = params[:q]
      #得到欲搜尋的變數q
      @results = Googling.search(@q)
      #使用先前寫的googling來執行剩下的動作(search和parse) 
      erb :search
      #用erb語法在/search顯示結果(詳細敘述請看view)
    end

View
--------

* 建立一個search.erb的檔案 sinatra_googling/views/search.erb`,本頁只會顯示結果，不包含邏輯計算的部分
* 插入一個form, 然後將method改成get, 這樣所發送的就會在url中顯示，可做為紀錄和追蹤。若使用post則會將結果存在body之中。
* <%  %>之內顯示的就是ruby語法 之外的就是html


<h1>Enter the keywords</h1>
<hr size="5" align="center" noshade width="90%" color="0000ff"><br>

<form action="/search" method="get">
  <input type="text" name="q"/>
  <input type="submit"/>
</form>  
<table border=2>
<td colspan=2 align=center><h2><b>=Search Result=<b><h2></td>
<tr>
<% @results.each do |node| %>
  <td><b>Title<b></td>
  <td><b><%= node.title %></b></td>
  <tr>
  <td>Link</td>
  <td><a href="<%= node.link %>" target="_blank"><%= node.link %></a></td>
  <tr>
  <td>Description</td>
  <td><%= node.description %></td><tr>
 
<% end %>
</table>

[html](http://www.powmo.com/)

[URL編碼](http://www.w3cschool.cc/tags/html-urlencode.html)