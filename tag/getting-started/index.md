---
layout: default
current: tag
title: Tag Page
cover: false
class: 'tag-template'
navigation: True
logo: 'assets/images/ghost.png'
---

<!-- default -->
<!-- The tag above means - insert everything in this file into the {body} of the default.hbs template -->

<!-- The big featured header, it uses blog cover image as a BG if available -->
<!-- #tag -->
{% include dynamic_tag_info.html %}
<header class="site-header outer {% if cover or page.cover %}" style="background-image: url({{ site.url }}{% if cover %}{{ cover }}{% else %}{{ page.cover }}{% endif%}) {% else %}no-cover{% endif %}">
    <div class="inner">
        {% include site-nav.html %}
        <div class="site-header-content">
            <h1 class="site-title">{{ page.tag | capitalizeall }}</h1>
            <h2 class="site-description">
                {% if tag_description %}
                    {{ tag_description }}
                {% elsif page.tag %}
    			    A collection of {{ paginator.total_posts }} posts
                {% endif %}
            </h2>
        </div>
    </div>
</header>
<!-- tag -->

<!-- The main content area -->
<main id="site-main" class="site-main outer" role="main">
    <div class="inner">
        <div class="post-feed">
            <!-- The tag below includes the markup for each post - partials/post-card.hbs -->
            {% assign words_per_minute = site.words_per_minute | default: 200 %}

            {% for post in paginator.posts %}
                <article class="post-card {{ page.class }}{% unless post.cover %} no-image{% endunless %}">
                    {% if post.cover %}
                        <a class="post-card-image-link" href="{{ site.url }}/{{ post.url | remove_first: '/' }}">
                            <div class="post-card-image" style="background-image: url({{ site.url }}/{{ post.cover }})"></div>
                        </a>
                    {% endif %}
                    <div class="post-card-content">
                        <a class="post-card-content-link" href="{{ site.url }}/{{ post.url | remove_first: '/' }}">
                            <header class="post-card-header">
                                {% if post.tags.size > 0 %}
                                    {% for tag in post.tags %}
                                        {% if forloop.index == post.tags.size %}
                                            <span class="post-card-tags">{{ tag | capitalize }}</span>
                                        {% else %}
                                        <span class="post-card-tags">{{ tag | capitalize }}</span>
                                        {% endif %}
                                    {% endfor %}
                                {% endif %}

                                <h2 class="post-card-title">{{ post.title }}</h2>
                            </header>
                            <section class="post-card-excerpt">
                                {% if post.excerpt %}
                                    <p>{{ post.excerpt | strip_html | truncatewords: 33, "" }}</p>
                                {% else %}
                                    <p>{{ post.content | strip_html | truncatewords: 33, "" }}</p>
                                {% endif %}
                            </section>
                        </a>
                        <footer class="post-card-meta">
                            {% for author in site.data.authors %}
                                {% if author[1].username == post.author %}
                                    {% if author[1].picture %}
                                    <img class="author-profile-image" src="{{ site.url }}/{{ author[1].picture }}" alt="{{ author[1].name }}" />
                                    {% endif %}
                                    <span class="post-card-author">
                                        <a href="{{ site.url }}/author/{{ post.author }}/">{{ author[1].name }}</a>
                                    </span>
                                {% endif %}
                            {% endfor %}
                            <span class="reading-time">
                                {% assign words = post.content | strip_html | number_of_words %}
                                {% if words <= words_per_minute %}
                                1 min read
                                {% else %}
                                {{ words | divided_by:words_per_minute }} min read
                                {% endif %}
                            </span>
                        </footer>
                    </div>
                </article>
            {% endfor %}
        </div>
    </div>
</main>
