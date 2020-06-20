# Opam Indent Setup Dependency Files Created 3 Yrs Ago Lost 

## Bug
I had this bug since 3/15/20. Whenever I type vim somefile in the terminal, a message 
"Error detected while processing /Users/huanqi/.vimrc: line 128: E471: Argument required" 
will show up. Only after pressing Enter or any key I will get into the vim page. 
This is very annoying so I lookup line 128 of the .vimrc file. 

## Cause
Line 128 of the .vimrc file is in the code block of ## added by OPAM user-setup for vim / base 
It also gives me a path where it misses. When I cd to that path, it indeed no longer exists. 
So the problem is that some Opam Indent setup dependency files are missing. 


## Solution
After searching this online, I found this [link](https://github.com/OCamlPro/opam-user-setup)
However when I try to follow the step `<opam install user-setup>`, it shows error indicating some 
dependency is still missing. Since the last time I touched OCaml was three years ago, I decided
to update OCaml and Opam.

Following [OCaml download page](https://ocaml.org/docs/install.html#Homebrew-Homebrew) I first
used brew to update both OCaml and Opam cause that's what I find convenient. However, this still 
does not solve the problem - I still cannot install user-setup. When I check the path that 
these are installed to, the paths are different from the missing path indicated in the error. 

So I decided to use the recommended way to install the OCaml: [OPAM](https://opam.ocaml.org/doc/Install.html)
This time the path Ocaml and Opam installed to seem correct. Then I tried `<opam install user-setup>`,
this time it works. Now when I do vim, no error message shows up.

## Thought
The reason why I record this debug experience here is that I was in a similar situation to solve some
OCaml downloading problems three years ago when I worked on a OCaml final project. I didn't have enough
patience or strategies back then and I did not figure out how to install some of the packages. When I 
look back, CS trains me to better deal with frustrations and keep patient, which are two of the major 
virtues I lack. For that, I thank CS. 

## Side
When I editted this file, I took some time to learn about syntax of [Markdown file](https://guides.github.com/features/mastering-markdown/)
So I can make my README.md prettier in my repos :) 
