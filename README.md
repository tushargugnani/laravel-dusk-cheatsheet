# laravel-dusk-cheatsheet
Cheat sheet for using Laravel Dusk

### Running Dusk Test

* Running All dusk test

        php artisan dusk
        
* Running single dusk test method

        php artisan dusk --filter testMethodName

* Running all methods of test class

        php artisan dusk --filter testClassName

### Creating Dusk Test

* Creating new dusk test

        php artisan dusk:make ExampleTest

* Creating new dusk test inside a folder

        php artisan dusk:make Folder/ExampleTest        
 
### Visiting URL 
 
* Visiting Home Page of URL

        $browser->visit('/')

* Visiting URL via named route

        $browser->visit(route('welcome'));

* Visiting External URL

        $browser->visit('https://www.google.com')
        
### Element Operation

* Click Element

        $browser->click('Element Selector');

* Clicking Link

        $browser->clickLink('Link Test Here');

* Pressing Button

        $browser->press('Button Test Here');

### Locating Elements

* Multiple Elements

        $browser->elements($selector)

* Single Elements

        $browser->element($selector)

### Form Input

* Input Box

        $browser->value($selector)
        //or
        $browser->type($selector)

        $browser->append($field, $value)

* Select Box

        $browser->select($field) //Random value

        $browser->select($field, $value)

* Radio Button

        $browser->radio($field, $value)

* Checkbox

        $browser->check($field, $optionalValue)

        $browser->uncheck($field, $optionalValue)

* Attach File

        $browser->attach($field, $path)

* TextArea

        $browser->keys($field, $value)

* CLear Field

        $browser->clear($field)

### Authentication

* Login

        $browser->loginAs('user@email.com');
        //Or
        $browser->loginAs($userObject);
        //Or User-id
        $browser->loginAs(3);
* Logout

        $browser->logout();

* Assert user authenticated 

        $browser->assertAuthenticated($guardOptional);

* Assert authenticated as user

        $browser->assertAuthenticatedAs($user, $guardOptional);

* Assert guest user

        $browser->assertGuest();


### Running in Headless Mode

### Taking Screenshots

### Waiting 

### Using Dusk Pages

### Using Dusk Components

### Using Dusk Components

### Execute Javascript

        $browser->script('javascript')

### Handle Javascript Dialog

* Accept Dialog

        $browser->acceptDialog();

* Dismiss Dialog

        $browser->dismissDialog();

* Type-in Dialog

        $browser->typeInDialog($value);