- References
-  https://jekyllrb.com/docs/variables/
-  https://jekyllrb.com/docs/themes/
-  https://jekyllrb.com/docs/continuous-integration/github-actions/
-  https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/creating-a-github-pages-site-with-jekyll
-  https://jekyllthemes.io/theme/bulma
-  https://github.com/chrisrhymes/bulma-clean-theme/#installation
-  https://idratherbewriting.com/documentation-theme-jekyll/mydoc_publishing_github_pages.html-

- Install Ruby+Devkit
  - https://github.com/oneclick/rubyinstaller2/releases/download/RubyInstaller-3.2.2-1/rubyinstaller-devkit-3.2.2-1-x64.exe
  - At the end of this install run the ridk install and choose option 3: MSYS2 and MINGW development tool chain



NOTE: This doesn't like git bash

Open a new console window so $path is updated
>$ gem install jekyll bundler

If all is well this will run successfully
>$ jekyll -v

Creates a new branch, with no history or contents, called gh-pages, and switches to the gh-pages branch
>$ git checkout --orphan gh-pages

Removes the contents from your default branch from the working directory
>$ git rm -rf *

Creates a Jekyll site in the current directory
>$ jekyll new --skip-bundle .

Edit Gemfile and _config.yml
>$ bundle

To run the site on localhost
>$ bundle exec jekyll serve

To run the site on all local IPs
>$ bundle exec jekyll serve --host=0.0.0.0



### To Localhost (for idiots)
- Need Ruby+Devkit as dependency
  - https://github.com/oneclick/rubyinstaller2/releases/download/RubyInstaller-3.2.2-1/rubyinstaller-devkit-3.2.2-1-x64.exe
- git bash to project root
  - >$ gem install jekyll bundler
  - >$ bundle
  - >$ jekyll -v
     - expect no errors
  - >$ bundle exec jekyll serve
    - optional flag of "--host=0.0.0.0"
- http://localhost:4000/
