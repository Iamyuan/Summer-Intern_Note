Test
=====
 * Minitest
 
 * Rspec
 
 * Factory_girl---building fack data to test 
 
 * Selenium
 
 * Capybara
 
 * JMeter
 
 
 Minitest
 --------
 
 ```
require 'minitest/autorun'
 
class TestCashRegister < MiniTest::Unit::TestCase
  def setup
    @register = CashRegister.new
  end
  
  def test_default_is_zero
    assert_equal 0, @register.total
  end
end 

```
 1. [How do i test wit minitest](http://rubylearning.com/blog/2011/07/28/how-do-i-test-my-code-with-minitest/)
 
 2. [minitest quick reference](http://mattsears.com/articles/2011/12/10/minitest-quick-reference)
 
 3.[ruby](http://www.railstutorial.org/book/beginning#sec-comments_for_various_readers)
 
 
 