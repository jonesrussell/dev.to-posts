# My blog posts @ dev.to

https://dev.to/jonesrussell

## How can I find the ID of my blog post on dev.to?

This repository is made to **edit** a blog post. Whether it's published or just a draft, you **have to create it** on dev.to directly. Unfortunately, dev.to does not display the ID of the blog post on the page. So once it's created, you can open your browser console and paste the following code to retrieve the blog post ID:  
`$('div[data-article-id]').getAttribute('data-article-id')`

## How do I configure every blog post individually?

A blog post has to have a [**front matter**](https://dev.to/p/editor_guide) header. You can find an example in this repository here: https://github.com/maxime1992/dev.to/blob/master/blog-posts/name-of-your-blog-post/name-of-your-blog-post.md

Simple and from there you have control over the following properties: `title`, `published`, `cover_image`, `description`, `tags`, `series` and `canonical_url`.

## How do I add images to my blog posts?

Instead of uploading them manually on dev.to, simply put them within your git repo and within the blog post use a relative link. Here's an example: `The following is an image: ![alt text](./assets/image.png 'Title image')`.

If you've got some plugin to preview your markdown from your IDE, the images will be correctly displayed. Then, on CI, right before they're published, the link will be updated to match the raw file.

## How to setup CI for auto deploying the blog posts?

If you want to use Github and Travis, a `.travis.yml` file has been already prepared for you.

First, you have to activate the repository on Travis: https://travis-ci.org/account/repositories

Then, you have to create a token on your dev.to account: https://dev.to/settings/account and set an environment variable on Travis called `DEV_TO_GIT_TOKEN` that will have the newly created token as value.

## README template

The following is simply a template that you may want to use for your own version of that repository.

# \<YOUR NAME\>'s blog source

https://dev.to/\<YOUR DEV.TO NICKNAME\>

## Blog posts

- [\<BLOG POST NAME\>](https://dev.to/\<BLOG POST LINK\>)
