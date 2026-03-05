# {{title}}
**Citekey:** @{{citekey}}
**Authors:** {{authors}}

---

## 🖍️ Annotations
{% persist "annotations" %}
{% for annotation in annotations -%}

{# Handle Image/Area Highlights #}
{%- if annotation.imageRelativePath %}
![[{{annotation.imageRelativePath}}]]
{%- endif %}

{# Handle Text Highlights #}
{%- if annotation.annotatedText %}
> {{annotation.annotatedText}} [p. {{annotation.pageLabel}}](zotero://open-pdf/library/items/{{annotation.attachment.itemKey}}?page={{annotation.pageLabel}})
{%- endif %}

{%- if annotation.comment %}
**Note:** {{annotation.comment}}
{%- endif %}

{%- if annotation.tags.length > 0 %}
**Tags:** {% for t in annotation.tags %}#{{ (t.tag or t.name) | replace(" ", "-") }} {% endfor %}
{%- endif %}

{% endfor %}
{% endpersist %}
---
## 🏷️ Item Tags
{% if tags.length > 0 -%}
{% for t in tags -%}
#{{t.tag | replace(" ", "-")}} 
{%- endfor %}
{% else -%}
#untagged
{%- endif %}