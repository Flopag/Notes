# Thread-Local Storage (TLS)

TLS allows each [Thread](Thread.md) (one TLS for per [Thread](Thread.md)) to have its own copy of data. It is useful when you do not have control over the [Thread](Thread.md) creation process (example : thread pool)

it is a sort of global (or static) variable