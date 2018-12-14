# ACCESS-OM2-1-025-010deg-report
This document is currently work in progress. The source files hosted here are the latest version.
If you want to see the draft report as a PDF, click [here](http://cosima.org.au/wp-content/uploads/2018/11/ACCESS-OM2-1-025-010deg-b0fd434.pdf) (this might not be completely up-to-date with the sources).

This document serves two purposes:
* It is a technical report to document the configuration and performance of the [ACCESS-OM2](http://cosima.org.au/index.php/models/) suite of coupled global ocean-sea ice models at 1, 0.25 and 0.1 degree horizontal resolution, intended to be a resource for the [COSIMA](http://cosima.org.au) community and readily updated.
* It will form the basis of one or more journal papers to announce and assess the performance of these models, most likely to be submitted to [GMD](https://www.geoscientific-model-development.net).

The report has two halves: a technical section coordinated by Andrew Kiss, and a model assessment section coordinated by Andy Hogg.

## For contributors
- Please sign up with GitHub and click _Watch_ (top right corner) to be kept informed of discussions.
- To (publicly) discuss aspects of the paper, please [post an issue](https://github.com/OceansAus/ACCESS-OM2-1-025-010deg-report/issues) instead of using email.
- This is a public repository, so our draft is viewable to anyone. If that bothers you, let us know here: https://github.com/aekiss/ACCESS-OM2-1-025-010deg-report/issues/4
- Figures are generated by Jupyter notebooks, viewable in [GitHub](https://github.com/OceansAus/ACCESS-OM2-1-025-010deg-report/tree/master/figures) or  [nbviewer](http://nbviewer.jupyter.org/github/OceansAus/ACCESS-OM2-1-025-010deg-report/tree/master/figures/).

## Quick start
Do this to download the sources for this document:
```
git clone https://github.com/OceansAus/ACCESS-OM2-1-025-010deg-report.git
cd ACCESS-OM2-1-025-010deg-report/
./setup.sh 
./pullfigs.sh 
```
You should then be able to generate ACCESS-OM2-1-025-010deg.pdf using latex. You'll also need to run bibtex to get the references.

`pullfigs.sh` gets all the figure files but requires membership of the hh5 group - apply [here](https://my.nci.org.au/mancini/project/). Alternatively, set the "overleaf" boolean to true in the header of ACCESS-OM2-1-025-010deg.tex to make it latex-able without figures.


### How to edit the report

We are using git to manage document versions and merging. You can edit the text in one (or both!) of two ways: either Overleaf or your own LaTeX installation (see below); also see below for how to create or edit figures. This git-based workflow looks complicated but allows all contributors to work in parallel and have their changes tracked and merged together easily. At least, that's what we hope! 

Alternatively (and only if you _really_ can't stand the hassle of git) you could just [download the central version as a ZIP file](https://github.com/OceansAus/ACCESS-OM2-1-025-010deg-report/archive/master.zip) and email Andrew Kiss or Andy Hogg your changes. But we'd prefer contributors to use a git-based approach if possible. 


#### To edit text via Overleaf v2 beta
Warning: Overleaf v2 is beta software. Use at your own risk.

You won't be able to see the figures when using Overleaf.

##### Initial setup
1. Sign up to [GitHub](https://github.com), go to  [https://github.com/OceansAus/ACCESS-OM2-1-025-010deg-report](https://github.com/OceansAus/ACCESS-OM2-1-025-010deg-report) and click _Fork_ (top right corner). This will give you your own copy of the report hosted on your GitHub page. 
2. Sign up to [Overleaf](https://overleaf.com).
3. Go to [https://v2.overleaf.com](https://v2.overleaf.com), choose _New Project_ -> _Import from GitHub_, give Overleaf write access to your GitHub repositories (if you're OK with that), and import ACCESS-OM2-1-025-010deg-report from your fork.
4. Set the "overleaf" boolean to false in the header of ACCESS-OM2-1-025-010deg.tex.
##### Workflow
1. Do your edits in [https://v2.overleaf.com](https://v2.overleaf.com).
2. Choose _Menu_ -> _Sync_ -> _GitHub_ to push your changes back to your fork on GitHub.
3. Go to your fork of ACCESS-OM2-1-025-010deg-report on [GitHub](https://github.com) and **do a _pull request_** (click _Pull requests_ -> _New pull request_ -> _Create pull request_) to have your changes be incorporated into the [central version](https://github.com/OceansAus/ACCESS-OM2-1-025-010deg-report) we all share.

It's a good idea to **do steps 2 and 3 fairly often** to keep your version in sync with the [central version](https://github.com/OceansAus/ACCESS-OM2-1-025-010deg-report) so that your changes can be easily merged, and everyone will have a clearer idea of what you intend for your part of the report.

#### To edit text via your own LaTeX installation
##### Initial setup
1. You will need LaTeX and git installed on your machine.
2. Sign up to [GitHub](https://github.com), go to  [https://github.com/OceansAus/ACCESS-OM2-1-025-010deg-report](https://github.com/OceansAus/ACCESS-OM2-1-025-010deg-report) and click _Fork_ (top right corner). This will give you your own copy of the report hosted on your GitHub page. 
3. Bring up a terminal on your machine, `cd` to a suitable directory and do `git clone https://github.com/YOUR-GIT-USERNAME/ACCESS-OM2-1-025-010deg-report.git`, inserting your git username in the obvious place. This will give you a local version of your forked repository.
4. Do `cd ACCESS-OM2-1-025-010deg-report; git remote add upstream https://github.com/OceansAus/ACCESS-OM2-1-025-010deg-report.git; ./setup.sh` 
5. Get all the figure files via `./pullfigs.sh`.

##### Workflow
Edit the document as usual. 

When you want to share your changes you will need to commit them to your local repository, push this to your GitHub fork, then do a pull request to have your GitHub fork merged into the [central version](https://github.com/OceansAus/ACCESS-OM2-1-025-010deg-report).

Here's how:
1. Bring up a terminal and `cd` to your document directory.
2. Do `git status -u` to see what files you've changed (for more detail, do `git diff`).
3. Do `git add FILENAME` repeatedly for each file whose changes you want to commit (replacing `FILENAME` with the file's relative path). Don't add any binary files (e.g. .pdf or .png).
4. If you added any files in step 3, do `git commit -m "My comments"` to commit these files to your local repository (with a comment on what was changed).
5. Do `git pull` to merge any changes from your GitHub repository into your local version (e.g. if you also pushed text changes via Overleaf or figure changes via the VDI).
6. Do `git pull upstream master` to merge any changes from the [central version](https://github.com/OceansAus/ACCESS-OM2-1-025-010deg-report) into the local version (hopefully there will be no merge conflicts).
7. Do `git push` to upload your repository to your fork on GitHub. This will also update the version that Overleaf sees when you sync it.
8. Go to your fork of ACCESS-OM2-1-025-010deg-report on [GitHub](https://github.com) and **do a _pull request_** (click _Pull requests_ -> _New pull request_ -> _Create pull request_) to have your changes be incorporated into the [central version](https://github.com/OceansAus/ACCESS-OM2-1-025-010deg-report) we all share.

It's a good idea to **do these steps fairly often**. This will keep your local version closely in sync with the [central version](https://github.com/OceansAus/ACCESS-OM2-1-025-010deg-report) so that your changes can be easily merged, and everyone will have a clearer idea of what you intend for your part of the report.


#### To add or edit figures
We would like all figures to be generated by Jupyter notebooks in the `notebooks` directory to facilitate editing and updating. The Jupyter notebooks are run on the [NCI VDI](http://nci.org.au/services/vdi/) so they have access to the model output data. 

##### Initial setup
1. Sign up [here](https://my.nci.org.au/mancini/signup/) if you don't have an NCI account. You need an NCI account in order to have access to the [VDI](http://nci.org.au/services/vdi/). You'll also need membership of the hh5 group to access the model output data - apply [here](https://my.nci.org.au/mancini/project/).
2. Open a terminal on your local machine and download [jupyter_vdi.py](https://raw.githubusercontent.com/OceansAus/cosima-cookbook/master/scripts/jupyter_vdi.py) with 
`curl -O https://raw.githubusercontent.com/OceansAus/cosima-cookbook/master/scripts/jupyter_vdi.py`
3. Make it executable: `chmod +x jupyter_vdi.py`
4. Run it: `./jupyter_vdi.py`
Hopefully this will open a web page (or give you a URL) showing the folders you have on the VDI (if it doesn't work, you may need to edit `~/cosima_cookbook.conf` to give it your VDI username, and run `./jupyter_vdi.py` again). 
5. In this web page, click _New_ -> _Terminal_ to get a terminal in the VDI.  
6. In this web page terminal, `cd` to a suitable directory and do `git clone https://github.com/YOUR-GIT-USERNAME/ACCESS-OM2-1-025-010deg-report.git`, inserting your git username in the obvious place. This will give you a copy of your forked repository on the VDI.
7. Do `cd ACCESS-OM2-1-025-010deg-report; git remote add upstream https://github.com/OceansAus/ACCESS-OM2-1-025-010deg-report.git`
8. Set up a suitable Python environment: `module use /g/data3/hh5/public/modules; module load conda/analysis3`
8. Download the [COSIMA Cookbook](https://github.com/OceansAus/cosima-cookbook): `cd ~; git clone https://github.com/OceansAus/cosima-cookbook.git`
9. ...and activate it with `cd cosima-cookbook; pip install --user -e .`

(If you [connect to the VDI GUI directly](https://opus.nci.org.au/display/Help/VDI+User+Guide) instead of using jupyter_vdi.py, you should bring up a terminal in the VDI and do steps 5 - 10. You can open Jupyter with `jupyter notebook` in the terminal.)

##### Workflow
You are now set up to modify and run existing notebooks or create your own.

The report figures are in `ACCESS-OM2-1-025-010deg-report/figures`. 
Please note:
* If you make a new notebook, put it in a new subdirectory of `ACCESS-OM2-1-025-010deg-report/figures`. Each notebook should be in a separate subdirectory (i.e. exactly one notebook per subdirectory), and all its output figures should be saved in that subdirectory so we can easily tell which script generated each plot.
* For LaTeX compatibility, don't use spaces or dots (other than for the final tag) in your subdirectory name, Jupyter notebook filename, or output image filenames.
* PDF is preferred for line plots. Map-type plots can be PDF or PNG. Don't use JPG.

There are a lot of useful example notebooks in the `cosima-cookbook` directory.
The tutorial from the 2018 COSIMA workshop may also be useful for those new to the COSIMA Cookbook:
`cosima-cookbook/DocumentedExamples/COSIMA_CookBook_Tutorial.ipynb`.
It can also be viewed [here](http://nbviewer.jupyter.org/github/OceansAus/cosima-cookbook/blob/master/DocumentedExamples/COSIMA_CookBook_Tutorial.ipynb).

When you want to share your *notebook* changes you will need to commit them to your local repository, push this to your GitHub fork, then do a pull request to have your GitHub fork merged into the [central version](https://github.com/OceansAus/ACCESS-OM2-1-025-010deg-report). You can do this by following all the steps in _Workflow_ under _To edit text via your own LaTeX installation_ [above](https://github.com/OceansAus/ACCESS-OM2-1-025-010deg-report#workflow-1), but in a VDI terminal. Then share the *figure files* with `./pushfigs.sh`. Please don't commit output files (e.g. .pdf or .png) to git.

If you just want to incorporate your new figure files from the VDI into the version on your local machine, do `./pushfigs.sh` in a VDI terminal, then bring up a terminal on your local machine, and do `./pullfigs.sh`. But please remember to also use git to commit and share your notebook changes.

#### Comparing Jupyter notebooks (and making git play nicely with them)
The standard git merge and diff tools don't work well with Jupyter notebooks, so it's better to install content-aware merge and diff using [nbdime](https://nbdime.readthedocs.io). 
Here's how:
1. On the VDI, bring up a terminal (e.g. from Jupyter in your browser) and do `pip install --user nbdime`. This will install nbdime in `~/.local/bin`. 
2. Do `which nbdime`. If this shows it can't be found, you'll need to add `~/.local/bin` to your path by opening `~/.bash_profile` in an editor (e.g. `nano ~/.bash_profile`) and adding
`PATH=$PATH:$HOME/.local/bin/` and 
`export PATH`
to the end. Save the file and and exit the editor, then `source ~/.bash_profile`.
3. Do `nbdime config-git --enable --global` to set up git to use nbdime for diff and merge.

That's it. git will now diff and merge notebooks in a way that respects their structure. You might also want to do this on your local machine if you've cloned your fork there too.

[nbdime](https://nbdime.readthedocs.io) also provides great web-based tools for comparing notebooks - see the [website](https://nbdime.readthedocs.io) for details.