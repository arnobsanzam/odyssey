+++
title = "Unraveling the Mysteries of Java's String"
date = "2023-03-11"
author = "Syed Sanzam"
cover = "img/string-pulling.jpg"
description = ""

+++

Java is a popular programming language that is used to build a wide variety of applications, ranging from small
utilities to large-scale enterprise systems. One of the core features of Java is its treatment of strings, which are
used to represent text data. In Java, string literals are stored in a special area of memory called the JVM String Pool,
which is a cache of unique string objects. A string literal is a sequence of characters enclosed in double quotes (" ").
String literals are used to represent string values in Java programs.

The JVM String Pool is a mechanism that optimizes memory usage by reusing strings that have already been created. When a
string literal is encountered in a Java program, the JVM checks to see if an equivalent string object already exists in
the string pool. If a match is found, a reference to the existing object is returned. If not, a new string object is
created and added to the string pool.

Let's consider a testcase.

```
    @Test
    void firstTest() {
        String s1 = "abc";
        String s2 = "abc";
        String s3 = new String("abc");

        System.out.println(s1 == s2); // true
        System.out.println(s2 == s3); // false

        s3 = s3.intern();

        System.out.println(s2 == s3); // true
    }

```

In this example, s1 and s2 are both string literals with the value "abc". Since string literals are cached in the JVM
String Pool, s1 and s2 are both references to the same object in the string pool. Therefore, s1 == s2 evaluates to true.

On the other hand, s3 is created using the new keyword, which always creates a new object. Therefore, s2 and s3 are not
the same object, and s2 == s3 evaluates to false.

To make s3 reference the same object as s1 and s2, we can use the intern() method, which returns a canonical
representation of a string object. This means that if there is another string object in the JVM's string pool that has
the same value as the string object being interned, the interned object will be a reference to the existing object in
the string pool.

Now that we have an idea about how string pool in JVM works, let's take a look at a few more
examples.

```
    @Test
    void secondTest() {
        String s1 = "abc";
        String s2 = "def";
        String s3 = "abcdef";
        System.out.println(s1 + s2 == s3); // false
    }

    @Test
    void thirdTest() {
        String s1 = "abc" + "def";
        String s2 = "abcdef";
        System.out.println(s1 == s2); // true
    }
```

In `secondTest()`, s1 and s2 are concatenated at runtime using the + operator. When we compare s1 + s2 to s3, the result
is false. This is because at runtime, Java creates a new string object to hold the concatenated result, which is not the
same object as the "abcdef" string literal.

On the other hand, in `thirdTest()`, when the Java compiler encounters the expression "abc" + "def", it recognizes that
both operands are string literals and
therefore known at compile-time. In this case, the Java compiler can optimize the code by performing a process called
**constant folding**. Constant folding is a process of simplifying expressions at compile-time by evaluating constant
expressions. In this
case, the Java compiler replaces the concatenation expression "abc" + "def" with the string literal "abcdef". As a
result, s1 and s2 point to the same string object, and the output of s1 == s2 is true.

Let's take a look at one final (pun intended) example.

```
    @Test
    void fourthTest() {
        final String s1 = "abc";
        final String s2 = "def";
        String s3 = "abcdef";
        System.out.println(s1 + s2 == s3); // true
    }
```

When Java compiles your code, it tries to optimize your code as much as possible to make it run faster.
In Java, the final keyword is used to declare a variable that cannot be reassigned once initialized. This means that the
value of a final variable is known at compile-time, and the Java compiler can optimize code that uses final variables
accordingly.

In the fourth test case, both s1 and s2 are declared as final variables. Since their values cannot be changed at
runtime, the Java compiler knows their values at compile-time. This means that the concatenation expression s1 + s2 can
be evaluated at compile-time using constant folding.

Because the Java compiler can evaluate s1 + s2 at compile-time, it can optimize the code by replacing the concatenation
expression with the string literal "abcdef". As a result, both s1 + s2 and s3 now refer to the same string object, and
the comparison s1 + s2 == s3 returns true.

In this example, we've discovered that the final keyword enables the JVM compiler to apply certain optimizations. But is it
always necessary to use final with variables? That's a topic that sparks debate among programmers.

Some developers swear by using final everywhere, arguing that it ensures their code is more reliable and less prone to
bugs. Others, however, believe that going overboard with final can actually make code harder to read and maintain. They
contend that the modern JVM is incredibly clever and can perform many optimizations without any explicit directives.

So, while using final can be a useful technique to allow the JVM to optimize code, it's not necessarily a hard-and-fast
rule that applies in all situations. Ultimately, the decision to use final or not should be based on careful
consideration of the specific requirements and constraints of each particular situation.

That's all for now. Peace!

> Additional reading materials:
+ https://www.baeldung.com/java-final-performance
+ https://softwareengineering.stackexchange.com/questions/98691/excessive-use-final-keyword-in-java
