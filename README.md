Hardware required:
A Mac

Software required (all free):
OS X 10.6+
[Sublime Text](http://www.sublimetext.com/2) or another text editor
[Ruby on Rails](http://railsinstaller.org/en) obviously
[Postgres.app](http://postgresapp.com/)


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

```bash
$ rails new myapp --database=postgresql
```

```bash
$ cd myapp
```

```bash
$ bundle install
```

```bash
$ rails generate controller welcome
```

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
rake db:create
```

```
$ rails server
```
Now visit [your local server](http://localhost:3000/)

It should look pretty cool...
![Hella Sick Website](http://i59.tinypic.com/elqma.png)

Time to do git stuff

```bash
$ git init
$ git add .
$ git commit -m "init"
```

Deploying to Heroku

```bash
$ heroku create
Creating cryptic-eyrie-5775... done, stack is cedar-14
https://cryptic-eyrie-5775.herokuapp.com/ | https://git.heroku.com/cryptic-eyrie-5775.git
Git remote heroku added
```

Deploy the code

```bash
$ git push heroku master
remote: Compressing source files... done.
remote: Building source:
remote:
...
remote: Verifying deploy... done.
To https://git.heroku.com/cryptic-eyrie-5775.git
```