# Blogmaker

This is an ultra-simple blog publishing solution. It is configured to be hosted on GitHub and be automatically built using GitHub actions.

### Dependencies for local development

* pandoc
* rsync (Only needed if you plan to publish the blog on your server)
  * Not needed if you are hosting on GitHub

### How to use

See the [posts](./posts) directory for what a post should look like. Posts must be written in [markdown](https://daringfireball.net/projects/markdown/syntax), and filenames must end in ".md". Dates must be in (yyyy/mm/dd) format. All posts must be in the posts directory.

If you need a post to use MathJaX to format LaTeX equations, add the line

```
[pandoc]: <> (--mathjax)
```

to the config at the top of the post.

To compile a post to html, run `./publish.py posts/name_of_post.md` (or `./publish.py posts/*` to recompile everything). Compilation also happens on GitHub Actions.

#### Using your own server

Use `./publish.py --sync` to upload the latest version of your site to your server (make sure to put your server details, as well as the site title and icon, in [config.md](./config.md)).

For the server, the simplest setup is to use any VPS, `apt install apache2`, make sure apache2 is running, and just set the directory to /var/www/html.

#### Hosting on GitHub pages
- Fork/clone this repo.
- Turn on GitHub pages from settings and set the branch as gh-pages and directory as root.
- Change the domain to your repo from `config.md`
- Push changes to `main` and voila!

### Credits:

- https://hackmd.io for CSS styles.
- @vbuterin for building and making his blogmaker open source.
