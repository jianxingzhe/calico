---
title: Releases
---

The following table shows component versioning for Calico  **{{ page.version }}**.

Use the version selector at the top-right of this page to view a different release.

{% for release in site.data.versions[page.version] %}
## {{ release.title }}

{% if release.note %}
{{ release.note }}
{% else %}
{% include {{page.version}}/release-notes/{{release.title}}-release-notes.md %}
{% endif %}

| Component              | Version |
|------------------------|---------|{% for component_name in release.components %}
| {{ component_name[0] }}   | [{{ component_name[1].version }}]({{ component_name[1].url }}) |{% endfor %}

{% endfor %}
