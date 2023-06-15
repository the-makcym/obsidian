- **Mutabilty** - property of variable corresponding to whether it can be mutated after assignment or not
- **Type inference** - Rust compiler feature that allows to omit type annotations in some cases when compiler can infer them unambiguously
- **Variable scope** - block of code where particular variable exists and therefore can be accessed there
- **Variables shadowing** - Rust compiler feature that allows to use variable name which is already occupied at the same variable scope
- **Reference** - address in memory that is guaranteed to point to existing and valid data
- **Dangling pointer** - address in memory which is supposed to contain some valuable data but it doesn't, for instance if the data was dropped
- **Memory safety** - state of being protected from various vulnerabilities related to accessing to memory like dangling pointers or indexing out of bounds
- **Ownership** - set of rules, that must be followed to make Rust program compiled and to ensure memory safety. Ownership demands one value is owned by only one variable and no other way around exists
- **Reference lifetime** - interval in overall program running time while reference is valid, i.e. it points to some valuable data
- **Reference lifetime specifier** - such feature of Rust that helps compiler to ensure memory safety through requiring programmer to specify how different reference lifetimes correlate
- **Slice** - special kind of reference which points to contigious sequence of elements in a collection rather than to the whole collection 
- **Scalar data type** - such data type that represents a primitive single value like an integer number, floating-point number or character
- **Compound data type** - such data type that combines several scalar data type instances to represent more complex entities  
- **Structure** - custom data type that packages meaningful set of values with predefined names
- **Enumeration** - custom data type that allows to enumerate possible variants of values and pick one of them at a time
- **Pattern matching** - the way of handling enumeration variants when programmer must exhaustively define the way of handling each possible variant 
- **Statement** - instruction performs some action and does not return any value
- **Expression** - like a statement it's instruction performs some action yet unlike a statement it's evaluated to some resultant value that should be handled
- **Loop labels** - Rust feature that allows giving loops names so it's possible to control loop execution from within it
- **Macro** - special kind of function that unlike usual functions evaluates at compile time and produces not a value but a code that can be further compiled
- **Crate** - smallest amount of code that the Rust compiler considers at a time 