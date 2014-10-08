---
layout: post
title: "Tom's First Post On Octopress - An attempt to understand Evaluation Strategy (aka a mashup of wikipedia, stackoverflow, actual TA knowledge, and my own musings)"
date: 2014-10-07 19:25:35 -0400
comments: true
categories: 
---

So, I'm not sure about you all, but it seems that everytime I modified an argument in a method I would make the wrong assumption as to what would happen to it outside of the method.  It took some googling, but I was able to figure how out Ruby passes arguments to methods - Ruby doesn't strictly use call-by-value or call-by-reference, but rather passes arguments by using call-by-sharing.
