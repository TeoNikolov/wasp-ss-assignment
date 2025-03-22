# Introduction
![](docs/assets/gifs/hello-there.gif)

This repo hosts the contents of the wasp summer school assignment brief. At the time of writing this README, the assignment brief website can be found here: https://wasp.teonikolov.com

# Backend
The project is built around [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/), where *MkDocs* is a documentation system that focuses on structuring Markdown content, and *Material for MkDocs* is a theme with various customizable plugins to make it prettier and more functional.

# Building and hosting the website
The website is hosted on Cloudflare and it is automatically built upon each Git commit. Note that I use my personal Cloudflare account to host the website, so you won't be able to see build logs if you need them. Normally, you don't need to worry about this if you only modify the `.md` files, but you might need the build logs to debug issues when installing or modifying MkDocs plugins and changing the contents of `requirements.txt`. Reach out to me if you need help.

# Modifying the content
## Using GitHub
The easiest way to modify the assignment content is using GitHub in your browser:
1. Find the `.md` file that you wish to modify (e.g. `docs/tutorial.md`). If you are looking at the page on the website, check the URL.
2. Open the file on GitHub (e.g. [https://github.com/TeoNikolov/wasp-ss-assignment/blob/main/docs/tutorial.md](https://github.com/TeoNikolov/wasp-ss-assignment/blob/main/docs/tutorial.md)) and press `Edit this file`. Alternatively, click the `Edit this page` shortcut available on any page on the website.
3. Make your changes.
4. Press `Commit changes... > Commit changes`. You can leave the default commit message.
5. Wait 30-60 seconds for Cloudflare to rebuild the website and for the changes to take effect.

## Using Docker
You may find it slower to iterate on the content by using GitHub; not only do you need to wait up to 1 minute for the changes to show up, but you can also work on 1 file at a time. Instead, you can install Docker on your machine and modify the website locally. With Docker, the changes are virtually instantaneous, and as a bonus you have access to the logs in case you are modifying MkDocs plugins.

Prerequisites:
- [Install Docker](https://docs.docker.com/engine/install/)
- Clone this repository

To build the website, run in terminal:
- `cd <path/to/cloned_repository>`
- `docker build --no-cache -t teonikolov/website-mkdocs -f Dockerfile .`

To host the website locally, run in terminal:
- `docker run --rm -it -p 8000:8000 -v "${PWD}:/docs" teonikolov/website-mkdocs`

You should now be able to access the website on `http://localhost:8000/`. Any changes you make to the `.md` files will refresh your current page and show the new content. When ready, commit the changes by running in terminal:
1. `git status` to show the modified files
2. `git add <file>` to add the file to staging
3. `git commit -m <commit message>` to make a commit
4. `git push origin main` to push the commit to GitHub and update the public website
5. Wait 30-60 seconds for Cloudflare to rebuild the website and for the changes to take effect.

# Contact
If you need any help, reach out at **tnikolov@hotmail.com**.
