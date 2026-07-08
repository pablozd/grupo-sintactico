---
title: "Members"
permalink: /integrantes/
classes: wide
lang: en
page_id: integrantes
---

This section brings together those who take part in Grupo Sintáctico. It may include students, faculty, graduates, or guests. Click a name to see their profile.

## Coordination

| Photo | Name | Role | Contact |
|---|---|---|---|
{%- for m in site.data.members.coordinators %}
| <img class="gs-member-photo" src="{{ m.photo | relative_url }}" alt="Photo of {{ m.name }}" width="44" height="44"> | <label class="gs-member-name" for="toggle-{{ m.id }}">{{ m.name }}</label> | {{ m.role.en }} | [{{ m.email }}](mailto:{{ m.email }}) |
{%- endfor %}

## Members

<div class="gs-participants-table" markdown="1">

| Photo | Name | Program / affiliation | Level | Interests | Contact |
|---|---|---|---|---|---|
{%- for m in site.data.members.participants %}
| <img class="gs-member-photo" src="{{ m.photo | relative_url }}" alt="{% if m.photo contains 'placeholder' %}Photo pending{% else %}Photo of {{ m.name.en }}{% endif %}" width="44" height="44"> | <label class="gs-member-name" for="toggle-{{ m.id }}">{{ m.name.en }}</label> | {{ m.program.en }} | {{ m.level.en }} | {{ m.interests.en }} | {% if m.email %}[{{ m.email }}](mailto:{{ m.email }}){% else %}TBD{% endif %} |
{%- endfor %}

</div>

## Guests

| Photo | Name | Affiliation | Topic |
|---|---|---|---|
{%- for m in site.data.members.guests %}
| <img class="gs-member-photo" src="{{ m.photo | relative_url }}" alt="Photo pending" width="44" height="44"> | <label class="gs-member-name" for="toggle-{{ m.id }}">{{ m.name.en }}</label> | {{ m.affiliation.en }} | {{ m.topic.en }} |
{%- endfor %}

{% for m in site.data.members.coordinators %}
<div class="gs-member-modal-wrapper">
<input type="checkbox" id="toggle-{{ m.id }}" class="gs-member-toggle">
<div class="gs-member-modal">
  <label for="toggle-{{ m.id }}" class="gs-member-modal__backdrop" aria-label="Close profile"></label>
  <div class="gs-member-modal__card" role="dialog" aria-modal="true">
    <label for="toggle-{{ m.id }}" class="gs-member-modal__close" aria-label="Close">&times;</label>
    <img class="gs-member-modal__photo" src="{{ m.photo | relative_url }}" alt="Photo of {{ m.name }}">
    <h3>{{ m.name }}</h3>
    <p class="gs-member-modal__role">{{ m.role.en }}</p>
    <p class="gs-member-modal__field"><strong>Contact:</strong> <a href="mailto:{{ m.email }}">{{ m.email }}</a></p>
  </div>
</div>
</div>
{% endfor %}

{% for m in site.data.members.participants %}
<div class="gs-member-modal-wrapper">
<input type="checkbox" id="toggle-{{ m.id }}" class="gs-member-toggle">
<div class="gs-member-modal">
  <label for="toggle-{{ m.id }}" class="gs-member-modal__backdrop" aria-label="Close profile"></label>
  <div class="gs-member-modal__card" role="dialog" aria-modal="true">
    <label for="toggle-{{ m.id }}" class="gs-member-modal__close" aria-label="Close">&times;</label>
    <img class="gs-member-modal__photo" src="{{ m.photo | relative_url }}" alt="{% if m.photo contains 'placeholder' %}Photo pending{% else %}Photo of {{ m.name.en }}{% endif %}">
    <h3>{{ m.name.en }}</h3>
    <p class="gs-member-modal__field"><strong>Program / affiliation:</strong> {{ m.program.en }}</p>
    <p class="gs-member-modal__field"><strong>Level:</strong> {{ m.level.en }}</p>
    <p class="gs-member-modal__field"><strong>Interests:</strong> {{ m.interests.en }}</p>
    {% if m.email %}<p class="gs-member-modal__field"><strong>Contact:</strong> <a href="mailto:{{ m.email }}">{{ m.email }}</a></p>{% endif %}
  </div>
</div>
</div>
{% endfor %}

{% for m in site.data.members.guests %}
<div class="gs-member-modal-wrapper">
<input type="checkbox" id="toggle-{{ m.id }}" class="gs-member-toggle">
<div class="gs-member-modal">
  <label for="toggle-{{ m.id }}" class="gs-member-modal__backdrop" aria-label="Close profile"></label>
  <div class="gs-member-modal__card" role="dialog" aria-modal="true">
    <label for="toggle-{{ m.id }}" class="gs-member-modal__close" aria-label="Close">&times;</label>
    <img class="gs-member-modal__photo" src="{{ m.photo | relative_url }}" alt="Photo pending">
    <h3>{{ m.name.en }}</h3>
    <p class="gs-member-modal__field"><strong>Affiliation:</strong> {{ m.affiliation.en }}</p>
    <p class="gs-member-modal__field"><strong>Topic:</strong> {{ m.topic.en }}</p>
  </div>
</div>
</div>
{% endfor %}
