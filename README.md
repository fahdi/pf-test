## Tools and techniques used

Text editor used : Sublime Text 3
Started : 22nd September 2014, 22:53 
Version Control: Local Git repo with private remote on beanstalk
Continuous Integration: Beanstalk and SFTP
Package Management: Bower and Node Package Manager
Code Compiler and task manager: GruntJS
CSS Preprocessor: Less http://lesscss.org/
Syncronous testing on muliple devices using Ghostlab


## Tech Description

Since I am using bower to manage all project depencies including bootstrap, so iot6s very easy to upgrade any package and manage everything including mamnaging different versions of jQuery compatibl with respective versions of boostrap. Also I can manage any git ende point to use as a package manager. 

Bower website: http://bower.io/

Some example bower use cases are

# Registered package 

I use this for bootstrap and pakcaged jQuery ( and many other packages). There is a git end point which essentially makes every git repo to be used as bower package.

$ bower install bootstrap 

# GitHub shorthand

```$ bower install desandro/masonryz```

# Git endpoint 

```$ bower install git://github.com/user/package.git```

# I have used the follwing packages from github 

```
$ bower install --save FlexSlider
$ bower install --save fontawesome ( For the facebook icon only, rest are all glyphicons that come with bootstrap)
``` 


# URL

```
$ bower install http://example.com/script.js
```

## Note: 

Question: A possible question that why I am checking in the bower_components and not the node modules?

Short Answer: Because I am customising the bootstrap via less files and adding depencies to it. Since I am not making any changes to node modules, I don't need them in my repo. 

Long Answer: http://addyosmani.com/blog/checking-in-front-end-dependencies/


## Customisation of bootstrap

This web page uses twitter bootstrap. You need to have node and grunt installed f0r any bootstrap related modification.

# Installing Grunt

To install Grunt, you must first download and install node.js (which includes npm). npm stands for node packaged modules and is a way to manage development dependencies through node.js.

Then, from the command line:

1. Install grunt-cli globally with npm install -g grunt-cli.
2. Navigate to the root /bootstrap/ directory, then run npm install. npm will look at the package.json file and automatically install the necessary local dependencies listed there.

When completed, you'll be able to run the various Grunt commands provided from the command line.

Available Grunt commands

grunt dist (Just compile CSS and JavaScript)
Regenerates the /dist/ directory with compiled and minified CSS and JavaScript files. As a Bootstrap user, this is normally the command you want.

grunt watch (Watch)
Watches the Less source files and automatically recompiles them to CSS whenever you save a change.

grunt test (Run tests)
Runs JSHint and runs the QUnit tests headlessly in PhantomJS.

grunt (Build absolutely everything and run tests)
Compiles and minifies CSS and JavaScript, builds the documentation website, runs the HTML5 validator against the docs, regenerates the Customizer assets, and more. Usually only necessary if you're hacking on Bootstrap itself.

Troubleshooting
Should you encounter problems with installing dependencies or running Grunt commands, first delete the /node_modules/ directory generated by npm. Then, rerun npm install.

## Customisation 

Since bootstrap has a very detailed 'less' file structure, it was pretty easy for me to add and edit things and get them compiled via Grunt tasks. I used other bower compnents to be compiled into bootstrap to keep the number of webpage resources to minimum which helps with performance of the website. 


## Important Notes regarding grid layout changes for responsive layout

I undertanhd that the given mockup is based on 940px wide container design. This could be easily converted to a 940px layout with right sidebar being 300px wide, but:

# The BIG 'BUT'

Our requirements are simple:

- The candidate needs to code the page showed in "mockup.jpg". Details are provided in "briefing.jpg".
- Show HTML5, CSS3 and JS skills.
- Responsive design.
- The text doesn't matter, just use some Lorem ipsum.
- Up to the candidate to decide if he wants to use CSS, JS or both for some features (buttons, pictures, responsiveness, etc...).
- Original pictures to use are attached, the candidate is not allowed to modify them other than using CSS or JS.
- We only consider people that will browse this page with a recent computer (2 years old at max).
- The candidate can extract icons with the background from the jpeg file since we do not provide icons with transparency. Just code it as if the icons were transparent.

There are two important points that I considered here: 

- One being that you will be only considering people with only two year old computers at maximum. That lands us is a sweet ( and rather new) spot where we have wide screens and 940px as the maximum width for a layout becomes a design bug rather than a feature. 

- Second being that the design is responsive and it has not only to conform to smaller screen sizes i.e tablets, phablets and phones but to bigger and wider displays that are common these days.

- So there are new changes in bootstrap 3 to support wider screen sizes and 940px is default no more. 

- As Grids are the cornerstone of Bootstrap, and they’ve received a major overhaul in 3. The fixed grid system with no responsiveness is still using the old 940px wide container though.

- The grid system is now a single fluid and mobile-first grid.

- This means the grid now only uses percentage based widths instead of pixel-based widths. And now that it’s mobile-first, the grid starts stacked and scales “up” for larger screens.

- In the past, Bootstrap was targeting a 940px width page, perfect for most desktop-oriented websites. But mobile growth has only continued to explode, and more and more websites need great mobile experiences to take advantage of this growth. With this in mind, Bootstrap 3 adds a set of classes that let you control grid behavior on all different devices. For example, you can configure your grid to not stack on small screens, or only expand into columns on large screens.

# What changes with all the new updates to the old system

With that change, the span-* classes are gone, so old grids will not work with the new grid system.

The new grid system is powerful, and I expect it’s going to confuse a lot of people. Expect to spend a good amount of time in the grids section of the Bootstrap docs before you get the hang of it. I know I had to!


# IE7, who are you?

With Bootstrap 3, support for Internet Explorer 7 has been removed from the project. I will work on the html5 shiv but wn't use any modernizr for old browser support again for the follwing reason:

	"We only consider people that will browse this page with a recent computer (2 years old at max)."



## Five columns in footer

I used the follwing .less code.

    .col-md-2-4{
      .make-md-column(2.4);
       padding-left:7px;
       padding-right: 7px;
    }
    .col-sm-2-4{
      .make-sm-column(2.4);
       padding-left:7px;
       padding-right: 7px;
    }

## About slider

I moved the thumbnails on mobile and small screens to under the full image as it looked awkward and too small once moving to small screens. The desktop version is just like as in mockup. 


## About forms on the sidebar

The forms on sidebar use collapse feature of bootstrap with ease in transitions applied to the dovs containing them. 
