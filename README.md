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


### Browser Options

* Refresh the Page

        $browser->refresh();

* Navigate to the previous page.

        $browser->back();

* Maximize the browser window

        $browser->maximize();

* Resize the browser window

        $brwoser->resize($width, $height);

* Make the browser window as large as the content.

        $browser->fitContent()

* Move the browser window

        $browser->move($x, $y)

* Scroll screen to element at the given selector.

        $browser->scrollTo($selector)

* Take a screenshot and store it with the given name.

        $browser->screenshot($name)

* Store the console output with the given name.

        $browser->storeConsoleLog($name)

* Close the browser

        $browser->quit();

* Dump Page Source

        $browser->dump();

* Pause execution of test and open Laravel Tinker

        $browser->tinker();

* Stop Running the test but leave the browser open

        $browser->stop();

### Waiting 

* Pause for the given amount of milliseconds.

        $browser->pause($milliseconds)

* Wait for the given selector to be visible.

        $browser->waitFor($selector, $secondsOptional)

* Wait for the given selector to be removed.

        $browser->waitUntilMissing($selector, $secondsOptional)

* Wait for the given text to be visible.

        $browser->waitForText($text, $secondsOptional)

* Wait for the given link to be visible.

        $browser->waitForLink($link, $secondsOptional)

* Wait for the given location.

        $browser->waitForLocation($path, $secondsOptional)

* Wait for the current page to reload.

        $browser->waitForReload();


### Using Dusk Pages

* Generating a new page

        php artisan dusk:page PageName

* Visiting page

        $browser->visit(new PageName)

        $browser->visit(new PageName($arg))

* Page Methods

        $browser->visit(new PageName)
                ->pageMethod()

        //Already on page
        $browser->on(new PageName)
                ->pageMethod()

### Using Dusk Components

* Generating Component

        php artisan dusk:component ComponentName

* Using Components

         $browser->within(new ComponentName, function ($browser) {
                        $browser->componentMethod();
                    })
        



### Execute Javascript

        $browser->script('javascript')

### Handle Javascript Dialog

* Accept Dialog

        $browser->acceptDialog();

* Dismiss Dialog

        $browser->dismissDialog();

* Type-in Dialog

        $browser->typeInDialog($value);


### Dusk Resources & Packages

[Laravel Dusk Documentation](https://laravel.com/docs/master/dusk)

[Laravel Dusk Dashboard Package](https://github.com/beyondcode/dusk-dashboard)
