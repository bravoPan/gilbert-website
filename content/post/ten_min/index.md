---
title: Ten Minute, A movie sharing platform
subtitle: A movie sharing platform to video the details of the movies, you can view the same videos by your favourite topic, and you can vote for the video you like.

# Summary for listings and search engines
summary: A full stack web application developed by python Django, all functions are implemented by MTC design pattern.

# Link this post with a project
projects: []

# Date published
date: "2020-10-01T00:00:00Z"

# Date updated
lastmod: "2020-11-01T00:00:00Z"

# Is this an unpublished draft?
draft: false

# Show this page in the Featured widget?
featured: false

# Featured image
# Place an image named `featured.jpg/png` in this page's folder and customize its options here.
image:
  caption: 'Image credit: [**Ten Min**](http://tenmin-eb-real-env.eba-mzrnikmw.us-west-2.elasticbeanstalk.com/)'
  focal_point: ""
  placement: 2
  preview_only: false

authors:
- admin

tags:
- Django
- Web Appilcation

categories:
- Django
- Web Appilcation
---

## Overview

1. Ten Minute can show you the simple movies' description in 10 minutes, just view the movie that caught your eyes.
2. Just Create your own Account and view the movies, vote for the movie you like!

{{< figure src="https://bravopan.github.io/ten_min_detail.png" title="The Detail of the movies which you are interested" >}}

<!-- ## What we have

- 👉 [**Create a new Account**](https://wowchemy.com/templates/)
- 📚 [**Personalize your site**](https://wowchemy.com/docs/)
- 💬 [Chat with the **Wowchemy community**](https://discord.gg/z8wNYzb) or [**Hugo community**](https://discourse.gohugo.io)
- 🐦 Twitter: [@wowchemy](https://twitter.com/wowchemy) [@GeorgeCushen](https://twitter.com/GeorgeCushen) [#MadeWithWowchemy](https://twitter.com/search?q=(%23MadeWithWowchemy%20OR%20%23MadeWithAcademic)&src=typed_query)
- 💡 [Request a **feature** or report a **bug** for _Wowchemy_](https://github.com/wowchemy/wowchemy-hugo-modules/issues)
- ⬆️ **Updating Wowchemy?** View the [Update Guide](https://wowchemy.com/docs/guide/update/) and [Release Notes](https://wowchemy.com/updates/) -->

<!-- ## Crowd-funded open-source software

To help us develop this template and software sustainably under the MIT license, we ask all individuals and businesses that use it to help support its ongoing maintenance and development via sponsorship. -->

<!-- ### [❤️ Click here to become a sponsor and help support Wowchemy's future ❤️](https://wowchemy.com/plans/) -->

As a cinephilia, you have to go check on **[Ten Minute](http://tenmin-eb-real-env.eba-mzrnikmw.us-west-2.elasticbeanstalk.com/)**!

<!-- ## Ecosystem

* **[Hugo Academic CLI](https://github.com/wowchemy/hugo-academic-cli):** Automatically import publications from BibTeX -->

<!-- ## Inspiration

[Check out the latest **demo**](https://academic-demo.netlify.com/) of what you'll get in less than 10 minutes, or [view the **showcase**](https://wowchemy.com/user-stories/) of personal, project, and business sites. -->

## Technical Parts

- **Login** - HTTP GET&POST, Form Validation, Form Authentication, Session Creation
- **Create Accont** - HTTP GET&POST, Form Authentication, Error Message Render, Form Filter
- **Video Listing** - ORM Query, Data Plugin, URL Design, Template Rendering
- **Pagination** - URL Design, Django Pagination Robot, ORM Query, Jinja Tag Condition, Template Rendering
- **Video Sort** - URL Redirection, ORM Query by Condition&Sorting,
- **User Authentication** - Django Authentication, Session Validation, JinJa Tag Condition
- **Detial Page** - URL Config, Web Crawler, Semantic Card Component, Redirect to Home
- **Deployment** - AWS Elastic Beanstalk, Python awsebcli, Virtual Environment Configuration
## Themes

Wowchemy and its templates come with **automatic day (light) and night (dark) mode** built-in. Alternatively, visitors can choose their preferred mode - click the moon icon in the top right of the [Demo](https://academic-demo.netlify.com/) to see it in action! Day/night mode can also be disabled by the site admin in `params.toml`.

[Choose a stunning **theme** and **font**](https://wowchemy.com/docs/customization) for your site. Themes are fully customizable.

## License

Copyright 2016-present [George Cushen](https://georgecushen.com).

Released under the [MIT](https://github.com/wowchemy/wowchemy-hugo-modules/blob/master/LICENSE.md) license.
