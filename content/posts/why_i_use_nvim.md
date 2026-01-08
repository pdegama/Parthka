+++
date = '2025-10-14T04:36:51+05:30'
draft = false
title = 'NeoVim Vs Other Text Editor!'
author = "Parthka"
description = "Why i use NeoVim as my primary Editor?"
tags = ["nvim", "NeoVim", "editor", "vim"]
keywords = ["nvim", "NeoVim", "editor", "vscode", "vim", "chromium"]
cover = "/img/nvim-4.png"
+++


When I used **bspwm** with **Arch Linux** for the first time, I also started using **Neovim**.  
Before Neovim, I used many editors like VS Code and others such as Atom (now dead), Brackets, etc.

Learning Neovim is difficult at the beginning. I mostly write **C language** code. After some time, I forgot the VS Code and other IDE keymaps. When I used another editor and needed to save a file, I pressed `<ESC>:w` in VS Code—but it didn’t work.

I’m also a web developer, so I used VS Code for web-related tasks, but it wasn’t as joyful as Neovim.  
So, I set up **LazyVim** and added language servers for TypeScript, JavaScript, and more. Now, I use Neovim as my **primary text editor**.

Currently, I use **Neovim with LazyVim + Hyprland + Arch Linux**.

Neovim is a fork of the Vim editor—an improved version of Vi.

![image](/img/nvim-3.webp)

Neovim and Vim both have similar keymaps. We can also add Vim extensions in VS Code and other text editors.  
After installing the extension, the code editor works like Vim. It supports `NORMAL`, `VISUAL`, `INSERT`, and `COMMAND` modes.

But the main problem with other text editors is not the keymap—it’s performance.  
Most text editors use Electron and Chromium. When I use Neovim, I realize it’s **much faster** than others.

For example, when I open 3–4 instances of Neovim, it only uses around **300MB of memory**, while a single instance of VS Code uses **470MB+**.  
You can configure VS Code to work like Neovim, but once you compare both, you’ll notice how much faster Neovim is.

![image](/img/nvim-2.png)

Neovim is a **CLI-based text editor**. It opens directly in the terminal—supported by most modern terminals.

The most difficult thing when learning Neovim/Vim is the commands:  
how to switch from insert mode to command mode feels confusing at first.  
But later, this becomes one of Neovim’s biggest advantages—**it makes Neovim faster**.

![image](/img/nvim-5.webp)

Nowadays, the difficult part is adding plugins and configuring Neovim.  
It’s a bit tricky for those who don’t know the **Lua** language, because all plugins and configuration files are written in Lua.

However, we have options such as using **LazyVim** or other pre-made configurations—or learning Lua and exploring things on our own.

![image](/img/nvim-1.jpg)
