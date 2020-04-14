---
layout: post
title:  Create a website in Corona times
date:   2020-04-10 12:00:00 +0300
image:  post01.jpg
tags:   Code
---
## Motivation.
Perhaps you are at home wondering that you cannot go out or asking yourself when this social isolation will finally get to an end. Even deeper, your mind wonders that you cannot do your job because it requires you to be on site. You already made all home organization that you planned once the time comes you would do. But it is still not enough and you feel like doing something else, something good to the society... You like to have a special place to communicate your project to the world... So, this post is for you!

I will introduce you through this tutorial how you can let your legacy to the world, by showing you __how to create a website__ without big need for programming knowledge (just a bit, but it won't hurts, I promise 😉), and so deliver your message, nicely, to your audience.

<br/>

## Creating a website with Jekyll and GitHub.

There are several ways how you can create your own blog or website. I decided to use <a href="http://jekyllthemes.org/">Jekyll themes</a> and host it on GitHub with <a href="https://pages.github.com/">GitHub Pages</a>. However, there are some alternatives as, <a href="https://blog.getpelican.com/">Pelican</a>, <a href="https://gohugo.io/">Hugo</a>, and others with even less coding requirements, such as <a href="https://br.wordpress.com/">WorldPress</a> and <a href="https://www.dokuwiki.org/dokuwiki">Dokuwiki</a>. But this is not the only way to create your website, for instance, you could do it also using __Blogdown__ and R, <a href="https://www.samples-of-thoughts.com/2018/how-to-make-a-website-using-blogdown-and-github/">here</a> is a good tutorial.

__What do we need to start?__

I am assuming from now that you have none of these things set up yet. Otherwise jump to **session 3**

**1. Downloading Git bash:** It allows us to run the command line 🤯 to connect local folders to GitHub repository 😵. Hang on! Guys don't worries with these terms, slowly we come along with it. Believe me.

**2. Installing Ruby and Jekyll:** It creates an environment for Jekyll runs since Jekyll is built in Ruby.

**3. Installing Jekyll Themes:** This is what will give the website a nice look. It is the layout of your website,

**4. Setting up a GitHub account:** It allows us to give the website a name.

**5. Create a GitHub repository:** It allows people to find you. This step publish your website by bring it to public server (GitHub).


![]({{ site.baseurl }}/images/post011.jpg)

So, let's get to start!!!

<br/>
### 1. Downloading and installing Git.

You can <a href="https://git-scm.com/downloads">download Git</a> and start installation.
For more information on how to install it, access link above.
If you are familiar with the command line, open command prompt and just run these lines bellow:

<br/>
__1.1 Git for Windowns:__ better way is to <a href="https://git-scm.com/downloads">download the driver</a> and install it.

<br/>
__1.2 Git for Linux:__ if you’re on a Debian-based distribution, such as Ubuntu.

```
$ sudo apt install git-all
```

<br/><br/>
__1.3 Git for macOS:__ first, check if it is already installed on your computer. probably it is! Open a Terminal and type:

```
$ git --v
```
<br/>
Otherwise download it <a href="https://sourceforge.net/projects/git-osx-installer/files/">here</a>.

<br/>
### 2. Downloading and installign Ruby and Jekyll.
Why do you need Ruby? So, you want your website to look pretty. For this, we need to download Jekyll Themes.
Because Jekyll is built using Ruby, we need to set up a Ruby environment (e.g. install Ruby) for Jekyll be able to run. For more information about Jekyll, have a look <a href="https://jekyllrb.com/docs/installation/windows/">here</a>.


**Open Git bash**, from now on we are going to type all command lines there.
Then, check if you already have Ruby installed on your computer:
```
$ ruby --v
```
<br/>
If you do not have it yet, let's install it!


__2.1 Install Ruby and Jekyll on Windowns__

* Download Ruby+Devkit <a href="https://rubyinstaller.org/">here</a>.
* Run the `ridk install`. For additional info see Ruby Installer <a href="https://github.com/oneclick/rubyinstaller2#using-the-installer-on-a-target-system">documentation</a>.
* __Installing Jekyll__: Open a new Git bash and install Jekyll and via Bundler (bundle provide an environment to run Ruby with `gem` command):

```
$ gem install jekyll bundler
```
<br/>
Check if Jekyll was installed properly. If so, you may be able to see something like: `jekyll 4.0.0`

```
$ jekyll -v
```
<br/>
If you run into error messages, jump to the session: **Dealing with errors**

<br/>
__2.3 Install Ruby and Jekyll on Linux__

```
$ sudo apt install ruby-full

$ sudo apt install rubygems  # or rubygems-integration

$ gem install jekyll bundler
```
<br/>

__2.4 Install Ruby and Jekyll on macOS__
Installing Ruby with Homebrew macOS (Homebrew is a commonly used package manager on macOS).

```
# Install Xcode command lines
$ xcode-select --install

# Install Homebrew
$ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
$ brew install ruby

# Add the brew ruby path to your shell config:
$ echo 'export PATH="/usr/local/opt/ruby/bin:$PATH"' >> ~/.bash_profile

# Then relaunch your terminal and check your updated Ruby setup:
$ which ruby
# /usr/local/opt/ruby/bin/ruby

$ ruby -v
$ ruby 2.6.3p62 (2019-04-16 revision 67580)

# Now all that is left is installing Bundler and Jekyll.
$ gem install --user-install bundler jekyll

# and then get your Ruby version using
$ ruby -v
# ruby 2.6.3p62 (2019-04-16 revision 67580)
```


Great, now all the needed environments are set up!

<br/>
### 3.Downloading a Jekyll theme.
Now it is time to choose your favourite Jekyll themes.
Go ahead to the website and try to get the one which fits the propose of your website most.
The themes I am using is zolan.
You can download it directly from the <a href="http://jekyllthemes.org/">website</a>, or, since you have already Git bash installed, run this command line, replacing `developer_name` and `themes_name`:

```
$ git clone https://github.com/developer_name/themes_name.git
```
<br/>
Now in the Git bash navigate via the command line to the folder your download the Jekyll themes:

First, check each folder you are currently in, by:

```
$ cd pwd
# C:Users\natsousa
```
<br/>
If you are at your user root, and for instance, you download Jekyll themes into Downloads folder you can navigate to there, by:

```
$ cd Downloads\your_nice_jekyll_themes_name
```
<br/>

Or, if you are in the up front folder (like: `C:Users\your_username\Desktop\some_folder`) and you need to go some folders back, you can do so by:

```
# C:Users\your_username\Desktop\some_folder
$ cd ..\..
$ cd Downloads\your_nice_jekyll_themes_name
```
<br/>
Now it is time to run your **unzipped** Jekyll themes folder by running:

```
$ bundle install

$ bundle exec jekyll serve
```
<br/>
You should now be able to see the following:
```
$ Configuration file: C:/Users/your_name/your_themes_name/_config.yml
              Source: C:/Users/your_name/your_themes_name
         Destination: C:/Users/your_name/your_themes_name/_site
   Incremental build: disabled. Enable with --incremental
        Generating...
                      done in 3.137 seconds.
   Auto-regeneration: enabled for 'C:/Users/deSousN1/blog'
      Server address: http://127.0.0.1:4001/blog/
    Server running... press ctrl-c to stop.
```
<br/>
So what you get?
Now you served your website locally on your computer, meaning that as soon the server is running you can access your website by search it in google by:

`http://127.0.0.1:4001/blog`

<br/>
**To stop the server**, run: `ctrl + C`, then: `Y`.

<br/>
**Editing the website files:**

You can see your files and edit them by right clicking on the folder and open it using <a href="https://notepad-plus-plus.org/downloads/">Notepad++</a>, or any other text editor you preferer.
Besides of notepad++, I would recommend <a href="https://atom.io/">Atom</a>, the one I am using, or <a href="http://www.sublimetext.com/">Sublime</a>.

<br/>
#### So, up to here all running good guys? Great! Jump to **Step 4**!

<br/>
#### Dealing with errors

Otherwise, if you get into some problems on the way and see an error message printed out like:

"`Please add the following to your Gemfile to avoid polling for changes: gem 'wdm', '>= 0.1.0' if Gem.win_platform?`"

It is because some gem dependencies are probably missing.
I installed all in the Windows system, and I could solve this problem by running:

```
$ gem install wdm

$ bundle exec jekyll serve
```
<br/>
Hopefully installing some missing packages like that solves your problem.

If you still run into some server port connection problems, you will get an error message like: "`Permission denied for 127.0.0.1:4000`".

It is because the port 4000 is already being used in your computer, then you can solve it by adding the following line to your **_config_yml** file: `port: 4001`

Else, try to update the gem file, as:

```
$ gem source -r https://rubygems.org/
$ gem source -a http://rubygems.org/
$ gem update --system
$ gem install rails -v 4.2.3 (4.2.5)
```
<br/>
Then start the server again:

```
$ bundle exec jekyll serve
```

<br/>
### 4.Setting up a GitHub account.
If you get until here, you are ready to publish your website to the world by serving it in GitHub with GitHub Pages.

But first, you need to create a <a href="https://github.com/join?source=header-home">GitHub account</a>, if you do not have one yet.

**Attention!** The username you give to your GitHub account will be the name of your website.
In the end, it looks like: *your_github_username.github.io*

Great. You are doing well!

<br/>
### 5.Publishing your website.
Now in GitHub create a repository:

__5.1 click in the  *+*  at the upright corner, then New repository:__

![]({{ site.baseurl }}/images/create_git_repos.jpg)


__5.2 Give your repository a name.__

**Attention!** the name of your repository (e.g: 'blog') will be added to your `your_github_username.github.io`,
as so:

`your_github_username.github.io/blog`.

Or, if you <a href="https://www.wpbeginner.com/beginners-guide/how-to-choose-the-best-domain-registrar/">bought a domain name</a>, and your domain is `my_nice_website_name.com`, place it as the name of your repository.

![]({{ site.baseurl }}/images/create_git_repos2.jpg)


__5.3 Now you should be able to see the following:__

![]({{ site.baseurl }}/images/create_git_repos3.jpg)

#### Great!

__5.4 Now in the website folder, open the *_config.yml* file and write your repository name in the baseurl line,
and in url line paste your base hostname & protocol for your site, as:__

![]({{ site.baseurl }}/images/create_git_repos21.jpg)

You can do something else, in **_settings.yml** file, you can add your social network information,
include <a href="https://disqus.com/">Disqus</a> (allow readers to comment, give likes on your posts. It is important because this is your way to communicate with you audience),
and <a href="https://mailchimp.com/">MailChimp</a> (send personalised email to your followers) credentials.

<br/>
__5.5 Now what you need to do is to tell your *local folder* that there is a *repository* waiting for it.__

In the Git bash, check if you are inside of your website folder (hint: `pwd`).
And initiate a <a href="https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control">version control</a> for your website folder, by running:

```
$ git init
```
<br/>
Now your folder can be tracked for changes and can communicate with the external GitHub repository that you just created.

How to get there? Write your first git commit.

Don't worry so much about git commands now, it is easy and soon you will get very familiar with it. Here is a <a href="https://www.udacity.com/course/version-control-with-git--ud123">free course</a> you can learn more about it.

<br/>
__5.6 Create a branch on your website project that up to now just have one (a master branch)__

```
$ git checkout -b gh-pages
```
<br/>

__5.7 Add the files from your website folder to the staging area (a place where files get together to gain a commit and start being tracked)__
```
$ git add .
```
<br/>
The **.** here means "add all files".

<br/>
__5.8 Write your first commit with a commit message:__
```
$ git commit -m "first commit"
```
<br/>

__5.9 Now communicate your *remote GitHub repository* with your *local folder* , by:__
```
$ git remote add origin https:://github.com/your_github_user_name/your_github_repository.git
```
<br/>

__5.10 Send your website local files to the remote repository, by:__
```
$ git push origin gh-pages
```
<br/>

#### Tahdaaah... There you are!!! 🎉

<br/>
In GitHub website go to settings and scroll down until GitHub Pages:

![]({{ site.baseurl }}/images/create_git_repos4.jpg)

There you see the link of your website:
![]({{ site.baseurl }}/images/create_git_repos5.jpg)


Then, from now whenever you modify your website files locally, check how does it looks like
by starting the Jekyll server (hint: `bundle exec jekyll server`).
After that, you have to add your modified files to the stage area, commit the changes and push them to your GitHub repository.
The commands your already know:

```
$ git add . # OR: git add file_name_1.md, file_name_2.htlm #etc, ...
$ git commit -m "your commit message explaining what you changed"
$ git push origin gh-pages
```
<br/>
#### Access your website and have fun!!! 💚

<br/>
<p style="text-align: center">I hope you have enjoyed with me.</p>
Share this article with your community. I am very happy to have guided you through this journey.
Feedbacks, comments, bugs... Just leave a message. I am willing to support with any further advise.
