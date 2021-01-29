---
layout: post
image: 
  src: '/assets/images/numbers.jpeg'
  alt: 'binary numbers'
title: Representing numbers in computers
date:   2017-04-25 11:33:33
tags: programming computers
subclass: 'post tag-programming tag-computers'
categories: 'Tech'
disqus: True
navigation: True
---

One of the basic laws on which computers were designed and built over time is
**abstraction**. under the hood all we can see and interact with on computers
is just a bunch of electronic signals stored and manipulated in magnetic or
electric form.

Wether it is a great painting by Van Gogh or the latest Tom Hanks movie,
behind the scene it is just a collection of zeros and ones stored on a disk,
converted into a collection of colored dots and displayed on a screen.  

Any sort of interaction on computers involves a **Decoder/Encoder**, there
is a continuous process of translation going on between the screen/speaker and
the storage disk.

All of this was built on a simple mathematical system, the binary system, which
is used to represent any number by using only two symbols: **0** & **1**.

In this article I'm going to explain how numbers are stored in computers. touching
these topics:

* [Binary numbers](#binary_numbers)
  * [Two's complement](#twos_complement)
* [Floating Point](#floating_point)
  * [Converting a real number into a float representation](#real_to_float)


## Binary numbers {#binary_numbers}

Binary numbers are base 2, meaning that they are written using only two digits:
0 or 1. each digit is called a ***bit*** which is an abbreviation for **bi**nary
digi**t**.

The position of the bit determines its weight. in the decimal system (base 10),
the weight of each position to the left is an increasing power of ten.
starting from ones in the rightmost position ```10^0```, then tenth ```10^1```,
hundreds ```10^2```, and so on; the same logic applies to the binary system (base 2)
only with different weights, the rightmost position has the weight ```2^0```,
then ```2^1``` to the left of it, then ```2^2```, and so on.

For example the number:

>     100101

to convert this number to the decimal notation, we simply multiply each bit with
it's weight and add them all, so from right to left:

>     1*2^0 + 0*2^1 + 1*2^2 + 0*2^3 + 0*2^4 + 1*2^5

that is:

>     1 + 0 + 4 + 0 + 0 + 32 = 37

The problem with this system is that as it only uses two symbols to represent numbers,
numbers can occupy larger spaces than in decimal, in the previous example the number ```37```
needed 6 digits to be represented in binary.

In programming languages such as **C** or **Java**, there are different value types
that can hold numbers, the integer *int* type in most systems is 32-bit wide,
that can hold numbers from 32 bits of ZEROS to 32 bits of ONES, which represents numbers
from 0 up to 4,294,967,295 (2^32 - 1). and this is for positive numbers only,
to represent negative numbers as well, a *signed int* is used, along with a
technique called **Two's complement**.

#### Two's complement {#twos_complement}

for a successful representation of negative numbers, it must respect a simple
mathematical rule:

> when adding a negative number to it’s positive version, the result is zero.

The two's complement satisfies that rule, to represent the number ```-7```, start
with the number ```+7```, I'll use a 4-bit representation but the same
technique applies for 32-bit ints:

```7``` => ```4 + 2 + 1``` => ```1*2^2 + 1*2^1 + 1*2^0``` which, stored in a 4-bit
word is ```0111```.

By converting each bit of the number ```0111``` to it's inverse, we get ```1000```,
which is the **One's complement** of ```7```. adding one to the result, we get ```1001```,
which is the **Two's complement** of ```7```, aka ```-7```.

to verify the addition rule:

>      0111
>     +
>      1001
>     =
>      0000

the extra ***carry-out 1*** overflows out of bounds, hence we get ```0000``` as the result.


In a *signed int* all negative numbers has a ```1``` in it's leftmost bit. that
makes the range that a *signed int* can hold: ```−2,147,483,648``` *(-2^31)* to
```2,147,483,647``` *(2^31 - 1)*.

## Floating Point {#floating_point}

The previous examples demonstrated how integers are represented on computers, but
*int* is not the only value type available. to represent *Real numbers*, **C** and
other programming languages introduce the *float* and *double* types.

The problem with real numbers is the need to always represent them in memory
in a limited number of bits regardless of the location of the decimal point
(hence this method is called *floating* point), so that a float variable
(which is 32 bit-wide) can hold the number 100.5 or the number 1.005

floating point calculations are done using these equations:

**Float equation:** ```( -1 )^S * ( 1 + F * 2^-23 ) * 2 ^ ( E - 127 )```

**Double equation:** ```( -1 )^S * ( 1 + F * 2^-52 ) * 2 ^ ( E - 1023 )```

**S** ***(sign bit)***, **F** ***(fraction bits)*** and **E** ***(exponent bits)***
are the values stored in memory to represent a real number.

A *float* variable in **C** is 32 bits-wide, starting from right, the *fraction bits (F)*
occupies 23 bits from bit #0 till bit #22, the *exponent bits (E)* occupies 8 bits
from bit #23 till bit #30, the *sign bit (S)* is the leftmost bit (bit #31).

A more precise *double* variable is 64 bits-wide. the *fraction bits (F)* occupies
52 bits from bit #0 till bit #51, the *exponent bits (E)* occupies 11 bits from
bit #52 till bit #63, the *sign bit (S)* is the leftmost bit (bit #64).

for example the number: ```0 01111100 00000000000000000000000```

here the sign bit **S** is *0*{: style="color: red"}, meaning a positive number,
while the exponent bits **E** are ```01111100``` which is *124*{: style="color: red"}
in decimal, and the fraction bits **F** equals *0*{: style="color: red"}. replacing
these values in the float equation:

(-1) ^ *0*{: style="color: red"} * ( 1 + *0*{: style="color: red"} * 2^(-23) )
* 2 ^ ( *124*{: style="color: red"} - 127 ) = 1 * 1 * 2^(-3) = 0.125

another example: ```0 10000101 10010010000000000000000```

The sign bit **S** is *0*{: style="color: red"}, while the exponent bits **E** are
```10000101``` which is *133*{: style="color: red"} in decimal, and the fraction
bits **F** are ```10010010000000000000000```, or *4,784,128*{: style="color: red"}
in decimal. using the float equation:

(-1) ^ *0*{: style="color: red"} * ( 1 + *4784128*{: style="color: red"} * 2^(-23) )
* 2 ^ ( *133*{: style="color: red"} - 127 ) = 1 * 1.5703125 * 2^6 = 100.5

#### Converting a real number into a float representation {#real_to_float}

To convert a real number like ```15.375``` into a float, convert the integer part ```15```
normally to a binary as described [here](#binary_numbers). the result is ```1111```.

Then multiply the fractional part of the number ```0.375``` by ```2```, that will yield
a new real number, separate the integer part in the answer as a bit of the 23 binary
fraction bits **F** and multiply the fractional part of the answer by ```2``` again,
repeat until the answer is 0 or filling all the **F** bits.

>     0.375 * 2 = 0.75 = 0 + 0.75 => ```0```
>     0.750 * 2 = 1.50 = 1 + 0.50 => ```1```
>     0.500 * 2 = 1.00 = 1 + 0.00 => ```1```

So the decimal ```0.375``` becomes in binary ```0.011```, and the whole number
```15.375``` becomes ```1111.011``` in binary.

To store this number in memory, saving the information about the position of the decimal
point as well, insert this number in the equation, shift the binary point *n*{: style="color: red"}
places to the left so that the result becomes in the form *1.xxxx*{: style="color: red"}
and multiply the result by 2^*n*{: style="color: red"} to compensate, in this example
that means shifting the binary point *3*{: style="color: red"} places to the left
and multiplying the result by 2^*3*{: style="color: red"}:

>     1111.011 = 1.111011 * 2^3 = 1 + 0.111011 * 2^3

Comparing ```1 + 0.111011 * 2^3``` with the float equation
```( -1 )^S * ( 1 + F * 2^-23 ) * 2 ^ ( E - 127 )```

E - 127 = 3 => E = 130 => E is ```10000010```

F * 2^(-23) = 0.111011 => F is ```11101100000000000000000```

S is ```0``` (a positive number).

So ```15.375``` is stored in computers as ```0 10000010 11101100000000000000000```.

While floats and doubles do a great job representing real numbers, they are not
really precise, it is impossible to represent the wide range of real numbers in a
limited number of bits, so some numbers like ```0.1``` and ```0.33``` are only
approximated.
