Hardware required:

1. A Mac (it's possible without one, but from what I've seen, it's pretty difficult to get working.)

Software required (all free):

1. OS X 10.6+
2. [Sublime Text](http://www.sublimetext.com/2) or another text editor
3. [Ruby on Rails](http://railsinstaller.org/en) obviously
4. [Postgres.app](http://postgresapp.com/) for your database

Create your RoR application

```bash
$ rails new myapp --database=postgresql
```

Change into your app directory

```bash
$ cd myapp
```

Create a controller to handle URL requests

```bash
$ rails generate controller welcome
```

##### Create the welcome page view

In file app/views/welcome/index.html.erb write:

```html
<h2>Hello World</h2>
<p>
  The time is now: <%= Time.now %>
</p>
```

In file config/routes.rb, on line 2 add:
```ruby
  root 'welcome#index'
```
Make sure you've created your database

```bash
$ rake db:create
```

And start up your server!

```
$ rails server
```
Now visit [your local server](http://localhost:3000/)

It should look pretty cool...
![Hella Sick Website](http://i59.tinypic.com/elqma.png)

The git stuff is all really easy

```bash
$ git init
$ git add .
$ git commit -m "init"
```

Login to Heroku

```bash
$ heroku login
Enter your Heroku credentials.
Email: schneems@example.com
Password:
Could not find an existing public key.
Would you like to generate one? [Yn]
Generating new SSH public key.
Uploading ssh public key /Users/adam/.ssh/id_rsa.pub
```

Deploy to Heroku

```bash
$ heroku create
Creating cryptic-eyrie-5775... done, stack is cedar-14
https://cryptic-eyrie-5775.herokuapp.com/ | https://git.heroku.com/cryptic-eyrie-5775.git
Git remote heroku added
```

Deploy all your code changes to Heroku (you will repeat this each time you make a change that you want to put on the website)

```bash
$ git push heroku master
remote: Compressing source files... done.
remote: Building source:
remote:
...
remote: Verifying deploy... done.
To https://git.heroku.com/cryptic-eyrie-5775.git
```

Visit the page

```bash
$ heroku open
```

[Get started with some Ruby on Rails guides!](http://guides.rubyonrails.org/v3.2.13/getting_started.html)