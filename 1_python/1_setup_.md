# Python Setup

Most of your work in data science will be done using Python, and we focus on that framework here. Before doing anything further, see below.

## Initial Setup

1. Before working on your first Python-based project, install [Miniconda](https://docs.conda.io/en/latest/miniconda.html). (The full Anaconda distribution is bloated and can get quite cumbersome.) This will create your "base" environment.
2. [Install JupyterLab](https://jupyterlab.readthedocs.io/en/latest/getting_started/installation.html), and any [Jupyter extensions](./1_setup_jupyter.md) you think you might like to have. **You should get into the habit of calling `jupyter lab` from the base environment.** See below for more on environments.
   - I also like to install pandas and seaborn in the base environment, for quick scratch work that exists outside of any project.
3. Then, run `conda update --all` (you might consider running this twice — package resolutions are weird).
4. Sign up for a [GitHub](https://github.com/) account if you haven't already. Then, [download GitHub Desktop](https://desktop.github.com/) (in my humble opinion, this is the most efficient way to interface with GitHub for most data science work).
    - [This is a great resource for Git](https://www.atlassian.com/git/tutorials/setting-up-a-repository).
5. Create a "Projects" folder somewhere convenient on your computer. You can name the folder whatever you like; for example, I have a "GitStuff" folder in my home directory (i.e., on a Mac, this is a folder in the same directory as *Movies* and *Pictures*, etc.). Here is where you'll put all future data science project git repositories.

## Initiate a Repository

For each new project ...

1. Create a new folder for your project (give it an [appropriate](https://gravitydept.com/blog/devising-a-git-repository-naming-convention) name), and place it in your "Projects" folder, mentioned above.
2. Initiate a Git repository in this folder with `git init` in the command line (after navigating to that folder with `cd`). Then, [add it to your GitHub Desktop](https://docs.github.com/en/desktop/contributing-and-collaborating-using-github-desktop/adding-and-cloning-repositories/adding-a-repository-from-your-local-computer-to-github-desktop).

## Build an Environment

Ideally, every data science project should have its own [environment](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html).

- In most cases, you'll use a **Conda environment**.
- If you run into versioning issues, use a **Pip environment**.
  - E.g., in summer 2023, scattertext and spaCy are only compatible together in a pip environment.
- If you plan to publish a web app online, use a **venv environment**.

**Notes:**
- Below, `<myenv>` should be replaced with your project environment name. This should clearly allude to your project uniquely (usually, I let the environment name match the GitHub repository name).
- In Windows, if you lose the anaconda prompt, you can activate anaconda with `call C:\anaconda3\Scripts\activate.bat` (depending on where that `activate.bat` file is).
- In general, I recommend using [JupyterLab](https://jupyterlab.readthedocs.io/en/stable/) over Jupyter Notebooks.

### Conda Environment (recommended)

1. Create your environment with `conda create -n <myenv> python=3.x ipykernel` where the Python version `x` is as you like. (`ipykernel` will allow us to access this environment in Jupyter Lab.)
2. Activate the environment with `conda activate <myenv>`.
3. Run `python -m ipykernel install --user --name <myenv> --display-name "<myenv>"`. This step will make use of Jupyter Lab much easier.
   - See the [IPython Kernels Docs](https://ipython.readthedocs.io/en/stable/install/kernel_install.html) for more info.
   - To see all kernels, use `jupyter kernelspec list`.
   - To remove a kernel use `jupyter kernelspec remove <myenv>`.
4. Do your work ... (see the Installing Packages section, below).
5. Deactivate this environment with `conda deactivate`.

### Pip Environment

[Pip](https://pip.pypa.io/en/stable/) is the [official](https://packaging.python.org/en/latest/guides/tool-recommendations/) package installer for Python. Where Anaconda tends to be most appealing to those new to Python, Pip tends to be an industry standard for professional projects.

1. Consider starting out with a yml file. For example:
   - **For NLP projects using scattertext and spaCy**, start with [this](https://github.com/leontoddjohnson/dstools/blob/main/envs/env_nlp.yml)
   - **For web apps**, start with [this](https://github.com/leontoddjohnson/dstools/blob/main/envs/env_app.yml)
2. Rename the file `environment.yml`.
3. Open the yml file, update the `name` field, and add (or change) any packages you know you'll need under `pip:` (and **only** under `pip:`).
4. Run `conda env create -f environment.yml` to create your environment.
5. Follow Step 2 and Step 3 in the previous section.
6. Do your work ... (see the Installing Packages section, below).
7. Deactivate this environment with `conda deactivate`.

> In general, using yml files is actually a good practice for both conda and pip environments!

### venv Environment

Venv is another industry standard, lightweight Python environment framework. If you're going to use [venv](https://docs.python.org/3/library/venv.html), make sure you completely deactivate Anaconda by running `conda deactivate` or `deactivate` until you can no longer see `(base)` in the terminal command line.

1. Create a "venvs" folder in your home directory (e.g., use `cd ~` then `mkdir venvs`).
2. Create your environment with `python3 -m venv ~/venvs/<myenv>`.
   - You may need to replace `python3` with `python`.
3. Activate the environment with `source ~/venvs/<myenv>/bin/activate`.
4. Run `pip install --upgrade pip`, then `pip install ipykernel`.
5. Follow Step 3 in the **Conda Environment** section.
6. Do your work ... (see the Installing Packages section, below).
7. Deactivate this environment with `deactivate`.

*Note: To return back to Anaconda, you can just close and reopen a new terminal, or run `conda activate`.*

> You can save a `requirements.txt` for this environment with `pip freeze > requirements.txt`.

### Installing Packages

In conda environments, only use `conda install` (see [this](https://www.anaconda.com/using-pip-in-a-conda-environment/)). If you're working in a conda environment, and you *really* need a package that cannot be installed any other way, let `pip` be the absolute last resort:
- These pip packages will not necessarily stay up to date with the rest of the conda packages, so be aware that you might need to update them later if things get squirrely.

In pip and venv environments, only use `pip install`.

**For each new package install, read the documentation *FIRST*.** For example, notice how installing [Plotly](https://plot.ly/python/getting-started/#installation) requires separate steps for [use in Jupyterlab](https://plotly.com/python/getting-started/#jupyterlab-support).

## Recommendations

- Keep environments named by global projects (e.g., company names of clients).
- Take a look at [this](http://scipy-lectures.org/intro/language/reusing_code.html) article! Remember **Put everything in functions in modules, THEN call those functions in a script. KEEP FUNCTIONS AS LOW LEVEL AS POSSIBLE.**
- Use the [.gitignore file](https://www.atlassian.com/git/tutorials/saving-changes/gitignore)!
- (If you want to get fancy ...) Have a working branch and a main branch. Do all your work in the working branch, and then do pull requests from the main branch when you have a working version. *Use the normal MAJORUPDATE.MINORUPDATE.PATCH convention* for each pull request.