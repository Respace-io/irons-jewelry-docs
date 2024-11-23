
# Initial Setup (one time)
## Install Ruby+Devkit
  - https://github.com/oneclick/rubyinstaller2/releases/download/RubyInstaller-3.2.2-1/rubyinstaller-devkit-3.2.2-1-x64.exe
  - At the end of this install run the ridk install and choose option 3: MSYS2 and MINGW development tool chain
  - Open a new console window so $path is updated

Install bundler
>$ gem install jekyll bundler

If all is well this will run successfully
>$ jekyll -v

## Initial config

Edit Gemfile and _config.yml
>$ bundle 

# Running the project
NOTE: This doesn't like git bash

To run the site on localhost
>$ bundle exec jekyll serve

To run the site on all local IPs
>$ bundle exec jekyll serve --host=0.0.0.0

## Local site address
- http://localhost:4000/
