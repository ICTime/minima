---
layout: post
categories: linux 
tags : [jekyll ]
---
You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. You can rebuild the site in many different ways, but the most common way is to run `jekyll serve`, which launches a web server and auto-regenerates your site when a file is updated.

To add new posts, simply add a file in the `_posts` directory that follows the convention `YYYY-MM-DD-name-of-post.ext` and includes the necessary front matter. Take a look at the source for this post to get an idea about how it works.

Jekyll also offers powerful support for code snippets:

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
{% endhighlight %}

{% highlight python %}
def print_hi(name):
  print "Hi",name
{% endhighlight %}

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: http://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/



# Markdown Introduction 
webpage original is from [here](http://support.mashery.com/docs/customizing_your_portal/Markdown_Cheat_Sheet/ "show txt"). 

## Level 2 Header (H2)
##### Level 5 Header (H5)

one or more consecutive lines of text separated by one or more blank lines. one or more consecutive lines of text separated by one or more blank lines.

This is another paragraph.

I am a sentence with  
a line break.


* Red
* Green
* Blue

+ Red
+ Green
+ Blue

- Red
- Green
- Blue

1. Bird
2. McHale
3. Parish

Term
: Definition

Multiple definitions

Apple
: Pomaceous fruit of plants of the genus Malus.
: An american computer company.

Term 1
Term 2
: Definition

I am *emphasized* and I am **bold**

This is [an example](http://example.com/ "Optional Title") inline link.

[id]: http://example.com/ "Optional Title Here"
This is [an example][id] reference-method link.

<http://example.com/> <address@example.com>

This is a normal paragraph.

         This is a code block


| First Header  | Second Header |
| ------------- | ------------- |
| Row1 Cell1    | Row1 Cell2    |
| Row2 Cell1    | Row2 Cell2    |



# Test Markdwon Table 

Left align|Right align|Center align|
:---------|----------:|:----------:|
This|This|This|
column|column|column|
will|will|will|
be|be|be|
left|right|center|
aligned|aligned|aligned|



\\
\`
\*
\_
\{\}
\[\]
\(\)
\#
\+
\-
\.
\!
\:
\|

{{ page.date | date_to_string }}
