# README

## Table of Contents

- [Setting Up Your Local Clone](#setting-up-your-local-clone)
- [Initial Installations](#initial-installations)
- [Install Gems and Migrate the Database](#install-gems-and-migrate-the-database)
- [Create the Database](#create-the-database)
- [Seed the Database](#seed-the-database)
- [Start the Server](#start-the-server)

## Setting Up Your Local Clone

Make sure you follow these steps in order to set up a clone on your local machine:

1. Fork the repo on to your own GitHub account. If you don't know how to do so, follow the GitHub documentation on how to [fork a repo](https://docs.github.com/en/get-started/quickstart/fork-a-repo).
2. Clone the forked repo to your local machine with one of the commands below. Be sure the `<your username>` text is replaced with your actual GitHub username, and the `<repo name>` with the actual repo name. You can also read the GitHub documentation on [cloning a repository](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository).

   ```bash
   # If you have SSH set up with Git:
   git clone git@github.com:<your username>/<repo name>.git
   # Otherwise for HTTPS:
   git clone https://github.com/<your username>/<repo name>.git

   # An example:
   git clone git@github.com:RandomUsername/css-exercises.git
   ```

## Initial Installations

Make sure you have Ruby and Ruby on Rails in your machine. Here are some great resources by [The Odin Project](https://www.theodinproject.com/) to get you started:

- [Installing Ruby](https://www.theodinproject.com/lessons/ruby-installing-ruby)
- Install Rails by following steps 1.1 and 1.2 in [your first Rails app](https://www.theodinproject.com/lessons/ruby-on-rails-installing-rails#your-first-rails-app)

> By the way, [The Odin Project](https://www.theodinproject.com/) is a great resource to learn about Full Stack Development. The community behind this project is really great and supportive, [I recently started to contibute](https://github.com/TheOdinProject/theodinproject/pull/4513) because I really like it and want to see it grow more and more 🚀

## Install Gems and Migrate the Database

Move inside the project directory:

```bash
$ cd secret_santa
```

Next, install the project's gems:

```bash
$ bundle install
```

**Note: If you are using **Postgres.App**, you may encounter an error installing the `pg` gem. This is likely due to a PATH issue where your pg_config is unable to be found. If you receive an error stating that this gem was not installed, you will need to run the following.**

```bash
find /Applications -name pg_config
```

Then save the path it returns, and then run:

```bash
gem install pg -- --with-pg-config=YOUR_PATH_HERE
```

**Note: If `bundle install` doesn't work and you get a "rbenv version" error of some kind, try running the following command to set your Ruby version in the project.**

```bash
rbenv local 2.7.2
```

## Create the Database

When bundle have finished installing everything, it's time to get the database set up. To create the database and load the schema:

```
$ rails db:create
$ rails db:environment:set RAILS_ENV=development
$ rails db:schema:load
```

## Seed the Database

Next you need to seed the database with some data like families, members and santa secret events.

```
$ rails db:seed
```

## Start the Server

```bash
$ bin/dev
```

Then visit [http://localhost:3000](http://localhost:3000) to view the app in your browser!
