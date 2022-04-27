# A geophysical tour of mid-ocean ridges

**Instructor:** [Leonardo Uieda](https://www.leouieda.com/)

Mid-ocean ridges are the places where the oceanic crust and lithosphere are
born.
They are large mountain ranges in the deep ocean, stretching all around the
globe and with heights rivalling that of the tallest mountains on land.
Ridges are also a key part of plate tectonics, a major component of the
biogeochemical cycle of the oceans, and the home of unique biological
communities.

**In this tutorial, we'll study the mid-ocean ridges through the lens of
geophysics.**
We'll use open geophysical data (gravity, bathymetry, lithospheric age) and
open-source Python tools to try to answer questions like:
How do ridges stay so tall?
Are they in isostatic equilibrium?
Why do ocean basins get deeper as they age?
Along the way, we'll also learn how to translate into code the physical models
of the cooling of the lithosphere so that we can compare their predictions with
our data.

<img src="https://github.com/compgeolab/transform2022/raw/main/figures/ridge-cooling-model-setup.png" alt="Sketch of the physical model and main variables used to describe mid-ocean ridges.">

|         | Info |
|--------:|:-----|
| What | Tutorial for [Transform2022](https://transform.softwareunderground.org/) |
| When | Wednesday 27 April 2022 08:00-10:00 UTC |
| Slack (Q&A) | [Software Underground](https://softwareunderground.org/) channel `#t22-wed-mor-geophysics` |
| Live stream | https://www.youtube.com/watch?v=NzJmRlJCNbQ |
| Level requirement | **Intermediate** Python coding experience: Learner has an understanding of variables, loops, and functions as well as the basics of the Scipy stack (numpy and matplotlib). |
| Conda environment  | `t22-wed-mor-geophysics` |
| Notebook | [`mid-ocean-ridge-geophysics.ipynb`](https://nbviewer.org/github/compgeolab/transform2022/blob/main/mid-ocean-ridge-geophysics.ipynb) |
| Notebook (empty version) | [`mid-ocean-ridge-geophysics-empty.ipynb`](https://nbviewer.org/github/compgeolab/transform2022/blob/main/mid-ocean-ridge-geophysics-empty.ipynb) |
| Run online | [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/compgeolab/transform2022/HEAD?labpath=mid-ocean-ridge-geophysics.ipynb) |

## 🧑🏿‍💻 How to take part

**[Transform](https://transform.softwareunderground.org/) is an fully online event.**
You can participate either synchronously (live) or asynchronously (any time in the future).

### Synchronous:

1. ⚠️ **Before the tutorial** ⚠️:
   1. Setup your computer (see below).
   1. Sign up for the [Software Underground Slack](https://softwareunderground.org).
1. Connect to the YouTube livestream at the tutorial time and hop on to the
   `#t22-wed-mor-geophysics` channel on Slack as well.
1. Follow along with the tutorial on your computer (I'll write the code live).
   I'd recommend having your Jupyter notebook and the livestream side-by-side.
1. If you have any questions, post them on the Slack and we'll get to them.

### Asynchronous:

1. Setup your computer (see below).
1. Open the YouTube recording.
1. Follow along with the tutorial on your computer (I'll write the code live).
   I'd recommend having your Jupyter notebook and the livestream side-by-side.
1. If you have any questions, post them on the [Software Underground Slack](https://softwareunderground.org)
   (make sure you mention which tutorial you're asking about).

## 🚶🏿‍♀️ How to follow along

I will be explaining things and typing out code live in
a Jupyter notebook. To follow along with the tutorial, you
have 2 options:

1. Type out the code with me as I go along.
   * **Pros:** Keeps you from getting distracted, builds muscle memory,
     and ensures you follow my reasoning.
   * **Cons:** It can be difficult to listen and type at the same time,
     particularly if you encounter an error.
   * **How to do it:** Download the "empty" version of the notebook
     (links above) that has most of the code removed. Open this
     and type along with me.
1. Run the code that is already written along with me.
   * **Pros:** You don't have to match my typing so it's one less
     thing to worry about.
   * **Cons:** Can get distracted or not fully understand how things are
     built up.
   * **How to do it:** Download the "full" version of the notebook
     (links above) that has the full code for the tutorial. Read
     the code as I type along and run the code cells when I do.

There is no right way to do it so you'll have to try what works best for
you.

> **My personal recommendation:**
> Download both notebooks and start by trying to type along with me in the
> empty version.
> If you miss anything or have trouble keeping up, either copy it from the
> full notebook or switch to that one entirely.
> With the video being on YouTube, you can always pause or slow it down
> so I highly encourage trying to type things out for yourself.

## 👩‍🎓 Learner profile

This tutorial is designed with learners of the following profile.

> **This does not mean that you need to fit this profile in order
> to take part**. It is meant only to communicate what is our starting point
> for building out the content of the tutorial.

* Undergraduate later in their studies or postgraduate in Earth Sciences.
* Has takes advanced level mathematics (summations, exponentials, trigonometric functions)
  and has had some exposure to calculus (differential equations).
* Is able to write Python code to analyze data, make figures, etc but not
  necessarily studied software development.
* Knows the basics of plate tectonic theory and global geology and geophysics,
  including the concept of isostatic equilibrium.

## 💻 Computer setup

For this tutorial, you'll need to have a specific Python environment setup.
The particular software that is required is listed in the
[`environment.yml` file](https://github.com/compgeolab/transform2022/blob/main/environment.yml).
Follow the instructions below to get set up.

### Step 1: Download a Python distribution

You'll need either one of:

* [Miniforge](https://github.com/conda-forge/miniforge#miniforge3) (preferred for Linux/Mac users)
* [Miniconda](https://docs.conda.io/en/latest/miniconda.html) (preferred for Windows users)
* [Anaconda](https://www.anaconda.com/products/distribution)

If you have any of these installed already, you don't need to reinstall or switch.

### Step 2: Create the tutorial environment

This step installs all of the extra things we need for the tutorial.
It does so in a separate *conda environment* to avoid messing with
your Python installations.

1. Download the [`environment.yml`](https://github.com/compgeolab/transform2022/blob/main/environment.yml) file to your computer.
1. Open a terminal (Linux/Mac) or Anaconda Prompt (Windows).
1. The following steps should be done in the terminal/prompt:
   1. Navigate to the folder that has the downloaded `environment.yml` file
      (if you don't know how to do this, take a moment to read the
      [Software Carpentry lesson on the Unix shell](http://swcarpentry.github.io/shell-novice/)).
   1. Type out the command `conda env create --file environment.yml` and hit `Enter` to create the conda environment
      (this will download and install all of the packages used in the tutorial so it could take a while).

If everything went smoothly, you should now have a *conda enviroment* called
`t22-wed-mor-geophysics` which has all our software installed!

### Step 3: Activate the environment and launch Jupyter

Now that everything has been installed, we can finally start
Jupyter and get to work!

> **This is the only step that needs to be repeated** whenever you stop working
> on the tutorial and come back. The previous steps only need to be done once.

In your terminal or Anaconda Prompt, run the following (type it out and hit `Enter`):

1. `cd` (return to your *home* folder)
2. `conda activate t22-wed-mor-geophysics` (activate the *conda environment*)
3. `jupyter lab` (start Jupyter Lab)

This should open your browser and load Jupyter Lab.

**Note for Windows users:** If Internet Explorer opens and you only get a blank page,
this is because Jupyter Lab does not work with Internet Explorer.
To get around this, install Firefox, Chrome, or any other browser and make it
your default browser. Close your terminal/prompt and repeat the steps above.

## 🧑‍🏫 For instructors

The tutorial is designed to be taught as a 2 hour session with **live-coding**.
To do so, create a copy of the notebook and delete all or most of the code
cells (it's OK to leave some in to allow more time in the tutorial).

Type in the code as you explain what you're doing. This will help you control
your pacing and avoid going too fast. It also opens up the opportunity for you
to make mistakes and teach students how to identify and solve them.

Ideally, have students follow along on their own computers, typing in the code
with you. Make sure you also share a copy of the pre-filled notebook with
students so that they can choose to not type and listen at the same time.

## ⚖️ License

The original material for this tutorial can be found at
[leouieda/transform2022](https://github.com/leouieda/transform2022).
Comments, corrections, and additions are welcome.

All source code is made available under the BSD 3-clause license. You can
freely use and modify the code, without warranty, so long as you provide
attribution to the authors.

Unless otherwise specified, all figures and Jupyter notebooks are available
under the [Creative Commons Attribution 4.0 License (CC-BY)](https://creativecommons.org/licenses/by/4.0/).

The full text of these licenses is provided in the [`LICENSE.txt`](LICENSE.txt)
file.
