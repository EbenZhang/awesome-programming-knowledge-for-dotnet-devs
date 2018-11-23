# Postfix/Prefix increment operator

The return value of the prefix increment operation is the value of the operand after it has been incremented, whereas the postfix increment operation returns the value before it has been incremented. For both operation the operand itself is incremented.

```text
int c = 1;
Console.WriteLine(++c); // outputs 2, c is incremented to 2
Console.WriteLine(c++); // outputs 2 as well, but c is incremented to 3
Console.WriteLine(c);   // outputs 3
```

Whenever you're not sure, just put it in a separate statement.

