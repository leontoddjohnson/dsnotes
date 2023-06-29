# R Setup

Whereas Python tends to be the most useful framework for the typical data science project, R is easily the preferred tool for statistical analysis. Here we discuss how to set up a sufficient R environment.

To become familiar with R, it is **highly recommended** that you go through the first three [R Primers on Posit Cloud](https://posit.cloud/learn/primers) (**[The Basics](https://posit.cloud/learn/primers/1)**, **[Work with Data](https://posit.cloud/learn/primers/2)**, and **[Visualize Data](https://posit.cloud/learn/primers/3)**).

## Initial Setup

It is recommended that you use Git and Github for all project work, whether it is in R or Python.

1. Sign up for a [GitHub](https://github.com/) account if you haven't already. Then, [download GitHub Desktop](https://desktop.github.com/) (in my humble opinion, this is the most efficient way to interface with GitHub for most data science work).
    - [This is a great resource for Git](https://www.atlassian.com/git/tutorials/setting-up-a-repository).
2. Create a "Projects" folder somewhere convenient on your computer. You can name the folder whatever you like; for example, I have a "GitStuff" folder in my home directory (i.e., on a Mac, this is a folder in the same directory as *Movies* and *Pictures*, etc.). Here is where you'll put all future data science project git repositories.

## R Setup

> Note: It is highly recommended you use [R Markdown](https://rmarkdown.rstudio.com/lesson-1.html) for any work in R.

1. First, [set up R and RStudio](https://www.modernstatisticswithr.com/thebasics.html#installation) (sections 2.1 - 2.3).
2. Install the following packages by running `install.packages("<packagename>")` in the RStudio console. You will only need to install these once. (These libraries will be more than sufficient for this course.)
   - Data Science Tools: `tidyverse`, `rmarkdown`, `car`
   - Visualization Tools: `ggrepel`, `ggthemes`, `lindia`, `viridis`
   - Datasets: `babynames`, `gapminder`, `nycflights13`

[Here](https://www.markdownguide.org/cheat-sheet/) is a great resource for using Markdown. *Note: for writing inline LaTeX math blocks, use `$math stuff$` syntax for inline rendering, and `$$ math stuff $$` for block rendering (this is a standard format for rendering math)*.

### Recommended Workflow (optional)

I am a huge fan of [Typora](https://typora.io/) for all things Markdown. Below is an example of a workflow I use:

1. Keep Typora, or your *preferred* Markdown editor in another window. I only say this because sometimes the editor in RStudio leaves some things to be desired.
2. Set your working directory in RStudio as you like, and keep the editor window open (the largest panel, at the top left), with the console (short, at the bottom left), the  environment variables pane (thin, on the upper right), and files/help (square, on the lower right).
3. Test short single-lined code in the console, and test multi-lined code in a separate *scratch.R* file in the script editor, highlighting and running the highlighted code with **Cmd + Enter**. 
4. Once you're happy with the code you want to present to others, put it in your .Rmd file in an organized way.
   - Each .Rmd file should "tell a story" in a clear way.
5. Edit the non-R code (in your .Rmd file) using Typora, or your preferred Markdown editor. **Please use Markdown often, and be descriptive!**