[comment]: <> (---)

[comment]: <> (layout: default)

[comment]: <> (permalink: /blog/)

[comment]: <> (title: blog)

[comment]: <> (nav: true)

[comment]: <> (nav_order: 1)

[comment]: <> (pagination:)

[comment]: <> (  enabled: true)

[comment]: <> (  collection: posts)

[comment]: <> (  permalink: /page/:num/)

[comment]: <> (  per_page: 5)

[comment]: <> (  sort_field: date)

[comment]: <> (  sort_reverse: true)

[comment]: <> (  trail:)

[comment]: <> (    before: 1 # The number of links before the current page)

[comment]: <> (    after: 3 # The number of links after the current page)

[comment]: <> (---)

[comment]: <> (<div class="post">)

[comment]: <> ({% assign blog_name_size = site.blog_name | size %})

[comment]: <> ({% assign blog_description_size = site.blog_description | size %})

[comment]: <> ({% if blog_name_size > 0 or blog_description_size > 0 %})

[comment]: <> (  <div class="header-bar">)

[comment]: <> (    <h1>{{ site.blog_name }}</h1>)

[comment]: <> (    <h2>{{ site.blog_description }}</h2>)

[comment]: <> (  </div>)

[comment]: <> (  {% endif %})

[comment]: <> ({% if site.display_tags and site.display_tags.size > 0 or site.display_categories and site.display_categories.size > 0 %})

[comment]: <> (  <div class="tag-category-list">)

[comment]: <> (    <ul class="p-0 m-0">)

[comment]: <> (      {% for tag in site.display_tags %})

[comment]: <> (        <li>)

[comment]: <> (          <i class="fa-solid fa-hashtag fa-sm"></i> <a href="{{ tag | slugify | prepend: '/blog/tag/' | relative_url }}">{{ tag }}</a>)

[comment]: <> (        </li>)

[comment]: <> (        {% unless forloop.last %})

[comment]: <> (          <p>&bull;</p>)

[comment]: <> (        {% endunless %})

[comment]: <> (      {% endfor %})

[comment]: <> (      {% if site.display_categories.size > 0 and site.display_tags.size > 0 %})

[comment]: <> (        <p>&bull;</p>)

[comment]: <> (      {% endif %})

[comment]: <> (      {% for category in site.display_categories %})

[comment]: <> (        <li>)

[comment]: <> (          <i class="fa-solid fa-tag fa-sm"></i> <a href="{{ category | slugify | prepend: '/blog/category/' | relative_url }}">{{ category }}</a>)

[comment]: <> (        </li>)

[comment]: <> (        {% unless forloop.last %})

[comment]: <> (          <p>&bull;</p>)

[comment]: <> (        {% endunless %})

[comment]: <> (      {% endfor %})

[comment]: <> (    </ul>)

[comment]: <> (  </div>)

[comment]: <> (  {% endif %})

[comment]: <> ({% assign featured_posts = site.posts | where: "featured", "true" %})

[comment]: <> ({% if featured_posts.size > 0 %})

[comment]: <> (<br>)

[comment]: <> (<div class="container featured-posts">)

[comment]: <> ({% assign is_even = featured_posts.size | modulo: 2 %})

[comment]: <> (<div class="row row-cols-{% if featured_posts.size <= 2 or is_even == 0 %}2{% else %}3{% endif %}">)

[comment]: <> ({% for post in featured_posts %})

[comment]: <> (<div class="col mb-4">)

[comment]: <> (<a href="{{ post.url | relative_url }}">)

[comment]: <> (<div class="card hoverable">)

[comment]: <> (<div class="row g-0">)

[comment]: <> (<div class="col-md-12">)

[comment]: <> (<div class="card-body">)

[comment]: <> (<div class="float-right">)

[comment]: <> (<i class="fa-solid fa-thumbtack fa-xs"></i>)

[comment]: <> (</div>)

[comment]: <> (<h3 class="card-title text-lowercase">{{ post.title }}</h3>)

[comment]: <> (<p class="card-text">{{ post.description }}</p>)

[comment]: <> (                    {% if post.external_source == blank %})

[comment]: <> (                      {% assign read_time = post.content | number_of_words | divided_by: 180 | plus: 1 %})

[comment]: <> (                    {% else %})

[comment]: <> (                      {% assign read_time = post.feed_content | strip_html | number_of_words | divided_by: 180 | plus: 1 %})

[comment]: <> (                    {% endif %})

[comment]: <> (                    {% assign year = post.date | date: "%Y" %})

[comment]: <> (                    <p class="post-meta">)

[comment]: <> (                      {{ read_time }} min read &nbsp; &middot; &nbsp;)

[comment]: <> (                      <a href="{{ year | prepend: '/blog/' | prepend: site.baseurl}}">)

[comment]: <> (                        <i class="fa-solid fa-calendar fa-sm"></i> {{ year }} </a>)

[comment]: <> (                    </p>)

[comment]: <> (                  </div>)

[comment]: <> (                </div>)

[comment]: <> (              </div>)

[comment]: <> (            </div>)

[comment]: <> (          </a>)

[comment]: <> (        </div>)

[comment]: <> (      {% endfor %})

[comment]: <> (      </div>)

[comment]: <> (    </div>)

[comment]: <> (    <hr>)

[comment]: <> ({% endif %})

[comment]: <> (  <ul class="post-list">)

[comment]: <> (    {% if page.pagination.enabled %})

[comment]: <> (      {% assign postlist = paginator.posts %})

[comment]: <> (    {% else %})

[comment]: <> (      {% assign postlist = site.posts %})

[comment]: <> (    {% endif %})

[comment]: <> (    {% for post in postlist %})

[comment]: <> (    {% if post.external_source == blank %})

[comment]: <> (      {% assign read_time = post.content | number_of_words | divided_by: 180 | plus: 1 %})

[comment]: <> (    {% else %})

[comment]: <> (      {% assign read_time = post.feed_content | strip_html | number_of_words | divided_by: 180 | plus: 1 %})

[comment]: <> (    {% endif %})

[comment]: <> (    {% assign year = post.date | date: "%Y" %})

[comment]: <> (    {% assign tags = post.tags | join: "" %})

[comment]: <> (    {% assign categories = post.categories | join: "" %})

[comment]: <> (    <li>)

[comment]: <> ({% if post.thumbnail %})

[comment]: <> (<div class="row">)

[comment]: <> (          <div class="col-sm-9">)

[comment]: <> ({% endif %})

[comment]: <> (        <h3>)

[comment]: <> (        {% if post.redirect == blank %})

[comment]: <> (          <a class="post-title" href="{{ post.url | relative_url }}">{{ post.title }}</a>)

[comment]: <> (        {% elsif post.redirect contains '://' %})

[comment]: <> (          <a class="post-title" href="{{ post.redirect }}" target="_blank">{{ post.title }}</a>)

[comment]: <> (          <svg width="2rem" height="2rem" viewBox="0 0 40 40" xmlns="http://www.w3.org/2000/svg">)

[comment]: <> (            <path d="M17 13.5v6H5v-12h6m3-3h6v6m0-6-9 9" class="icon_svg-stroke" stroke="#999" stroke-width="1.5" fill="none" fill-rule="evenodd" stroke-linecap="round" stroke-linejoin="round"></path>)

[comment]: <> (          </svg>)

[comment]: <> (        {% else %})

[comment]: <> (          <a class="post-title" href="{{ post.redirect | relative_url }}">{{ post.title }}</a>)

[comment]: <> (        {% endif %})

[comment]: <> (      </h3>)

[comment]: <> (      <p>{{ post.description }}</p>)

[comment]: <> (      <p class="post-meta">)

[comment]: <> (        {{ read_time }} min read &nbsp; &middot; &nbsp;)

[comment]: <> (        {{ post.date | date: '%B %d, %Y' }})

[comment]: <> (        {% if post.external_source %})

[comment]: <> (        &nbsp; &middot; &nbsp; {{ post.external_source }})

[comment]: <> (        {% endif %})

[comment]: <> (      </p>)

[comment]: <> (      <p class="post-tags">)

[comment]: <> (        <a href="{{ year | prepend: '/blog/' | prepend: site.baseurl}}">)

[comment]: <> (          <i class="fa-solid fa-calendar fa-sm"></i> {{ year }} </a>)

[comment]: <> (          {% if tags != "" %})

[comment]: <> (          &nbsp; &middot; &nbsp;)

[comment]: <> (            {% for tag in post.tags %})

[comment]: <> (            <a href="{{ tag | slugify | prepend: '/blog/tag/' | prepend: site.baseurl}}">)

[comment]: <> (              <i class="fa-solid fa-hashtag fa-sm"></i> {{ tag }}</a>)

[comment]: <> (              {% unless forloop.last %})

[comment]: <> (                &nbsp;)

[comment]: <> (              {% endunless %})

[comment]: <> (              {% endfor %})

[comment]: <> (          {% endif %})

[comment]: <> (          {% if categories != "" %})

[comment]: <> (          &nbsp; &middot; &nbsp;)

[comment]: <> (            {% for category in post.categories %})

[comment]: <> (            <a href="{{ category | slugify | prepend: '/blog/category/' | prepend: site.baseurl}}">)

[comment]: <> (              <i class="fa-solid fa-tag fa-sm"></i> {{ category }}</a>)

[comment]: <> (              {% unless forloop.last %})

[comment]: <> (                &nbsp;)

[comment]: <> (              {% endunless %})

[comment]: <> (              {% endfor %})

[comment]: <> (          {% endif %})

[comment]: <> (    </p>)

[comment]: <> ({% if post.thumbnail %})

[comment]: <> (</div>)

[comment]: <> (  <div class="col-sm-3">)

[comment]: <> (    <img class="card-img" src="{{ post.thumbnail | relative_url }}" style="object-fit: cover; height: 90%" alt="image">)

[comment]: <> (  </div>)

[comment]: <> (</div>)

[comment]: <> ({% endif %})

[comment]: <> (    </li>)

[comment]: <> (    {% endfor %})

[comment]: <> (  </ul>)

[comment]: <> ({% if page.pagination.enabled %})

[comment]: <> ({% include pagination.liquid %})

[comment]: <> ({% endif %})

[comment]: <> (</div>)
