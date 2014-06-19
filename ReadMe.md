# Codestellation Site #

This is the repository for the Codestellation site. It's build on Middleman, SCSS, and Bourbon + Neat + Bitters. Quick note: While SCSS and SASS are two distinct syntaxes, we are using the SCSS language. [This article](http://thesassway.com/editorial/sass-vs-scss-which-syntax-is-better) provides a good explanation the differences between the two.

## Prerequisites ##

This site is build on [Middleman](http://middlemanapp.com). It's a Ruby-based static site generator, which has an asset pipeline for ERB/SCSS, templates for pages, and best of all, it's easily hackable. To install it, you need the Ruby language (a version number greater than 2.1), as well as RubyGems, a package management framework for Ruby. It is recommended to use [RailsInstaller](http://railsinstaller.org/en) to set up the environment for a Ruby-based workflow.

Once those requirements are filled, you can install Middleman using the command `gem install middleman`. Depending on your Ruby installation, this may throw a permissions error, which in that case, you'd need to run `sudo gem install middleman`.

## Getting Started ##

Easiest way to get started is to clone this repository. Switch to the folder you'd like to be working in, and type the following into your console:

		git clone https://github.com/davidbarsky/Codestellation-Site.git
		
Be sure to familiarize yourself with [Bourbon](bourbon.io), [Neat](neat.bourbon.io), and [Bitters](bitters.bourbon.io). Bourbon is a mixin library, Neat is the grid system, and Bitters provides a set of base styles to work with.

In addition, please the articles on [The Sass Way](http://thesassway.com) to familiarize yourself with the methodology used in making this site.

Currently, the serif typeface is [Tisa Pro](https://typekit.com/fonts/ff-tisa-web-pro), and the sans-serif is [Proxima Nova](https://typekit.com/fonts/proxima-nova). They are delivered via Adobe Typekit.

To compile the site, run the command `middleman` in any folder in the project directory. Middleman will create a server at `http://0.0.0.0:4567`.

## Working on the Project ##		

Do all your work in the `/source` directory. In order to keep this clean and organized (as well as easy to migrate to future systems, should we choose to reuse these styles for the actual sign-up system) every element in the site is treated as a partial. 

For instance, a navigation partial will have its own structure file in `source/partials/_nav.erb`, and the associated styles would be placed in `/source/stylesheets/partials/_nav.scss`. Once an partial is created, it is necessary to `@import` it in the `all.scss` file, located in the `/source/stylesheets/` folder. The import code would look like this: 

		@import "partials/nav";

**It is not necessary to place an underscore inside an import statement**. The Sass compiler is smart enough to figure out what variable you are referencing.

One more thing: **do not work on the master branch**. Instead, create a local Git branch when working on a feature. This prevents nasty merge conflicts. Remember, Git branches are cheap, so don't feel shy making local branches!

And of course, feel free to ask me any questions about this.