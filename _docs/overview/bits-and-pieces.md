---
title: bits-and-pieces
published: false
---

## Real-time DSP {#real-time-dsp}

Make your own DSP signal chain. [Start
low-level](2012-06-07-dsp-basics-in-extempore.org) (with unit generators,
envelopes, LFOs, etc.) and [build whatever abstractions take your
fancy](2012-06-07-more-dsp-and-extempore-types.org). You can even build
Extempore 'instruments' which can be played like soft synths (here's a simple
and And because it's all dynamically compiled, if things aren't working for you
you can dig into the source and change things on the fly :)

The `examples/core/audio_101.xtm` example file is a good place to start
for this sort of thing.

## Higher-level (note based) audio sequencing {#higher-level-note-based-audio-sequencing}

If writing raw bits to the sound card isn't your cup of tea, then there's a
'[instrument](2012-10-16-a-really-simple-instrument.org)' (note-level) audio
framework in Extempore as well. You can [load an
instrument](2012-10-17-loading-and-using-a-sampler.org), [trigger sounds using
the familiar pitch/velocity/duration
arguments](2012-10-15-playing-an-instrument-part-i.org), and build [complex
rhythmic and harmonic patterns](2012-10-15-playing-an-instrument-part-ii.org)
(this type of musical coding will be [familiar to Impromptu
users](2012-10-15-extempore-for-impromptu-users.org)).

Apart from the aforelinked blog posts, the `examples/core/polysynth.xtm` example
file is a good place to start for this type of musical interaction. There aren't
a heap of preset instruments available currently, but more will be added as
development continues.

It's important to point out that there's nothing forcing you to choose between
these high-level and low-level music making approaches. Mixing Scheme and xtlang
code is the whole point of Extempore---so pick whichever approach is the best
fit for what you're trying to achieve.

## Graphics processing {#graphics-processing}

This 'philosophy' document doesn't cover it, but Extempore also has support for
working with graphics. Both 2D (via [nanovg]()) and 3D (via
[OpenGL](http://www.opengl.org)) graphics are supported, and again everything
can be tweaked on the fly.

There are a few OpenGL examples in `examples/external/` which might be
of interest for those who want to get started with graphics in
Extempore.

## Working with external C libraries {#working-with-external-c-libraries}

If there's a particular C library that you'd like to explore in a more dynamic
way than is possible with a statically compiled binary, then you can create
xtlang bindings for the library, load it at runtime and away you go. This could
be used, for instance, to add OpenCV image processing to a computer-vision based
program, or to leverage GStreamer for playback and remixing of video content in
real-time.

If you've got the compiled library and the header file (so that you can
determine the types/function signatures of the library's functions), you can
bind it on the fly and add it into the live programming loop. Check out the
`libs/external` directory to see how it's done.

## And much more… {#and-much-more}

I'm sure you can think of a way to leverage Extempore that I haven't
even thought of :)
