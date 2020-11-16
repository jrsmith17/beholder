<!-- This was generated with DocToc, I just don't want their preaml-->
- [Beholder](#beholder)
  - [Motivation](#motivation)
  - [Surveying Available Options](#surveying-available-options)
  - [High Level Design and Roadmap](#high-level-design-and-roadmap)
  - [Scheduling](#scheduling)
  - [Contributing](#contributing)
  - [Feature Requests](#feature-requests)
  - [License](#license)

# Beholder

Beholder is going to be a cross operating system customization manager. Specifically, this tool will explore customizing visuals and behavior / settings at a program and OS level.

**Why call it beholder?** Mostly, it's a dumb reference to things "being in the eye of the beholder". I'm also going to create (or pay someone to create) a project logo loosely tied to DnD's beholder monster, but cute. You might think I'm a heavy DnD player given that, but no. I just wanted to double down on my joke name.

## Motivation

I often find myself wishing that programs would behave differently or appear more consistently. Also, whenever I start at a new job or get a new piece of personal hardware, I like to settle in by fiddling with all the settings. Because productivity guilt eventually settles in, I usually leave this half done - which is not ideal.

Manually configuring all of my programs across the various OSes that I use is time intensive, error prone, and induces a catotonic thousand yard stare in me. Moreover, I'm *really* bad at remembering various settings - e.g. I vastly prefer CMake so I never have to remember what setting does this or that in a sln file. I would much rather develop a program that can implement all of these things for me and it would delight me if other people benefited from this effort.

Possibly most important of all, though not aesthetic driven, both Windows and OS X are becoming increasingly difficult to use "freely" as the average user. I mean free as in "not tracked all the time", not free as in beer. I hope to explore how these companies are tracking us, for my own personal knowledge expansion if nothing else, but also to help other people retain better control of their digital life.

## Surveying Available Options

There's already a lot of nice options available in the desktop and program customization space. Why not use some of those? First, many of the options focus on just the OS (or a portion of it), just a singular OS, or just a singular program. Second, I can be a little persnickety (or particular, if I'm being kind) in how I want things to work. Third, while I have written a fair amount of Rust and a fair amount of OS specific code (in C++), I have not had a chance to write OS specific code in Rust.

But you may not be interested in my approach, so here are some nice options I found while doing initial research:

- [https://cairodesktop.com/] Promising looking Windows desktop customization
- [https://www.rainmeter.net/] A classic in this space. May either look at their project for inspiration or integration - hopefully making it easy for their community to try out this project without losing what they've already invested into Rainmeter.
- [https://www.stardock.com/products/start10/] Literally the only thing making Windows 10 usable to my mind. It's what I currently use. I am happy with it, I'm just picky and like finer grained control.

You may notice that I didn't include anything for OSX, Linux, BSD, Android, iOS, etc. I have used all of those on personal devices (except iOS and BSD, will have to figure those out), but I have admittedly less experience researching what options are available in that space - **especially Linux**, where I know there's plenty of options but I usually use it via the command line 99% of the time.

## High Level Design and Roadmap

As alluded to earlier, I plan on using Rust for this project. It's one of the recent (ish?) crop of languages that I have been most excited about. As the project matures, I do plan on posting a public Trello roadmap. I expect the initial design will iterate quickly as I learn what is possible. In these early stages though, I think it is useful to lay out some design *goals*, if not the actual design itself.

- **Cross platform:** Have a theme, collection of settings, etc. that you like on one platform that you want to readily share amongst the devices you use? Me, too!
- **Coverage:** While I certainly don't use every tool under the sun, I want this project to support as many tools as possible. If visuals help, look at how many programs the excellent [https://draculatheme.com/] covers. I find that inspiring, even though personally I think my own theme will be more aligned to [https://github.com/morhetz/gruvbox].
- **Ease of Use:** Back in my baby programmer days (read: early 20s) I make an abortive attempt at this idea. I tabled it because I felt it was above my skill level at the time. I want it to be just as easy for non-technical enthusiasts to pick up as for programmers to dive in and add functionality to fits their needs.
- **Community Driven:** I'm hoping to build a nice, cozy community of users that contribute themes, code, and generally cheer each other on.
- **Empowers Users:** Even if for my own paranoid privacy obsessed purposes, I want this program to help users shut off OS tracking that they don't want. Just as an example, the best current option to turn off Windows 10 telemetry is a Powershell script hosted as a gist. That's not even ideal for the average programmer, much less the average user.
- **Purposefully Open Ended:** I couldn't come up with a better term than open ended, but here's what I mean. I suspect that the Rust win32 crate, or maybe some other crate we'll end up using, may be early in it's maturity. If I end up using Stream time to contribute back to these crates to meet the project needs, that seems reasonable to me. Also, if it makes sense to dive into something conceptually on a stream or two - that may also be useful.
- **Website:** I'm planning on building a website to faciliate theme sharing, ease of binary downloads, etc. But it's definitely not the first priority.

## Scheduling

I am planning on starting this project in earnest in the second week of December 2020. In addition to my full time job, I'm also in grad school. My current semester ends the first week of December and I think that *starting* a new project during the next few weeks would prove overwhelming.

I am going to stream regularly on my Twitch channel at [https://www.twitch.tv/abysmallytall]. I haven't locked down the exact hours of the stream, but I aiming to stream for 2 hour blocks twice on Mondays - once in the morning and once in the evening. I think 4 hours / week is a reasonable commitment to make given my other responsibilities. This doesn't mean I won't work on it outside of those times, live streamed or not, but I wanted to set a reasonable minimum time so that I can feel like I am making forward progress in something that brings me joy no matter how the rest of my week is going.

## Contributing

In the beginning, I do not plan on accepting (major?) contributions. This is largely because part of the fun for me is figuring out *how* to make this work and then iteratively designing the architecture as I go along. One can, of course, do that collaboratively. However, I already do that at work and it's much easier to coordinate the early stages of a personal project with just one person even when I plan on opening it up.

Medium to long term, I *absolutely* plan on opening up this project for contributions. Between operating system updates, API changes, and the wide swath of programs to support, there's no way that one person could maintain this as a solo effort.

In terms of financial support, I have no concrete plans as of yet. I have considered a one time license fee a la [https://www.sublimetext.com/] or a Patreon backed approach akin to [https://github.com/ocornut/imgui]. If I go either route, I'm included to pursue the latter as it matches the wide scope of work with a central maintenance team. I'm also intrigued by the GitHub sponsorship model, but I have not afforded myself much time to read up on it.

**Caveat:** I'm open to being convinced to open up contributions earlier than planned. Especially compared to some other personal projects I have planned. e.g. I have a computer vision project planned for *some time in the future*. There, personally learning and practicing the math and sytems involved is more important to me than the eccentricities of given OS APIs.

**Second Caveat:** I am only fluent in English. I could write *readable, but not fluent* docs in German and Spanish. If anyone wants to contribute anything documentation wise in another language, I will eagerly accept that. I plan on making an attempt in the languages I have learned / am learning if no one else is available, but I'd much rather have a native speaker take point on this.

## Feature Requests

While I'm not initially planning on accepting contributions in the form of PRs, I definitely want to hear what you would want out of this tool. While I am primarily making this for me, I would really consider this a success if it helps other people as well. In addition to my Twitch streams, I can be reached at [https://twitter.com/abysmallytall] or via email at jrsmith17 (at) protonmail (dot) com.

## License

License selection TBD before I start the first official stream. I'm likely going to choose among the more permissive licenses, I just feel obliged to refresh myself on the finer details every time I make a selection.