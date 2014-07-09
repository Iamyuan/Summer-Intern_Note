 [Markdown](http://daringfireball.net/projects/markdown/)
=========  
>Markdown的目標是實現「易讀易寫」, 語法全由標點符號所組成，並經過嚴謹慎選，是為了讓它們看起來就像所要表達的意思, 相較於HTML, 其更容易書寫、閱讀和修改，省去許多非必要的符號，更能專注在內容的編譯。


1. Words size
---------------
 
###※When you write down...
    
`###### H6最小` 

`# H1最大`

`標題`

`======`

`分隔線`

`-------`


###※What you see...

###### H6最小 

# H1最大  

標題
======

分隔線
------


2. Lists
-----------

清單項目標記通常是放在最左邊，但是其實也可以縮排，最多三個空白，項目標記後面則一定要接著至少一個空白或tab

換行時需要多空一行，在內容中才會顯示換行，如果中間無多空一行則會皆在上一行後面，但如果是list則不用刻意多空一行。

###※When you write down...

` 1. 空一格再開始打字`

` 1. 第二行即使不是2.也會按順序顯示`

` * 甚至是星號也可以` 

`+ +也可以`

 `- -也行`

 ` * 如果星號前多一個空格就是圓圈` 

 ` * 並且會接往後對齊`

 `+ +也可以是圓圈`
 
 `- -也行`


###※What you see...
 
1. 空一格再開始打字
1. 第二行即使不是2.也會按順序顯示
* 甚至是星號也可以
+ +也可以
- -也行

  * 如果星號前多一個空格就是圓圈 
  * 並且會接往後對齊
  + +也可以是圓圈
  - -也行

3. Links
-----------
[foo]: http://example.com/  "Optional Title Here"
[foo]: http://example.com/  'Optional Title Here'
[foo]: http://example.com/  (Optional Title Here)

###※When you write down...
 
[輸入欲顯示的內容1]：(網址1)

[輸入欲顯示的內容2]

`[foo]`

`[foo]: 網址foo  "Optional Title Here"`

`[foo]: 網址foo  'Optional Title Here'`

`[foo]: 網址foo  (Optional Title Here)`

[輸入欲顯示的內容2]：網址2

`<http://www.youtube.com/watch?v=6A5EpqqDOdk>`

###※What you see...
[輸入欲顯示的內容1]

[輸入欲顯示的內容2]

[foo]

<http://www.youtube.com/watch?v=6A5EpqqDOdk>
4. Emphasis
------------
星號數量會改變字體型式，內容前後加兩個星號為粗體字, 加一個星號或者底線則為斜體字。
###※When you write down...
 `*斜體字*`

 `_斜體字_`

`**粗體字**`

`***粗體字且粗體字***`

`*沒有任何改變`

`**斜體字*`

`*斜體字**`
###※What you see...
*斜體字*

_斜體字_

**粗體字**

***粗體字且粗體字***

沒有任何改變*

**斜體字*

***斜體字**

5. Image
----------
###※When you write down...
`![任意名稱](http://lh6.ggpht.com/-3EHhpkjOs6w/T6oovnaxF5I/AAAAAAAACY0/5rVys-SX_qU/logo-iShow-2_thumb.jpg?imgmax=800)`


`![紅寶石][任意名稱2]`

`[任意名稱2]:http://lh6.ggpht.com/-3EHhpkjOs6w/T6oovnaxF5I/AAAAAAAACY0/5rVys-SX_qU/logo-iShow-2_thumb.jpg?imgmax=800`

`![紅寶石](http://lh6.ggpht.com/-3EHhpkjOs6w/T6oovnaxF5I/AAAAAAAACY0/5rVys-SX_qU/logo-iShow-2_thumb.jpg?imgmax=800 "任意名稱3")`

###※What you see...
![任意名稱](http://lh6.ggpht.com/-3EHhpkjOs6w/T6oovnaxF5I/AAAAAAAACY0/5rVys-SX_qU/logo-iShow-2_thumb.jpg?imgmax=800)

![紅寶石][任意名稱2]
[任意名稱2]:http://lh6.ggpht.com/-3EHhpkjOs6w/T6oovnaxF5I/AAAAAAAACY0/5rVys-SX_qU/logo-iShow-2_thumb.jpg?imgmax=800

![紅寶石](http://lh6.ggpht.com/-3EHhpkjOs6w/T6oovnaxF5I/AAAAAAAACY0/5rVys-SX_qU/logo-iShow-2_thumb.jpg?imgmax=800 "任意名稱3")


6. Blockquotes
--------
大於符號（>）用來標記引言區塊，這和 Email 裡的使用方式很像，所以你要引用一段文字，讓他看起來有縮排的效果，只要在這段文字的開頭處加上 > 就可以了，像是

>####This is a very long line that will still be quoted properly when it wraps. Oh boy let's keep writing to make sure this is long enough to actually wrap for everyone. Oh, you can put Markdown into a blockquote.





Further Explanation
------------
大部分的語法都在[Markdown-Cheatsheet]中說明，若是Windows系統可以下載[markdownpad]來編輯Markdown, 而Mac則是下載[Mou]，其中有些差別，[markdownpad]無法編輯table，而且也無法在文章前後分別用三個 ` 來囊括一段文字(可以選擇不同的程式語言),除此之外大致相同。 
[Mou]:http://mouapp.com/
[Markdown-Cheatsheet]:https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet
[markdownpad]:http://markdownpad.com/download.html