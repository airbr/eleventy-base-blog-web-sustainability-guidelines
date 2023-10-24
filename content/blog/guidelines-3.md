---
pagination:
    data: guidelines.category[3].guidelines
    size: 1
    alias: guide
    addAllPagesToCollections: true
permalink: "guidelines/{{ guide.guideline | slugify }}/"
tags: posts
date: ""
eleventyComputed:
  title: "{{ guide.guideline }}"
  tags: 
    - posts
    - "effort-{{ guide.effort | slugify }}"
    - "impact-{{ guide.impact | slugify }}"
---


#### {{ guide.description }}

## Benefits

{% for name, item in guide.benefits[0] %}
  <details>
  <summary>{{ name }}</summary>
  {{ item }}
</details>
{% endfor %}

## Success Criteria

{% for item in guide.criteria %}
  <details>
  <summary>{{ item.title }}</summary>
  {{ item.description }}
</details>
{% endfor %}