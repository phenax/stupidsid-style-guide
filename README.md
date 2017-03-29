
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

- **Lines**
    * Line length must be less than 90 characters long.
    * Line soft limit is 120 characters
    * Leave a blank line after a block starts.
    * Curly brace opening or start of the block must be on the same line as the declaration.

```php

```


- **Indentation**
    * Use 4 spaces for indentation.
    * Must not use extra spaces to align.
    * Indent for new blocks, array elements, method chaining.

:white_check_mark: Correct
```php
switch($someKey) {
    case 'hello': {
        $instituteID= 1;
        break;
    }
    case 'world': {
        $instituteID= 2;
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
$query = $this->Institutes->find()
                          ->group('InstituteCourses.id')
                          ->where([ 'Institutes.id' => $iID ]);
```



<br /><br />


### Controllers
* lorem ipsum


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
    "name": "stupidsid-admin",
    "description": "Stupidsid admin panel",
    "root": ".",
    "directory": {
        "php": "src",
        "js": "static/js/",
        "css": "static/css/"
    },
    "db_changes": {
    	"notifications": "Added notifications table (id, name, content, sent_at, number_of_users)",
    	"institutes": "app_id column added(TEXT)"
    }
}
```
