# Bookdown.io With Bootswatch Styles And Prism Syntax Highlighting

This package is now part of [bookdown](http://bookdown.io/). You can enable it by setup your bookdown.json 
```json
{
"template": "bookdown/themes"
}
```

## Installation
Just install [bookdown](http://bookdown.io/) and setup your `bookdown.json`

## Configuration
At the moment you can setup the `theme` with the following settings per `bookdown.json`

```json
"theme": {
    "toc": {
      "collapsibleFromLevel": 1
    }
  }
```
### Table of Contents (toc)

<table>
<tr>
<th>Property</th>
<th>Type</th>
<th>Description</th>
</tr>
<tr>
<td><i>collapsibleFromLevel</i></td>
<td>integer</td>
<td>The toc is collapsible from apart this value</td>
</tr>
</table>

## Styles
Choose your preferred style by setting the `CSS_BOOTSWATCH` and `CSS_PRISM` environment variable before generating the book. 
The default Bootswatch style is `cerulean` and for Prism `ghcolors`. See the example below how to use another style.

Visit [bootswatch.com](https://bootswatch.com/) to see how the style looks like.

* cerulean
* cosmo
* cyborg
* darkly
* flatly
* journal
* lumen
* paper
* readable
* sandstone
* simplex
* slate
* spacelab
* superhero
* united
* yeti

Visit [prismjs.com](http://prismjs.com/) / [prism-styles](https://github.com/PrismJS/prism-themes) to see how the Prism style looks like.

* prism
* dark
* funky
* okaidia
* twilight
* coy
* atom-dark
* base16-ateliersulphurpool.light
* cb
* ghcolors
* hopscotch
* pojoaque
* xonokai

## Top menu logo
To add an individual logo instead of displaying *Home* you can set the environment variable `MENU_LOGO` which must be
an absolute URI to an image.

## Generate Documentation

> Change the path to your bookdown.json file.

See the [documentation example](https://github.com/tobiju/bookdown-bootswatch-templates-example). It can be compiled 
using [bookdown](http://bookdown.io) and [Docker](https://www.docker.com/).
The following example uses the [Docker Bookdown](https://hub.docker.com/r/sandrokeil/bookdown/) and you can use it also
out of the box for your project.

The style is set by an environment `CSS_BOOTSWATCH` variable and the PRISM style by `CSS_PRISM`. 
Here is an example for the `superhero` style with the prism `coy` style.

```console
$ docker run -it --rm -e CSS_BOOTSWATCH=superhero -e CSS_PRISM=coy -v $(pwd):/app sandrokeil/bookdown doc/bookdown.json
$ docker run -it --rm -p 8080:8080 -v $(pwd):/app php:5.6-cli php -S 0.0.0.0:8080 -t /app/doc/html
```

or for Bookdown via Composer.

```console
$ export CSS_BOOTSWATCH=superhero && export CSS_PRISM=coy && php ./vendor/bin/bookdown doc/bookdown.json
$ php -S 0.0.0.0:8080 -t doc/html/
```

Then browse to [http://localhost:8080/](http://localhost:8080/)

## Bookdown Bootswatch templates in action
Here are some documentation examples generated with this Bookdown.io template.

* [prooph components](http://getprooph.org/)
* [interop-config](http://sandrokeil.github.io/interop-config/)

## Further Information

* [Bookdown](https://github.com/bookdown/Bookdown.Bookdown)
* [Bootswatch](https://bootswatch.com/)
* [PrismJS](http://prismjs.com/)
* [Docker Bookdown image with these templates](https://hub.docker.com/r/sandrokeil/bookdown/)
