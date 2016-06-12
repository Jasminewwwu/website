% PyTA Help Documentation

This is some welcome text.

## Pylint errors {#pylint}

### R0101: Too many nested blocks {#R0101}

This error occurs when you have more than three nested blocks in your code.
This type of nesting is a sign that your function is too complex,
and should be broken down using helper functions.

Note: the nested block doesn't doesn't include function or class definition
as a block, so the example below is considered to have *four* nested blocks,
not five.

Note: we set a limit of three nested if blocks.

~~~~ {include="R0101_too_many_nested_blocks"}
~~~~


### R0102: Simplifiable if statement {#R0102}

This error occurs when you have an if statement that can be simplified
simply by using the value of the condition, rather than putting in extra
`True` and `False` literals.

~~~~ {include="R0102_simplifiable_if_statement"}
~~~~

The above example can be simplified to:

```python
def is_even(num):
    """Return whether <num> is even or odd."""
    return num % 2 == 0
```

### E1101: no-member {#E1101}

This error occurs when you access an object(variable, function...) for a non-exist
member. To be specific, you should not call a variable or function which is not
defined.

~~~~ {include="E1101_no_member"}
~~~~


### E1102: not-callable {#E1102}

This error occurs when you call an object which has not been inferred to a
callable object. In the following example, we should not call x() because x is
a variable which is not callable.

~~~~ {include="E1102_not_callable"}
~~~~


### E1111: assignment-from-no-return {#E1111}

This error occurs when you assign to a function call with the inferred function
does not return an object. This error is similar to E1128. In the following example,
f() does not return anything. As a result, x has no value if we assign x f().

~~~~ {include="E1111_assignment_from_no_return"}
~~~~


### E1120: no-value-for-parameter {#E1120}

We expect you to pass values for each argument (one for each) in a function.
In the following example, there should be three values passed to the function
instead of two.

~~~~ {include="E1120_no_value_for_parameter"}
~~~~

Corrected version
```python
get_sum(1, 2, 3)
```


### E1121: too-many-function-args {#E1121}

This error indicates you should pass values for each argument (one for each) in a
function. It is just the opposite to E1121. In the following example, more
values are passed to the function.

~~~~ {include="E1121_too_many_function_args"}
~~~~

Corrected version
```python
get_sum(1, 2)
```


### E1126: invalid-sequence-index {#E1126}

This error occurs when a sequence indexed with an invalid type. For example,
inside a list, you should always use the index with type integer.

~~~~ {include="E1126_invalid_sequence_index"}
~~~~

Corrected version

```python
a = ['p', 'y', 'T', 'A']
print(a[0])      # Error on this line
```


### E1127: invalid-slice-index {#E1127}

This error occurs when you use a slice index with wrong types. For example,
inside a list, whenever you want to get slices of this list, you should use the
indexs which are integers to indicate where to start and stop.

~~~~ {include="E1127_invalid_slice_index"}
~~~~

Corrected version

```python
a = ['p', 'y', 'T', 'A']
print(a[0:3])
```


### E1128: assignment-from-none {#E1128}

This error occurs when an assignment is done on a function call but the inferred
function returns nothing but None. This error is similar to E1111. In the
following example, f() return None. As a result, x has no value if we assign
x f().

~~~~ {include="E1128_assignment_from_none"}
~~~~


### E1130: invalid-unary-operand-type {#E1130}

This error occurs when the unary operand on the objects does not support this
type of operation. For example, we should never add string to integer.

~~~~ {include="E1130_invalid_unary_operand_type"}
~~~~


### E1131: unsupported-binary-operation {#E1131}

This error occurs when two operands do not support binary arithmetic operation.
For example, a dictionary could not be added to a list.

~~~~ {include="E1131_unsupported_binary_operation"}
~~~~


### E1135: unsupported-membership-test {#E1135}

This error occurs when you use an instance in membership test expression which
implement membership protocol. This error may be similar to E1101.
For example, if you want to check if a specific instance is inside another
object, please make sure the object has this kind of membership.

~~~~ {include="E1135_unsupported_membership_test"}
~~~~


### E1136: unsubscriptable-object {#E1136}

This error occurs when you subscript value which does not support subscription.
In the following example, b[0] could not work on 5.

~~~~ {include="E1136_unsubscriptable_object"}
~~~~


### E1305: too-many-format-args {#E1305}

This error occurs when you do not use one argument for a {} for format string.
This error is similar to E1121, meanwhile opposite to E1306.
In the following example, we give more values than the number of {}.

~~~~ {include="E1305_too_many_format_args"}
~~~~

Corrected version

```python
name = "Amy"
age = "17"
country = "England"

s = "{} who is {} lives in {}".format(name, age, country)
```


### E1306: too-few-format-args {#E1306}

This error occurs when you do not use one argument for a {} for format string.
This error is similar to E1120, meanwhile opposite to E1305.
In the following example, we give fewer values than the number of {}.

~~~~ {include="E1306_too_few_format_args"}
~~~~

Corrected version

```python
s = "{} and {}".format("first", "second")
```


### E1310: bad-str-strip-call {#E1310}

This error occurs when a constant string contains duplicate characters.

~~~~ {include="E1310_bad_str_strip_call"}
~~~~


### W1303: missing-format-argument-key {#W1303}

This error occurs when a format string that uses named fields does not
receive required keywords. This error is similar to E1120 and E1306. In the
following example, we should assign three values for bond, james and act.

~~~~ {include="W1303_missing_format_argument_key"}
~~~~


### W1305: format-combined-specification {#W1305}

This error occurs when a format string contains both automatic field numbering
(e.g. ‘{}’) and manual field specification (e.g. ‘{0}’).
For example, we should not use {} and {index} at the same time.

~~~~ {include="W1305_format_combined_specification"}
~~~~

Corrected version

```python
s = "{} and {}".format("a", "b")
```
or

```python
s = "{0} and {1}".format("a", "b")
```


### W1401: anomalous-backslash-in-string {#W1401}

This error occurs when a backslash is in a literal string but not as an escape.

~~~~ {include="W1401_anomalous_backslash_in_string"}
~~~~


### R0204: Redefined variable type {#R0204}

This error occurs when the type of a variable changes inside a method or a 
function. See the examples below.

~~~~ {include="R0204_redefined_variable_type"}
~~~~


### E0401: Import error {#E0401}

The module is unable to be imported. Check the spelling of the module name, or
whether the module is in the correct directory.

~~~~ {include="E0401_import_error"}
~~~~

There are other forms of import statements that may cause this error, for
example:

```python
import missing_module as foo  # this module does not exist.
```


### W0406: Import self {#W0406}

A module should not import itself. So for example, if the module is named 
`W0406_import_self` you cannot import it as follows:

~~~~ {include="W0406_import_self"}
~~~~


### W0404: Reimported {#W0404}

A module should not be imported more than once.

~~~~ {include="W0404_reimported"}
~~~~


### W0401: Wildcard import {#W0401}

Only import what you need. Wildcard imports (shown below) are generally 
discouraged because they add all the functions from the imported module into the
global namespace. Problems can occur when identical names conflict.

~~~~ {include="W0401_wildcard_import"}
~~~~

Rather than importing everything with wildcard '*', try importing specific
functions for example:

```python
from module_name import certain_definition
```

Or, if you need to import many functions, import them the following way, to
keep them separated in the namespace by module name. Then you can use the
function like, module_name.function_name

```python
import module_name
```

Or, you can create an alias for module names in the way below. Which can be
used like: dino.function_name

```python
import tyrannosaurus_rex as dino
```


### C0411: Wrong import order {#C0411}

Used when PEP8 import order is not respected (do the standard imports first,
then third-party libraries, then local imports)

~~~~ {include="C0411_wrong_import_order"}
~~~~


### C0413: Wrong import position {#C0413}

Imports should be placed at the top of the module above any other code 
(below the docstring).

~~~~ {include="C0413_wrong_import_position"}
~~~~


### C0412: Ungrouped imports {#C0412}

Imports should be grouped by packages.

~~~~ {include="C0412_ungrouped_imports"}
~~~~

Logically group the imports by same package name:

```python
from sys import byteorder  # same packages should be grouped
from sys import stdin  # same packages should be grouped
from math import floor
```


### C0410: Multiple imports {#C0410}

Don't import multiple modules on one line.

~~~~ {include="C0410_multiple_imports"}
~~~~

Do this instead:

```python
import sys
import math
```

Although, note that you can import multiple functions on a line, when they are
from the same module, for example:

```python
from sys import byteorder, stdin
```


### W1503: Redundant unittest assert {#W1503}

The first argument of assertTrue and assertFalse is a "condition", which should
evaluate to True or False. If the condition is a constant value, then it is
considered to always be True, since it cannot be anything different.

The warning message looks like:
Redundant use of (assertTrue or assertFalse) with constant value <your-constant>

~~~~ {include="W1503_redundant_unittest_assert"}
~~~~


### R0913: Too many arguments {#R0913}

The function or method is defined with too many arguments.

Note: the limit is 5 arguments.

~~~~ {include="R0913_too_many_arguments"}
~~~~


### R0912: Too many branches {#R0912}

The function or method has too many branches, making it hard to follow.

Note: the limit is 12 branches.

~~~~ {include="R0912_too_many_branches"}
~~~~


### R0902: Too many instance attributes {#R0902}

The class has too many instance attributes, try to reduce this to get a
simpler (and easier to use) class.

Note: the limit is 7 instance attributes.

~~~~ {include="R0902_too_many_instance_attributes"}
~~~~

One solution is to logically decompose into more classes, each with fewer 
instance attributes. Then we can use composition to access those attributes in 
another class.

```python
class Edible(object):
    """Example with fewer instance attributes."""

    def __init__(self):
        """Below are the instance attributes:"""
        self.bread = "Sourdough"
        self.liquid = "Water"


class Ownership(object):
    """Example with fewer instance attributes."""

    def __init__(self):
        """Below are the instance attributes:"""
        self.animal = "Dog"
        self.clothing = "Shirt"


class Description(object):
    """Example with fewer instance attributes."""

    def __init__(self):
        """Below are the instance attributes:"""
        self.colour = "Black"
        self.shape = "Circle"
        self.direction = "Up"
        self.number = 3


class Composition(object):
    """Example showing composition of other classes into instance attributes."""

    def __init__(self):
        """Construct instance attributes. For example, 
        self.ownership.animal is "Dog"
        """
        self.edible = Edible()
        self.ownership = Ownership()
        self.description = Description()
```


### R0914: Too many locals {#R0914}

The function or method has too many local variables.

Note: the limit is 15 local variables.

~~~~ {include="R0914_too_many_locals"}
~~~~


### R0915: Too many statements {#R0915}

The function or method has too many statements. You should then split it
in smaller functions / methods.

Note: comments do not count as statements

Note: the limit is 50 statements.

~~~~ {include="R0915_too_many_statements"}
~~~~


### C0111: Missing docstring {#C0111}

This is some helpful description of the C0111 error.


### C0102 Blacklisted name {#C0102}

This error occurs when a variable name is listed in the black list. The black 
list includes names:
 
 - foo
 - bar
 - baz
 - toto
 - tutu
 - tata

Students are expected to use meaningful variable names.

~~~~ {include="C0102_blacklisted_name"}
~~~~


### C0103 Invalid Name {#C0103}

This error occurs when a name does not follow the format associated with to its type (constant, variable ...). 

- Variable/Attribute/Method/Argument: All variable/attribute/method/argument names should be of the form: a lowercase letter followed by a lowercase letter or digit. The minimum number of characters should be 2 and the maximum should be 30.

- Constant: All constant names should be of the form: an uppercase letter followed by a uppercase letter or digit.

- Class: All class names should be of the form: an uppercase letter followed by a lowercase letter or uppercase letter or digit.

A special character accepted in all types of names is '_'.

~~~~ {include="C0103_invalid_name"}
~~~~


### C0111 Missing Docstring {#C0111}

This error occurs when a module, function, class or method has no docstring. 
Some special methods like __init__ don't require a docstring. Students are 
expected to write docstrings for every module, function, class and method.

~~~~ {include="C0111_missing_docstring"}
~~~~


### C0112 Empty Docstring {#C0112}

This error occurs when a module, function, class or method has an empty 
docstring like,

```python
"""
"""
``` 

Students are expected to write complete docstrings for every module, 
function, class and method.

~~~~ {include="C0112_empty_docstring"}
~~~~


### C0113 Unneeded not {#C0113}

This error occurs when a boolean expression contains an unneeded negation. If 
you are getting this error, the expression can be simplified to not use a 
negation.

~~~~ {include="C0113_unneeded_not"}
~~~~

The above can be modified to:

```python
def is_true():
    """
    @rtype: bool
    """
    temp = 5
    if temp <= 3:
        return False
    else:
        return True
```


### C0121 Singleton comparison {#C0121}

This is an error that occurs when an expression is compared to singleton values 
like True, False or None.

~~~~ {include="C0121_singleton_comparison"}
~~~~

The above can be modified to:

```python
def is_true():
    """
    @rtype: bool
    """
    temp = 5
    if temp is None:
        return False
    else:
        return True
```


### C0123 Unidiomatic type check {#C0123}

This error occurs when type() is used instead of isinstance() for a type check. 
Students are expected to use `isinstance(x, Y)` instead of `type(x) == Y`.

~~~~ {include="C0123_unidiomatic_typecheck"}
~~~~

The above can be modified to:

```python
def is_int(obj):
    """Check is the given object is of type 'int'.
    
    @type obj: object
    @rtype: bool
    """
    return isinstance(obj, int)
```


### E0101 Return in init {#E0101}

This error occurs when a return statement is used in the __init__ method. 
Students should not use a return statement in the  __init__ method as it is not 
directly called by your code. Instead, it is called by the code that 
initializes objects at runtime. 

~~~~ {include="E0101_return_in_init"}
~~~~


### E0102 Function redefined {#E0102}

This error occurs when a function, class or method is redefined. If you are 
getting this error, you should make sure all the functions, methods and classes 
you define have different names.

~~~~ {include="E0102_function_redefined"}
~~~~


### E0103 Not in loop {#E0103}

This error occurs when `break` and `continue` keywords are used outside loops. 
The keyword `break` is used to exit a loop early and the keyword `continue` is 
used to skip an iteration in a loop. Hence both the keywords only belong inside 
loops.

~~~~ {include="E0103_not_in_loop"}
~~~~


### E0104 Return outside function {#E0104}

This error occurs when a `return` statement is found outside a function or 
method. If you are getting this error, please check the indentation levels in 
your code carefully.

~~~~ {include="E0104_return_outside_function"}
~~~~


### E0108 Duplicate argument name {#E0108}

This error occurs if there are duplicate argument names in function 
definitions. If you are getting this error, please make sure all the arguments 
have distinct names.

~~~~ {include="E0108_duplicate_argument_name"}
~~~~


### W0101 Unreachable {#W0101}

This error occurs when there is some code behind a `return` or `raise` 
statement. This code will never be run.

~~~~ {include="W0101_unreachable"}
~~~~


### W0102 Dangerous default value {#W0102}

This error occurs when a mutable value such as a list or dictionary is given a 
default value in the function or method definition. It is dangerous to give 
mutable objects a default value only when the function/method modifies the 
argument. If you modify a default argument it will persist until the next call. 
Hence your "empty" list or dictionary will start to contain values on calls 
other than the first call.

~~~~ {include="W0102_dangerous_default_value"}
~~~~

Though the output to this is be expected to be:

```
[0, 1, 2, 3, 4]
[0, 1, 2, 3, 4]
```

The actual output is:

```
[0, 1, 2, 3, 4]
[0, 1, 2, 3, 4, 0, 1, 2, 3, 4]
```

If you want to avoid this situation then, you should use `None` as a default 
value. Students should be careful when assigning a default value to mutable 
objects.

### W0104 Pointless statement {#W0104}

This error occurs when a statement doesn't have any effect. This means that 
when the code for a statement is run, nothing is executed. This may not be what was 
intended.

~~~~ {include="W0104_pointless_statement"}
~~~~


### W0107 Unnecessary pass {#W0107}

This error occurs when a `pass` statement is used that can be avoided (or has 
no effect). If you are able to remove the `pass` statement without changing the 
effect of the program, then the statement is "unnecessary" and can be avoided.

~~~~ {include="W0107_unnecessary_pass"}
~~~~

In the above example, the `pass` statement is "unnecessary" as the program's 
effect is not changed if `pass` is removed.


### W0109 Duplicate key {#W0109}

This error occurs when a dictionary expression binds the same key multiple 
times.

~~~~ {include="W0109_duplicate_key"}
~~~~


### W0125 Using constant test {#W0125}

This error occurs when a conditional statement like an `if` statement uses a 
constant value for its test. This is bad as the conditional statements using a 
constant test always evaluate to the same value. In such a case, a conditional 
statement should not be used. 

~~~~ {include="W0125_using_constant_test"}
~~~~


### W0199 Assert on tuple {#W0199}

This error occurs when an "assert" statement is called like `assert (x, y)`. 
`assert` acting on a tuple always returns true if the tuple is non-empty, and 
false if it is empty. If you want to assert that two expressions are true then, 
you should use `assert x, y` instead.

~~~~ {include="W0199_assert_on_tuple"}
~~~~


### E0601: Used before assignment {#E0601}

This error occurs when you are using a variable before its assignment.

~~~~ {include="E0601_used_before_assignment"}
~~~~


### E0602: Undefined variable {#E0602}

This error occurs when you are using a variable that has not been defined.

~~~~ {include="E0602_undefined_variable"}
~~~~


### E0611: No name in module {#E0611}

This error occurs when you are trying to access a variable from an imported
module, but that variable name could not be found in that referenced module.

~~~~ {include="E0611_no_name_in_module"}
~~~~


### E0632: Unbalanced tuple unpacking {#E0632}

This error occurs when you have an unbalance unpacking assignment with a
sequence.

~~~~ {include="E0632_unbalanced_tuple_unpacking"}
~~~~


### E0633: Unpacking non sequence {#E0633}

This error occurs when the unpacked result is not a sequence. For example,
if in an unpacking assignment, the unpacked result is None, then it is not
a sequence and will raise this error.

~~~~ {include="E0633_unpacking_non_sequence"}
~~~~


### W0611: Unused import {#W0611}

This error occurs when you have a imported module that is unused in your code.

~~~~ {include="W0611_unused_import"}
~~~~


### W0612: Unused variable {#W0612}

This error occurs when you have a defined variable that is never used.

~~~~ {include="W0612_unused_variable"}
~~~~


### W0613: Unused argument {#W0613}

This error occurs when a function argument is never used in the function.

~~~~ {include="W0613_unused_argument"}
~~~~


### W0621: Redefined outer name {#W0621}

This error occurs when you are trying to redefine a variable name that has
already been defined in the outer scope. For example, this error will occurs
when you have a local name identical to a global name. The local name takes
precedence. but it hides the global name, makes it no longer accessible.

~~~~ {include="W0621_redefined_outer_name"}
~~~~


### W0622: Redefined builtin {#W0622}

This error occurs when you are trying to redefine/override a built-in function.

~~~~ {include="W0622_redefined_builtin"}
~~~~


### W0631: Undefined loop variable {#W0631}

This error occurs when a loop variable is possibly used outside the loop that
is undefined.

~~~~ {include="W0631_undefined_loop_variable"}
~~~~


### E0601: Used before assignment {#E0601}

This error occurs when you are using a variable before its assignment.

~~~~ {include="E0601_used_before_assignment"}
~~~~


### E0602: Undefined variable {#E0602}

This error occurs when you are using a variable that has not been defined.

~~~~ {include="E0602_undefined_variable"}
~~~~


### E0611: No name in module {#E0611}

This error occurs when you are trying to access a variable from an imported
module, but that variable name could not be found in that referenced module.

~~~~ {include="E0611_no_name_in_module"}
~~~~


### E0632: Unbalanced tuple unpacking {#E0632}

This error occurs when you have an unbalance unpacking assignment with a
sequence.

Note: Number of label(s) on the left side and number of value(s) on the right
side must always be the same in an unpacking assignment.

~~~~ {include="E0632_unbalanced_tuple_unpacking"}
~~~~


### E0633: Unpacking non sequence {#E0633}

This error occurs when the unpacked result is not a sequence. For example,
if in an unpacking assignment, the unpacked result is None, then it is not
a sequence and will raise this error.

~~~~ {include="E0633_unpacking_non_sequence"}
~~~~


### W0611: Unused import {#W0611}

This error occurs when you have a imported module that is unused in your code.

~~~~ {include="W0611_unused_import"}
~~~~


### W0612: Unused variable {#W0612}

This error occurs when you have defined a variable that is never used.

~~~~ {include="W0612_unused_variable"}
~~~~


### W0613: Unused argument {#W0613}

This error occurs when a function argument is never used in the function.

~~~~ {include="W0613_unused_argument"}
~~~~


### W0621: Redefined outer name {#W0621}

This error occurs when you are trying to redefine a variable name that has
already been defined in the outer scope. For example, this error will occurs
when you have a local name identical to a global name. The local name takes
precedence. but it hides the global name, makes it no longer accessible.

~~~~ {include="W0621_redefined_outer_name"}
~~~~


### W0622: Redefined builtin {#W0622}

This error occurs when you are trying to redefine/override a built-in function.

~~~~ {include="W0622_redefined_builtin"}
~~~~


### W0631: Undefined loop variable {#W0631}

This error occurs when a loop variable is possibly used outside the loop that
is undefined.

~~~~ {include="W0631_undefined_loop_variable"}
~~~~


### R0201: No self use {#R0201}

If a method (a function in a class) does not make use of the 'self' (or
first) argument, that means the function is not performing anything that
is related to the object itself. This means the function could be moved
outside of the class since none of the code inside makes use of anything
inside the class it's defined.

```python
class NoSelfUsage:
    def __init__(self):
        self.a = 42

    def no_self(self, num):
        num = num + 2
        print(num)

# You would fix it as follows by moving it outside the class:
def no_self(num):
    num = num + 2
    print(num)
```


### E0202: Method hidden {#E0202}

If you accidentally mask a method with an attribute, it can cause other code
to attempt to invoke what it believes to be a method, which will fail since
it has become a field instead (a variable). The syntax will cause the program
to raise an error.

```python
class Example(object):
    def field(self, num):
        return num
    def __init__(self):
        self.field = 'Masking the function with this string'

# If you call Example().field(num), it will yield an error since we masked it
```


### E0203: Access to member before definition {#E0203}

Before trying to use a member of a class, it should have been defined at
some point. If you try to use it before assigning to it, Python cannot
resolve the value and an error will occur.

```python
class MyClass:
    def __init__(self):
        print(self.a)  # Haven't defined self.a yet, can't use
        self.a = 5
```


### E0211: No method argument {#E0211}

Each method in a class needs to have at least one argument (which is usually
_self_). Python uses this to call methods, and the first argument is populated
with the object that is calling the method. This is what allows you to access
the calling object.

For example, the following two are equivalent:

```python
class A:
    def __init__(self):
        pass
    def method(self):
        print('Hi')

a = A()
a.method()   # Calls 'method' on object 'a' (this is how you should do it).
A.method(a)  # Also calls 'method' on object 'a' in a different way.
```

Therefore, if you do not provide any arguments, then Python does not know
how to pass the object to the method, and it will error out. To fix this,
put _self_ in the parenthesis for the method call.

```python
class MyClass:
    def __init__(self):
        pass
    def method():
        print('Missing argument for method definition')
```

### E0213: Self as the first argument {#E0213}

The first argument should be the exact word 'self'. This is not an error,
but it's such a common practice that this is considered an error. The
following is an example of a good, and bad example:

```python
class MyClass:
    def __init__(self):
        pass
    
    def methodA(something):  # Should be the argument 'self', not 'something'.
        pass

    def methodB(self):  # Good.
        pass
```


### E0239: Inheriting from a non-class {#E0239}

When you inherit, it must come from a class. If you use something that is
not a class, you won't be able to inherit from it. In the following example,
trying to inherit from a string is not allowed. While a string is a class,
this is passing in an object rather than the actual class itself.

```python
class newclass("str"):
    pass
```


### E0241: Duplicate bases {#E0241}

When inheriting, you should only specify a class once to inherit from,
multiple times is an error:

```python
class A:
    pass
    
class B(A, A):  # Only include A once to inherit properly
    pass
```


### E0302: Unexpected special method signature {#E0302}

Occurs when a special method (has underscores on both sides) does not have
the expected number of arguments. Python comes with an expected signature
of arguments, and if we create a method with the same name and a different
amount of arguments, it can cause exceptions to be raised.

```python
class A:
    def __init__(self):
        pass
    def __str__(self):  # Good, this is what is expected.
        return 'string'
        
class B:
    def __init__(self):
        pass
    def __str__(self, a):  # Bad, Python won't know what to put in 'a'.
        return 'string'
```


### E0701: Bad exception order {#E0701}

Except blocks are analyzed sequentially (from top to bottom) and the
block that meets the criteria for catching the exception first will be
used. This means if you have a more generic exception type before a
specific exception type, you will never trigger the code in the block
that is hidden by the generic exception.

It is also good practice since you want to narrow down the exception
type to be as specific as possible, since the more generic exception
may catch other types as well.

```python
def func(num):
    try:
        raise ZeroDivisionError()
    except Exception:
        print('This is always triggered')
    except ZeroDivisionError:
        print('Cannot ever be reached')

```


### E0702: Raising bad type {#E0702}

You have to raise an object that is an exception, you can't raise anything
like a number. If it does not descend at some point from an Exception class,
it should not be raised. To solve this issue, extend a new class from the 
Exception class, name it appropriately, and raise that.

```python
def raise_bad():
    raise 1
```


### E0704: Misplaced bare raise {#E0704}

When you call _raise_, it's usually to throw an exception. If you are inside
an 'except' block after you catch an exception, you can continue to pass on
the exception to later code. You may want to do this if your intention is to
capture a generated exception, then do something before passing it onwards
(such as maybe closing a file or some other sensitive operation that must
be done for program integrity that an exception would break). You can do this
by calling _raise_ on its own without a class as follows:

```python
def func():
    try:
        raise MyException()
    except MyException:
        # Do something important here (if needed).
        # Now, raise again what we just caught.
        raise
```

If you call _raise_ outside of an 'except' block, it can't work because there
is no exception to throw as seen in the following example:

```python
def bad_raise()
    # Bad example, needs to be in an 'except' block:
    raise
```

### E0710: Raising non-exception {#E0710}

You cannot raise an object that is not a descendant of Exception (which implies
being a child of BaseException). Anything you raise must at some point descend
from a class that inherits exception.

The solution is either to create your own exception, or to find a proper
exception that best describes the problem.

```python
class ClassWithNoExceptionParent:
    def __init__(self):
        pass

def throw_exception():
    raise ClassWithNoExceptionParent()
```


### E0711: Bad exception context {#E0711}

NotImplemented is intended to be a return value for methods, such as when you
create your own comparisons (ex: using __eq__), when what you actually want
is to throw the exception. Forgetting the suffix 'Error' is a common mistake
and do what you intended.

This is also related to another error where raising a non-exception is not
allowed.

```python
def call_exception():
    raise NotImplemented()
    # Should be: raise NotImplementedError()
```


### E0712: Catching non-exception {#E0712}

If your 'except' class uses a class that does not inherit from BaseException
at some point, then you are trying to catch an exception that is not a
well-defined exception. Your code should only try to catch exceptions
that extend from BaseException. Python requires you to raise exceptions
that derive from BaseException, and having a class type that does not extend
from this and being raised will cause a problem.

```python
# Notice how it does not extend from Exception (or BaseException for that matter)
class RandomClass:
    pass

def throw_exception():
    try
        n = 5 / 0  # Will throw a ZeroDivisionError
    except RandomClass:
        print('The above does not inherit from BaseException')
    except ZeroDivisionError:
        print('Will not be reached due to erroring out earlier')
```


### W0201: Attribute defined outside init {#W0201}

Any attribute you define for a class should be created inside the _init_
method. Defining it outside is considered bad practice as you might at
some point in the future introduce the same attribute in the class, and
any code that sets values outside may cause the program to break or
behave in unexpected ways.

Therefore you should always define your variables for the instance to
occur inside the _init_ method.

```python
class MyClass:
    def __init__(self):
        self.num = 1

c = MyClass()
c.other_num = 2  # This should be defined in __init__ first
```

You should do this instead:

```python
class MyClass:
    def __init__(self):
        self.num = 1
        self.other_num = 2
```


### W0211: Bad static member {#W0211}

Static methods are methods that do not operate on instances. Including
one inside a class can be done if you feel the logic belongs inside the
class and should be encapsulated by it for clarity, but static methods
mean they do not operate on classes, and therefore 'self' is very likely
a programming error unless you know what you are doing (and even then,
it is a bad practice).

When you make a static method, you should not name any variable 'self'
to avoid confusion.

```python
class C:
    def __init__(self):
        self.num = 5
    
    @staticmethod
    def method(self):  # Static methods do not have a 'self'
        self.num += 1
```


### W0212: Protected member access {#W0212}

Variables starting with underscores are a convention that means the field should
not be accessed outside of the calling class. This encapsulation is a
hint to the user that they should not change the field as it may be
critical to the proper functioning of the object. Any field that does
not have an underscore the user may interact with. Furthermore, this also
applies to methods with underscores since calling them may also cause
adverse affects.

If you want to access a field with an underscore, check to see why it is
an underscore and change it to not having an underscore if you discover
that it does not need to be hidden from the user. If you are using any
other class from another developer, then you are assumed to not tamper
with the internals of their class.

```python
class MyClass:
    def __init__(self)
        self._num = 42

# Should not be calling the underscore field:
c = MyClass()
print(c._num)
```


### W0232: No init method {#W0232}

The _init_ method is invoked when an object is created. Therefore you
should always have some kind of initialization method for your classes.
Note that this also applies to classes which have parents who do not
define their own _init_ methods.

If you find that you do nothing in the initialization method, then you
should ask yourself why you are creating the object in the first place.
If an object does not store any values and you want to pass around a set
of methods, consider having a function that returns a function or look
into making a class with purely static methods.

```python
def ClassWithNoInit:
    # Missing the __init__ method here
    
    def return_forty_two(self):
        return 42
```


### W0222: Different method signature {#W0222}

When declaring a method in a child class, if you're going to provide a
method name that is the same as a method in the parent class, both the
parent and child should not differ in their signature (the number of
arguments).

When you have a method with the same name, the arguments should stay the
same.

```python
class Parent:
    def __init__(self):
        self.num = 2
    
    def return_num(self, multiple):
        return self.num * multiple

class Child(Parent):
    def __init__(self)
        Parent.__init__(self)
    
    def return_num(self):  # Missing argument (to keep signature identical)
        return 42
```


### W0231: Super init not called {#W0231}

When inheriting from a parent, you need to call the parent's _init_
method using itself as a parameter (or use _super_ if you are more
familiar with that). The whole goal of extending a class is to be
a child of the class you extend from, and properties that the parent
sets in its constructor would not be propagated into the child you are
creating.

Therefore you must always call the parent initializer.

```python
class Parent:
    def __init__(self):
        self.num = 1

class Child(Parent):
    def __init__(self):
        Parent.__init__(self)  # You must have this
```


### W0233: Bad parent init {#W0233}

You should call the _init_ method of the parent, not some arbitrary and
unrelated class. To fix this, use the _init_ from the parent of the class
you are inheriting from.

```python
class ClassA:
    def __init__(self):
        pass

class Parent:
    def __init__(self):
        pass

class Child(Parent):
    def __init__(self):
        ClassA.__init__(self)  # Not a child of class A
```


### W0702: Bare exception {#W0702}

While you can catch any exception without specifying a class to catch after
the _except_ keyword, this is bad practice since it will mask other exceptions
that could appear which you do not want to catch, making your code not resilient
as it could be through .

Always provide the classes you expect to catch.

```python
def no_catching():
    try:
        raise TypeError()
    except:
        print('Requires an exception class')
```


### W0703: Exception is too generic {#W0703}

Similar to exception error W0702, if your exception is too generic then you
may end up burying errors since they will be always caught. Because of this,
you should not be using _except Exception_ as your except block since it can
catch exceptions you do not want caught.

```python
def generic_catch():
    try:
        a = 5 / 0
    except Exception:
        print('Got exception')
```


### W0705: Duplicate except blocks {#W0705}

When you list an exception to be caught, you should not list it again. Only
have one block for each exception. This does not include having child and 
parent exceptions, but rather it means don't have _exception MyException_,
and then later on when listing exceptions you have _exception MyException_
again.

```python
def repeat_except_blocks():
    try:
        raise Exception()
    except Exception:
        print('This is triggered')
    except Exception:
        print('Duplicate exception block')
```


### W0711: Binary op exception {#W0711}

The proper way to have an except block catch multiple exceptions is to have
the exception classes in a tuple. You can incorrectly write an except block 
in Python with multiple classes separated by an _or_ (see example). If you do
it the second way, the _or_ binary operator will not do what you think it does
-- in fact, the exception on the right side of the _or_ will not be caught and
proceed to be passed up the call stack (which likely will yield an uncaught
exception, terminating your program).

```python
class MyException(Exception):
        pass

class MyDoubleException(Exception):
        pass
        
def binary_capture():
        try:
                # Not caught, 'or' doesn't do what you think.
                # Need to do: except (MyException, MyDoubleException):
                raise MyDoubleException()
        except MyException or MyDoubleException:
                print('Will not detect MyDoubleException due to how "or" works')
```

## Custom errors {#custom}

### E9999: Forbidden imports {#E9999}

For your work in CSC148, we expect you to use only the Python language
features we have covered in lectures, or ones that we have explicitly
mentioned for an exercise/lab/assignment. If you are getting this error,
please check your code carefully.

```python
import copy   # Error on this line

x = [1, 2, 3]
y = copy.copy(x)
```


### E9998: Forbidden IO function {#E9998}

We do not expect to see I/O functions(input, open and print) in your code in
this course. If you are getting this error, please check your code carefully.

~~~~ {include="E9998_forbidden_io_function"}
~~~~


### E9991: Dynamic Execution {#E9991}

This error occurs when you use a dynamic execution of code. Use of builtin
functions exec(), eval() and compile() is not allowed.

~~~~ {include="dynamic_execution_example"}
~~~~
