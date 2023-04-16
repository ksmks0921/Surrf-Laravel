<h1 align="center">Surrf 🏄‍♀️</h1>

## Introduction

Surrf, the opinionated Software as a Service Starter Kit that can help you build your next great idea 💰. Surf is fork off [Wave](https://devdojo.com/wave), and is built with [Laravel](https://laravel.com), [Voyager](https://voyager.devdojo.com), [TailwindCSS](https://tailwindcss.com), and a few other awesome technologies. Here are some of the awesome features ✨:

 - [Authentication](https://wave.devdojo.com/docs/features/authentication)
 - [User Profiles](https://wave.devdojo.com/docs/features/user-profiles)
 - [User Impersonation](https://wave.devdojo.com/docs/features/user-impersonation)
 - [Subscriptions](https://wave.devdojo.com/docs/features/billing)
 - [Subscription Plans](https://wave.devdojo.com/docs/features/subscription-plans)
 - [User Roles](https://wave.devdojo.com/docs/features/user-roles)
 - [Notifications](https://wave.devdojo.com/docs/features/notifications)
 - [Announcements](https://wave.devdojo.com/docs/features/announcements)
 - [Fully Functional Blog](https://wave.devdojo.com/docs/features/blog)
 - [Out of the Box API](https://wave.devdojo.com/docs/features/api)
 - [Voyager Admin](https://wave.devdojo.com/docs/features/admin)
 - [Customizable Themes](https://wave.devdojo.com/docs/features/themes)

## Deployment Issues

Surrf has not been tested with DigitalOceans APP platform. If you are using Surrf on DigitalOcean, don't be surprised if you experience issues. Docker has also not been tested and is not recommended.

## Installation

To install Surrf, you'll want to clone or download this repo:

```
git clone https://github.com/thinkverse/surrf.git project_name
```

Next, we can install Surrf with these **5 simple steps**:

### 1. Create a New Database

We'll need to utilize a MySQL database during the installation. For the following stage, you'll need to create a new database and preserve the credentials.

### 2. Copy the `.env.example` file

We need to specify our Environment variables for our application. You will see a file named `.env.example`, you will need to duplicate that file and rename it to `.env`.

Then, open up the `.env` file and update your *DB_DATABASE*, *DB_USERNAME*, and *DB_PASSWORD* in the appropriate fields. You will also want to update the *APP_URL* to the URL of your application.

```bash
APP_URL=http://surrf.test

DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=surrf
DB_USERNAME=root
DB_PASSWORD=
```

### 3. Add Composer Dependencies

Following that, we'll need to install all composer dependencies through the following command:

```php
composer install
```

### 4. Update Paddle Plans

To make sure your plan IDs are up-to-date, you'll need to update the [PlansTableSeeder](database/seeders/PlansTableSeeder.php).

To create a Paddle plan, navigate to your Paddle account and click on Catalogue » **Subscription Plans**.

<small>Use the [**sandbox-vendors.paddle.com**](https://sandbox-vendors.paddle.com) account for testing, and [**vendors.paddle.com**](https://vendors.paddle.com) account for production.</small>

Update the `plan_id`, `price`, `trial_days`, etc. in the plans seeder array.

```diff
    'name' => 'Basic',
    'slug' => 'basic',
    'description' => 'Signup for the Basic User Plan to access all the basic features.',
-   'plan_id' => '1',
+   'plan_id' => '12345',
    'default' => 0,
    'price' => '5',
    'trial_days' => 0,
```

### 5. Run Migrations and Seeds

We must migrate our database schema into our database, which we can accomplish by running the following command:

```php
php artisan migrate
```

Finally, we will need to seed our database with the following command:

```php
php artisan db:seed
```

That's it! You will now be able to visit your URL and see your Surrf application up and running. 🎉

## Watch, Learn, and Build

DevDojo got a full video series on how you can setup, build, and configure Wave, which is the underlying starter kit Surrf is made from. You can watch first few videos for free, and additional videos will require a [DevDojo Pro](https://devdojo.com/pro) subscription. By subscribing to a [DevDojo Pro](https://devdojo.com/pro) subscription you will also be supporting the ongoing development of this project. It's a win win! 🙌

[Click here to watch the Wave Video Series](https://devdojo.com/course/wave).

## Documentation

Checkout the [official Wave documentation here](https://wave.devdojo.com/docs).

## Support Wave

Give Wave and DevDojo support by following DevDojo on [Twitter](https://twitter.com/thedevdojo) and upvoting them on [Product Hunt](https://www.producthunt.com/posts/wave-2-0).

<p align="center"><a href="https://www.producthunt.com/posts/wave-2-0" target="_blank"><img src="https://cdn.devdojo.com/images/april2021/upvote-product-hunt-img.png" height="auto" width="auto"></a></p>
