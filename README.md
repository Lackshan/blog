# Project Blog
![](https://github.com/Lackshan/blog/workflows/Build%20and%20deploy%20Jekyll%20site%20to%20GitHub%20Pages/badge.svg)

This blog showcases my various projects.

## Prerequisites
First follow the instructions [here](https://jekyllrb.com/docs/installation/) to install Jekyll.

## Build
### Serve site locally for testing
To host the site locally run:
```bash
JEKYLL_ENV="production" bundle exec jekyll serve
```

### Generate static files for hosting
```bash
JEKYLL_ENV="production" bundle exec jekyll build
```
## Deploy
### Automated deployment using GitHub Actions
After every commit, the action defined in ```.github/workflows/github-pages.yml``` will build the site and copy the contents of the resulting ```_site``` folder to the ```gh-pages``` branch.

[Source](https://jekyllrb.com/docs/continuous-integration/github-actions/)
[Also helpful](https://github.com/MichaelCurrin/jekyll-actions-quickstart)

### Accessing site
The site is hosted on [blog.lackshan.dev](https://blog.lackshan.dev)

## Credits
This blog uses the sudo theme which can be found [here](https://github.com/oneohthree/sudo-jekyll).
