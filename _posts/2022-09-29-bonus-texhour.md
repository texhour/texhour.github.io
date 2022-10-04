---
key: y2022w39-bonus
title: Rethinking TeX in STEM (discussion)
slug: rethink-tex-in-stem-discuss
layout: post
hours: "6:30 to 8:30pm"
---

Above is the discussion that followed [these presentations]({%
post_url 2022-09-29-texhour %}).


Here's the chat messages referred to in the discussion:

* Jonathan Fine: <https://ncatlab.org/nlab/show/HomePage>
* Peter Williams: Re: Charles's question: part of the way that I approached Tectonic was because I came to the conclusion that reimplementing from scratch was infeasible, especially since I also wanted the engine to support Unicode and TrueType/OpenType fonts natively
* Peter Williams: Dennis you said "plain TeX" I think, so you are not including those, I would guess?
* Dennis Müller: I do not - I am for now restricted to the fonts tex gives us. But I will have to bite the bullet at some point and mimic (at least) xetex, otherwise we're excluding at least (basically) all of asia :/
* Charles Frankston: Well, if Dennis really has a mostly-complete TeX engine … maybe it's time to finally retire Prof. Knuth's code :-)?
* Peter Williams: I would love to swap out the core engine with something that isn't the WEB2C-plus-futzing mess that we have now!
* Charles Frankston : Martin -- it wasn't clear to me exactly where in the TeX pipeline you get your HINT information. It seems to me that once the DVI is output your info is lost?
* Peter Williams: @Martin: I might suggest that you think of it less as "convert HiNT to HTML" as "implement a HiNT viewer in JavaScript that emits HTML on-the-fly"
* Charles Frankston : Also, I'm wondering if the issues with the eBook you showed at the beginning are because of eBook format limitations … which are perhaps less rich than HTML (and certainly not as extensible)
* Peter Williams: I think the dynamism of the HINT approach, which is super cool and valuable, means that you do need an active "viewer" program, but that can be something that runs in the browser.
* Peter Williams: @Dennis, I really like this mathhub site! It does a lot of stuff that I've been thinking about
Jonathan Fine: Rougly speaking, HINT uses the boxex that TeX creates internally before they are made into pages and shipped out. I spoke about this in a previous TeX Hour.
* Kaveh Bazargan: So is Martin’s output using the full TeX engine and running on the fly? If so it is really astonishing
* Peter Williams: Regarding ebook formats, it amazes me that (as far as I can tell) we're still lacking a compelling standard for saving non-trivial websites to some kind of archive file. There's an IETF standard in teh works, buit it's still a draft: <https://wpack-wg.github.io/bundled-responses/draft-ietf-wpack-bundled-responses.html>
* Peter Williams: Personally I think this lack is a huge barrier to adoption by academics, because it means you can't save or view "personal copies" of articles reliably
* Peter Williams: @Kaveh I believe that it's basically running the linebreaking algorithm on the fly?
* Peter Williams: But not reparsing the document from scratch
* Charles Frankston: To be fair Peter, the www community probably contributed to the problem by having proprietary, incompatible ways of bundling multiple html files + image files and the like for a complete web page
* Peter Williams: So I think all three projects give up on WEB, but in different ways!
* Shamsi Brinn: there are dyslexia fonts that are important for some reading disabilities
* Kaveh Bazargan: <https://opendyslexic.org/>. We use it on our hosting system, e.g. press eye, bottom left here: <https://gigabytejournal.com/articles/68>
* Shamsi Brinn: 👍
* Shamsi Brinn: Two topics noted for future discussion: 1) font rendering, 2) TeX engine in rust?
* Charles Frankston: 2&1 -- font rendering in the Rust Tex engine :-)
* Peter Williams: Also note that luatex is based on a fresh C implementation, and it includes Unicode/OpenType
* Charles Frankston: Absolutely required
* Shreevatsa: +1 I've just been listening but just want to say I'm very excited to see all this work and discussion happening :-)
* Unknown: To introduce a new thought: note also that Rust with WASM could also enable TeX to run in the browser, and have a better UX: more debuggability, easier-to-understand error messages.
* Unknown: Overleaf is doing some of this but without changing/hooking into the TeX they can only go so far.
* Unknown: [It would be nice if we could] gently nudge users away from writing source documents that would be hard to translate into HTML (e.g. a warning message when someone uses page references).
* Phillip Helbig: <https://en.wikipedia.org/wiki/HTML5#Error_handling>
* Charles Frankston: Interesting. I have to read more on that
* Peter Williams: Bye all!
