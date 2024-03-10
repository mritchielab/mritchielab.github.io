---
layout: page
title: Software
permalink: /software/
---

{% for software in site.software %}
<div class="software-container">
    <h2>
        <img src="/assets/images/software/{{ software.icon }}" class="software-package-icon" alt="{{ software.name }}"/>
        {{ software.name }}
    </h2>
    <p>
        {{ software.description }}
    </p>
    <p>
    </p>
    <p>
        <a href="{{ software.github }}">
            <svg class="svg-icon"><use xlink:href="/assets/minima-social-icons.svg#github"></use></svg>
        Github
        </a>
    </p>
    <p>
        <a href="{{ software.bioconductor }}"><img src="/assets/images/bioc.png" class="software-link-icon"/> Bioconductor</a>
    </p>
    {%- if software.papers -%}
    <h4>Research papers</h4>
    <ul>
        {%- for paper in software.papers -%}
        <li>
            <a href="{{ paper.url }}">{{ paper.name }}</a>
        </li>
        {%- endfor -%}
    </ul>
    {%- endif -%}
</div>
{% endfor %}
