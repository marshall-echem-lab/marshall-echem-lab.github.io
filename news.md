---
title: news
permalink: /news/
---

### **News from the lab**

<div class="content list">
  {% assign news_posts = site.posts | where_exp: "post", "post.categories contains 'news'" | sort: "date" | reverse %}
  {% for post in news_posts %}
    <div class="list-item">
      <p class="list-post-title">
        <a href="{{ post.url | prepend: site.baseurl }}">
            <div class="row">
                <div class="col-sm-4">
                    <img src="/{% if post.header-img %}{{ post.header-img }}{% else %}{{ site.header-img }}{% endif %}">
                </div>
                <div class="col-sm-8">
                    <h3 class="post-title">
                        {{ post.title }}
                    </h3>
                    <p class="list-post-title">
                      posted on {{ post.date | date: "%B %-d, %Y" }}
                    </p>
                    <p class="list-detail">
                      {{ post.content | strip_html | truncatewords: 30 }}
                    </p>
                </div>
            </div>
            <hr/>
        </a>
      </p>
    </div>
  {% endfor %}
</div>
