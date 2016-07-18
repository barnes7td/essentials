Double and Single quotes are interchangeable, but have different abilities. Double quotes can do String interpolation. Singles cannot.

```ruby
adjective = "licky"
"Let me introduce you to my #{adjective} dog."
```

My rule is use doubles if by default for any new code you create, with the exception that if you add code to a file (like in Rails routes.rb file) that already exclusively uses Single Quotes, don't rock the boat.

There are also time in Rails views, where we have templates (views) with the purpose of processing out valid HTML. Since HTML needs quotes in it's syntax, sometimes we need our Ruby String (erb) inside the template to output the actual quote mark (either one). So it can be useful to mix the 2. 

```
"This is the 'best' day ever!"
```

If we used the same quote mark we started the String with Ruby would interpret it as the String is closed, unless we use the other kind of quote or we escape (which is done with a backslash `\`

```
"This is the \"best\" day ever!"
```

In fact Ruby when asked to show any String will always show it as double quotes with escape marks.
