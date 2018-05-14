
## Stuff you need to do differently in Kotlin 
> As compared to good old Java days

* `@Rule` will not work like Java but you need to use `@Rule @JvmField` because otherwise it will complain that it needs to be public.

