## My First Amazing Music Guru App

We're going to modify this Ruby/Sinatra, HTML and CSS application to get an idea
of what web development is all about. The aim is for you to publish your very
own first web application to the web by the end of play.

# Install

* Sign up for EchoNest and follow the instructions: https://developer.echonest.com/account/register
* Log into your account screen and make a note of the API key. You'll need these
to make your app work.

* Create a folder to use for your upcoming project work, I suggest /projects

```
    cd ~
    mkdir projects
    cd projects
```

* Fork this repo by clicking the 'fork' button above
* Clone your forked repository, the URL is on your new bitbucket page.

```
    git clone ssh://git@bitbucket.org/wegotcoders/music-guru.git
```

* Change into your new project folder

```
    cd music-guru
```

* Install bundler

```
    sudo gem install bundler --no-ri --no-rdoc
```

* Install the ruby gems required for the application

```
   bundle
```

* Ensure that you have all the dependencies installed for EchoPrint https://github.com/echonest/echoprint-codegen

```
  Linux:
  sudo apt-get install ffmpeg libboost1.49-dev libtag1-dev zlib1g-dev
```

```
  Mac OSX:
  brew install ffmpeg boost taglib
```

* Sign up for Heroku: https://id.heroku.com/signup
* Setup Heroku toolbelt: https://toolbelt.heroku.com
* Login to Heroku by typing:

```
    heroku login
```

* Create an app on Heroku using:

```
    heroku create
```

* Make a note of the URL it gives you. Will be something like
http://cool-bananas-9212.herokuapp.com.

* Using the EchoNest API key from earlier, create a file in the working directory
called api.key and paste in the contents

```
    echo "YOUR_API_KEY" > api.key
```

* Set the Heroku config variable API_KEY so that the application knows your
EchoNest API key.

```
    heroku config:add API_KEY="YOUR_API_KEY"
```

* We're depending here on some binaries to process the signal form the audio file
and read the ID3 tags, ffmpeg and taglib. We'll use this command to pull them in automatically.

```
    heroku config:add BUILDPACK_URL=https://github.com/ddollar/heroku-buildpack-multi.git
```

* Push the example app from your cloned repository to your heroku repository:

```
    git push heroku master
```

* Cut+paste your heroku URL into your favourite web browser. You should see
the example app. Or simply run

```
    heroku open
```

# Development cycle

You should work through the TODO list below, using the following methodology:

1. Run the example application using the following command. You should see the web application running locally in your browser at
http://localhost:4567.

```
    ruby music_guru.rb
```

2. Make a change locally in your text editor.

3. If you make a change to the music_guru.rb, you'll need to restart the
server. You do this by killing the process using CTRL+C in your terminal window.

4. Once you're happy with your change and its working locally,
save your changes to your local repo using the following commands:

```
    git add .
    git commit -m "Write down briefly what you changed in here"
```

5. Test your changes on the Heroku URL you remembered from before. Make sure it
worked!

```
    git push heroku master
```

# TODO

Working in pairs, see if you can figure out how to do the following:

1. Change the title in the browser title bar to something more exciting.
2. Change the image to something more interesting or relevant to you.
3. Employ some of the CSS tricks you picked up during the morning's lecture to
pretty the page up a bit:

  * Try out some different fonts
  * Try out some different font sizes
  * Try out some different colours
  * Try changing the layout, so that the form questions appear to the right hand
  side of the image
  * Change the appearance of the submit button so that it is something that you
  would like to click
  * Add some nice background colour or a gradient
  * Improve the appearance of the flash notice

5. Prevent the form from being submitted sent unless the checkbox
is ticked. In that event, show a flash message to explain why the form was wrong.
6. Prevent the from from being submitted from being sent unless the user entered
a track into the upload form.
7. Change the app so that the user must provide their name and put their name in
 the thank you flash message that is displayed
8. In your pairs, come up with another use for this application and completely
modify it, changing the title, image and purpose of the submission form. Prizes
for the best application that get finished by the end of the day. Look at these
documentation sources for inspiration:

  * http://developer.echonest.com/docs/v4/
  * http://echowrap.com/

9. Invite your friends and family on the web to try your application by posting
your heroku URL on Twitter/Facebook.
10. When you have finished, submit a pull request so that I can review your work.
Info on how to do that is here: https://help.github.com/articles/using-pull-requests
