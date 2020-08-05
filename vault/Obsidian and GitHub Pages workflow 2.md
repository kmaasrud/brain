For easy sharing and viewing on mobile, I publish my [Obsidian.md]({{ ref "Obsidian.md.md" }}) vault to <http://www.kmaasrud.com/brain/>. To make the note-taking process as simple and frictionless as possible, I've set up automated publishing using [Hugo]({{ ref "Hugo.md" }}) and [GitHub Pages]({{ ref "GitHub Pages.md" }}) (as well as a [Python]({{ ref "Python.md" }}) script I've written myself). This is whats needed to get it set up:

## Some sort of [VCS]({{ ref "Version control system.md" }})
I use [Git]({{ ref "Git.md" }}) as my preffered [VCS]({{ ref "Version control system.md" }}) and host my vault on [GitHub]({{ ref "GitHub.md" }}). Using version control, I'm able to track how my notes evolve over time and roll back changes if necessary. This is in contrast to automatically syncing to the cloud with a service like [OneDrive]({{ ref "OneDrive.md" }}) or [Dropbox]({{ ref "Dropbox.md" }}). Hosting my vault on [GitHub]({{ ref "GitHub.md" }}) also allows me to use [GitHub Actions]({{ ref "GitHub Actions.md" }}) to easily automate the following actions.

## Convert propietary [Obsidian]({{ ref "Obsidian.md.md" }}) syntax into [Hugo]({{ ref "Hugo.md" }})'s [CommonMark]({{ ref "CommonMark.md" }}) compliance
Even though I'm able to only use vanilla [Markdown]({{ ref "Markdown.md" }}) syntax in [Obsidian]({{ ref "Obsidian.md.md" }}) and achieve much the same result - the [wiki link syntax]({{ ref "Wiki-style links.md" }}) is a lot quicker and intuitive for me. Thus, I need them converted into complying with [Hugo]({{ ref "Hugo.md" }}) and how it handles relative links. I do this using a [Python script](https://github.com/kmaasrud/obsidian-hugo) I've written. Here's a list of what needs to be replaced:

- `[wiki link]({{ ref "wiki link.md" }})` -> `[wiki link]("wiki link.md")`
- `[alias]({{ ref "wiki links.md" }})` -> `[alias]("wiki link.md")`
- `[[wiki link#header name]]` -> `[wiki link]("wiki link.md"#header-name)`
- `![image or embed]({{ ref "image or embed.md" }})` -> `![](image or embed)` (NOTE: Embedding other [Markdown]({{ ref "Markdown.md" }}) files is not part of [CommonMark]({{ ref "CommonMark.md" }}) and must therefore be replaced by a link)

## Making a static site using [Hugo]({{ ref "Hugo.md" }})
With the content properly formatted, [Hugo]({{ ref "Hugo.md" }}) does the heavy lifting. For [GitHub]({{ ref "GitHub.md" }}) users like myself, there's a great [Action]({{ ref "GitHub Actions.md" }}) found [here](https://github.com/peaceiris/actions-hugo) that has [Hugo]({{ ref "Hugo.md" }}) generate the site and later pushes the generated content to another repo or branch. This is perfect, as it allows me to have the source of my site separated from the content that is published through [GitHub Pages]({{ ref "GitHub Pages.md" }}).

## Publishing everything through [GitHub Pages]({{ ref "GitHub Pages.md" }})