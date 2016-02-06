# Coding Standard

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119][rfc2119].

This document MUST be considered a living document.

## 1. Files

### 1.1. Line endings

All PHP files MUST use the Unix LF (linefeed) line ending.

All PHP files MUST end with a single line, containing only a single newline (LF) character.

### 1.2. Encoding

PHP code MUST use only UTF-8. Files MUST NOT contain a BOM.

### 1.3. PHP Tags

PHP code MUST use the long `<?php ?>` tags or the short-echo `<?= ?>` tags in template files.

The short echo syntax MUST only be used in template (.phtml) files.

The opening PHP tag MUST only be added at the first line of the file in files containing only PHP.

The closing `?>` tag MUST be omitted from files containing only PHP.

### 1.4. Strict types

PHP code MUST use strict types. The strict type declartion MUST be on the first line of files with a space between the PHP opening tag and without spaces in the declaration.

    <?php declare(strict_types=1);

### 1.5. Indentation

Code MUST be indented by 4 spaces for each indentation level.

### 1.6. Keywords

The PHP types and keywords array, int, true, object, float, false, mixed, bool, null, numeric, string, void and resource MUST be in lower case.

## 2. Namespaces and Use Declarations

### 2.1. Namespaces

A namespace MUST be defined in any file containing PHP code which is not a template file.

There MUST be a blank line after the namespace definition.

### 2.2. Use Declarations

Functions, traits, interfaces and classes not in the global namespace MUST be imported using a use statement.

Use statements MUST NOT use the group syntax `use Foo\{Bar, Baz}`

Use statements MUST only contain a blank lines after all the use statements.

## 3. Classes, Interfaces and Traits

### 3.1. Instantiation

Parenthesis MUST always be present when instantiating a class.

    new Foo();

### 3.2. Extends and Implements

The `extends` keyword MUST come before any `implements`.

The `extends` and `implements` keywords MUST be declared on the same line as the class name.

Composition SHOULD be favored over inheritance.

### 3.3. Traits

Traits SHOULD NOT be used.

### 3.4. Visibility

Visibility MUST be declared on all properties and methods.

### 3.5 Properties

There MUST NOT be more than one property declared per statement.

### 3.6 Methods and Functions

Methods and functions MUST declare the arguments types when applicable.

Methods and functions MUST declare the return type when applicable.

Opening braces MUST go on the next line after the function or method declaration.

Closing braces MUST go on the next line after the body.

### 3.7. `abstract`, `final`, and `static`

When present, the `abstract` and `final` declarations MUST precede the visibility declaration.

When present, the `static` declaration MUST come after the visibility declaration.

The `static` keyword SHOULD NOT be used.

### 3.8. Method and Function Calls

When making a method or function call, there MUST NOT be a space between the method or function name and the opening parenthesis, there MUST NOT be a space after the opening parenthesis, and there MUST NOT be a space before the closing parenthesis. In the argument list, there MUST NOT be a space before each comma, and there MUST be one space after each comma.

Argument lists MAY be split across multiple lines, where each subsequent line is indented once. When doing so, the first item in the list MUST be on the next line, and there MUST be only one argument per line.

When chaining methods every method call MUST be on its own line.

When chaining methods the closing semi colon MUST be on its own line.

## 4. Control Structures

- There MUST be one space after the control structure keyword
- There MUST NOT be a space after the opening parenthesis
- There MUST NOT be a space before the closing parenthesis
- There MUST be one space between the closing parenthesis and the opening brace
- The structure body MUST be indented once
- The closing brace MUST be on the next line after the body

## 5. Strings

### 5.1. Quotes

Strings MUST use single quotes when there is no need for string interpolation.

Concatenation SHOULD ne prefered instead of string interpolation.

### 5.2. Concatenation

When concatenating there MUST be a space before and after the dot (`.`).

    echo 'foo' . 'bar';

## 6. Doc Blocks

### 6.1. File

### 6.2. Classes, Traits and Interfaces

### 6.4. Properties

### 6.3. Functions and Methods

## 7. Examples

### 7.1. Class

```php
<?php declare(strict=1);

namespace CodingStandard;

use Foo\Bar;
use Foo\Baz;

class Demo extends Bar implements Bar
{
    private $qux;

    public function __construct(string $qux)
    {
        $this->qux = $qux;
    }

    public function getQux(): string
    {
        return $this->qux;
    }
}
```

### 7.1 Template

```php
<?php declare(strict=1); ?>
<!DOCTYPE html>
<html>
    <head>
        <title><?= $this->title; ?></title>
    </head>
    <body>
        <h1>Coding Standard</h1>
        <ul>
            <?php foreach ($this->standards as $standard) { ?>
                <li><?= $standard; ?></li>
            <?php } ?>
        </ul>
    </body>
</html>
```

[rfc2119]: http://www.ietf.org/rfc/rfc2119.txt
