# shelvoke-drewry-2.0

This is a Jekyll static site that aims to build a new iteration of the [shelvoke-drewry.co.uk](https://shelvoke-drewry.co.uk) site.

## Local Development

Clone this repository, change into the directory and run docker-compose up

    git clone git@gitlab.com:caprenter/shelvoke-drewry-2.0.git
    cd shelvoke-drewry-2.0
    docker-compose up

The site should be up on:

    http://0.0.0.0:4000/

### Developer Notes

#### baseurl

As this is currently deployed in a subdirectory of GitHub pages, we set a base URL to match that.

#### Search

Search is implemented using lunr.js following these instructions: [Search with Lunr.js](https://jekyllcodex.org/without-plugin/search-lunr/)

The search is included in the `_layouts/home.html` and `_layouts/page.html`.

They make it much longer to render the site so we could consider turning the search off for development.

#### Theme

We use the [Start Bootstrap - Clean Blog Jekyll theme](https://github.com/StartBootstrap/startbootstrap-clean-blog-jekyll).

We add that to _config.yml as a remote theme so that gitHub pages can build it

    remote_theme: StartBootstrap/startbootstrap-clean-blog-jekyll

#### Jekyll version
 
We let the `gem "github-pages"` take care of the Jekyll version (I think!), so we don't specify a version in the `_config.yml`

#### Gallery 

Relies on a set of thumbnails that must be generated yourself to sit in the `/assets` directory.

Use something like this:

    find . \( -name '*.jpg' -or -name '*.JPG' \) -print0 |  while read -d $'\0' file ; do convert -define jpeg:size=400x400  "$file" -thumbnail 300x300^ -gravity center -extent 300x300  ../thumbnails/"$file" ; done

## Contributing

Contributions are welcome.

Make a ticket,and or fork the project and submit a pull request please.

## Authors and acknowledgment

The website was the work of my dad, Brian Carpenter - he does a pretty good job of acknowledging the content creators in the site.

## License

https://creativecommons.org/licenses/by-nc/4.0/ - Attribution-NonCommercial 4.0 International 

## Project status

Minimally maintained, but nudge me if it needs a poke.
