# Homework 2: Unix shell

This homework will assess your ability to run commands in the shell and make a simple script.

Replace the lines specified in _italics_ with your answers and save as a text file.


## Problem 0

**60 points**

Complete the interactive tutorial.

Thanks for the tutorial--I usually join lectures from lab so only have my laptop screen for zoom-- it was helpful to be able to walk-through on my own time. No real complaints, i really appreciate the step-by-step because shell is totally new to me.


## Problem 1

**20 points**

Learn about the difference between standard out ("stdout") and standard error ("stderr") from [this article](https://www.howtogeek.com/435903/what-are-stdin-stdout-and-stderr-on-linux/) (feel free to read the whole thing, but you can stop before the section "Detecting Redirection Within a Script").
Note that in reading this article, you don't need to come up with a script that will throw an error: we have one at `tfcb_2021/lectures/lecture03/06-scripting/script2.sh`.

`$ ./script2.sh 1> stdout.txt 2> stderr.txt`

## Problem 2

**20 points**

You might have noticed that the files we're dealing with have "extensions" that describe their file type.
For example, text files are marked with `.txt`, and shell scripts are labeled with `.sh`.

This is a handy convention which is used heavily by a command-line library called [imagemagick](https://imagemagick.org/index.php) to manipulate images.
ImageMagick has been installed on rhino, but needs to be loaded before you use it:

    ml ImageMagick

Don't forget to load the updated version of parallel:

    ml parallel

Once the library is loaded, go to the `lecture03/slides/images` directory and try

    convert betty-crocker.jpg betty-crocker.png

which converts `betty-crocker.jpg` (a JPG image) to `betty-crocker.png` (a PNG image).
You can confirm proper conversion using `file`.
Now, your turn:

`ls *.jpg | parallel convert {} {.}.png`

Big hint: There is a very similar sort of command in the "Compute intensive jobs and substitution" section of the `parallel` man page.

Next:

`#!/bin/sh`
`#all jpgs to pngs`

`ls *.jpg | parallel convert {} {.}.png`
`montage *.png montage.png`

`echo "jpg to png complete"`