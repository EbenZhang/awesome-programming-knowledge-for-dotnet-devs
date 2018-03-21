# Avoid having BOOL Function Parameters

A boolean can often make code more complex and less straightforward, it introduces a branch into your function and allows the callers to control the flow, which is usually confusing.

Also see: https://martinfowler.com/bliki/FlagArgument.html