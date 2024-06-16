# My Vulnerable Class Tracker
Forked From [here](https://github.com/tapan288/inertia-vue-tutorial) - on the basis of "I found tutorials to follow along to actually make sense of the code". So while none of this code is actually mine, and I haven't written any new features, I have followed along building it so I have a decent understanding of controllers/resources/api/middleware etc in the context of Laravel. Can't break the house if you don't know what its built from :^). 

# Installation
This application runs off Laravel/Vue with Inertia as the glue between them. Getting it going is fairly simple: 
1. In the root of the terminal - `composer install` - this installs all the add ons this project using (Breeze & Sanctum for auth, etc)
2. Copy `.env.example` file to `.env` of your root folder.
3. You *can* go and update env variables if needed - but we're running this off of a simple SQLite DB - so unless you have a reason to do otherwise, skip this step.
4. `php artisan key:generate` - This creates a random application key and sets it in the env file. This lets us encrypt data stored in sessions. 
5. `php artisan migrate --seed` - Setting this project up - there are a few migrations to add new tables (student, classes, sections) - we've also gone ahead and used some seeders to seed random data - you'll need to use this flag to get it going. Here it'll ask you to go ahead and create a sqlite DB.
6. `php artisan serve` - this will actually start up the laravel server and get it running on localhost. 
7. We'll also need to consider our front end dependencies - open a new tab in your terminal, run `npm install`
8. Run `npm run dev`

With both `artisan serve` running, and `npm`, we're off to the races. You can go ahead and dig in the db files (under UsersTableSeeder.php) for the admin user.

# Features
This application is fairly straight forward - it tracks students. You can add students and assign them into classes and sections, as well as edit and delete them. There's also a search function. It's built on Breeze, so if you've seen the UI, you know the basic scaffolding of dashboard/user profile comes out of the box. 

# Security Findings
I'll be breaking this section up into 2 parts: 
1) Initial findings and improvements - i.e. what I've found in this application thats questionable and how I would fix it (if anything). You can find this [here](link)
2) Make it worse - because a lot of security goodness already comes out of the box (looking at you Eloquent), we'll go ahead and introduce some common vulnerablities that aren't currently present, with explanation as to how these are exploited. You can find this [here] (link)