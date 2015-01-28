# Reproducible Research Resources

It should be obvious why reproducible research (RR) is preferred to non-reproducible research.  Googling "reproducible research" should provide all the details.  Needless to say, most published research data analyses are very difficult to reproduce and hence the results of these analyses can easily be called into question.  A simple remedy is to do all research in a reproducible manner, from the very beginning, the exploratory analyses.

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
- been distracted by too much commented code that you kept just in case
- been frustrated by the logistics of collaborative writing (either code or documents)

If you have, then version control can help, especially if you code a lot.

### Why use GitHub for version control?

Not only is GitHub multiplatform (Linux, Mac, Windows) and open source, but users clone (copy) the entire respository (project), so working offline is easy.  Plus, it appears that GitHub is currently (2014) the most popular version control platform (with commits to the cloud), so collaborating with others should be relatively easy with GitHub.

Plus GitHub should handle any text-based file format well, whether that is .R, .tex, .Rnw, .Rmd, .md, .sh, .cpp, .py, etc.

No private repositories are possible with a standard free GitHub account, so please apply for an [educational discount](https://education.github.com/discount_requests/new) after signing in with your University email address.  Your account [should](https://github.com/blog/1775-github-goes-to-school) be upgraded to a free Micro account for the next two years, which means up to 5 private repositories.  If 5 private repositories per user is insufficient, then instead of GitHub, we can consider using [Bitbucket](https://bitbucket.org/plans), which has an "unlimited academic plan".

There are plenty of GitHub tutorials online in both written and video formats.  Yes, there is a learning curve, but it will save time in the long run.

### Fast GitHub Tutorial

As an example, let's use the README.md file which is the basis for this webpage.

1. Go to the GitHub respository for this page: https://github.com/cui-lab/cui-lab.github.io
2. While signed in to GitHub and on the repository page of interest, click the Fork button, to fork your own copy of _ to your account
3. Copy the HTTPS clone URL: https://github.com/youraccount/cui-lab.github.io.git
4. At preferred directory on your local computer: $ git clone https://github.com/youraccount/cui-lab.github.io.git
5. Changes can be made to README.md
6. $ git add README.md 
7. $ git commit -m "made a few changes" # -m means comment
8. Use git push to push to youraccount
9. On youraccount's GitHub and on the cloned repository, click on Pull Requests, and then click New pull request

### add some thing by watson
### add other by watson

### GitHub and My Own Files
