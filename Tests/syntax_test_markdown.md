| SYNTAX TEST "Packages/Markdown Extended/Syntaxes/Markdown Extended.sublime-syntax"

| <- text.html.markdown

# Heading 1
| ^^^^^^^^^ meta.block-level.markdown markup.heading.markdown markup.heading.1.markdown
| <-  punctuation.definition.heading.markdown

## Heading 2
|  ^^^^^^^^^ meta.block-level.markdown markup.heading.markdown markup.heading.2.markdown
| <-  punctuation.definition.heading.markdown
Lorem ipsum dolor
| ^^^^^^^^^^^^^^^ meta.paragraph.markdown

# Lists

## Unordered

- Unordered list item
| <-             punctuation.definition.list_item.markdown
| ^^^^^^^^^^^^^^ markup.list.unnumbered.markdown meta.paragraph.list.markdown

- Subsequent list item
| ^^^^^^^^^^^^^^ markup.list.unnumbered.markdown meta.paragraph.list.markdown

    - Nested list items aren't necessarily identified
|     ^^^^^^^^^^ markup.list.unnumbered.markdown meta.paragraph.list.markdown

Break paragraph

- Unordered list item *tight-spaced*
| <-             punctuation.definition.list_item.markdown
| ^^^^^^^^^^^^^^ markup.list.unnumbered.markdown meta.paragraph.list.markdown
- Subsequent list items have broken punctuation
| ^^^^^^^^^^^^^^ markup.list.unnumbered.markdown meta.paragraph.list.markdown
    - Nested list items aren't necessarily identified
|     ^^^^^^^^^^ markup.list.unnumbered.markdown meta.paragraph.list.markdown

Break paragraph

+ Alternative list punctuation
| <-             punctuation.definition.list_item.markdown
| ^^^^^^^^^^^^^^ markup.list.unnumbered.markdown meta.paragraph.list.markdown
+ Subsequent list items have broken punctuation
| ^^^^^^^^^^^^^^ markup.list.unnumbered.markdown meta.paragraph.list.markdown
    * Nested list items aren't necessarily identified
|     ^^^^^^^^^^ markup.list.unnumbered.markdown meta.paragraph.list.markdown

## Ordered

1. Ordered list item
| <- punctuation.definition.list_item.markdown
| <- punctuation.definition.list_item.number.markdown
| ^^^^^^^^^^^^^^^^^^ markup.list.numbered.markdown

2. Subsequent item
| <- punctuation.definition.list_item.markdown
| <- punctuation.definition.list_item.number.markdown
| ^^^^^^^^^^^^^^^^^^ markup.list.numbered.markdown

Break paragraph

1. Ordered list item *tight-spaced*
| <- punctuation.definition.list_item.markdown
| <- punctuation.definition.list_item.number.markdown
| ^^^^^^^^^^^^^^^^^^ markup.list.numbered.markdown
2. Subsequent items have broken punctuation
| ^^^^^^^^^^^^^^^^^^ markup.list.numbered.markdown

# Inline markup

Some [self-links][], [ref-links][1], and [inline links](#).
|    ^              punctuation.definition.string.begin.markdown
|    ^^^^^^^^^^^^^^ meta.link.reference.literal.markdown
|     ^^^^^^^^^^    string.other.link.title.markdown
|               ^   punctuation.definition.string.end.markdown
|                ^  punctuation.definition.constant.begin.markdown
|                 ^ punctuation.definition.constant.end.markdown
|                    ^              punctuation.definition.string.begin
|                    ^^^^^^^^^^^^^^ meta.link.reference.markdown
|                     ^^^^^^^^^     string.other.link.title.markdown
|                              ^    punctuation.definition.string.end.markdown
|                               ^   punctuation.definition.constant.begin
|                                ^  constant.other.reference.link.markdown
|                                 ^ punctuation.definition.constant.end
|                                        ^                 punctuation.definition.string.begin
|                                        ^^^^^^^^^^^^^^^^^ meta.link.inline.markdown
|                                         ^^^^^^^^^^^^     string.other.link.title.markdown
|                                                     ^    punctuation.definition.string.end
|                                                      ^   punctuation.definition.metadata.markdown
|                                                       ^  meta.link.inline.markdown markup.underline.link.markdown
|                                                        ^ punctuation.definition.metadata.markdown
Asterisk *italics*, **bold**, and ***bold italics***.
|        ^         punctuation.definition.italic.markdown
|        ^^^^^^^^^ markup.italic.markdown
|                ^ punctuation.definition.italic.markdown
|                   ^^       punctuation.definition.bold.markdown
|                   ^^^^^^^^ markup.bold.markdown
|                         ^^ punctuation.definition.bold.markdown
|                                    ^^^^^^^^^^^^ markup.bold.markdown markup.italic.markdown
Underscore _italics_, __bold__, and ___bold italics___.
|          ^         punctuation.definition.italic.markdown
|          ^^^^^^^^^ markup.italic.markdown
|                  ^ punctuation.definition.italic.markdown
|                     ^^       punctuation.definition.bold.markdown
|                     ^^^^^^^^ markup.bold.markdown
|                           ^^ punctuation.definition.bold.markdown
|                                      ^^^^^^^^^^^^ markup.bold.markdown markup.italic.markdown
Inline `code` strings, some with `escaped``backticks`.
|      ^      punctuation.definition.raw.markdown
|      ^^^^^^ markup.raw.inline.markdown
|           ^ punctuation.definition.raw.markdown
|                                ^                    punctuation.definition.raw.markdown
|                                ^^^^^^^^^^^^^^^^^^^^ markup.raw.inline.markdown
|                                                   ^ punctuation.definition.raw.markdown
Some ~~crossed out text~~ should be tested.
|    ^^                   punctuation.definition.strike.markdown
|    ^^^^^^^^^^^^^^^^^^^^ markup.strike.markdown
|                      ^^ punctuation.definition.strike.markdown

***
|^^ meta.block-level.markdown meta.separator.markdown

# Code blocks

## Indentation-defined

    indented code (blocks) {
        make.poor(haiku + material);
    } // for unit testers
|   ^^^^^^^^^^^^^^^^^^^^^ meta.block-level.markdown markup.raw.block.markdown

## Backtick-fenced

```
this is raw plaintext
| markup.raw.block.fenced.markdown
```

```sh
git commit
|^^ markup.raw.block.fenced.markdown source.shell support.function.external.shell
```

## Jekyll liquid

{% highlight sh %}
git commit
|^^ markup.raw.block.fenced.markdown source.shell support.function.external.shell
{% endhighlight %}


# Block Quotes

> An ancient pond!
> With a sound from the water
> Of the frog as it plunges in.
| <-                            punctuation.definition.blockquote.markdown
| ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^ meta.block-level.markdown markup.quote.markdown

>> ## Nested block quote
>> More text here
|  ^^^^^^^^^^^^^^ markup.quote.markdown markup.quote.markdown

> # Lists

> ## Unordered

> - Unordered list items are not recognized
>
> - Subsequent list item
>
>     - Nested list item in quote misidentified as code

> Break paragraph

> - Unordered list item *tight-spaced*
> - Subsequent list item
>     - Nested list item in quote misidentified as code

> Break paragraph

> + Alternative list punctuation
> + Subsequent list item
>     * Nested list item in quote misidentified as code

> ## Ordered

> 1. Ordered list item
>
> 2. Subsequent item

> Break paragraph

> 1. Ordered list item *tight-spaced*
> 2. Subsequent items have broken punctuation

> # Inline markup

> Some [self-links][], [ref-links][1], and [inline links](#).
|      ^              punctuation.definition.string.begin.markdown
|      ^^^^^^^^^^^^^^ meta.link.reference.literal.markdown
|       ^^^^^^^^^^    string.other.link.title.markdown
|                 ^   punctuation.definition.string.end.markdown
|                  ^  punctuation.definition.constant.begin.markdown
|                   ^ punctuation.definition.constant.end.markdown
|                      ^              punctuation.definition.string.begin
|                      ^^^^^^^^^^^^^^ meta.link.reference.markdown
|                       ^^^^^^^^^     string.other.link.title.markdown
|                                ^    punctuation.definition.string.end.markdown
|                                 ^   punctuation.definition.constant.begin
|                                  ^  constant.other.reference.link.markdown
|                                   ^ punctuation.definition.constant.end
|                                          ^                 punctuation.definition.string.begin
|                                          ^^^^^^^^^^^^^^^^^ meta.link.inline.markdown
|                                           ^^^^^^^^^^^^     string.other.link.title.markdown
|                                                       ^    punctuation.definition.string.end
|                                                        ^   punctuation.definition.metadata.markdown
|                                                         ^  meta.link.inline.markdown markup.underline.link.markdown
|                                                          ^ punctuation.definition.metadata.markdown
> Asterisk *italics*, **bold**, and ***bold italics***.
|          ^         punctuation.definition.italic.markdown
|          ^^^^^^^^^ markup.italic.markdown
|                  ^ punctuation.definition.italic.markdown
|                     ^^       punctuation.definition.bold.markdown
|                     ^^^^^^^^ markup.bold.markdown
|                           ^^ punctuation.definition.bold.markdown
|                                    ^^^^^^^^^^^^ markup.bold.markdown markup.italic.markdown
> Underscore _italics_, __bold__, and ___bold italics___.
|            ^         punctuation.definition.italic.markdown
|            ^^^^^^^^^ markup.italic.markdown
|                    ^ punctuation.definition.italic.markdown
|                       ^^       punctuation.definition.bold.markdown
|                       ^^^^^^^^ markup.bold.markdown
|                             ^^ punctuation.definition.bold.markdown
|                                        ^^^^^^^^^^^^ markup.bold.markdown markup.italic.markdown
> Inline `code` strings, some with `escaped``backticks`.
|        ^      punctuation.definition.raw.markdown
|        ^^^^^^ markup.raw.inline.markdown
|             ^ punctuation.definition.raw.markdown
|                                  ^                    punctuation.definition.raw.markdown
|                                  ^^^^^^^^^^^^^^^^^^^^ markup.raw.inline.markdown
|                                                     ^ punctuation.definition.raw.markdown
> Some ~~crossed out text~~ should be tested.
|      ^^                   punctuation.definition.strike.markdown
|      ^^^^^^^^^^^^^^^^^^^^ markup.strike.markdown
|                        ^^ punctuation.definition.strike.markdown

> ***
| ^^^ meta.block-level.markdown meta.separator.markdown

> # Code blocks

> ## Indentation-defined

>     indented code (blocks) {
>         only highlight the
>     } // first line in quotes

> ## Backtick-fenced

> ```
this is raw plaintext
```

> ```sh
git commit
```

> ## Jekyll liquid

> {% highlight sh %}
git commit
{% endhighlight %}



>! Spoilers aren't separately identified, which is fine.

# Bibliography

[1]: http://example.com/ref
| <-                        punctuation.definition.constant.markdown
|^^^^^^^^^^^^^^^^^^^^^^^^^^ meta.link.reference.def.markdown
|^                          constant.other.reference.link.markdown
| ^                         punctuation.definition.constant.markdown
|  ^                        punctuation.separator.key-value.markdown
|    ^^^^^^^^^^^^^^^^^^^^^^ markup.underline.link.markdown