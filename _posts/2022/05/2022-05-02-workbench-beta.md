---
layout: page
authors: ["Zhian N. Kamvar"]
teaser: "Initial outline and plan for the Beta Phase of The Carpentries Workbench"
title: "The Carpentries Workbench: Beta Phase and Beyond"
date: 2022-05-02
time: "09:00:00"
tags: ["Lesson Infrastructure", "Community", "Carpentries Workbench", "Beta", "Dovetail"]
---

## TL;DR

We will be transitioning some of the lessons to [The Carpentries Workbench](https://carpentries.org/blog/2022/01/live-lesson-infrastructure/) in the
next few months as a beta test. The beta test will live in parallel to the
current lessons for at least two months before fully transitioning. If you are a
maintainer, and would like to have your lesson enter the beta test, please [sign
up and tell us about your lesson and when is the earliest time for you to start 
the beta testing][beta-test-signup-maintainer].

We expect to transition all lessons (including lessons in The Carpentries Incubator and The Carpentries Lab) to use [The
Carpentries Workbench][workbench] by January 2023.

<a href="https://example.com/#TODO" class="button expand">
    Sign up to enroll your lesson in the Workbench beta
</a>


## Things are going to get beta

We are pleased to announce that we are officially opening applications for
maintainers to volunteer for beta testing The Carpentries Workbench on their own
lessons. Details can be found in [the presentation I gave during the April
Maintainer Meeting][beta-test-slides]. 

While we have lessons such as [The Workbench Documentation][workbench] and
[Collaborative Lesson Development Training][ldt] that currently use the
workbench, understanding the advantages and limitations of the workbench can
only be achieved if it is being used on a variety of lessons and tested by
multiple Maintainers. **The purpose of the beta phase is to test out the
workbench in live conditions and get feedback from early adopters** Thus, we
would like to get a breadth of lessons using The Workbench.

Before I go on, because I will be referring to two versions of any given lesson,
I want to introduce some helpful terminology:

"beta"
: The beta phase of the workbench transition. This explicitly does NOT mean beta
  phase for the content of a lesson.

"styles"
: The Jekyll-based engine and styling that has been the basis of Carpentries
  lessons since 2015: <https://carpentries.github.io/lesson-example/>. 

"workbench"
: The Pandoc + R-based engine and styling that will replace styles:
  <https://carpentries.github.io/sandpaper-docs>. 

Because the websites for the lessons will look different depending on the engine,
I will be referring to them as "styles" or "workbench" websites. 

## Why have a beta phase at all?

Our lesson have a _wide_ audience including, Instructors, Learners, Maintainers,
and others who use the CC-BY content in their own work. In the past, [changes to
the way we build lessons happened at a fairly rapid pace][blog-pushing-back],
which resulted in frustration from the community. 

In the end, we will transition all lessons by January 2022. The beta phase is 
intended to allow early adopters to play around with the workbench and help
shape it to best fit the community needs.

## Beta Logistics

The workbench beta phase is **non-reversible**[^1], thus, the descision to begin
the beta phase for any given lesson must be a **joint decision by the
mainainers of the lesson**. It is important to note that the transition itself
is the responsibility of myself alone and will be performed automatically via
the [lesson transition tool][lesson-transition].

### Website

During the workbench beta phase, the URLs for the styles and the workbench
websites will be in the following forms:

 - **styles**: `https://<program>.github.io/<lesson>` (e.g. <https://datacarpentry.github.io/r-novice-gapminder>)
 - **workbench**: `https://lessons.<program>.org/<lesson>` (e.g. <https://lessons.datacarpentry.org/r-novice-gapminder>)

<figure style="text-align: center">
  <img src="{{ site.urlimg }}/blog/2022/05/styles-url.png" 
   alt="cartoon representation of the styles version of a lesson with the url pattern underneath" width="40%"/>
  <img src="{{ site.urlimg }}/blog/2022/05/workbench-url.png" 
   alt="cartoon represntation of the workbench version of a lesson with the url pattern underneath" width="45%"/>
  <figcaption>
  The styles and workbench versions of the websites will live in parallel at separate URLs during the first two stages of the workbench beta phase
  </figcaption>
</figure>

### Stages

The transition will occur for each lesson independently in three phases with targeted feedback from community segments as noted below:

- [Pre-beta](#pre-beta): convert snapshot of lesson to use [The Carpentries Workbench][workbench] in a temporary, sandboxed repository.
  - Timeline: 4 weeks
  - Instructors: teaching demo-style feedback
  - Maintainers: triage and resolve existing pull requests; experiment with new repository
- [Beta](#beta): lesson-release and archive of styles version; source conversion to workbench
  - Timeline: 8 weeks
  - Instructors: opt-in to training + teaching demo-style feedback
  - Maintainers: receive and merge at least 2 pull requests
  - New Instructors: encouraged to contribute to workbench beta phase by adding/moving Instructor notes
- [Release Candidate](#release-candidate): fully transition to workbench and new URL; old URL will redirect to new.
  - Timeline: 6 months
  - Instructors: teach new version of lesson
  - Maintainers: continue to work on new lesson with two-track feedback mechanism

<figure style="text-align: center">
  <img src="{{ site.urlimg }}/blog/2022/05/workbench-beta-flow.png" 
   alt="Diagram of three phases of the beta release. At the top is box labelled 'current' that contains a GitHub logo, a cartoon of a lesson page. Below is a box labelled 'Pre Beta' with the same contents as the box above plus an additional GitHub logo in blue with a camera above it (to indicate a snapshot) and a new cartoon of a lesson page with a padlock over it. There is a clock indicating a timeframe of four weeks. The next box below is labelled 'Beta'. The GitHub logo has become blue and there is a lightning bolt and a line connecting it to the previous logo, indicating that a transformation happened. A smaller, grey GitHub logo is adjacent with a lock over it, indicating that it is archived. The  old lesson page now has a lock and information symbol above it. The new lesson page does not have any symbols above it. The timreframe is 6 to 8 weeks. The final box is titled 'Release Candidate' and has a single blue GitHub logo, a faded old lesson page, and a new lesson page with a timeframe of 6 months"/>
  <figcaption>
An overview of the workbench beta phase for the Git repository and the website, separated
into three stages. The entire process will take about 8-9 months until lesson
release with The Carpentries Workbench.
  </figcaption>
</figure>

#### Pre-Beta

A snapshot of the lesson will be taken and migrated to the new lesson URL. The
styles version of the website will have a new banner announcing the pre-beta
phase of the lesson and a link for feedback. 

**Maintainers** will use the snapshot to inspect the differences in their
lessons. Because the new layout of the lesson will represent only a snapshot at
this point, changes made to the lesson will not be reflected in this new URL
(but that should not prevent Maintainers from making necessary changes).

This is the phase in which Maintainers can make inquiries about transitioning
to the workbench beta phase. Importantly, they should **begin the process of
consolidating issues and pull requests in their repositories to avoid conflicts
with the new format**[^1].

**Instructors** will give teaching-demo style feedback in groups of three during
which they will be specific teaching prep tasks (determined by the Instructor
Development Committee) to complete with the snapshot and then give two kinds of
feedback:

- Feedback related to the infrastructure
- Feedback for each other

#### Beta

Reminders:

1. This stage is a one-way transition. There is no going back
2. Any open pull requests must be re-opened using the new infrastructure[^1]

A lesson release is minted into a zenodo DOI (by François), [the lesson
repository is be archived][backing-up], and subsequently converted in place
using the [lesson transition tool][lesson-transition]. The current default
branch will be copied to a static branch called “legacy”. The styles version of
the website will have a banner that announces that an up-to-date version of the
website can be found at the workbench URL with a link for feedback. 

**Maintainers** will work on the `main` branch of the lesson using the workbench
and can give feedback in one of two ways:

1. General feedback in Maintainer meetings and at
   <https://github.com/carpentries/sandpaper/discussions>
2. Maintainers can practice giving feedback via friction logs in paired
   sessions where they are asked to perform a specific task and give narrative
   feedback regarding their experience (good, mildly confusing/irritating, or
   throw-your-laptop-out-a-window frustrating). 

**Instructors** can continue to give feedback in the teaching demonstration
fashion and they can additionally try this out in lessons that they are
actively teaching if they so choose. They can also contribute Instructor notes
to the inner portions of the lesson if they choose.

If the Learners use the new version of the lesson, there will be a link where
they can give feedback. 

**New Instructors** will be encouraged to contribute to the lessons by
submitting Instructor notes inside the lesson content.

#### Release Candidate

During this phase, the styles version of the lesson will officially redirect to
the new version of the lesson and any future workshops will use this version.
There is no guarantee that it will be free from minor mistakes from the
translation process, but it will contain the correct content.

## Challenges

Of course, this transition will not be without any number of challenges.

### Cognitive Load

Teaching a workshop is hard and learning coding skills is hard. Testing out a
new format of a website on top of that is added cognitive load, especially if
only ONE lesson is different from the others. We mitigate this by having two
versions of the lesson for three months. This way, even if one out of three
lessons is currently in Beta, the default lesson website is still available so
the transition is not so jarring. 

### Format Change

A lot of thought has gone into the design of the lesson infrastructure and the
lesson website to make things more accessible and easier to navigate. Despite
this, people are creatures of habit and it's difficult to switch contexts in a
lesson. For some Maintainers, this may be wanting to write block quotes instead
of fenced divs, for others this may be wanting to work from the `gh-pages`
branch instead of `main`. This is why we have the pre-beta stage of the beta
phase where the workbench exists as a sandbox so that Maintainers can practise
using it without worrying about doing any permanent damage.


### The Weight of History

Because the styles-version of our lessons bundled all the tools needed to build
the lessons, we end up with a situation where it's difficult to attribute credit
to lesson authors because there are commits that have nothing to do with the
lesson content (e.g. changes to CSS or Makefiles). Moreover, R-based lessons
created before 2020 contained rendred content, which increased repository sizes
by ~100MB in some cases. To address these challenges, the [lesson transition
tool][lesson-transition] cleans the commit history of everything but the lesson
content.

## Moving Forward

The first few lessons in workbench beta will involve a lot of iteration and
feedback, and during this time, I will be posting updates in this blog as a new
series called "The Dovetail", where you can get information about:

 - Updates to The Carpentries Workbench
 - Upcoming and Current Lessons in Beta
 - Updates from Instructors and Maintainers about working in Beta
 - Tips and Tricks for using The Workbench

If you follow Carpentries Clippings, it will be automatically included.

By January 2023, we expect to have transitioned all of our lessons to use The
Carpentries Workbench. 


<a href="https://example.com/#TODO" class="button expand">
    Sign up to enroll your lesson in the Workbench beta
</a>


[beta-test-signup-maintainer]: https://example.com/#TODO
[beta-test-slides]: https://docs.google.com/presentation/d/1qA9U4BkLKW_kOn696jKkDbUgv910_i-sGbHTZ9tyURQ/edit?usp=sharing
[workbench]: https://carpentries.github.io/sandpaper-docs
[styles]: https://github.com/carpentries/styles/
[ldt]: https://carpentries.github.io/lesson-development-training/
[blog-pushing-back]: https://software-carpentry.org/blog/2015/07/pushing-back.html
[design-principles]: https://carpentries.org/blog/2020/08/lesson-template-design/
[lesson-transition]: https://github.com/data-lessons/lesson-transition/#readme
[backing-up]: https://ropensci.org/blog/2022/03/22/safeguards-and-backups-for-github-organizations/#backing-up-github-repositories
[{sandpaper}]: https://carpentries.github.io/sandpaper/
[{pegboard}]: https://carpentries.github.io/pegboard/
[{varnish}]: https://carpentries.github.io/varnish/
[alpha-test]: https://carpentries.org/blog/2021/07/infrastructure-testing/
[ux-test]: https://carpentries.org/blog/2021/05/lesson-template-design-process/
[yt-vid]: https://www.youtube.com/watch?v=vd8XZSuY_Rs&list=PLSFzyC3wp8-csb8rtreOUoW8C_1J87QD5&index=1&t=1271s
[slide-19]: https://zkamvar.github.io/user2021/#19
[old-episodes]: https://web.archive.org/web/20220125163344/https://carpentries.github.io/sandpaper-docs/episodes.html
[new-episodes]: https://web.archive.org/web/20220128171242/https://carpentries.github.io/sandpaper-docs/episodes.html
[sandpaper-cache]: https://carpentries.github.io/sandpaper/articles/building-with-renv.html
[pr-preview]: https://carpentries.github.io/sandpaper-docs/instructor/pull-request.html

[^1]: See the [lesson-transition] tool for details. In short, the folder
  structure AND the commits will change. Any PRs from styles-based repositories
  will appear to add hundreds of new commits and files even if they were
  originally changing a few lines of content.

