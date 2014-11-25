---
layout: post
title: GitHub Pages
author: Katja
categories:
- github
- jekyll
---
This is where we are going to document what we do at each meeting. Everybody who gives a presentation can contribute to this site.

\[edit 28 January 2014\]

### How to add posts

Posts are published by pushing a markdown file to the \_posts directory in our [GitHub Pages repository](https://github.com/CodeHubOrg/codehuborg.github.io).

Once you have access to the repo, you could create the file directly in the web interface, or you clone the repo to your machine. 

{% highlight bash %}
    
  $ git clone https://github.com/CodeHubOrg/codehuborg.github.io.git
    
{% endhighlight %}
    
If you have [jekyll](http://jekyllrb.com) installed, you can run a copy of this site locally. 

{% highlight bash %}
        
  $ cd codehuborg.github.io/
  $ jekyll serve --watch
    
{% endhighlight %} 
You can then view the site in your browser at http://localhost:4000.

Create a new file in the \_posts directory, for example by copying the one for this post. You need to name the file in the YYYY-MM-DD-title.md format. In the file, you can set the title and categories of the posts at the top. Keep the layout set to \'post\'. 

For example this post has in its [front matter](http://jekyllrb.com/docs/frontmatter/): 
{% highlight bash %}
  ---
  layout: post
  title: GitHub Pages
  categories:
  - github
  - jekyll
  --- 
{% endhighlight %}

For writing the post, you can use Markdown or HTML. Also, Github Pages uses [Pygments](http://pygments.org/), and it is enabled for this site. That means when you want to highlight code, you can use a syntax like the following, taking PHP as an example.

<div class="highlight">
  {<span style="color:#222">'</span>% highlight php %}
  <pre>
    &lt;?php  
    $html = 'This statement is ';  
    //I love ternary operators
    $html .= ($number_of_people &gt; 30)? 'right' : 'wrong';  
    echo $html;  
    ?&gt;
</pre>
  {<span style="color:#222">'</span>% endhighlight %}
</div>

It will look on the site like this: 
  {% highlight php %}
    <?php  
    $html = 'This statement is ';  
    //I love ternary operators
    $html .= ($number_of_people > 30)? 'right' : 'wrong';  
    echo $html;  
    ?>{% endhighlight %}
Once you have written your post, push it to the repository on GitHub. - If you have run the site locally, don\'t forget to list the \_site directory in your .gitignore file. 

Some useful resources if you are not familiar with Git and GitHub: 
- [http://opentechschool.github.io/social-coding/](http://opentechschool.github.io/social-coding/)
- [http://opentechschool.github.io/github-from-scratch/](http://opentechschool.github.io/github-from-scratch/)
- [http://sixrevisions.com/web-development/git-tips/](http://sixrevisions.com/web-development/git-tips/)
<p>&nbsp;</p>
If you haven\'t used Markdown before: [http://daringfireball.net/projects/markdown/basics](http://daringfireball.net/projects/markdown/basics)
    






