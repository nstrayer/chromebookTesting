# Web Development On A Chromebook!

In an effort to join the #chromebookDataScience movement I have decided to see how easy javascript development is.

One would think when an opporating system is literally build on a webbrowser that developing in the language underlying that browser would be easy.

Turns out, it kinda is.

## Programs needed to do this.

[Web Server For Chrome](https://chrome.google.com/webstore/detail/web-server-for-chrome/ofhbbkphhbklhfoeikjpcbhemlocgigb?hl=en): This is a tiny little chrome app that spins up a very simple http server for you to run on your chromebook. Basically you just point it to a folder and you're good to go.

[Caret Editor](https://chrome.google.com/webstore/detail/caret/fljalecfjciodhpcledpamjachpmelml?hl=en): This is a simple text editor with syntax highlighting for the chromebook. It's super fast, has a nice file tree setup on the side and does what it needs to. You don't get some of the fancy features you might have come to expect in editors like Visual Studio Code or Atom (eslint etc) but it does a good job of clearly displaying your code and efficiently viewing your project's filestructure.

These are the bare minimum you need. You can throw your files into google drive and be done with it. I have done a few more things however that make switching a little easier from my usual workflow.

## Module Based Code.

The second you start building apps that are more than a few javascript commands modularizing your code makes your life much easier. Javascript ES6 has a fantastic module system for just this purpose. Unfortunately it's not enabled by default on chrome so you have to go to `chrome/flags` in your browser and then search for 'experimental web platform' and then click enable to use them. You may note that this is not exactly sustainable and if you're planning on deploying your app you're going to run into the problem of many user's not having es6 features enabled. This is a problem that I have not yet solved, but should be rather easy to overcome by simply running your code through a bundler like browserify/webpack etc once on a machine with node installed and throwing the bundle in your script tags when you're ready to deploy.

## Git support

The second thing you're most likely to want is git support for your projects. I personally am entirely dependent on git for all my development. I could not find a good git client chromebook app available (although it seems entirely possible) so I had to break the #chromebookDataScience creed a tiny bit and put my chromebook into developer mode to enable access to the commandline.

There are plenty of [fantastic](https://www.howtogeek.com/210817/how-to-enable-developer-mode-on-your-chromebook/) [tutorials](https://www.cnet.com/how-to/how-to-enable-developer-mode-on-a-chromebook/) on how to do this online but it's short enough of a process that I will describe it here.

1. Make sure you're okay with loosing all your local data on your chrombook. This processes wipes your data entirely but if you're truly embrasing the chromebook lifestyle this shouldn't be too big of an issue at all (cloud all the things!).
2. Press and hold the `escape` key, `refresh` (little spinny arrow key to the right of escape) and the `power` button all at the same time. Your chromebook will reboot and you'll see a big scary looking screen. You're doing well!
3. Press `control` + `d` to enable developer mode and then your chromebook should do a little install process for a bit and restart again.
4. After this next restart simple press `control` + `d` again and your chromebook will boot up now in developer mode! (Note that everytime you restart when in developer mode you need to press `control` + `d` to get past the boot screen.

Now that you've got your chromebook into developer mode you can install [`chromebrew`](http://skycocker.github.io/chromebrew/) (which is a fantastic port/clone of the mac package manager [`homebrew`](https://brew.sh/)) by entering the terminal mode (`control` + `alt` + `t`) and typing `shell` and pressing `enter`. From here you just run the command `wget -q -O - https://raw.github.com/skycocker/chromebrew/master/install.sh | bash`. This will install not only `chromebrew` but also ruby and git. So youre essentially ready to go.

To check if the command worked properly you should be able to run the following and get similar output.

```bash
$ which git
# >/usr/local/bin/git <- response should look like this.
```

## To Come

Instructions on start to finish simple website this way.