---
layout: slide
title: "RUB Markdown Template"
subtitle: "20.04.18"
description: A presentation for reveal.js using the RUB template and written in markdown only
theme: /theme/rub.css
highlight: /theme/hl/github.css
section_header: true
section_footer: true
transition: convex
---

# The RUB theme for reveal.js
## This is a html sample

---

# Sliding
## Even vertical stacking should work

as you will see below


# Largest
## Larger
### Large
#### Small
##### Smaller

Demo

Note: These are speaker notes!

---

# Lists
## Some stuff with lists

Was ist eigentlich mit <span>\\(\phi\left(5\right) = 4\\)</span>?


### Only unordered

- Level one
    - Level two
        * And Level three
        * with stuff
    - More
- And even more


### Unordered in ordered

1. Level one
    - Level two
        2. Level three
    - More
3. And even more


### Ordered in unordered

+ Level one
    1. Level two
        - Level three
    2. More
+ And even more


### Only ordered

2. Level one
    1. Level two
        6. And level three
        3. with stuff
    2. More
3. And even more

---

<h1>And this is inline html</h1>
<h2> Resulting in a list</h2>
<ul>
    <li>at least I hope so</li>
    <li>this should be second</li>
</ul>

---

<h2>And even more html</h2>
<ol>
    <li>In the Form of</li>
    <li>Numbered Lists</li>
</ol>

---

# Code Highlights
## We can even do code highlighting


### Some python code

```
def main():
    print("Hello World!")

# Start directly
if __name__ == '__main__':
    main()
```

Very important!!!


### Just a cup of Java

```
public class HelloWorld {
    /* Say hello to all our friends
     * out there in the wild! :)
     */
    public static void main(String[] args) {
        System.out.println("Hello World!");
    }
}
```

- This is cool
- And can be themed


### I can't C # #

```
#include &lt;stdio.h&gt;

// The entry point
int main() {
    printf("Hello World!\n");
    return 0;
}
```

