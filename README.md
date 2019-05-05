# Fruity ASM Presenter

A small presentation tool for giving talks using any of the
Apple ][ line of computers. The assembly is written for use
with the **Merlin 32** assembler, though it may work with the
**Merlin 16** assembler or **Merlin 8** assemblers.

## How to use:

Use the **space bar** to advance the presentation and the **left
arrow** to go back to the previous slide. If you hit the **"m" key**
at any point you will jump into the Monitor program. To return
to your presention (assuming you haven't overwritten it in
memory) you can hit **control-"y" then the return key**. If you jump
into Basic you can return to the presentation by running
`CALL 1016`.

## Authoring you presentation:

Include `fruity_asm_presentor` as the first part of your assembly
file. After that, add a `START_OF_SHOW` macro on a label entitled
`slide_data_start`. Put a `END_OF_SHOW` macro at the end of your
slides. At that point you can start writing your slides with the
provided macros:

### `SLIDE`
  Start a new slide. The `START_OF_SHOW` macro does the same
  thing as the `SLIDE` macro, except it only works properly at
  the start of the first slide.

### `TITLE "some text"`
  Prints the given string as a centered line of text with some
  blank lines before and after it. The string must not be 40
  characters or longer.

### `_ "some text"`
  Prints the given string as a left aligned line of text.
  The string should not be 40 characters or longer.

### `___ "some text"`
  Prints the given string as a centered line of text.
  The string must not be 40 characters or longer.

### `PAUSE`
  Place anywhere you want the slide show to pause mid slide,
  waiting for you to hit the space bar before it continues.

## Why did you make this?

I needed to give a talk using the Apple ][ and figured it would
be fun/easier to write a presentation tool using assembly.
The macros made it very easy to quickly author/edit slides in a
WYSIWYG-like manor.

## License

Fruity ASM Presenter is Open Source under the terms of the **BSD-3-Clause** License. See the **License** section of `fruity_asm_presenter.s` for details.
