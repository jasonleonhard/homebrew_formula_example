## Homebrew Terminology

| Term           | Description                                                | Example                                              |
|----------------|------------------------------------------------------------|------------------------------------------------------|
| **Formula**    | The package definition                                     | `ls /usr/local/Library/Formula (grep to search)`     |
| **Keg**        | The installation prefix of a **Formula**                   | `ls /usr/local/Cellar          (or  brew ls)`        |
| **opt prefix** | A symlink to the active version of a **Keg**               | `ls /usr/local/opt/foo`                              |
| **Cellar**     | All **Kegs** are installed here                            | `ls /usr/local/Cellar`                               |
| **Tap**        | An optional Git repository of **Formulae** and/or commands | `/usr/local/Library/Taps/homebrew/homebrew-versions` |
| **Bottle**     | Pre-built **Keg** used instead of building from source     | `qt-4.8.4.mavericks.bottle.tar.gz`                   |


# Tutorial: Create your own Homebrew script


### FYI: You will want to change each of these words to suit your needs as they appear below

#### The repo is called 
  
    homebrew_formula_example

#### My github handle is 

    un5t0ppab13

#### The scripts name is 

    example_cmd

#### Create a new github repo and make sure to create a README.md

    open https://github/new

#### Follow githubs steps as suggested.... ie

    echo "# homebrew_formula_example" >> README.md
    git init
    git add README.md
    git commit -m "first commit"
    git remote add origin https://github.com/un5t0ppab13/homebrew_formula_example.git
    git push -u origin master

#### For the purposes of this tutorial we will create a folder and enter it

  mkdir ~/homebrew_scripts
  cd ~/homebrew_scripts

#### Clone that repo wherever you want it locally stored on your machine
    git clone https://github.com/un5t0ppab13/homebrew_formula_example.git
  cd homebrew_formula_example

#### Create a script, this is a simple one that just echos upon running

  echo '#!/bin/sh
  echo "Some example text shown when user runs the command: example_cmd"' > example_cmd

#### Change its permissions and run it

  chmod u+x example_cmd
  ./example_cmd

#### Tag that repo with a version

  git tag 1.0.0
  git push --tags

#### Go ahead and add, commit, push

  git add .
  git commit -am "second"
  git push          # git push origin master

#### Open the following link (again change username and repo first)

  https://github.com/un5t0ppab13/homebrew_formula_example/releases
  
This is the format https://github.com/username/reponame/releases

#### Right click the tar.gz option and copy link address 

Now this is in the clipboard run the command
 
  brew create https://github.com/un5t0ppab13/homebrew_formula_example/archive/1.0.0.tar.gz

#### This creates this file which you need to edit

  /usr/local/Library/Formula/homebrew_formula_example.rb

# 1. Delete all comments
# 2. And everything between def install ...... end
# 3. Paste this inside of that def

    bin.install "example_cmd"

Again remember to use your command name not mine

#### Now you reinstall 

  brew reinstall homebrew_formula_example

It downloads to: /Library/Caches/Homebrew/homebrew_formula_example-1.0.0.tar.gz

🍺  /usr/local/Cellar/homebrew_formula_example/1.0.0

#### Verify this worked with the following

  which example_cmd

It should say something like /usr/local/bin/example_cmd

You should now be able to run

  example_cmd
 
At this point you do not need a local copy of the repo if you do not want it
 
 
Thank you for reading this tutorial, all I request is that you do not replicate this material and claim it to be your own.
ie no need to copy this tutorial, just link it, share it, fork it, etc...