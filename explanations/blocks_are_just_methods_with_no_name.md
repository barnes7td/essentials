# Blocks Are Just Methods with No Name

`.each` is just a internal for loop. Much of the time with for loops (like in JavaScript) we are just using the loop to do the same thing to all the elements in an Array. In a for loop we have to manually track the index (number of loops) and use that index to access the next element in the Array. Since that is such a common pattern, why not just say “FOR each item in this Array do this” instead of “For each number 0 through 5, take the item indexed in the Array at that number and do this”. 

See it is just a more concise pattern, because it is so common. Now you also seem to be confused about syntax and that is common. And it always centers around the “arguments” in the “pipes” `|variable|`. It may help to realize that blocks are just methods without names, called instantly (typically) and to not confuse blocks with regular methods, Ruby uses a different syntax for arguments. Parenthesis for methods `(var1, var2)` and Pipes for blocks `|var1, var2|`. And arguments are just the doorway (input) to your block or method from the outside. 

With methods, because methods are defined with the purpose of being called at a later point in a different location, the arguments are assigned at the method calling. With blocks, because they are used at the place they are defined and at the same location (typically), they get their arguments assigned from the method called immediately before. For instance 

```
array.each {|n| n + 2 }
```

The block `{|n| n + 2 }` get its argument(s) assigned by the `each` method before. And it, `each`, (somewhat) dictates how many arguments the block should take. In this case, we called `each` on an Array, which returns 1 item of the array every loop. So we define are arguments (in the pipes) accepting one argument. And just like methods, we can call the arguments whatever, we want. Though, I suggest you use something specific and descriptive. 

Now I lied a bit, because the method before the block could send you 3 inputs and you still only create your block with one argument, because that is all you need for your block. So truthfully the method doesn’t actually dictate anything (except what possible inputs you are given), but that is a different post.
