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
        
### Locating Elements

### Filling Form Input

### Clicking Link and Buttons

### Running in Headless Mode

### Taking Screenshots

### Waiting 

### Using Dusk Pages

### Using Dusk Components

### Using Dusk Components
