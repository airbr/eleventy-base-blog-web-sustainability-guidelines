---
pagination:
    data: guidelines.category[1].guidelines
    size: 1
    alias: guide
    addAllPagesToCollections: true
permalink: "guidelines/{{ guide.guideline | slugify }}/"
date: ""
eleventyComputed:
  title: "{{ guide.guideline }}"
  tags: 
    - posts
    - "effort-{{ guide.effort | slugify }}"
    - "impact-{{ guide.impact | slugify }}"
---

#### {{ guide.description }}


### Example: 
  {{ guide.example[0].content }}
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

## GRI 
<details>
  <summary>Global Reporting Initiative</summary>
  {% for name, item in guide.GRI[0] %}
  * {{ name[0].toUpperCase() }}{{ name.slice(1) }}: {{ item }}
  {% endfor %}
</details>

## Resources

{% for name, item in guide.resources[0] %}
  * [{{ name }}]({{ item }})
</details>
{% endfor %}


## Topics

{% for item in guide.tags %}
  * {{ item }}
{% endfor %}