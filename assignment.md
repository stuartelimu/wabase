# Laravel Assignment 

Laravel is a free and open source PHP web application framework. It features expressive and elegant syntax which makes development of common tasks used in the majority of web projects, such as authentication, routing, sessions, and caching easier.

## Installing Laravel
---
Laravel utilizes Composer to manage its dependencies. Go to https://getcomposer.org/ , download and install Composer on your machine.

There are two ways to install Laravel on your machine:
  - Via Laravel Installer : First, download the Laravel installer using Composer. In your terminal type this command 

    ` composer global require laravel/installer `

    Once that's done you will then add composer's system-wide vendor bin directory to your `$PATH` so the laravel executable can be located by your system. In Linux this directory is located at :
    ` $HOME/.composer/vendor/bin `

    NOTE: `$PATH` is an environmental variable in Linux and other Unix-like operating systems that tells the shell which directories to search for executable files.

    Once that's done, you can create a new laravel project with this command:

    `laravel new <project-name>`

    This command will create a fresh Laravel installation in the directory you specify. It will create a directory named `<project-name> ` containing a fresh Laravel installation with all of Laravel's dependencies already installed.



  - Via Composer Create-Project : Alternatively, you may also install Laravel by issuing the Composer `create-project` command in your terminal:

    `composer create-project --prefer-dist laravel/laravel <project-name> "5.8.*"`

## User Registration
---

To add user registration to your laravel project, you will run the following commands in the fresh laravel application that you created.

`php artisan make:auth && php artisan migrate`

These two commands will take care of scaffolding your entire authentication system!

## Model View Controller ( MVC )
---

MVC is a software architectural pattern that separates business logic from the rest of the user interface. It does this by separating the application into three parts: the model, view, and controller.

The Model represents shape of the data and business logic. It maintains the data of the application. Model objects retrieve and store model state in a database.

The view effectively provides the user interface element of the application. It’ll render data from the model into a form that is suitable for the user interface.

Controller handles the user request. Typically, users interact with view, which in-turn raises appropriate URL request. This request will be handled by a controller. The controller receives user input and makes calls to model objects and the view to perform appropriate actions.

These three components work together to create the three basic components of MVC.

## Laravel Collective
---

Laravel Collective is a package for Laravel 5.0+. It allows you to handle easy to manage forms in your blade files as well as intricate model binding to your forms.

To use this package, begin by installing it using composer, run this command in your terminal

`composer require laravelcollective/html`

NOTE: In the newer versions(v5.5+) of laravel this is all you will need to do. For older versions we have to do the following.

Add your new provider to the providers array of `config/app.php`:

```
  'providers' => [
    // ...
    Collective\Html\HtmlServiceProvider::class,
    // ...
  ],
```

Finally, add two class aliases to the aliases array of `config/app.php`:

```
'aliases' => [
    // ...
      'Form' => Collective\Html\FormFacade::class,
      'Html' => Collective\Html\HtmlFacade::class,
    // ...
],

```

### Example
---

In this example you will create a form with one input field and a submit button using laravel collective.

```
{!! Form::open(['url' => 'foo/bar']) !!}
    {{ Form::text('username') }}
    {{ Form::submit('Click Me!') }}
{!! Form::close() !!}

```
A POST method will be assumed by default; however, you are free to specify another method





 


