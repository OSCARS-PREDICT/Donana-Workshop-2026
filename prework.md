---
layout: default
permalink: /prework/
title: "Before you travel"
eyebrow: "Pre-workshop requirements and forms"
standfirst: "Technical workflow requirements, forms to fill out, and one short set of update slides to make."
footer_image: /assets/img/road.jpg
footer_alt: "Road in Doñana"
---

## The pre-workshop technical requirements

### 1. A functional R workflow

<span class="chip">by Monday 12th October 2026</span>

Your own forecasting workflow, running end to end locally, from input data through to forecast output.
For the workshop, this should be a subset of your data (especially if your study area is large / spatial resolution is high!)

**What "functional" means**

- Paths to example data are relative based on <code>./mnt/inputs/</code> and <code>./mnt/outputs/<code> to mimic being integrated in LifeWatch ERIC (LWE)
- Parameters are coded as <code>arguments<code> (imagine everything is a function, rather than hard-coded)
- Inputs are a <code>small subset<code> of your study
- It writes outputs to disk in a documented format, e.g., <code>.OMX</code> or other open standard
- Includes a short <code>.txt file</code> indicating all installations, packages and versions required
- Component annotation metadata file created <code>.json file</code> see [https://gitlab.lifewatch.dev/workflows/legacy-component-metadata/-/blob/main/annotation-schema.json?ref_type=heads]
- Pushed to a <code>firstimplement</code> branch off <code>develop</code> branch in GitLab (see below)

**What it does not need to be**

Elegant, final, or scientifically finished.
Just think first version/first implementation. 
This stays private to us, and will not be published yet. 
We will be pushing to the 'develop' branch which is closed/only visible by us.


### 2. Your first push to LWE via GitLab

<span class="chip">before you leave for the workshop</span>

Push your first version code to the LWE GitLab (branched off the 'develop' branch - not 'main'!) to show work in progress, version control, and create our shared working area.
This leaves the workshop clear for collaborative coding sessions, and pathway to full LWE integration.

**Steps**

Check back here to find full LWE guidance [link will be added TBC]. Here is a high-level summary:
1. Confirm set up on all LWE systems (you can arrange meeting with Emma & LWE to discuss your workflow diagram/ideas, component requirements and dependencies).

2. Raise ICT ticket to request component repository be set up for you [https://ictdesk.lifewatch.eu/front/helpdesk.public.php].

3. Clone the newly created component repository to your local computer/machine:
 a. Log into LWE [Gitlab](https://gitlab.lifewatch.dev/), navigate to your new component repo, click Clone > Copy (make a note of the http link path)
 
 b. Set up a local document folder on your computer
 
 c. Navigate to that local folder within your computer's Command Prompt app (cmd line) using the 'cd' command N.B. File paths on Windows machines use forward slash (/), Apple MAC use back slash (\) Emma's example:  
    
    cd .\Documents\PREDICT\LWE
    
 d. Use the cmd line, and the http link copied from your GitLab component page to clone the repository onto your machine, for e.g., (make sure to replace "EcologicalForecastingEvaluator" with your actual component name!)
    
    git clone https://gitlab.lifewatch.dev/workflows/workflow-components/EcologicalForecastingEvaluator.git
  
 
 This brings all the LWE necessary metadata file templates onto your local machine. 

4. Use file explorer to paste your functioning code/scripts and associated metadata to this same folder.

5. Push your code update back to LWE GitLab on a new (temporary/private) branch off the 'develop' branch named e.g., <code>firstimplement</code>:
 
 a. How to do this with the cmd line:
    
    git fetch origin
    
  This fetches the remote develop branch so git knows it exists locally.
    
    git checkout -b feature/firstimplement origin/develop
    
  Creates your 'firstimplement' feature branch off develop (not main)

Next you can stage your new code files using "git add filename.fileformat" - here are some examples:
    
    git add README.md        #(README helpful for group understanding of your code)
    git add annotation.json  #(The most important file that explains your code parameters/arguments)
    git add yourscript.R     #(your scripts - can be any language)
    git add yourpackages_installations.txt #(Describes to LWE which packages require installaing to run your code)
    git add Dockerfile       #(leave as template if you not yet working)
    git add entrypoint.sh    #(leave as template if Docker not yet working)
    git status               #(to check status and see what git sees is already there)

Next write your comit message e.g.,:
    
    git commit -m "feat: add Climate Data Downloader component v0.1.0 (Copernicus CDS + CHELSA)"
Finally, push to the new feature branch off develop (e.g., firstimplement)
    
    git push origin feature/firstimplement

You can view the web version of your code repository in [GitLab](https://gitlab.lifewatch.dev/) to check it all uploaded ok. 

**Done means:** your repository is visible to you (with a lock symbol - this means it is not published yet) inside the [LWE workflow components project](https://gitlab.lifewatch.dev/workflows/workflow-components), the pipeline has run at least once locally, and you are ready for LWE support to get fully integrated.

### 3. Setting up Docker containerisation

<span class="chip">(Ideally) before October workshop, but not mandatory if you have not worked with Docker before</span>

Eventually, your workflow will need to be able to run the same way on someone else's machine and on LWE infrastructure. 
That means it needs a container. LWE are working on a new and easier way to make this happen, and guidance will be shared soon.
We are also running a pre-workshop drop in session(s) in September to help with this.

**What you need**

- A `Dockerfile` at the root of your repository.
- An image that builds from scratch, on a clean machine, with no manual steps.
- Your workflow running inside that container and producing the same output as it does on your laptop.

**Starting point** — LWE are writing a technical guidance to help, they also provide templates for starting out and we are running pre-workshop drop-in support sessions.


## Pre-workshop checklist

<ul class="check">
<li>Your LWE account GitLab account active (https://gitlab.lifewatch.dev/)</li> 
<li>Your initial workflow diagram ready, with individual components planned, first meeting/discussion with LWE completed</li>
<li>Your script parameters are clearly defined, and set up as arguments in your code</li>
<li>Your workflow components run locally with a small subset of data</li>
<li>Your annotation schema is created (.Json file). This is your component metadata - must match the arguments expected in the [LWE template](https://gitlab.lifewatch.dev/workflows/legacy-component-metadata/-/blob/main/annotation-schema.json?ref_type=heads)</li>
<li>Your dependencies (e.g., R packages and installations required) are ready in a .txt file (this is a planned workaround if Docker is not working for you)</li>
<li>Your component repository(s) are requested to LWE and they set up for you inside GitLab (https://gitlab.lifewatch.dev/workflows/workflow-components)</li>
<li>You clone your component repository(s) locally to your machine</li>
<li>Your first working code is copied into your cloned local repository</li>
<li>Your first code is pushed back into a new "firstimplement" branch (branched from "develop" branch) of the component repository in LWE GitLab</li>
<li>Ideally: Dockerfile written and image builds from scratch but LWE can help with this if not (come to our drop in session in Septemberm or we follow a workaround)</li>
<li>Laptop packed, along with its charger and adaptor if needed, brain in gear ready to share, collaborate and get stuff done</li>
</ul>

## If you get stuck

Understandable! Please do not go quiet or get put off by the more technical elements. Two routes, both fine to use as often as you need:

- **Drop-in session(s)** - September TBC with LWE Engineers on hand to help. No agenda, no preparation. Bring whatever is broken/not running and we can help.
- **Open an issue** - Raise a ticket with [LWE ICT Helpdesk](https://ictdesk.lifewatch.eu/). You have to be registered, any issues speak to Emma.

The **Monday 12th October** deadline for your first code push is real, please respect it.
Sharing any issues you have early costs you nothing, and helps our collective progress.
Don't forget, we are here to help!

## The other three admin-y things

### 1. Pre-workshop stakeholder engagement survey

Melina our PREDICT partner is building a stakeholder engagement workshop session that requires your input first. 
Please participate as honestly as possible in where you are with these considerations in your workflow development.
<span class="chip chip--quiet">Submitted by Monday 31 August</span> — [fill out here](https://ee.kobotoolbox.org/x/s9yfCDz5)

### 2. Workflow update: "My workflow in 5 minutes"

<span class="chip chip--quiet">Submitted by Friday 9th October</span> — upload to [our shared google drive](https://drive.google.com/drive/folders/1qqk_UDSeDCP8-x8PZqfBe5jC8SVx3yXW)

You will present these when we arrive in Doñana. Five minute updates, three slides max:

1. **What I run** — a diagram of the workflow
2. **What it takes as input** — data sources, formats, resolution, update frequency
3. **What it produces** — output format, units, uncertainty representation, how often

No formal introduction needed, no results slides. If you have done the pre-workshop technical requirements above, these slides are mostly screenshots and should not take long to put together.

### 3. Organisational forms to fill out (travel info, dietary requirements)
#### Dietary info

Any allergies or intolerances, which meals you will be present for, so we can update the catering team.
<span class="chip chip--quiet">Submitted by Monday 31st August 2026</span> — [Fill out here](https://ee.kobotoolbox.org/x/8be7qdKo)


#### Travel details

<span class="chip chip--quiet">Submitted by Monday 31st August 2026</span> — [Fill out here](https://ee.kobotoolbox.org/x/hydbfNID)

Arrival time in Sevilla, flight or train number, and a mobile number we can reach you on during travel day.
Even better, download the LWE chat app onto your phone and saves sharing personal info. See FAQ for help.

