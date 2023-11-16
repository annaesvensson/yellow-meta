<p align="right"><a href="README-de.md">Deutsch</a> &nbsp; <a href="README.md">English</a> &nbsp; <a href="README-sv.md">Svenska</a></p>

# Meta 0.8.17

Meta data for humans and machines.

<p align="center"><img src="SCREENSHOT.png?raw=true" alt="Screenshot"></p>

## How to install an extension

[Download ZIP file](https://github.com/annaesvensson/yellow-meta/archive/refs/heads/main.zip) and copy it into your `system/extensions` folder. [Learn more about extensions](https://github.com/annaesvensson/yellow-update).

## How to add meta data

This extension generates meta data for the [Open Graph protocol](https://ogp.me/).

You can set `Title`, `Description`, `Image` and `ImageAlt` in the [page settings](https://github.com/annaesvensson/yellow-core#settings-page) at the top of a page. You can configure additional meta data in the HTML header, for example in file `system/layouts/header.html`.

## Examples

Content file with meta data:

    ---
    Title: Example page
    Description: Example for your website
    Image: photo.jpg
    ---
    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut 
    labore et dolore magna pizza. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris 
    nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit 
    esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt 
    in culpa qui officia deserunt mollit anim id est laborum.

Content file with meta data from first image:

    ---
    Title: Example page
    Description: Example for your website
    ---
    [image photo.jpg]

    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut 
    labore et dolore magna pizza. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris 
    nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit 
    esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt 
    in culpa qui officia deserunt mollit anim id est laborum.

Layout file with additional meta data for search engines:

    <!DOCTYPE html>
    <html lang="<?php echo $this->yellow->page->getHtml("language") ?>">
    <head>
    <title><?php echo $this->yellow->page->getHtml("titleHeader") ?></title>
    <meta charset="utf-8" />
    <meta name="description" content="<?php echo $this->yellow->page->getHtml("description") ?>" />
    <meta name="author" content="<?php echo $this->yellow->page->getHtml("author") ?>" />
    <meta name="generator" content="Datenstrom Yellow" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <meta name="robots" content="index, follow" />
    <?php echo $this->yellow->page->getExtraHtml("header") ?>
    </head>
    ...

Layout file with additional meta data for Mastodon:

    <!DOCTYPE html>
    <html lang="<?php echo $this->yellow->page->getHtml("language") ?>">
    <head>
    <title><?php echo $this->yellow->page->getHtml("titleHeader") ?></title>
    <meta charset="utf-8" />
    <meta name="description" content="<?php echo $this->yellow->page->getHtml("description") ?>" />
    <meta name="author" content="<?php echo $this->yellow->page->getHtml("author") ?>" />
    <meta name="generator" content="Datenstrom Yellow" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <link rel="me" href="https://mastodon.social/@datenstrom" />
    <?php echo $this->yellow->page->getExtraHtml("header") ?>
    </head>
    ...

## Settings

The following settings can be configured in file `system/extensions/yellow-system.ini`:

`MetaDefaultImage` = page image, `favicon` to use the default icon of the website  

The following files can be customised:

`system/layouts/header.html` = layout file for default HTML header  

## Acknowledgements

This extension was previously maintained by Steffen Schultz. Thank you for the good work.

## Developer

Anna Svensson. [Get help](https://datenstrom.se/yellow/help/).
