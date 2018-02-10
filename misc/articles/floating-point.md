# Floating Point Accuracy

The fact that floating-point numbers cannot precisely represent all real numbers, and that floating-point operations cannot precisely represent true arithmetic operations, leads to many surprising situations for example `0.1f.Equals(0.1f)` may not be true.

It's usually fine to compare in terms of greater-than or less-than, but when you're interested in equality you should always consider whether what you actually want is near equality: is one number almost the same as another. One simple way of doing this is to subtract one from the other, use Math.Abs to find the absolute value of the difference, and then check whether this is lower than a certain tolerance level.

For more, see WikiPedia's [Floating-point Accuracy Problems](https://en.wikipedia.org/wiki/Floating-point_arithmetic#Accuracy_problems), C\# in depth's [FloatingPoint](http://csharpindepth.com/Articles/General/FloatingPoint.aspx) and [Decimal](http://csharpindepth.com/Articles/General/Decimal.aspx)

