For easy sharing and viewing on mobile, I publish my [[Obsidian]] vault to <http://www.kmaasrud.com/brain/>. To make the note-taking process as simple and frictionless as possible, I've set up automated publishing to [[GitHub Pages]] via [this script](https://github.com/kmaasrud/obsidian-html), that I've written in [[Python]]. Here's a brief description of my process:

## Some sort of [[Version control system|VCS]]
I use [[Git]] as my preffered [[Version control system|VCS]] and host my vault on [[GitHub]]. Using version control, I'm able to track how my notes evolve over time and roll back changes if necessary. This is in contrast to automatically syncing to the cloud with a service like [[OneDrive]] or [[Dropbox]]. Hosting my vault on [[GitHub]] also allows me to use [[GitHub Actions]] to easily automate the below actions.

## Convert propietary [[Obsidian]] syntax into vanilla [[Markdown]]
Even though I'm able to use vanilla [[Markdown]] syntax in [[Obsidian]] and achieve the same result - the [[Wiki-style links|wiki link syntax]] is a lot quicker and intuitive for me. Thus, I first need them converted into vanilla [[Markdown]] to simplify generating the page. 

## Making a static [[HTML]] pages
When my vault is represented in [[Markdown|vanilla Markdown]], my script uses the [[Python]] package [markdown2](https://github.com/trentm/python-markdown2) to convert all pages into [[HTML]]. In addition, it places this [[HTML]] tree into a specified template to support the published vault's styling. 

## Publishing everything through [[GitHub Pages]]
In the end I publish the generated site through [[GitHub Pages]], giving me free hosting. This step is still [[WIP]]...