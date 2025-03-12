---
layout: default
title: Words
permalink: /words/
---
<main class="words">
    <p>
        I'm doing a thing here you should absolutely never do. I'm using significant figures with years instead of writing e.g. "1730s" or "late 14th century", so that they sort in an aesthetically pleasing way. Very, very loosely speaking:
        <ul>
            <li>dates more than 250 years old are accurate to within 10 years</li>
            <li>dates more than 500 years old are accurate to within 30 years</li>
            <li>dates more than 1000 years old are accurate to within 100 years</li>
            <li>dates more than 2000 years old are accurate to within 1000 years</li>
            <li>dates labeled "-3000" could actually be any time before 3000 BCE, we can't really narrow it down any more than that with current methods</li>
        </ul>
    </p>
    <h1 class="page-heading">Index of all words</h1>
    <ol>
        {% assign sortedPosts = site.categories.etym | sort: "origin" %}
        {%- for post in sortedPosts -%}
        <li>
            <a href="{{ post.url | relative_url }}">{{ post.title | escape }}</a>
            ({{ post.origin }})
        </li>
        {%- endfor -%}
    </ol>
</main>
