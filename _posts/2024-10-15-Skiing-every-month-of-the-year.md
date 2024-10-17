---
# layout: posts
title:  "Skiing every month of the year"
date: 2024-10-15

header:
  image: /assets/images/posts/dummy_post_img.jpg
  teaser: /assets/images/posts/dummy_post_img.jpg

# categories:
#   - Setup
#   - Uncategorized
# tags:
#   - ruby
#   - fork
#   - github
related: true
share: False
---

# Welcome

1. I forked the repo from [https://github.com/mmistakes/minimal-mistakes](https://github.com/mmistakes/minimal-mistakes) following this tutorial: [https://happygitwithr.com/fork-and-clone#fork-and-clone](https://happygitwithr.com/fork-and-clone#fork-and-clone).
    a. because I want to get the most recent changes for this template, I have to periodically fetch changes from the source repo to my fork. For that, I configure the source repo as the `upstream` remote and make my local `master` branch track to `upstream/master`.
    b. so now I have a working configuration with a local `master` branch, which looks like this:
    ![A working fork configuration looks like this](/assets/images/fork-them.jpeg)
2. But I want to keep the `master` branch clean so that I can fetch new changes to the source code from `upstream/master` without conflicts. So I had to create a branch of my local `master` branch in which I can do all my edits and deployments. 
    a. I even created 2 branches, one is called `deploy`, from which I deploy the website, and the second is called `dev-site`, which I use to make my edits, posts etc.
3. If I want to make any changes to the website I will follow this routine using git bash on windows:
    i. Connect to the `dev-site` branch using `git checkout dev-site`
    ii. Make changes, add posts, media etc.
    iii. Stage changes to the `dev-site` branch using `git add .`
    iv. Commit changes to the `dev-site` branch using `git commit -m "Message with changes"`
    v. Push changes using `git push origin dev-site`
    vi. Merge the two branches `dev-site` and `deploy` if I'm happy with the changes made: First, `git checkout deploy` then merge with `git merge dev-site` and lastly `git push origin deploy`. This will merge my changes to the `deploy` branch which is used to deploy the website.
4. If I want to sync the source repo with my repo and local branches, I can follow steps 32.3 or 32.4 in this tutorial: [https://happygitwithr.com/upstream-changes#touched-main](https://happygitwithr.com/upstream-changes#touched-main).
5. It's important, that I never touch my local `master` branch and that I don't merge the other branches with this one. 


# See the website before deployment
- For that I wanted to follow the procedure that Spencer Pao describes in this video: [https://www.youtube.com/watch?v=g6AJ9qPPoyc&t=120s](https://www.youtube.com/watch?v=g6AJ9qPPoyc&t=120s) (starting from 6:50 min), which uses `bundle` in the git terminal
- Since I didn't have `bundle` installed, I had to install Ruby on my Windows machine using the RubyInstaller: [https://rubyinstaller.org/downloads/](https://rubyinstaller.org/downloads/), more info is found here [https://www.ruby-lang.org/en/downloads/](https://www.ruby-lang.org/en/downloads/)
- Once Ruby was installed, Bundle was also installed (see [https://bundler.io/](https://bundler.io/))
- then, I ran `bundle install` 
- next, I ran `bundle exec jekyll serve` to build the website locally


# Deploy the website from git bash
- after merging the most recent changes to the `deploy` branch, make sure to be on the `deploy`branch using `git checkout deploy`.
- run `bin/deploy --user`

# Resources for Jekyll websites
## Posts
- [https://jekyllrb.com/docs/posts/](https://jekyllrb.com/docs/posts/)
