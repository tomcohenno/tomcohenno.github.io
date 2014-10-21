---
layout: post
title: "RRRRRRRspec"
date: 2014-10-20 18:04:34 -0400
comments: true
categories: 
---
![alig](http://www.quickmeme.com/img/d3/d3bd7d4e0150df19d47a9f8b773848f0bb8e50d9f1c99ace7b4b4f38245ff8c7.jpg)

# An introduction to RubyTest


Given the massive number of times that we need to run Rspec, I found it helpful to install a package for Sublime that would let me run tests without having to leave the program.  This program, RubyTest, is an add-in to Sublime and is installable directly through the program.  

### Step 1 - Install Package Control

If you haven't already, you need to install Package Manager for Sublime.  It's really easy.  Just open a Sublime document and hit command + shift + P.  Type in "Install Package" (or at least enough of the letters...) and hit enter.

<figure>
   <img class="center" src="/Users/TomCohenno/Documents/repos/octopress/source/images/install.png" />
   <figcaption>(Not an actual Ruby method.)</figcaption>
</figure>

![hello](/Users/TomCohenno/Documents/repos/octopress/source/images/install.png)

After Package Control is installed we are ready to install the actual package that will be running our Rspec tests - RubyTest.
	
### Step 2 - Download RubyTest 

This is done in the same way that we installed Package Control.  From within Sublime, hit command + shift + P again to bring up our dialog box.  Type "RubyTest" and hit enter to install.  

![rubytest](/Users/TomCohenno/Documents/repos/octopress/source/images/rubytest.png)

### Step 3 - Tell RubyTest about RVM

When RVM is installed it slightly modifies your Ruby directory structure, and RubyTest needs to be made aware of this in order to work.  Thankfully the fix is relatively straightforward.  Since Sublime uses various text files to manage package settings, we need to modify the User settings for RubyTest. 


First, open Sublime and go to Sublime Text -> Preference -> Package Settings -> RubyTest -> Settings - User

![find settings](/Users/TomCohenno/Documents/repos/octopress/source/images/find_settings.png)

In the empty text file that appears, copy/paste the following code in order to inform Sublime about RVM.  

```
{
	"check_for_rvm": true
}
```

Now save, close the file, and quit Sublime.  

### Step 4 - Using RubyTest

Using RubyTest is relatively straightforward, however, you must open documents from the terminal.  This is nothing diferent than how most of us open documents already.  Just type `subl .` in your directory to get started.  

There are two main options when you run Rspec:

1 - Run all tests at once - Right click anywhere in your rspec document and go to RubyTest -> Run all tests.

This will run all rspec tests and output the results in the test panel. 

![all_tests](/Users/TomCohenno/Documents/repos/octopress/source/images/rspec all.png)
	
2 - Run only a specific test - In the rspec file, right click on the specific test that you want to run and click "Run single test".  This will run the test(s) that fall under the context of the rspec.  

For example, in the screen below, only the spec 'has a title' will run. However, if the cursor had been on line 14 instead of 17, running "run single test" will actually run all tests that fall under the parent context of 'Movie.new'.  

![rspecfail](/Users/TomCohenno/Documents/repos/octopress/source/images/rspec_example.png)

### Step 5 - Find out how to run tests vertically and let me know how to do so :)