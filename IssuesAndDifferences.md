# Known Issues #

The smart wrapping modes 0 and 3 are not implemented entirely correctly (as per spec): in libass, both modes try to equalize line length over all lines. The specification states that the renderer should try to make the first line longer than the others in mode 0 and the last line longer in mode 3.

The fadeawayheight/fadeawaywidth parameters for the "Banner", "Scroll up" and "Scroll down" effects are not supported. However, these are very rarely used, if at all.

\K karaoke is always filled left-to-right.

# Advantages to VSFilter #

libass is about 50% faster than VSFilter most of the time.

libass supports kerning (but it is disabled by default).

Bidirectional text and shaping support is much better.

# Differences to VSFilter #

BiDi support in VSFilter is broken beyond repair. libass does not emulate this.

Empty lines, i.e. "\N\N" or a "\N" at the start of an event are not handled like VSFilter in some cases.

Syntax errors in certain tags are handled different.

BorderStyle 3 ("opaque box") does not behave like in VSFilter all the time. VSFilter's implementation is buggy and emulation of these bugs is hard. If possible, avoid using it.