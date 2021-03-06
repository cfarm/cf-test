The cf-typography component includes multiple patterns for headings,
links, lists, and other advanced typographic treatments.

The [`cf-core`](../core) component is a dependency of this component
and has more basic typography patterns.


> NOTE: If you use `cf-typography.less` directly,
  be sure to run the file through
  [Autoprefixer](https://github.com/postcss/autoprefixer),
  or your compiled Capital Framework CSS will
  not work perfectly in older browsers.

## Table of contents

- [Variables](#variables)
    - [Color variables](#color-variables)
    - [Font source variables](#font-source-variables)
- [Headings](#headings)
    - [Heading with icon](#heading-with-icon)
- [Headers](#headers)
    - [Slug header](#slug-header)
    - [Meta header](#meta-header)
- [Link patterns](#link-patterns)
    - [Links with icons](#links-with-icons)
    - [Jump link](#jump-link)
    - [Block link](#block-link)
- [Lists](#lists)
    - [Unstyled list modifier](#unstyled-list-modifier)
    - [Spaced list modifier](#spaced-list-modifier)
    - [Horizontal list modifier](#horizontal-list-modifier)
    - [Link list modifier](#link-list-modifier)
- [Miscellaneous text](#miscellaneous-text)
    - [Micro copy](#micro-copy)
    - [Date](#date)
    - [Pull quote](#pull-quote)


## Variables

Theme variables for setting the color and sizes. Overwrite them in your own
project by duplicating the variable `@key: value`.

### Font variables

```
@webfont-regular: 'AvenirNextLTW01-Regular';
@webfont-italic: @webfont-regular;
@webfont-medium: 'AvenirNextLTW01-Medium';
@webfont-demi: 'AvenirNextLTW01-Demi';
```

### Font source variables

Use this variable to specify where the fonts files used in the `@webfont-*`
variables are located when self-hosting fonts.
Can be either a relative or absolute path.

```
@cf-fonts-path: '/fonts'
```

If you want to load fonts from a Fonts.com Web Fonts project,
set the following variable to `true`,
otherwise set it to `false` to use the self-hosted font path:

```
@use-font-cdn: true;
```

### Color variables

Color variables referenced in comments are from [cf-core cf-brand-colors.less](https://github.com/cfpb/capital-framework/blob/master/src/cf-core/src/cf-brand-colors.less).

```
// Running text elements

// .a-micro-copy
@micro-copy:                    @black;

// .a-date
@date:                          @gray;

// .m-pull-quote
@pull-quote_body:               @black;
@pull-quote_citation:           @gray;

// Headings

// .a-heading__icon
@heading__icon:                 @black;
@heading__icon__hover:          @link-text-hover;

// Headers

// .m-slug-header
@slug-header_border__thin:      @gray-10;
@slug-header_border__thick:     @green;

// .m-meta-header
@meta-header_border:            @gray-40;

// Links

// .a-link__jump
@jump-link_bg:                  @gray-10;
@jump-link_border:              @gray-40;
```


### Heading with icon

The heading with icon is typically used for listing categories in a meta
header. Since categories can be repetitive, we suggest placing a label with
`.u-visually-hidden` prior to the headings to add more context for screen
readers (see Meta Header below).

<a href="#" class="a-heading a-heading__icon">
    <span class="cf-icon cf-icon-dialogue"></span>
    Consumer finance
</a>

```
<a href="#" class="a-heading a-heading__icon">
    <span class="cf-icon cf-icon-dialogue"></span>
    Consumer finance
</a>
```


## Headers

### Slug header

<header class="m-slug-header">
    <h2 class="a-heading">
        Blog summary
    </h2>
</header>

```
<header class="m-slug-header">
    <h2 class="a-heading">
        Blog summary
    </h2>
</header>
```

### Meta header

Note that the example shows `.m-meta-header_left` using the `.a-heading__icon`
pattern and `.m-meta-header_right` using the `.a-date` pattern but you could use
other patterns in place of them. Or you can even swap them so that date is
attached to `.m-meta-header_left` and `.a-heading.a-heading__icon` is attached to
`.m-meta-header_right`.

#### Default meta header

<header class="m-meta-header">
    <div class="m-meta-header_right">
        <span class="a-date">
            Nov 4, 2013
        </span>
    </div>
    <div class="m-meta-header_left">
        <span class="u-visually-hidden">Categories: </span>
        <a href="#" class="a-heading a-heading__icon">
            <span class="cf-icon cf-icon-credit-card"></span>
            Consumer finance
        </a>
        |
        <a href="#" class="a-heading a-heading__icon">
            <span class="cf-icon cf-icon-credit-card"></span>
            Consumer finance
        </a>
    </div>
</header>


## Link patterns

### Links with icons

- Styles to enable adding an icon to a link and preventing the link's underline
  from extending under the icon.
- For the underlined icon prevention to work, you must wrap the link text with
  a `span.icon-link_text`. There can be no whitespace between the text and the
  opening and closing `span` tags.

#### Default pattern

- The modifier names match the cf-icon names of commonly-used icons.
- Icons appear to the right of a link, by default.

<p>
    For more information, email
    <a class="a-link
              a-link__icon
              cf-icon
              cf-icon__after
              cf-icon-mail"
       href="#">
        <span class="a-link_text">john.smith@cfpb.gov</span>
    </a>.
    Alternatively, you can
    <a class="a-link
              a-link__icon
              cf-icon
              cf-icon__after
              cf-icon-download"
       href="#">
        <span class="a-link_text">download the info sheet</span>
    </a>.
    Oh, you might also want to visit this
    <a class="a-link
              a-link__icon
              cf-icon
              cf-icon__after
              cf-icon-external-link"
       href="#">
        <span class="a-link_text">other organization's website</span>
    </a> for further details.
</p>


```
<p>
   For more information, email
    <a class="a-link
              a-link__icon
              cf-icon
              cf-icon__after
              cf-icon-mail"
       href="#">
        <span class="a-link_text">john.smith@cfpb.gov</span>
    </a>.
    Alternatively, you can
    <a class="a-link
              a-link__icon
              cf-icon
              cf-icon__after
              cf-icon-download"
       href="#">
        <span class="a-link_text">download the info sheet</span>
    </a>.
    Oh, you might also want to visit this
    <a class="a-link
              a-link__icon
              cf-icon
              cf-icon__after
              cf-icon-external-link"
       href="#">
        <span class="a-link_text">other organization's website</span>
    </a> for further details.
</p>
```

#### Links with icons on the left

- Simply add the `.icon-link__before` modifier to place the icon before the
  link text.
- You can omit the `span.icon-link_text` wrapper if you do not need an
  underline on a particular link.

<a class="a-link a-link__icon
          cf-icon
          cf-icon__before
          cf-icon-mail"
    href="#">
    <span class="a-link_text">john.smith@cfpb.gov</span>
</a><br>
<a class="a-link
          a-link__icon
          cf-icon
          cf-icon__before
          cf-icon-phone"
   href="#">
    <span class="a-link_text">(123) 456-7890</span>
</a>

```
<a class="a-link a-link__icon
          cf-icon
          cf-icon__before
          cf-icon-mail"
    href="#">
    <span class="a-link_text">john.smith@cfpb.gov</span>
</a><br>
<a class="a-link
          a-link__icon
          cf-icon
          cf-icon__before
          cf-icon-phone"
   href="#">
    <span class="a-link_text">(123) 456-7890</span>
</a>
```

#### Non-wrapping icon links

- Warning: Icons added to inline links can sometimes break onto the next line.
  If you want to prevent this, you can add the `__no-wrap` modifier to
  `.icon-link`.


For more information, email
<a class="a-link
          a-link__icon
          a-link__no-wrap
          cf-icon
          cf-icon__after
          cf-icon-mail"
   href="#">
    <span class="a-link_text">john.smith@cfpb.gov</span>
</a>.

```

For more information, email
<a class="a-link
          a-link__icon
          a-link__no-wrap
          cf-icon
          cf-icon__after
          cf-icon-mail"
   href="#">
    <span class="a-link_text">john.smith@cfpb.gov</span>
</a>.
```

### Jump link

<a class="a-link
          a-link__jump
          cf-icon
          cf-icon__after
          cf-icon-right"
   href="#">
    <span class="a-link_text">Default jump link</span>
</a>

```
<a class="a-link
          a-link__jump
          cf-icon
          cf-icon__after
          cf-icon-right"
   href="#">
    <span class="a-link_text">Default jump link</span>
</a>
```

#### Jump link with large link modifier

The large jump link has an `18px` `font-size`, compared to the default of `16px`.

<a class="a-link
          a-link__jump
          a-link__large
          cf-icon
          cf-icon__after
          cf-icon-right"
   href="#">
    <span class="a-link_text">Large jump link</span>
</a>

```
<a class="a-link
          a-link__jump
          a-link__large
          cf-icon
          cf-icon__after
          cf-icon-right"
   href="#">
    <span class="a-link_text">Large jump link</span>
</a>
```

#### Jump link with before link modifier

Jump links can also have icons before the text, like icon links.

<a class="a-link
          a-link__jump
          cf-icon
          cf-icon__before
          cf-icon-left"
   href="#">
    <span class="a-link_text">Jump link with icon on left</span>
</a>

```
<a class="a-link
          a-link__jump
          cf-icon
          cf-icon__before
          cf-icon-left"
   href="#">
    <span class="a-link_text">Jump link with icon on left</span>
</a>
```

#### Jump link with bg link modifier (only visible on small screens)

<a class="a-link
          a-link__jump
          a-link__bg
          cf-icon
          cf-icon__after
          cf-icon-right"
   href="#">
    <span class="a-link_text">Jump link with grey background and
        solid borders on small screens</span>
</a>

```
<a class="a-link
          a-link__jump
          a-link__bg
          cf-icon
          cf-icon__after
          cf-icon-right"
   href="#">
    <span class="a-link_text">Jump link with grey background and
        solid borders on small screens</span>
</a>
```

### Block link

The block link class converts a standard inline link to a block-level element
with `padding`, `background`, and `border`.

It is primarily used within a max-width `@bp-xs-max` media query
(see `.link__jump` and `.list__links`).

<a class="a-link__block" href="#">
    Default block link
</a>

```
<a class="a-link__block" href="#">
    Default block link
</a>
```


## Lists

### Unstyled list modifier

Unstyled list removes bullets and other styling from a list.

<ul class="m-list m-list__unstyled">
    <li class="m-list_item">List item 1</li>
    <li class="m-list_item">List item 2</li>
    <li class="m-list_item">List item 3</li>
</ul>

```
<ul class="m-list m-list__unstyled">
    <li class="m-list_item">List item 1</li>
    <li class="m-list_item">List item 2</li>
    <li class="m-list_item">List item 3</li>
</ul>
```

### Spaced list modifier

Spaced list adds extra padding to every element in a list.

#### Default spaced list

<ul class="m-list m-list__spaced">
    <li class="m-list_item">List item 1</li>
    <li class="m-list_item">List item 2</li>
    <li class="m-list_item">List item 3</li>
</ul>

```
<ul class="m-list m-list__spaced">
    <li class="m-list_item">List item 1</li>
    <li class="m-list_item">List item 2</li>
    <li class="m-list_item">List item 3</li>
</ul>
```

#### Nested list example

<ul class="m-list m-list__spaced">
    <li class="m-list_item">List item 1</li>
    <li class="m-list_item">
        List item 2
        <ul class="m-list m-list__spaced">
            <li class="m-list_item">List item 2a</li>
            <li class="m-list_item">List item 2b</li>
            <li class="m-list_item">List item 2c</li>
        </ul>
    </li>
    <li class="m-list_item">List item 3</li>
</ul>

```
<ul class="m-list m-list__spaced">
    <li class="m-list_item">List item 1</li>
    <li class="m-list_item">
        List item 2
        <ul class="m-list m-list__spaced">
            <li class="m-list_item">List item 2a</li>
            <li class="m-list_item">List item 2b</li>
            <li class="m-list_item">List item 2c</li>
        </ul>
    </li>
    <li class="m-list_item">List item 3</li>
</ul>
```

### Horizontal list modifier

A modifier for the list to make it show items horizontally.

<ul class="m-list m-list__horizontal">
    <li class="m-list_item">List item 1</li>
    <li class="m-list_item">List item 2</li>
    <li class="m-list_item">List item 3</li>
</ul>

```
<ul class="m-list m-list__horizontal">
    <li class="m-list_item">List item 1</li>
    <li class="m-list_item">List item 2</li>
    <li class="m-list_item">List item 3</li>
</ul>
```

### Link list modifier

The link list modifier is intended to be used for lists where each item is a
link. It converts to a finger-friendly link with a large tap area on smaller
screens.

<ul class="m-list m-list__links">
    <li class="m-list_item">
        <a class="m-list_link" href="#">List item 1</a>
    </li>
    <li class="m-list_item">
        <a class="m-list_link" href="#">List item 2</a>
    </li>
    <li class="m-list_item">
        <a class="m-list_link" href="#">List item 3</a>
    </li>
</ul>

```
<ul class="m-list m-list__links">
    <li class="m-list_item">
        <a class="m-list_link" href="#">List item 1</a>
    </li>
    <li class="m-list_item">
        <a class="m-list_link" href="#">List item 2</a>
    </li>
    <li class="m-list_item">
        <a class="m-list_link" href="#">List item 3</a>
    </li>
</ul>
```

## Miscellaneous Text

### Micro copy

The `.a-micro-copy` class is good for highlighting small pieces of text,
typically legal copy.

<p class="a-micro-copy">
    Lorem ipsum dolor sit amet
</p>

```
<p class="a-micro-copy">
    Lorem ipsum dolor sit amet
</p>
```

### Date

<span class="a-date">
    Nov 4, 2013
</span>

```
<span class="a-date">
    Nov 4, 2013
</span>
```

### Pull quote

Use a pull quote to highlight excerpts from the current work.
This is not to be confused with `blockquote` which quotes from an external
work. Since a pull quote is an excerpt and repeats content from the article
you should use the `aside` element.

#### Default pull quote

<aside class="m-pull-quote">
    <p class="m-pull-quote_body">
        Lorem ipsum dolor sit amet, consectetur adipisicing elit.
        Cum corrupti tempora nam nihil qui mollitia consectetur
        corporis nemo culpa dolorum!
    </p>
    <footer>
        <cite class="m-pull-quote_citation">
            Author Name
        </cite>
    </footer>
</aside>


```
<aside class="m-pull-quote">
    <p class="m-pull-quote_body">
        Lorem ipsum dolor sit amet, consectetur adipisicing elit.
        Cum corrupti tempora nam nihil qui mollitia consectetur
        corporis nemo culpa dolorum!
    </p>
    <footer>
        <cite class="m-pull-quote_citation">
            Author Name
        </cite>
    </footer>
</aside>
```

#### Large pull quote

<aside class="m-pull-quote m-pull-quote__large">
    <div class="m-pull-quote_body">
        Lorem ipsum dolor sit amet, consectetur adipisicing elit.
        Cum corrupti tempora nam nihil qui mollitia consectetur
        corporis nemo culpa dolorum!
    </div>
    <footer>
        <cite class="m-pull-quote_citation">
            Author Name
        </cite>
    </footer>
</aside>

```
<aside class="m-pull-quote m-pull-quote__large">
    <div class="m-pull-quote_body">
        Lorem ipsum dolor sit amet, consectetur adipisicing elit.
        Cum corrupti tempora nam nihil qui mollitia consectetur
        corporis nemo culpa dolorum!
    </div>
    <footer>
        <cite class="m-pull-quote_citation">
            Author Name
        </cite>
    </footer>
</aside>
```
