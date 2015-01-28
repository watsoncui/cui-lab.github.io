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

Let's use the GitHub GUI to start a simple repository.

1. Create a GitHub user account at [github.com](https://github.com/).
2. Once logged in, click the "+" (plus) sign in the top right-hand corner, and select "New repository".
3. Name the repository "helloworld", select "Initialize this repository with a README" and select "Create Repository".
4. Click on the README.md link and then on the pencil icon to edit README.md.
5. Write in "Hello, world!" on the third line, then click "Commit changes" at the bottom.
6. The file should be updated with your text. You can even turn your README.md file into a website by following the directions at the [GitHub Pages](https://pages.github.com/) site.

### GitHub Pull Request Tutorial

As an example, let's use the README.md file which is the basis for this webpage.

1. Sign in to GitHub, if not already signed in, and go to the GitHub respository for this page: [https://github.com/cui-lab/cui-lab.github.io](https://github.com/cui-lab/cui-lab.github.io).
2. Click the "Fork" button, to fork your own copy of the cui-lab.github.io respository to your account
3. Copy the HTTPS clone URL (notated by `*HTTPS_clone_URL*`) on the right side of the page.
4. In the terminal, change directory into your prefered working directory and input the command: `$ git clone *HTTPS_clone_URL*`
5. Change directory into cui-lab.github.io and make and save some changes to README.md.
6. Input the following terminal commands `$ git add README.md`
7. $ git commit -m "made a few changes" # -m means comment
8. Use git push to push to youraccount
9. On youraccount's GitHub and on the cloned repository, click on Pull Requests, and then click New pull request, the owner will check your pull request and decide whether to accept/merge changes

### GitHub SSH Key Tutorial

Because putting in the username and password each time is a hassle...

1. Assuming you have a GitHub account and git is installed on your computer
2. Change directory to ~/.ssh and check to see if you already have an rsa key, if you do, you can skip steps 3-5
3. Generate the SSH key with $ ssh-keygen -t rsa
4. Replace 'user' in the following question, with a user name: "Enter file in which to save the key (/home/user/.ssh/id_rsa): user_id_rsa
5. Do not enter a passphrase
6. GitHub youraccount settings > SSH keys under personal settings > Add SSH key
7. $ cat cui-lab_id_rsa.pub and copy the key and paste it into the SSH keys website with a title (like the name of the computer) and click on Add key
8. Verify that everything is okay by using $ ssh -T git@github.com
Hopefully the output states: Hi! You've successfully authenticated, but GitHub does not provide shell access.
If it states something else, follow the directions
9. Start an new GitHub respository called test
10. Make a new directory for your respository ~/github$ mkdir test and cd into this directory
11. ~/github/test$ git init
12. $ git remote add origin git@github.com:githubusername/test.git
13. $ git remote -v
we should see:
origin  git@github.com:githubusername/test.git (fetch)
origin  git@github.com:githubusername/test.git (push)
14. Create a README text file
15. $ git add README
16. $ git commit -m "some comment about the commit"
17. $ git push origin master # Where we are listing the default values of origin (respository) and master (branch)
18. Edit the file on the GitHub website and commit changes to the master branch
19. Pull the changed README file into our local directory: $ git pull origin master
20. Check to see that the local file has the change.  Then make a change with the local computer and repeat steps 15-17 to make the change in the GitHub repository and then confirm the change on the GitHub website







