Learn `each` before you learn `inject`. All Ruby Enumerable methods are derived from `each`, that is why it is important to learn, first. `inject` is a more specialized method for holding a tally as you iterate over a collection, but learn to do with with `each` first, so that you can really understand what inject is doing for you.


## For example

```
def sum_numbers(array)
  count = 0
  
  array.each do |number|
    count = count + number 
  end

  count
end
```

is the same as

```
def sum_numbers(array)
  array.inject(0) do |number, count|
    count = count + number 
  end
end
```

is the same as

```
def sum_numbers(array)
  array.inject(0, :+)
end
```

Each new version is more concise, but more importantly built on the previous. You must understand the 1st version, to get the 2nd, and the 2nd to get the 3rd. See how inject, removes the need to manually track the count. Tracking the count (tally) is part of the functionality of `inject`, it is the reason that the `inject` method exist, because keeping a tally is a common pattern. And because it is common in an `inject` to just sum (or call a single method) on each element, the symbol to proc syntax was created `.inject(:+)` 

Being concise is great, but jumping to concise without understanding will leave gaps in your understanding, which will make you a dangerous coder. 

(BTW, thanks for your feedback about the exercises. Keep it coming)
