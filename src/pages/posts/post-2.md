---
layout: ../../layouts/MarkdownPostLayout.astro
title: Alternatives for media -- Let's make the web accessible (1/5)
author: Zach
description: "The WCAG (Web Content Accessibility Guidelines) are a list of standards that are meant to help people make their sites accessible to everyone. But if you've ever taken a look at the official list of guidelines provided by W3.org, they can be pretty overwhelming! It can be hard to find a good place to start!"
image: 
    url: "src/assets/blog-post-1.png"
    alt: "Alternatives for media, Let's make the Web Accessible! 1/5"
pubDate: 2022-10-06
tags: ["blogging", "learning in public"]
---

The WCAG (Web Content Accessibility Guidelines) are a list of standards that are meant to help people make their sites accessible to everyone. But if you've ever taken a look at the official [list of guidelines](https://www.w3.org/TR/WCAG21/) provided by W3.org, they can be pretty overwhelming! It can be hard to find a good place to start!

![This is a lot to take in.](https://media.giphy.com/media/IplvQCq2ZdwPUGcaVN/giphy.gif align="left")

This is my attempt to make those guidelines a little more digestable. In this series of blog posts, I'm going to be breaking up the current version of the WCAG (2.1) into five different sections, starting with media.

\*Disclaimer: The landscape of web accessibility is evolving all the time. WCAG 3.0 is currently in draft and it's bound to hold some new guides to follow. There is also always going to be multiple ways to tackle different issues you come across. Alongside the guidelines, I am going to provide resources and examples I use to help make sure I am structuring things the best way I can.

So let's get started!

![Let's get started](https://media.giphy.com/media/l2JecCAExsqUC4HDy/giphy.gif align="left")

## Alternatives for Media

The first post in this series is about using media on websites, things like videos, podcasts, animations, or even livestreams.

### Videos

If you plan on having videos on your site, it's likely they're going to have to go through a few steps before they're fully accessible.

#### What's required?

* Video that has dialogue or speech needs to have a text transcript to go along with it.
    
* Closed Captions
    
* Video only (no audio), needs have an audio description
    
* There needs to be a way to pause, stop, or hide the video.
    
* In terms of the actual content, there can't be any flashing lights that flash more than 3 times a second.
    

Youtube can help you get some of the way there, they have all the functionality that you need when you embed a video into your site. However the auto-generated captions that youtube uses, sometimes aren't fully accurate, and in turn aren't ADA compliant. So you would still need to go back and write your own captions.

Here are two examples of fully accessible video players:

[Example 1](https://www.w3.org/WAI/perspective-videos/contrast/)

[Example 2](https://www.accessibilityoz.com/ozplayer/#:~:text=The%20world%27s%20first%20completely%20accessible%20video%20player!&text=OzPlayer%20is%20the%20only%20one,navigation%20but%20not%20audio%20tracks.)

When you're wire-framing a site, this should be a consideration for sure. If you want to embed videos in your site, you're going to need to make some room for a transcript. It's a similar story with audio tracks.

### Audio

Similar to video, audio-only elements on a site needs to have a way for non-hearing people to be able to access it. This means utilizing a transcript, and a fully functional audio player that has a pause button, audio control, the works.

A great place to look for ideas of what an audio player should look like is podcast websites. Some of them will use a transcript of the whole podcast, like the podcast [This American Life](https://www.thisamericanlife.org/750/transcript).

#### What's required?

* Captions
    
* Transcript
    
* There needs to be a way to pause, stop, or hide the audio.
    

### Images

Images are a type of media, they are a visual representation of something.

They are also fairly easy to make accessible, all you need to do is use the

![](undefined align="left")

tag, and give it some good and descriptive alt text.

But what if you need to use background images instead? If they are important to convey information, you can use an empty span next to the element with the background image, and give them the appropriate aria labels, just like the example below.

```plaintext
<div style="background-image=url('')"></div>
<span role="img" aria-label="Put the alt description here" aria-hidden="false"></span>
```

Also important to note, images with text in them are pretty frowned upon, but if you don't have any other option, then you can use the alt text to describe exactly what text is on the image.

#### What's required?

* Images need alt text that is descriptive of the actual image it's attached to.
    
* If background images are used, and they convey information. You can use a next to the html element with the background image, and give it a role="image" and an aria-label="alt text"
    

### Animation and Motion

A popular design technique is using parallax effect on images as you scroll through a site. It's best to avoid using this as it affects people that are prone to getting dizzy. An example of the parallax effect being used well is on the [Epicurrence site](https://epicurrence.com/).

You can see the background image has a parallax effect, but it is minimal and doesn't affect the user. it is also using an image that doesn't have anything really important to convey, so a screen-reader can skip over it.

#### What's required?

* If there's content within a parallax scrolling section, you need to be able to access it with a keyboard
    
* The color contrast between content and it's background need to be above a ratio of 4.5 to 1.
    

## What to take away.

When you're designing a site, pay attention to what media you're using.

Going to be using embedded videos? need to have room for a transcript.

Going to be using a big background image that conveys important information? make sure there's good enough contrast between the picture and the elements on top of it.

It's better to prepare for these things in the design stage, rather then after you've already developed it!

**Thanks for reading! If I missed anything, or you have anything to add, please leave a comment! My goal for this series is to open a discussion about peoples experiences with Web Accessibility!**