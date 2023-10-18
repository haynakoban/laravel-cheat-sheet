# Laravel Packages Installation Cheat Sheet

This cheat sheet provides quick instructions for installing Laravel packages that can enhance your experience as a new Laravel developer. You can choose to install these packages as you explore Laravel and its capabilities.

## Table of Contents

1. [Introduction](#introduction)
2. [Prerequisites](#prerequisites)
3. [Installation Instructions](#installation-instructions)
   - [Fresh Laravel Project](#fresh-laravel-project)
   - [Package 1: Livewire](#package-1-livewire)
   - [Package 2: Tailwind CSS](#package-2-tailwind-css)
4. [Usage](#usage)
5. [Getting Help](#getting-help)

## Introduction

This cheat sheet provides guidance for new Laravel developers, helping you get started with a fresh Laravel project and then installing packages to explore Laravel's capabilities. These packages are not mandatory, but they can enhance your learning experience as you dive into Laravel.

## Prerequisites

Before you can start with Laravel and the packages, make sure you have the following prerequisites in place:

-   PHP (>=8)
-   Composer
-   MySQL
-   NodeJS
-   A code editor of your choice (e.g., Visual Studio Code)

## Installation Instructions

Follow the instructions below to set up a fresh Laravel project and then install Laravel packages that can enhance your experience as you explore Laravel. You can choose to install these packages based on your interests and learning goals.

### Fresh Laravel Project

Before diving into packages, let's start by creating a fresh Laravel project.

**Installation Steps**

1. **Install Laravel using Composer:**
   ```bash
   # create a new Laravel project via the Composer "create-project" command:
   composer create-project laravel/laravel your-project-name

   # Or, you may create new Laravel projects by globally installing the Laravel installer via Composer.
   composer global require laravel/installer

   laravel new your-project-name

2. **Navigate to your project directory:**
   ```bash
   cd your-project-name

3. **Generate an application key:**
   ```bash
   php artisan key:generate

4. **Configure your .env file with your database connection details.**

Now that you have a fresh Laravel project set up, you can proceed to install Laravel packages.

### Package 1: Livewire

[Livewire](https://laravel-livewire.com/) is a powerful package for building dynamic web applications in Laravel without writing any JavaScript. You can choose to install Livewire if you want to explore this approach.

**Installation Steps**

1. **Install Livewire via Composer:**
   ```bash
   composer require livewire/livewire

### Package 2: Tailwind CSS

[Tailwind CSS](https://tailwindcss.com/docs/guides/laravel#mix) is a utility-first CSS framework that simplifies the process of styling your web applications. With Tailwind CSS, you can create beautiful, responsive designs without writing extensive custom CSS. You can choose to install Tailwind CSS if you want to streamline your styling process in Laravel and explore its approach to efficient front-end development.

**Installation Steps**

1. **Install Tailwind CSS using Laravel Mix:**
   ```javascript
   npm install -D tailwindcss postcss autoprefixer
   npx tailwindcss init

2. **Configure your template paths:**

   Add the paths to all of your template files in your **tailwind.config.js** file.
   ```javascript
   /** @type {import('tailwindcss').Config} */
   module.exports = {
     content: [
       "./resources/**/*.blade.php",
       "./resources/**/*.js",
       "./resources/**/*.vue",
     ],
     theme: {
       extend: {},
     },
     plugins: [],
   }

4. **Install Laravel Mix via npm:**
   ```javascript
   npm install laravel-mix --save-dev

   // in your file directory check if have a file called webpack.mix.js,
   // If the file exist then ignore this otherwise create the file.
   touch webpack.mix.js
   
5. **Add Tailwind to your Laravel Mix configuration:**
   In your webpack.mix.js file, add tailwindcss as a PostCSS plugin.
   ```javascript
   const mix = require('laravel-mix');
   
   mix.js("resources/js/app.js", "public/js")
     .postCss("resources/css/app.css", "public/css", [
       require("tailwindcss"),
     ]);
    
6. **Add the Tailwind directives to your CSS:**
   Add the @tailwind directives for each of Tailwind’s layers to your ./resources/css/app.css file.
   ```css
   @tailwind base;
   @tailwind components;
   @tailwind utilities;

7. **Start using Tailwind in your project**
   Make sure your compiled CSS is included in the <head> then start using Tailwind’s utility classes to style your content.
   ```html
   <!doctype html>
   <html>
      <head>
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
   
         <-- Add the link below in your blade template -->
        <link href="{{ asset('css/app.css') }}" rel="stylesheet">
      </head>
      <body>
        <h1 class="text-3xl font-bold underline">
          Hello world!
        </h1>
      </body>
   </html>

8. **Configure your Package.json**
   In your package.json file, under the scripts property add the following:
   ```javascript
   "script": {
      "development": "mix",
      "watch": "mix watch"
   }

9. **Start your build process**
   Run your build process with npm run watch.
   ```javascript
   npm run watch
   
## Usage

Once you've installed these packages, you can explore and experiment with them in your Laravel project. Refer to the respective package's documentation for guidance on using their features.

## Getting Help

If you encounter any issues or have questions while using these packages or Laravel in general, don't hesitate to seek help from the Laravel community. You can ask questions on the [Laravel Forums](https://laracasts.com/discuss), [Stack Overflow](https://stackoverflow.com/questions/tagged/laravel), or [Laravel's official documentation](https://laravel.com/docs).



