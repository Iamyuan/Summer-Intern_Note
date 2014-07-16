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