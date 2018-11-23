# Single Level of Abstraction

Single Level of Abstraction \(SLA\): Each method should be written in terms of a single level of abstraction.

All statements of a method should belong to the same level of abstraction. If there is a statement which belongs to a lower level of abstraction, it should go to a private method which comprises statements on this level. Doing so will result in smaller methods.

Copied from [here](http://principles-wiki.net/principles:single_level_of_abstraction), can also read One Level of Abstraction per Function in book Clean Code: A Handbook of Agile Software Craftsmanship page 36

