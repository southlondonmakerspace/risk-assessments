# South London Maker Space Risk Assessments

jcl/2016-07-31

At South London Maker Space we have many tools, most of which
need risk assessments in order to be safely and legally used.

This project contains

* The master copies of the risk assessements
* Some scripts for formatting them
* The outputs until we have a better place

The master copies were made by scripts from the original
shared spreadsheet, and are in Markdown format.

The layout of them for use is done into HTML via JSON.

It automatically adds 
* Formatting
* Images of tool (of same name as filename but .jpg),
* PPE icons (for a few known kinds)
* Calculates the risk from the severity-likelihoods
* Colour codes the risks
* Labels the tool with the worst pre-control risk

It also makes a summary table so we can read all the
hazard tables on a single web page.

The masters are in Markdown because non-technical people
need to edit them, most likely at Github online editor.

# The Hazard matrix

Part of the script calculates the correct risk from the 
severity and likelihood of the hazard, according to the
table on discourse from 2016-07-25:

| Level | Description | Theoretical | Very Unlikely | Unlikely | May Happen |  Likely | Certain |
|-|:-|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| 0 | No injury				|None  |None  |None  |None  |None  |None  |
| 1 | Minor injury			|Low   |Low   |Low   |Low   |Medium|High  |
| 2 | Significant injury		|Low   |Low   |Medium|Medium|High  |High  |
| 3 | Serious injury			|Low   |Medium|Medium|High  |High  |High  |
| 4 | Fatality, life-changing injury	|Low   |Medium|High  |High  |High  |High  |

If we want to change this, it's a simple change to the code
to get all the RAs updated.

# Required format

The formatter accepts Markdown but with required headings,
and formats the outputs appropriately.

    # Tool
    Computer Mouse
    
    # Induction
    Required
    
    # Activity
    * Pointing at objects on screen
    
    # Personal Protective Equipment
    * Ear protection
    
    # Procedure
    ## Before
    * Perform a visual inspection of mouse
    * Ensure all high voltage is removed
    
    ## During
    * Keep mouse away from cat at all times
    
    ## After
    * Ensure mouse poo removed
    
    # Risk
    ## Hazard
    RSI
    
    ## Who
    Operator

    ## Severity/Likelihood
    Before 3-3 After 1-1
    
    ## Controls
    * Seat at correct height

    # History
    2016-08-01 / jcl: created

# Where to put the output files

Ideally we want to put them on discourse.southlondonmakerspace.org,
however there are currently some formatting and logistical problems
in doing so.

Therefore we have a _temporary_ site at
 htts://sysdiary.org/slmsrams

Edits to the Git hub master pages update the pages at that site
automatically (once a minute).

# How to remake the output files

If you know about git and want to make a local copy
 git pull origin master
 ./doit

(end)
