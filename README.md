# Gallery Generator

This is a [Jekyll plugin](https://github.com/mojombo/jekyll/wiki/Plugins) that will take a directory full of images and generate galleries. It uses [RMagick](http://rmagick.rubyforge.org/) to create thumbnails.

See [my gallery](http://geoff.greer.fm/photos/) for an example of what it looks like.

### Install dependencies

    brew install imagemagick
    gem install RMagick

### To use

    cp gallery\_generator.rb jekyll-site/\_plugins/
    cp gallery\_index.html jekyll-site/\_layouts/
    cp gallery\_page.html jekyll-site/\_layouts/

Copy your image directories into `jekyl-site/photos/`. Here's what my directory structure looks like:

    % ls photos
    best/                   chile_trip/             japan_trip/
    % ls photos/chile_trip 
    IMG_1039.JPG  IMG_1046.JPG  IMG_1057.JPG  ...

### Optional

If you want to have a different path than `/photos/`, set `gallery_dir` in your `_config.yml`. You can also set favorite images that get shown on the index page. Here's what my `_config.yml` looks like:

    gallery_dir: photos
    galleries:
      chile_trip:
        best_image: IMG_1068.JPG
      japan_trip:
        best_image: IMG_0690.JPG
      best:
        best_image: snaileo_gonzales.jpg

If you don't set a `best_image` for a gallery, the generator will use the last image. All images and galleries are sorted alphabetically.