
# Styleguide

<br />

### Extended from

- [PSR-2 PHP standard](http://www.php-fig.org/psr/psr-2/)
- [CakePHP standard](https://book.cakephp.org/3.0/en/contributing/cakephp-coding-conventions.html)
- [Airbnb JS](https://github.com/phenax/javascript)
- [Idiomatic CSS](https://github.com/phenax/idiomatic-css)




<br /><br />

### Code style

- **Naming**
    * Variable and method names must be camel cased. Class names must be pascal cased. For SCSS, use only dash casing for variable and mixins names and camel casing for function names.
    * No underscores for variable, method or class names(the only exception being '_' as a prefix for private and protected fields and methods).
    * CSS class naming will follow BEM and the directory structure for SCSS modules will follow atomic standard(atoms, molecules, quarks and utils).

- **Lines**
    * Line length must be less than 90 characters long.
    * Line soft limit is 120 characters
    * Leave a blank line after a block starts.
    * Curly brace opening or start of the block must be on the same line as the declaration.


- **Whitespaces**
    * Use 4 spaces for indentation.
    * Must not use extra spaces to align indentation.
    * Indent for new blocks, array elements, method chaining.
    * Must have spaces around operators.
    * No trailing whitespaces

:white_check_mark: Correct
```php

$hello = 'world';
$world = 'hello';

switch($someKey) {
    case 'hello': {
        $instituteID = 1;
        break;
    }
    case 'world': {
        $instituteID = 2;
        break;
    }
}

$query =
     $this->Institutes
        ->find()
        ->where([
            'Institutes.id' => $instituteID
        ]);
```

:x: Wrong
```php

$hello= 'world';
$world ='hello';

switch($someKey) {
  case 'hello': {
      $instituteID = 1;
        break;
   }
case 'world': {
       $instituteID = 2;
        break;
}
}

$query = $this->Institutes->find()
                          ->group('InstituteCourses.id')
                          ->where([ 'Institutes.id' => $iID ]);
```



<br /><br />


### Controllers
* Methods that are not a route must be declared private or protected and must be prefixed with an '_'


<br /><br />

### Model

#### Table
* Methods starting with find and list (Eg - `findUniversities()`, `listSubjects()`, `listBySubjects()`) must return a query object.
* Methods can also have by in the method name (Eg - `listBySubject(int $subjectID)`) if the emphasis is on the input rather than the output.
* Methods starting with get (Eg - `getSubscription()`) must return an Entity.

#### Entities
* lorem ipsum




<br /><br />

### Configuration

#### stupidsid.json
* This file has all the project related information.
* Fields - name, descriptions, root, directory[php, js, css, etc.], db_changes(All changes in the database columns that have not been reflected to the server or any of the developers machines), etc.

Example -
```json
{
    "Name": "yocket",
    "Description": "Yocket website",
    "Paths": {
        "css": "./static/css",
        "js": "./static/js",
        "php": "./src",
        "root": "."
    },
    "Meta": {
        "DB": {
            "messages": "Added table",
            "users": "Added column name varchar"
    	},
        "Branches": {
            "forex": "Forex service orders",
            "v-2.0.0": "The next version"
        }
    }
}
```
