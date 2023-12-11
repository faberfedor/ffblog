---
layout: post
title: Getting a Mastodon Icon In the Footer
date: 2023-12-07 00:00 -05:00
---

For my first blog post, I wanted to share the process of adding that little Mastodon icon you see at the bottom of the page. I'm using the Jekyll framework, specifically the [Jekyll Now](https://github.com/barryclark/jekyll-now)  instance, which is a fully functional blog that you can customize.

Since I'm reconnecting with my decentralized roots, having a Mastodon icon in the footer was a must. Surprisingly, I couldn't find one readily available, so I had to create my own and figure out how to integrate it into the Jekyll framework.

Here's a quick overview, but you can check out the results in my GitHub repository:

1. Add the following code to `_sass/_svg-icons.scss`:
```scss
	&.mastodon	  { background-image: url('data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgaGVpZ2h0PSIxNiIgZmlsbD0iY3VycmVudENvbG9yIiBjbGFzcz0iYmkgYmktbWFzdG9kb24iIHZpZXdCb3g9IjAgMCAxNiAxNiI+CiAgPHBhdGggZD0iTTExLjE5IDEyLjE5NWMyLjAxNi0uMjQgMy43Ny0xLjQ3NSAzLjk5LTIuNjAzLjM0OC0xLjc3OC4zMi00LjMzOS4zMi00LjMzOSAwLTMuNDctMi4yODYtNC40ODgtMi4yODYtNC40ODhDMTIuMDYyLjIzOCAxMC4wODMuMDE3IDguMDI3IDBoLS4wNUM1LjkyLjAxNyAzLjk0Mi4yMzggMi43OS43NjVjMCAwLTIuMjg1IDEuMDE3LTIuMjg1IDQuNDg4bC0uMDAyLjY2MmMtLjAwNC42NC0uMDA3IDEuMzUuMDExIDIuMDkxLjA4MyAzLjM5NC42MjYgNi43NCAzLjc4IDcuNTcgMS40NTQuMzgzIDIuNzAzLjQ2MyAzLjcwOS40MDggMS44MjMtLjEgMi44NDctLjY0NyAyLjg0Ny0uNjQ3bC0uMDYtMS4zMTdzLTEuMzAzLjQxLTIuNzY3LjM2Yy0xLjQ1LS4wNS0yLjk4LS4xNTYtMy4yMTUtMS45MjhhMy42MTQgMy42MTQgMCAwIDEtLjAzMy0uNDk2czEuNDI0LjM0NiAzLjIyOC40MjhjMS4xMDMuMDUgMi4xMzctLjA2NCAzLjE4OC0uMTg5em0xLjYxMy0yLjQ3SDExLjEzdi00LjA4YzAtLjg1OS0uMzY0LTEuMjk1LTEuMDkxLTEuMjk1LS44MDQgMC0xLjIwNy41MTctMS4yMDcgMS41NDF2Mi4yMzNINy4xNjhWNS44OWMwLTEuMDI0LS40MDMtMS41NDEtMS4yMDctMS41NDEtLjcyNyAwLTEuMDkxLjQzNi0xLjA5MSAxLjI5NnY0LjA3OUgzLjE5N1Y1LjUyMmMwLS44NTkuMjItMS41NDEuNjYtMi4wNDYuNDU2LS41MDUgMS4wNTItLjc2NCAxLjc5My0uNzY0Ljg1NiAwIDEuNTA0LjMyOCAxLjkzMy45ODNMOCA0LjM5bC40MTctLjY5NWMuNDI5LS42NTUgMS4wNzctLjk4MyAxLjkzNC0uOTgzLjc0IDAgMS4zMzYuMjU5IDEuNzkxLjc2NC40NDIuNTA1LjY2MSAxLjE4Ny42NjEgMi4wNDZ2NC4yMDN6Ii8+Cjwvc3ZnPg=='); background-repeat: no-repeat ; background-position: center;} 
```

Make sure it's all on one line with no spaces inside the `url()` part. Dealing with that block of code inside Vim can be a bit tricky.


2. Add the following code to the `footer_links` section of `_config.yml`:
```yaml
footer-links:
  ...
  googleplus: # anything in your profile username that comes after plus.google.com/
  mastodon: 
    username: <user-name>
    instance: <mastodon-instance>
```
Note: the `username` and `instance` lines should be indented under the
`mastodon:` heading. I don't know how to do that yet in Markdown -> YAML.

Currently, the code can only handle one Mastodon account.

3.  And finally, add the following code to `_includes/svg-icons.html`
```html
{% if site.footer-links.mastodon %}<a href="https://{{ site.footer-links.mastodon.instance }}/@{{ site.footer-links.mastodon.username }}"><i class="svg-icon mastodon"></i></a>{% endif %}
```
These steps will help you display a Mastodon icon in your blog's footer. If you want more details, feel free to dive into the GitHub repository.
