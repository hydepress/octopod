---
title: Post structure
---

The post template can be found in `/includes/post.html`. It renders the posts from the `/_post` directory.
Each post has to have a certain structure which consists of the YAML front matter and of the body part.

## The YAML front matter

jekyll-octopod's YAML front matter is an extension of [Jekyll's YAML front matter](https://github.com/mojombo/jekyll/wiki/YAML-Front-Matter).  

The attributes that can be set here are best described with the following example; they are quite self-explanatory:

```
title: Episode 0
subtitle: Getting Started Is Never Easy
summary: Otherwise the summary is the first paragraph of the show notes
episode-cover: "/img/episode-cover0.jpg'
datum: March 22nd 2016
layout: post
author: Arne and Stefan
explicit: 'no'
duration: "0:03:13"
audio:
  mp3: episode0.mp3
  ogg: episode0.ogg
  m4a: episode0.m4a
chapters:
  - '00:00:00.000 Intro.'
  - '00:00:30.000 ... Shoubidoubidoo ...'
  - '00:02:45.000 Outro.'
tags:
  - "a tag"
  - "another tag"
posts-dir: "/path/to/post/dir" # default: '_posts'
```

## The body

The body part can contain arbitrary markdown content.

At minimum a short text, the web player (embedded in an iframe) and some links are recommended. For example:

```
Getting started is hard.
{% raw %}
{{ page | web_player_moderator:site }}
{% endraw %}
## Show Notes und Links

  * Link lists are easily created: [Aua-uff-Code! Podcast](https://aua-uff-co.de)
  * another link to [Jekyll](https://jekyllrb.com/)
```

Audio and script tags get filtered out of the body for feed creation, 
so that they do not disturb in podcatchers rendering the shown notes.

