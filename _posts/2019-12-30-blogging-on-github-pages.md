---
title: Blogging on GitHub Pages
---
This blog is hosted on [GitHub Pages](https://pages.github.com/). You can see the source… well, you can see the source in your browser, of course, this being a website and all. But I'm using software called [Jekyll](https://jekyllrb.com/) to generate the website, and you can see the input for this generator at [github.com/kairathmann/kai.codes](https://github.com/kairathmann/kai.codes).

The posts are just Markdown files located in [/\_posts](https://github.com/kairathmann/kai.codes/tree/master/_posts). Jekyll can parse the date and title from the filename. For example, this post is saved in a file called `2019-12-30-blogging-on-github-pages.md`. The date happens to be in the same `yyyy-MM-dd` format that I use for display – the [correct date format](https://xkcd.com/1179/) – but you can configure Jekyll to display a different one.

Jekyll uses the title from the filename both for the displayed title and for the URL of your blog post. For the URL, Jekyll uses the filename's capitalization as-is: You can verify in your browser's URL bar that this post is available under `/blogging-on-github-pages`. For the displayed title, Jekyll capitalizes the first letter of every word and lowercases the rest. For this post, I needed to override this behavior to capitalize "GitHub" correctly. You do this by putting so-called [Front Matter](https://jekyllrb.com/docs/front-matter/) at the top of the Markdown file. In the case of this post:

```yaml
---
title: Blogging on GitHub Pages
---
```

The next important file to look at is [\_config.yml](https://github.com/kairathmann/kai.codes/blob/master/_config.yml). It contains various configuration values that affect your site. Some of these values are inserted into the HTML, such as the site's title or your name.

As a template for this blog, I started with the [Hacker-Blog](https://github.com/tocttou/hacker-blog) theme for Jekyll. I did some minor edits to the CSS located in [/css](https://github.com/kairathmann/kai.codes/tree/master/css) and the HTML located in [/\_includes](https://github.com/kairathmann/kai.codes/tree/master/_includes) and [/\_layouts](https://github.com/kairathmann/kai.codes/tree/master/_layouts).

During development, you can test your site locally. After completing the necessary [installations](https://help.github.com/en/github/working-with-github-pages/testing-your-github-pages-site-locally-with-jekyll), run the following command in the root folder of your local git workspace:

```bash
bundle exec jekyll serve --trace
```

This will serve your site at `localhost:4000`. You can keep the command running in a separate terminal, and it will pick up any changes you make to your files. If you make a syntax error, it will abort and explain the problem.

GitHub Pages normally serves the output of the static site generation at `<user>.github.io/<repository>`, in my case [kairathmann.github.io/kai.codes](https://kairathmann.github.io/kai.codes). To serve your website under your own domain instead, you need to do two things:

1. Create a file called `CNAME` in your GitHub repository, containing your domain name. GitHub does this for you if you enter your domain name in the repository settings.
2. Configure DNS records for your domain to point to GitHub.

My blog is reachable both with and without `www.` in front of the domain name. For the plain `kai.codes`, called an apex domain, I needed to set four A records to point to the four IPv4 addresses of GitHub Pages as described on the [help page](https://help.github.com/en/github/working-with-github-pages/managing-a-custom-domain-for-your-github-pages-site). For `www.kai.codes`, I needed to set a CNAME record to point to `kairathmann.github.io`.

