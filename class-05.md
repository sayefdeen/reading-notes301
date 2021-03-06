# HEROKU

[Home](https://sayefdeen.github.io/reading-notes301/).

Heroku is a cloud platform as a service supporting several programming languages. One of the first cloud platforms, Heroku has been in development since June 2007, when it supported only the Ruby programming language, but now supports Java, Node.js, Scala, Clojure, Python, PHP, and Go.

## Set UP

in You command line (Ubunto).

`heroku login` : this will open your browser and make you ogin in in your heroku account (you have to create a new account in this platform).
This authentication is required for both the heroku and git commands to work correctly.

Before you continue, check that you have the prerequisites installed properly. Type each command below and make sure it displays the version you have installed. (Your versions might be different from the example.) If no version is returned, go back to the introduction of this tutorial and install the prerequisites.

        node --version
        v12.16.3

        npm --version
        6.14.4

        git --version
        git version 2.17.0

prepare a sample application that’s ready to be deployed to Heroku,To clone a local version of the sample application that you can then deploy to Heroku, execute the following commands in your local command shell or terminal:

        git clone https://github.com/heroku/node-js-getting-started.git

        cd node-js-getting-started

## Deploy the app.

Create an app on Heroku, which prepares Heroku to receive your source code.

        heroku create
        Creating sharp-rain-871... done, stack is heroku-18
        http://sharp-rain-871.herokuapp.com/ | https://git.heroku.com/sharp-rain-871.git
        Git remote heroku added

When you create an app, a git remote (called `heroku`) is also created and associated with your local git repository.

Heroku generates a random name (in this case tranquil-eyrie-67149.git) for your app, or you can pass a parameter to specify your own app name.

Now deploy your code:
git push heroku master

The application is now deployed. Ensure that at least one instance of the app is running:

        heroku ps:scale web=1

Now visit the app at the URL generated by its app name. As a handy shortcut, you can open the website as follows:

        heroku open

Or you can manually visit you website generate by heroku:

(Your random name that was generated).herokuapp.com

## View Logs

Heroku treats logs as streams of time-ordered events aggregated from the output streams of all your app and Heroku components, providing a single channel for all of the events.

        heroku logs --tail
