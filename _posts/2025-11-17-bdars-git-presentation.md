---
layout: post
title: "Presenting about Git and GitHub at BDARS"
date: 2025-11-17 19:30:00 +1000
categories: git webdev programming talks
---

# Presenting about Git and GitHub at BDARS

On the 17th of November 2025, I have been invited to present at the Bayside District Amateur Radio Society about using Git and GitHub. The focus of the talk is in relation to amateur radio, and how Git and GitHub can be used to create personal websites and manage configurations for Radios and suchlike.

This was a unique opportunity to provide my knowledge as a software and platform engineer who uses these tools daily, to a group of people not quite familiar with them, but which would benefit their workflows significantly.

For Amateur Radio operators, it is particularly advantageous to have a personal website to link to for a bio and for the social aspect of Amateur Radio. GitHub Pages is a great tool for this as it is free and accessible with minimal technical know-how.

## Additional resources

- [git](https://git-scm.com/)
- [install git](https://git-scm.com/)
- [git cheatsheet](https://education.github.com/git-cheat-sheet-education.pdf)
- [another git cheatsheet](https://git-scm.com/cheat-sheet)
- [learn how to use GitHub](https://skills.github.com/)
- [Linus Torvalds talks about Git](https://www.youtube.com/watch?v=idLyobOhtO4)
- [GitHub Pages quickstart](https://docs.github.com/en/pages/quickstart)

---

<iframe width="560" height="315" src="https://www.youtube.com/embed/idLyobOhtO4?si=2WA7DZXgoMKKrn7m" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

## Make your own GitHub Pages website for free*

This website is built using GitHub pages. You can [view the source code here](https://github.com/SeanLMcCullough/personal-site).

To get started, create a public GitHub repository, and add an `index.md` file in Markdown format. Example [here](https://github.com/SeanLMcCullough/personal-site/blob/main/index.md?plain=1).

Then go into your repository settings and enable GitHub pages. In about a minute your page should be live!

GitHub uses [Jekyll](https://jekyllrb.com/), a static website framework, to generate webpages from a Markdown+HTML hybrid format. It is very powerful, and there are [many themes available](http://jekyllthemes.org/). When changes are made, a default GitHub action is triggered in your repository which will build and deploy your website.

To add more content to your website [check out this guide](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/adding-content-to-your-github-pages-site-using-jekyll)

* by default, your site will use a `github.io` domain ([example](https://seanlmccullough.github.io/antennas/)). To use a custom domain you will have to own or reigster one, and point it to GitHub's DNS servers.

## Presentation slides

<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vSbm_WBlYCqpmeFCtXlP3YYOsDELi6oZp1RE87aesEoRZ-sbKyQsXC1Xrjp-rTZC9afU8ipUPzEgIt9/pubembed?start=true&loop=true&delayms=3000" frameborder="0" max-width="1440" width="100%" height="839" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>

[Read more about our tech night here](https://bdars.org.au/events/technight-nov25-jpg/)
