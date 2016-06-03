---
title: Usage
---

Next, update the configuration settings in the configuration file
`_config.yml` in the application directory. (You are already in it.)

- You might want to change the images and logos in the `img` directory
- You might want to change the demo episode file and the Jekyll Welcome post
  in `_posts` and `_episodes`

You can find a documentation of all the non-Octopod-specific settings
on the [Configuration page of the Jekyll Documentation](http://jekyllrb.com/docs/configuration/).

Jekyll is highly customizable, if you are into coding (or even just want to get into it),
read the [Jekyll Documentation](https://jekyllrb.com/docs/home/).
It is very detailed and quite easy to grasp.

First of all, your new podcast episode needs audio data. Octopod assumes
that your ready to use audio files stay within the `episodes` directory
in your projects root.

```
$ cp ~/my_superduper_audio_files/ocp001.m4a episodes
```

In addition, jekyll-octopod assumes that the different audio files of each of
your episodes are the same content in various formats -- with the same duration
and everything.
If they are not, you may confuse your listeners -- at least when you are using the chapters feature.

Next up, your episode needs some metadata. A title, some kind of a description, maybe chapters and so on. jekyll-octopod keeps all these metadata in one single text file (Protip: these dear little tots feel very lucky when they might live in a version control system!).
jekyll-octopod kindly helps you to generate these files with the
`octopod episode` command. You will get more information on the
The command line tool later.

The following command

```
$ octopod episode --title "Why I <3 Octopod"
```

will generate you a template
called **YYYY-MM-DD-why-i-_3-octopod.md** (YYYY-MM-DD represents the current date)
in your `_posts` subdirectory. When you open it in your text editor
you'll see something like this:

```
---
title: Why I <3 Octopod
subtitle: A Subtle Subtitle
date: May 22nd, 2016
layout: post
author: Uncle Octopod
explicit: 'no'
audio:
  m4a: name.m4a
  mp3: name.mp3
  ogg: name.ogg
chapters:
- '00:00:00.000 Intro.'
- '00:00:30.000 Outro.'
---
##

{% raw %}{{ page | web_player:site }}{% endraw %}


## Shownotes and Links

* Note
```

The part between the "`---`" and the "`---`" is the
[YAML front matter](http://jekyllrb.com/docs/frontmatter/).
This is where all the metadata is stored. Below the YAML frontmatter is the area (body)
where you can write down your post's content (like the show notes and stuff).
This strange looking
{{% raw %}`{{ page | web_player:site }}`{% endraw %}} thingy is the Liquid filter,
which represents the iframe where the web player will be included later.

When all this work is done you are ready to take a first look.
The following command generates your site and starts a local webserver for a preview. You can check your new podcasting website by opening `http://localhost:4000`.

```
$ octopod --url "http://localhost:4000" --server
```

If everything is alright you can finally generate your "real" Site:

```
$ octopod
```

And deploy it to your server:

```
$ octopod deploy
```

_Warning_: The Rsync settings in your `_config.yml` are mandatory
for this last step. But it is no problem to upload the generated website
from the `_site` subdirectory via FTP or something.
