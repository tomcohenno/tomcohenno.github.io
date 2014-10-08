---
layout: post
title: "Tom's First Post On Octopress - An attempt to understand Evaluation Strategy"
date: 2014-10-07 19:25:35 -0400
comments: true
categories: 
---

So, I'm not sure about you all, but it seems that everytime I modified an argument in a method I would make the wrong assumption as to what would happen to it outside of the method.  It took some googling, but I was able to figure how out Ruby passes arguments to methods - Ruby doesn't strictly use call-by-value or call-by-reference, but rather passes arguments by using call-by-sharing.

Basically, Ruby neither completely replicates an argument in memory (call-by-value), nor does it send only a reference that could mutate the original argument in a given method.  Ruby merely creates another variable "label" that points to the exact same location in memory as the runtime argument.  Here comes my major revelation - the method can now "act" as a call-by-value OR a call-by-value, depending on what functions are called within the method.  

There are two types of functions - those that modify a memory location and those that modify the label that points to a memory location.  For example, the << operator actually modifies the memory location that both the run-time variable and the in-method argument point to.  The = operator merely assigns a given variable to ANOTHER memory location.  Thus, the shovel acts as pass-by-reference since the run-time variable is modified, and the equal sign acts as pass-by-value since the original value is unchanged.