# developer.testpress.in

This is Testpress API resource built with [slate](https://github.com/tripit/slate/). 

## Getting Started 

### Prerequisites

You're going to need:

 - **Linux or OS X** — Windows may work, but is unsupported.
 - **Ruby, version 1.9.3 or newer**
 - **Bundler** — If Ruby is already installed, but the `bundle` command doesn't work, just run `gem install bundler` in a terminal.

### Set Up

 1. Clone this repository to your hard drive with `git clone https://github.com/YOURUSERNAME/slate.git`
 2. `cd developer.testpress.in`
 3. Install all dependencies: `bundle install`
 4. Start the test server: `bundle exec middleman server`, For OS X `EXECJS_RUNTIME=Node bundle exec middleman server`

You can now see the docs at <http://localhost:4567>.

### Publishing Your Docs to Github Pages

 1. Commit your changes to the markdown source: `git commit -a -m "Update index.md"`
 2. Push the *markdown source* changes to Github: `git push`
 3. Compile to HTML, and push the HTML to Github pages: `rake publish`

### Publishing Your Docs to Your Own Server

Instead of using `rake publish`, use `rake build`. Middleman will build your website to the build directory of your project, and you can copy those static HTML files to the server of your choice.

## Contributors

Slate was built by [Robert Lord](https://lord.io) while at [TripIt](http://tripit.com).

Thanks to the following people who have submitted major pull requests:

- [@chrissrogers](https://github.com/chrissrogers)
- [@bootstraponline](https://github.com/bootstraponline)
- [@realityking](https://github.com/realityking)

Also, thanks to [Sauce Labs](http://saucelabs.com) for helping sponsor the project.

## Special Thanks
- [Middleman](https://github.com/middleman/middleman)
- [jquery.tocify.js](https://github.com/gfranko/jquery.tocify.js)
- [middleman-syntax](https://github.com/middleman/middleman-syntax)
- [middleman-gh-pages](https://github.com/neo/middleman-gh-pages)
- [Font Awesome](http://fortawesome.github.io/Font-Awesome/)
