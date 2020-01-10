---
title: Introducing my newsletter
---
kai.codes now has a [newsletter](newsletter) for blog updates. I tried sharing updates on Facebook, but while the story "Kai has a new blog with a cool domain" was broadly relatable, my subsequent technical posts were interesting only to a few of my friends. And these friends weren't even guaranteed to see my updates. Hence, the newsletter – and a new topic to write a post about.

The obvious choice of newsletter service was [Mailchimp](https://mailchimp.com/). Mailchimp is the one name in the newsletter space that I've kept coming across over the years. Their service comes with a generous free tier for up to 2,000 contacts (subscribers) and 10,000 monthly emails (counting each newsletter issue sent to each contact as one email). I love this kind of pricing:

* Let me do my hobby project for free.
* Start charging me if and when I reach notable scale.
* Still have reasonable pricing at the non-free tiers. (Non-free Mailchimp starts at $9.99 per month.)

I'm hosting this blog as a [static site on GitHub Pages](blogging-on-github-pages). The only way to include a newsletter subscription in this case is an embedded form. Dynamic sites can have pop-up forms, but I don't miss those because they're more annoying for the user.

Unfortunately, signing up for Mailchimp and embedding the form weren't the only things I needed to do. The European Union has the General Data Protection Regulation (GDPR), which among other things apparently requires me to add verbiage to the [subscription form](newsletter) as well as an entire [privacy policy](privacy) to the site. Mailchimp has some helpful configuration options such as a GDPR field in the form builder and double opt-in, meaning the usual confirmation email where you need to click a link to finish subscribing. Both the GDPR field and double opt-in aren't selected by default, so you need to be careful not to forget these if you're based in the European Union.

For the privacy policy, I found a helpful [generator](https://www.ratgeberrecht.eu/leistungen/muster-datenschutzerklaerung.html) by a German law firm that offered just the right amount of customizability as well as an option for English output. All they require in return for using their text is keeping a linked reference to them that they insert at the end of the text.
