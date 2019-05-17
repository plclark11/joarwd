---
layout: post
title:  "Deploy a Static Jekyll Website to Github Pages from Windows 10"
date:   2019-05-17T15:20:00Z
categories: how-to
---

1. Create Github account.
2. Create repository for new-site.
2. Download Github Desktop [https://desktop.github.com/](https://desktop.github.com/) 
and command line [https://gitforwindows.org/](https://gitforwindows.org/)
2. Jekyll/Ruby install via RubyInstaller 
[https://jekyllrb.com/docs/installation/windows/](https://jekyllrb.com/docs/installation/windows/)
3. Clone new-site repository to desktop with Github Desktop.
4. `cd` to new-site directory. 
5. `git checkout -b gh-pages`
5. `cd` up to new-site directory parent. 
6. Create Jekyll site in new-site repository. `jekyll new new-site`. Use --force if needed.
6. Modify _config.yaml: add repository name to baseurl parameter. (baseurl: "/newsite" )
7. To run site locally: `jekyll build`, `jekyll serve --watch`
7. Add pages/posts as you like.
8. Use Github desktop to commit/push to github.com.
9. Visit your published site.

#### References
* [https://jekyllrb.com/docs/](https://jekyllrb.com/docs/)
* [https://help.github.com/en/articles/setting-up-your-github-pages-site-locally-with-jekyll](https://help.github.com/en/articles/setting-up-your-github-pages-site-locally-with-jekyll)