---
title: "Bye! Bye! WordPress"
summary: Learn About Hugo a Best and Better Alternative to WordPress
date: 2025-02-12
weight: 2
aliases: ["/hugo-setup"]
tags: ["WordPress", "Setup", "Tutorial", "Hugo"]
author: ["Sphinx"]
cover:
  image: images/hugo.png
  hiddenInList: true
---

## intro
Okay, maybe I *did* get a *little* carried away with the title.  But seriously, Hugo is a fantastic alternative for a blog.  WordPress... well, let's just say it's a *journey*.  If you want a simple, static blog, Hugo is your jam.  Don't believe me? Check out this [site!](https://brain-chunk.vercel.app/)  And the best part? It's completely free! (Free as in beer, not free as in puppy – you still have to put in the work).
P.S If you are one of those who didn't get the joke [HERE YOU GO!](https://opensource.stackexchange.com/questions/620/what-is-the-difference-between-free-as-in-beer-and-free-as-in-speech)

## Why Ditch WordPress?

Let's be honest, WordPress can be a bit of a *mess*.  Free WordPress can feel like navigating a labyrinth blindfolded while juggling flaming torches.  Okay, maybe a *slight* exaggeration, but it can be frustrating.  For a simple static blog, Hugo is just *so* much cleaner.

## How to Hugo (Get it?!)

Convinced? Let's dive in! We'll be setting up Hugo using WSL2 (Windows Subsystem for Linux). Because who doesn't love a good command line?

### Prerequisites

Before we start, you'll need:

*   WSL installed (because Linux is cool, even on Windows)
*   Git setup (so your code doesn't get lost in the digital void)
*   An IDE (VS Code is recommended – it's like the Swiss Army knife of code editors)
*   Python 3 and Go language installed (highly recommended – they're useful, trust me)

### Step 1: Install Hugo (The Fun Part!)

You can check out the [official documentation](https://gohugo.io/installation/) (because reading is fundamental), or just follow along with my witty instructions.

1.  **Debian-based System?**  `sudo apt install hugo` (Easy peasy, lemon squeezy!)

    If you're rocking a different Linux distro, look up the command for your package manager (e.g., `pacman`, `dnf`, `zypper`).

    The problem with this method?  You might get an older version of Hugo.  So, we're going the pre-built binaries route for maximum freshness.

2.  **Grab the Goods:** Head over to the [latest release page](https://github.com/gohugoio/hugo/releases). Download the `hugo_0.x.x_linux-amd64.deb` (if you're Debian-based) or the tar file.

    *   **.deb Package:** `sudo dpkg -i hugo_0.x.x_linux-amd64.deb` (boom!)

    *   **Tar File:**

    ```sh
    # Create the directory (if it doesn't exist)
    mkdir -p ~/bin

    # Go there
    cd ~/bin

    # Unpack the tarball
    tar -xvzf ~/Downloads/hugo_0.x.x_linux-amd64.tar.gz

    # Check if it works
    ./hugo version
    ```

3.  **Add Hugo to Your Path:**  This lets you run Hugo from anywhere.

    ```sh
    # Check if Hugo is already in the path
    which hugo
    ```

    If it doesn't show anything, you need to add it:

    ```sh
    nano ~/.bash_profile  # Or your shell's equivalent
    ```

    Add this line:

    ```
    export PATH=$PATH:$HOME/bin
    ```

    Close and reopen your terminal.

4.  **Verify:** `hugo version` (Make sure it's v0.128.0 or later).

### Step 2: Theme Time! (PaperMod, baby!)

Let's add some style. We'll use the PaperMod theme.

1.  **Create a Website:**

    ```sh
    hugo new site MyBlog --format yaml  # Replace MyBlog with your site's name
    ```

2.  **Git It:** `git init` (because version control is your friend).

3.  **Submodule Magic:**

    ```sh
    git submodule add --depth=1 [https://github.com/adityatelange/hugo-PaperMod.git](https://github.com/adityatelange/hugo-PaperMod.git) themes/PaperMod
    git submodule update --init --recursive
    git submodule update --remote --merge
    ```

4.  **Configure:** In `hugo.yaml`, add:

    ```yaml
    theme: ["PaperMod"]
    ```

5.  **Run!** `hugo server` (This starts a local server on port 1313).

    Visit `http://localhost:1313/` in your browser.

## How to Add a Post (The Actual Blogging Part!)

Hugo uses Markdown files.  Write your article in Markdown, or if you're feeling lazy (like me), copy and paste your text into ChatGPT:

`convert this text into a markdown file <Paste All your text here>`

Then, go to `website/MyBlog/content/posts/`, create a new file (e.g., `MyFirstPost.md`), and paste the Markdown.

Run `hugo server` again, and your post should appear!

## Free Hosting (Because Free is Awesome!)

Head to [vercel.com](vercel.com), log in with your GitHub account, select your repo, choose Hugo, and save. Vercel will build and deploy your site automatically!  They'll give you a link, and boom – you're on the internet!


## Outro

I hope this tutorial helps you get started with Hugo! If you have any questions or run into any problems, feel free to leave a comment below... *eventually*.  Yes, the comment section is currently undergoing some serious renovations (think: digital dust and construction cones).  So, for now, if you have questions or just want to tell me how awesome (or hilariously terrible) this tutorial was, you'll have to contain your excitement. But fear not! I'm working on it, and soon you'll be able to unleash your thoughts and witty remarks.  In the meantime, Go Build your site.

YOU BUNCH OF VAMPIRES!