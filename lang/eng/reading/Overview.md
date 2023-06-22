I read the book called "*The Rust Programming Language*" and I'm gonna give my review on it.
Rust is the programming language which is positioned by the creators as the one empowering to build all kinds of software systems, ranging from low-level embedded software to dynamic web applications.

---

Here you can see the symbol of Rust Language which is *Ferris The Crab*.
It offers quite extraordinary ways to workaround common programming problems such as memory safety and concurrency. Unlike some popular languages, for instance, Python, Rust has static typing, that aims to data consistency ensurance.
Rust also has features that seemed unexpected to me like ownership concept. Ownership means that one value must have single variable that owns it. If another variable wants to access value behind it's owner it should borrow it using references. What was remarkable for me is that references in Rust has their unique lifetimes and sometimes programmers are enforced to specify lifetime parameters explicitly. Such lifetime parameters are used by Rust compiler to ensure that no value isn't dropped while there are references on it. Such feature guarantees that we won't get memory leaks and other funny troubles.
However, in this semester I wrote graphics engine as the course project. During this I wrote almost 4000 lines of code and got valuable and amazing experience with this language. Rust kind of changed my mind on how to writing programs better enforcing me to thinking more about how memory is allocated and freed and how to make my programs easy-extensible.