---
layout: default
---

internal state like @params, but without a chance to mess it up (can't instantiate it)

i don't want you to instantiate an operatoin without runnin because it will end up like an AR "container"

maybe think about operations the other way round: ask yourself what processing needs to happen when you browse to page of your app, or when you trigger a function like "follow user". that's the operation. the presentation of the result is a completely different story

don't confuse the operation with a UI specific thing like a calendar -> edit day


## What's A Concept?
calendar/
  day.rb # domain object/poro/twin
  month.rb
  stat.rb
  cell/
      month.rb
      week_row.rb
  views/
      month.slim
  edit_day.rb # operation

again, this is simply me thinking aloud. but i guess it's better to start of with a concept too big and then refine it instead of going the other way when you don't know your domain, yet.




## Validation

Just because validations now sit in the operation (or better: the form object) doesn't mean you can't use the model, for instance, to perform a uniquness validation. The opposite is the case: You may cleanly wrap the check and write in a table lock for a _real_ uniqueness validation in one atomic step.

