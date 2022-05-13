---
title: "How-to Github Actions: Building your Android App"
categories: "Android"

excerpt: "Setting up a Continuous Integration system for your Android App on Github has never been so easy with Github Actions"

header:
    image: "./assets/images/posts/howto-github-actions-building-android/header.jpg"
    teaser: "./assets/images/posts/howto-github-actions-building-android/teaser.jpg"
    caption: "Waltershofer Hafen - Hamburg, Germany"
---

One of the [first things I set up](/blog/my-android-project-template) when working on a project, is a **Continuous Integration** (CI) system. 

I've recently spent some time migrating several projects of mine to **Github Actions**. I have to admit that I was amazed by how **easy** it was to set up, together with the **performance boost** I gained from it.
 
In this blog-post series, I will walk you through **how to set up your CI** with Github Actions. While I **migrated real-world projects** I collected tips and tricks that will help you get your CI up to speed. This first blog-post will serve as an **introduction** and will help you to get started with Github Actions. 🚀

# What is Github Actions?

Github Actions is a service offered by Github to set up a Continuous Integration (CI) system for your projects hosted on Github. With Github Actions, you can automate tasks of your development lifecycle such as **build**, **test**, **analyze**, **bundle**, **release**, and **deploy**.

Having a good CI is **crucial** in your development flow. 

You can find plenty of material online on how to write good tests, but:

> It's useless to write tests if you are not running them

## Ready for Android

The runners offered by Github Actions allow you to run your build on **Linux**, **Mac**, and **Windows**.

They all have **Java** and **Android** already installed and configured (the list of [pre-installed software](https://github.com/actions/virtual-environments/blob/main/images/linux/Ubuntu1804-README.md) is pretty long).

You don't have to bother accepting Android Licenses anymore (`yes | sdkmanager` and permutations of those commands). Workers can build the majority of Android project out of the box without further setup.


* There is a **many-to-many** relationship between triggers and workflows.
* There is a **one-to-many** relationship between workflows and jobs. 

<figure>
    <img src="/assets/images/posts/howto-github-actions-building-android/diagram2.jpg" alt="diagram of relationships between workflow, trigger and jobs">
    <figcaption/>
</figure>

Let's have a closer look to each concept.

# Workflow
 
Each workflow lives in a separate **workflow file**. Workflow files use the **YAML** syntax and live inside the `.github/workflows` folder of your repository. 

Let's create our first workflow file `.github/workflows/build.yaml` and let's give our workflow a `name`:


<figure>
    <img src="/assets/images/posts/howto-github-actions-building-android/sample-action-run.png" alt="sample github action run screenshot">
    <figcaption>An Action running on Github</figcaption>
</figure>

You can find the full example in this gist file below:
{% gist cb379bdf3cea8e843a1feb00a806496a %}

# Conclusions

Github Actions has become my go-to CI solution for Android projects on Github, thanks to its **simplicity** and its **performances**. As you saw in this blog-post, you can spin up a CI system for Android with 10 lines of YAML.

In the following blog-posts, we will see some more advanced techniques I'm currently using in CIs for real-world projects.

Make sure you don't miss the upcoming articles, you can find me as [@cortinico on Twitter <i class="fab fa-twitter"></i>](https://twitter.com/cortinico).
