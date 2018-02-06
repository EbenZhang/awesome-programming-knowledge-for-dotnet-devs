# Avoid Variables with Hidden Meaning

> Another way in which a variable can be used for more than one purpose is to have different values for the variable mean different things. For example:
>
> * The value in the variable pageCount might represent the number of pages printed, unless it equals -1, in which case it indicates that an error has occurred.
> * The variable customerId might represent a customer number, unless its value is greater than 500,000, in which case you subtract 500,000 to get the number of a delinquent account.
> * The variable bytesWritten might be the number of bytes written to an output file, unless its value is negative, in which case it indicates the number of the disk drive used for the output.

From [Code Complete 2nd edition page 256](https://books.google.com.au/books?id=LpVCAwAAQBAJ&lpg=PA256&dq=code complete Avoid variables with hidden meanings&pg=PA256#v=onepage&q&f=false)

