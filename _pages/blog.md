---
layout: page
permalink: /blog/
title: blog
nav: true
nav_order: 2
years: [2026]
posts:
  - title: "PoLoRA: a preconditioned orthogonalized LoRA optimizer"
    year: 2026
    url: /polora/
    preview: polora_rank.png
---

<div class="publications blog-list">
{% for y in page.years %}
  <div class="year-section">
    <div class="year"><strong>{{ y }}</strong></div>
    <div class="year-papers">
      <ol class="bibliography">
      {%- for post in page.posts %}{% if post.year != y %}{% continue %}{% endif %}
        {%- if post.url contains '://' -%}
          {%- assign post_href = post.url -%}
        {%- else -%}
          {%- assign post_href = post.url | relative_url -%}
        {%- endif -%}
        <li>
          <div class="row align-items-center">
            <div class="col-sm-3 preview">
              {%- if post.preview -%}
              <a href="{{ post_href }}" target="_self">
                {%- if post.preview contains '://' -%}
                <img class="preview z-depth-1 rounded" src="{{ post.preview }}" alt="{{ post.title }} preview">
                {%- else -%}
                <img class="preview z-depth-1 rounded" src="{{ post.preview | prepend: '/assets/img/publication_preview/' | relative_url }}" alt="{{ post.title }} preview">
                {%- endif -%}
              </a>
              {%- endif -%}
            </div>
            <div class="col-sm-9">
              <div class="title"><a href="{{ post_href }}" target="_self">{{ post.title }}</a></div>
            </div>
          </div>
        </li>
      {%- endfor %}
      </ol>
    </div>
  </div>
{% endfor %}
</div>
