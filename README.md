##Fibonacci's Code: Recursion and Memoization for Ruby Beginners##


__A method for basic Fibonacci term calculation:__

```language-ruby
def fibonacci(n)
  if n < 2
		n
  else  
		fibonacci(n-1) + fibonacci(n-2)
  end
end
```


__The Bad One; or, two separate methods for fibonacci calculation
and fibonacci-value storage:__

```language-ruby
def fibonacci(n)																	
  return n if n <= 1 															
    fibonacci(n-1) + fibonacci(n-2)												
end

def fib_store(n)
  fib_array = []																
  (0..n).each { |x| fib_array << fibonacci(x) }	
  fib_array
end  
```


__The Good One; or, a method that memoizes Fibonacci values as they are calculated:__

```language-ruby
@fib_hash = {}

def best_fib(n) 
  @fib_hash[n] = 																	
    if n <= 1																		
      n    																			
    else 
      @fib_hash[n] ||= best_fib(n-1) + best_fib(n-2)								
    end																			     
end
```






            