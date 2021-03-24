---
jupytext:
  cell_metadata_filter: -all
  formats: md:myst
  text_representation:
    extension: .md
    format_name: myst
    format_version: '0.8'
    jupytext_version: 1.5.0
kernelspec:
  display_name: 'Python 3.8.6 64-bit (''codeforecon'': conda)'
  language: python
  name: codeforecon
---

# The Command Line

In this chapter, you'll meet the *command line* and learn how to use it. Beyond a few key commands like `pip install <packagename>`, `conda activate <environmentname>`, and `jupyter lab`, you don't strictly need to know how to use the command line to follow the rest of this book. However, even a tiny bit of knowledge of the command line goes a long way in coding and will serve you well.

To try out any of the commands in this chapter on your machine, you can select 'New Terminal' from the menu bar in Visual Studio Code (Mac and Linux), use the Windows Subsystem for Linux or git bash (Windows), or use a free [online terminal](https://cocalc.com/doc/terminal.html).

This chapter has benefited from numerous sources, including [Grant McDermott](https://grantmcdermott.com/)'s notes, Melanie Walsh's [Introduction to Cultural Analytics & Python](https://melaniewalsh.github.io/Intro-Cultural-Analytics/welcome.html), [Data Science Bootstrap](https://ericmjl.github.io/data-science-bootstrap-notes/) and [Research Software Engineering with Python](https://merely-useful.tech/py-rse/).

## What is the command line?

The command line is a way to directly issue text-based commands to a computer one line at a time (as distinct from a graphical user interface, or GUI, that you navigate with a mouse). It goes under many names: shell, bash, terminal, CLI, and command line. These are actually different things but most people tend to use them to mean the same thing most of the time. The *shell* is the part of an operating system that you interact with but mostly people use shell to mean the command line. *bash* is the programming language that is used in the command line; it's actually a synonym for 'Born Again SHell'. The *terminal* is sometimes used to refer to the command line on Macs. Finally, a *CLI* is just an acronym for command line interface, and is often used in the context of an application; for example, pip has a command line interface because you run it on the command line to install packages (`pip install packagename`).

It's worth mentioning that there's a big difference between the command line on UNIX based systems (MacOS and Linux), and on Windows systems. Here, we'll only address the UNIX version. There is a command line on Windows but it's not widely used for coding. If you're on a Windows machine, you can access a UNIX command line using the Windows Subsystem for Linux.

## Why is the command line useful?

The command line has many uses. Graphical user interfaces are, generally, a bit easier to use *but* they're not very repeatable or scalable. Because the command line uses text-based instructions and can be programmed, it is both repeatable and scalable; properties that are very useful for research and analysis.

The broad reasons you might use the command line to issue instructions include:

- software functionality: some software *only* has a command line interface so sometimes it's the only way

- efficiency: your computer has limited memory, which graphical user interfaces use a lot of-the command line uses less

- reproducibility: scripts that run on the command line are reproducible in a way that clicking around a graphical user interface is not

- hardware functionality: for high-performance and cloud computing the command line is often the only game in town

- automation: multiple programmes, with inputs and outputs, can be run in sequence from a script launched in the command line

Here are some specific tasks you might use the command line to complete:

- keep your code under version control

- renaming and moving multiple files in one command

- finding files on the computer

- transforming between document types, for example $\LaTeX$ (.tex) to Word (.docx)

- connecting to, and using, cloud resources

## Using the command line

Bash is often the default command line shell on UNIX but zsh has gained popularity and is now the default for Mac. If you're wondering what to use then I recommend zsh (Z Shell) from [oh-my-zsh](https://ohmyz.sh/).

To open up the command line within Visual Studio Code, you can use the ``⌃` `` keyboard shortcut (Mac) or ``ctrl` `` (Windows), or by clicking "View > Terminal".

Let's try a simple command: type `date` into a command line window and hit return. You should see today's date and time (and timezone). You could also try `echo hello` and `whoami`.


All commands that you run in the terminal have the same structure:
`command`, followed by `option(s)`, followed by `argument(s)`. The options are also called flag.s An example serves to demonstrate this: if you have a terminal open in a directory that includes a CSV file called 'data.csv', the command to look at the first 5 lines is:

```bash
head -n 5 data.csv
```

here `head` is the command that looks at the start of the file, `-n` is an option, `5` is the argument to get 5 lines of the file, and `data.csv` is the final argument-the file name.

The flags or options, such as `-n` in the example above, typically begin with a dash (`-`) or, occasionally, a double dash (`--`). They can also be chained together, for example `ls -la` combines `ls -a` and `ls -l`.

```{warning}
Spaces take on a special role when using the command line. For this reason, it's good practice to avoid spaces in file names. If you need to refer to a filename with spaces in, you’ll need to use quotes or escape the spaces in the file names using a `\`, for example `this is my file.txt` becomes `this\ is\ my\ file.txt`
```

To run programmes from the command line, all you need is the name of the programme as the command: in fact, commands *are* programmes. The `date` command refers to an actual programme on your computer that you can find. And this also explains a bit of what's going on when you *run a script from the command line* (more on that later).

Once you've run a few commands, you'll notice that you can't navigate around the command line like you can a text file or Python script. Here are some tips for navigating the command line:

- use tab to complete commands you've only partially written out. Try it by typing `dat` then hitting tab.

- use the ↑ (and ↓) keys to scroll through previous commands.

- to skip whole words, use ⌥+→ (and ⌥+←) on Mac, Ctrl+→ (and Ctrl+←) on Windows and Linux.

- Ctrl+a to move the cursor to the beginning of the line.

- Ctrl+e moves the cursor to the end of the line.

- Ctrl+k to delete everything to the right of the cursor.

- Ctrl+u to delete everything to the left of the cursor.

- Ctrl + r to search through previously used commands
clear to clear your terminal.

### Navigating directories

While we're on navigating, it's useful to understand *where* in the computer you are when you open the command line. If you open a terminal pane within VS Code, you will start (by default at least) within the same folder as your project. Starting a terminal instance outside of VS Code will get you a terminal in a root directory for your computer; for example, on a Mac, opening a new terminal window starts you in `/Users/yourusername/`.

To find out "where" you are when you open a terminal, you can use the `pwd` command, which stands for "print working directory".

The table below shows some useful commands for moving around your computer using the command line. Note that `cd` accepts a location *relative* to your current directory.

| Command      | What it does |
| ----------- | ----------- |
| `pwd`      | Shows current directory       |
| `cd`   | Change directory command        |
| `cd ..`   | Go up one level in the directory (`cd ../..` for two levels)        |
| `cd ~`   | Go to your home directory        |
| `cd -`   | Go to the previous directory        |
| `cd -`   | Go to the previous directory        |
| `cd documents/papers`   | Go directly to a directory named 'papers' |


## Using Python on the command line

There are several ways in which the command line is useful for Python (and these ways are applicable to other languages too).

Of course, packages are installed at the command line, for example to install Jupyter Lab (for running notebooks), the command is

```bash
pip install jupyterlab
```

and many packages can also be installed with `conda install packagename` too.

Say you have a script called `analysis.py`, you can run it with Python on the command line using

```bash
python analysis.py
```

which calls Python as a programme and gives it `analysis.py` as the argument. If you have multiple versions of Python, which you should do if you're following best practice and using a version per project, then you can see *which* version of Python is being used with

```bash
which python
```

Remember, if you're using Anaconda to manage your Python environments, you can switch between the version of Python that is called using, for an env called `projectenv`

```bash
conda activate projectenv
```

Try switching between Python environments and running `which python` to see how this works.

Jupyter Notebooks are also run from the command line. If you have Jupyter Lab installed, you can start a notebook server with

```bash
jupyter lab
```

## Useful commands for the terminal

Now we'll see some useful commands for the terminal.

| Command      | What it does |
| ----------- | ----------- |
| `man <command>`      | Shows a manual for the given command       |
| `touch <filename>`   | Creates an empty file named `<filename>`        |
| `code <filename>`   | Open a file in VS Code (creating it, if it does not exist) |
| `mkdir <foldername>`   | creates a new folder called `foldername`|
| `echo <text>`   | Prints `<text>`   |
| `cat <filename>`   | Print the full contents of `<filename>` |
| `head <filename>` | Print the start of a file |
| `tail <filename>` | Print the end of a file |
| `> <filename>`   | Redirects output from screen to `<filename>`. For example, `echo "Hello World" > hello.txt` |
| `>> <filename>` | Redirects output from screen to the end of `<filename>`, ie appends output rather than overwrites it |
| `| ` | The pipe symbol: uses output from one command as input into another. For example, `head -n 10 data.csv | > hello_world.txt` would write the first 10 lines of data.csv into a file called hello_world.txt
| `less <filename>` | Print out the contents of a file in paginated form. Use `ctrl+v` and `Alt+v` (or `⌘+v` and `⌥+v` on Mac) to move up and down. Press `q` to quit.|
| `wc -l` | Returns number of lines in input, for example `cat <filename> | wc -l` |
| `sort` | Arrange lines in a file in alphabetical order |
| `uniq` | Remove duplicate lines from input, for example `cat <filename> | uniq` or `uniq -d` to show duplicate files |
| `mv` | Move or rename a file; for example, `mv file1 file2` would rename `file1` to `file2` while `mv file1 ~` would move `file1` to the home directory|
| `cp` | Copy a file; for example, `cp file1 file2` would copy `file1` to `file2` while `cp file1 ~` would make a copy of `file1` in the home directory|
| `rm <filename>` | Permanently remove a file |
| `rmdir <directory>` | Permanently remove an empty directory |
| `rm -rf <directory>` | ⚠ Permanently remove everything in a directory ⚠ |
| `grep <searchterm>` | Search for a given term, for example `cat hello_world.txt | grep world` |
| `ls` | Basically, this means list stuff (files and folders) in the current directory |
| `ls -a` | List stuff in the current directory even if it's hidden |
| `ls -l` | List stuff in a more readable format and show permissions |
| `file <filename>` | Give information on the file type of `<filename>`|

You can write for loops in bash (remember, it's a language). The general structure is

```bash
for i in LIST
do
  OPERATION $i # the $ sign indicates a variable in bash
done
```

These can be squeezed into a single line (though it's less readable):

```bash
for i in {1..5}; do echo $i; done
```

A more interesting example is giving the number of lines of text, number of words, and number of characters of every CSV file in a directory:

```bash
for i in $(ls *.csv)
do 
  wc $i
done
```

Wait, but what's that asterisk doing there? It's a *wildcard character*, it tells bash to look for anything that ends in ".csv".

We can get even more fancy with the above example and put those counts in a new text file:

```bash
touch counts_of_csvs.txt
for i in $(ls *.csv)
do 
  wc $i >> counts_of_csvs.txt
done
```

## Bash scripting

TODO

## Useful command line tools

[**pandoc**](https://pandoc.org/) is absolutely brilliant: if you need to convert files containing text from one format to another, it really is a swiss-army knife. There isn't space here to list the ridiculous number of documents it can convert between, but, importantly, it can translate back and forth between all of the following: markdown, $\LaTeX$, Microsoft Word's docx, OpenOffice's ODT, HTML, and Jupyter Notebook.

It can also write from any of those formats (and more) in one direction *to* PDF, Microsoft Powerpoint, and $\LaTeX$ Beamer.

To use **pandoc**, install it following the instructions on the website and then call it like this:

```bash
pandoc mydoc.tex -o mydoc.docx
```

This is an example where the input is a .tex document and the output, `-o`, is a Microsoft Word docx file.

You can get quite fancy with **pandoc**, for example you can translate a whole book's worth of latex into a Word doc complete with a Word style, a bibliography via biblatex, equations, and figures. Nothing can save Word from being painful to use, but **pandoc** certainly helps.

Here's a real example of doing all of that, taken from an open source [**cookie-cutter-latex-book-manuscript**](https://github.com/aeturrell/cookie-cutter-latex-book-manuscript) that I wrote:

```bash
pandoc -s -N --reference-doc ref.docx -F pandoc-crossref -Mchapters book_compiler.tex --bibliography=book_bibliography.bib --csl=nature.csl -o exported_word/book.docx
```

- `-s` tells pandoc to make a standalone document
- `-N` enforces numbering (though not in docx, it's included here in case of other output formats being used)
- `--reference-doc` tells pandoc to use styles from a reference word doc (can also be used with .odt)
- `-F` calls a pandoc filter, in this case pandoc-crossref
- `-Mchapters` tells this filter to use chapters
- `*.tex` is the input file
- `--bibliography=*.bib` tells pandoc where to find citations
- `--csl=*.csl` is the name of the style file for citations
- `-o` means output, in this case a word document


[**exa**](https://the.exa.website/) is an upgrade on the `ls` command. It is designed to be an improved file lister with more features and better defaults. It uses colours to distinguish file types and metadata. Follow the instructions on the website to install it on your operating system. To replace `ls` with `exa`, you can use a terminal *alias*. There's a good guide [available here](https://ericmjl.github.io/data-science-bootstrap-notes/create-shell-command-aliases-for-your-commonly-used-commands/).

## Review

This brief introduction to the command line, should have made you feel comfortable with: opening terminal windows; using built-in commands to change directories, rename files, and list files; using Python on the command line; and using installed command line tools such as **pandoc**.