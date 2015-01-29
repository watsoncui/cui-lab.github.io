# Reproducible Research Resources

It should be obvious why reproducible research (RR) is preferred to non-reproducible research.  Googling "reproducible research" should provide all the details.  Needless to say, most published research data analyses are very difficult to reproduce and hence the results of these analyses can easily be called into question.  A simple remedy is to do all research in a reproducible manner, from the very beginning with the exploratory analyses.

Dynamic report generation and version control can help!  Hence, we consider knitr and GitHub below.

### knitr, the dynamic report generation engine for R

- [Review of knitr](http://yihui.name/knitr/demo/minimal/)
- [knitr examples](https://github.com/yihui/knitr-examples/)
- For non-PDFLaTeX output like .html or .docx, try using R Markdown (.Rmd) as it is quite easy to implement
- knitr can be used with LaTeX slides and posters, in the same way as LaTeX documents
- Figures and plots are easy with knitr
- Formatted tables, not so much, but we can work on that

### Why use version control?

If you have ever ...

- changed your code, then sometime later, wanted to revert back to your old code
- had to develop multiple versions of your code
- wanted to merge a new feature into a different version of your code
- lost the code backup you needed
- wanted to test a new feature without messing with your working code
- been distracted by too much commented code that you kept "just in case"
- been frustrated by the logistics of collaborative writing (either code or documents)

If you have, then version control can help, especially if you code a lot.

### Why use GitHub for version control?

Not only is GitHub multiplatform (Linux, Mac, Windows) and open source, but users clone (copy) the entire respository (project), so working offline is easy.  Plus, it appears that GitHub is currently (2014) the most popular version control platform (with commits to the cloud), so collaborating with others should be relatively easy with GitHub.

Plus GitHub should handle any text-based file format well, whether that is .R, .tex, .Rnw, .Rmd, .md, .sh, .cpp, .py, etc.

No private repositories are possible with a standard free GitHub account, so please apply for an [educational discount](https://education.github.com/discount_requests/new) after signing in with your University email address.  Your account [should](https://github.com/blog/1775-github-goes-to-school) be upgraded to a free Micro account for the next two years, which means up to 5 private repositories.  If 5 private repositories per user is insufficient, then instead of GitHub, we can consider using [Bitbucket](https://bitbucket.org/plans), which has an "unlimited academic plan".

There are plenty of GitHub tutorials online in both written and video formats.  Yes, there is a learning curve, but using version control, like GitHub, will save time in the long run.

### GitHub "Hello, world!" Tutorial

Let's use the GitHub GUI to start a simple repository.  Many GitHub tutorials give much more detail than is necessary, so I thought that we could distill the GitHub tasks, most important to our lab, into these few tutorials.

1. Create a GitHub user account at [github.com](https://github.com/).
2. Once logged in, click the "+" (plus) sign in the top right-hand corner, and select "New repository".
3. Name the repository "helloworld", select "Initialize this repository with a README" and select "Create Repository".
4. Click on the README.md link and then on the pencil icon to edit README.md.
5. Write in "Hello, world!" on the third line, then click "Commit changes" at the bottom.
6. The file should be updated with your text. You can even turn your README.md file into a website by following the directions at the [GitHub Pages](https://pages.github.com/) site.

### GitHub Pull Request Tutorial

"Pull request" means that you want to collaborate on someone else's repository, so you download ("fork") their repository, make some changes to it, then submit it back to them ("pull request") so that they can consider accepting your changes.  As an example, let's use the README.md file which is the basis for this webpage.

1. Install `git` on your computer and set the global user name and user email with the following example terminal commands:
`$ git config --global user.name "GitHub_username"`, then `$ git config --global user.email GitHub_useremail@example.com`.
2. Sign in to GitHub, if not already signed in, and go to the GitHub respository for this page: [https://github.com/cui-lab/cui-lab.github.io](https://github.com/cui-lab/cui-lab.github.io).
3. Click the "Fork" button, to fork your own copy of the cui-lab.github.io respository to your account.
4. Copy the HTTPS clone URL (notated by `HTTPS_clone_URL`) on the right side of the page.
5. In the terminal, change directory into your prefered working directory and input the command: `$ git clone HTTPS_clone_URL`.
6. Change directory into cui-lab.github.io and then make, and save, some changes to README.md.
7. Add the README.md file to the index to prepare for the next commit using the command: `$ git add README.md`.
8. Commit and comment (in quotes, after the `-m` option) on your commit using the example command: `$ git commit -m "made a few changes"`.
9. Push the committed file(s) to your GitHub repository using the following command and then inputing your username and password: `$ git push`.
10. You should then see the changes on the cloned repository on your account.  If you would like to submit your changes to the original owner of the cloned repository, then on the page for your cloned repository, click on the "Pull Requests" and create a new pull request.  The owner will check your pull request and decide whether to accept and merge your changes.

### GitHub SSH Key Tutorial

Use an SSH key if you don't want to have to input your username and password each time you `git push`.

1. Assuming you have a GitHub account and git is installed on your computer, change directory to ~/.ssh and check to see if you already have a public RSA key.  If you do, skip steps 2-4.
2. Generate an SSH key with the command: `$ ssh-keygen -t rsa`.
3. Upon the question, "Enter file in which to save the key (/home/user/.ssh/id_rsa):", use something like "user_id_rsa", but replace the "user" part. 
4. Do not enter a passphrase.
5. After logging in to GitHub, open Settings > SSH keys > Add SSH key.
6. The public key can be copied from `$ cat user_id_rsa.pub` and pasted in the "Key" space.  After adding a title, for instance the name of the computer, click on Add key.
7. Verify that the SSH key was correctly set up by using this terminal command: `$ ssh -T git@github.com`.  Hopefully the output states something like:
`Hi! You've successfully authenticated, but GitHub does not provide shell access.`  If not, then follow the given instructions, or Google the output for help online.
8. Start an new GitHub respository called test.
9. Make a new directory for your respository, on your local computer, and change directory into this directory.
10. Use the following commands, making sure to replace `GitHub_username` with your GitHub username:
`$ git init`, then `$ git remote add origin git@github.com:GitHub_username/test.git` and then `$ git remote -v`.
The output should be:
`origin  git@github.com:GitHub_username/test.git (fetch)` and `origin  git@github.com:GitHub_username/test.git (push)`.
11. Create a README.txt text file in your repository's directory, then use the following commands:
`$ git add README.txt`, then `$ git commit -m "some comment about the commit"` and then `$ git push origin master`.
The `origin master` part indicates that we are pushing into the repository named "origin", and specifically the "master" branch of "origin".  Unlike in the previous tutorial, you will not need to input your GitHub username and password.
12. The README.txt should appear on the GitHub website.  Make some changes to this file using the GitHub website and commit the changes to the master branch.
13. Pull the changed README.txt file into your local directory using the following terminal command: `$ git pull origin master`.
14. Check to see that the local file has the most recent changes.  Then make other changes with your local computer and use the commands in step 11 to see the changes reflected in the online GitHub repository.

### More on Branching and Merging

Until a simplified tutorial on this is written, allow Google to be your teacher.

