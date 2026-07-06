---
title: "Integrantes"
permalink: /integrantes/
classes: wide
lang: es
page_id: integrantes
---

Esta sección reúne a quienes participan del Grupo Sintáctico. Puede incluir estudiantes, docentes, graduados/as o personas invitadas. Hacé clic en un nombre para ver su ficha.

## Coordinación

| Foto | Nombre | Rol | Contacto |
|---|---|---|---|
{%- for m in site.data.members.coordinators %}
| <img class="gs-member-photo" src="{{ m.photo | relative_url }}" alt="Foto de {{ m.name }}" width="44" height="44"> | <a class="gs-member-name" href="#ficha-{{ m.id }}">{{ m.name }}</a> | {{ m.role.es }} | [{{ m.email }}](mailto:{{ m.email }}) |
{%- endfor %}

## Participantes

| Foto | Nombre | Carrera / pertenencia | Intereses |
|---|---|---|---|
{%- for m in site.data.members.participants %}
| <img class="gs-member-photo" src="{{ m.photo | relative_url }}" alt="Foto pendiente" width="44" height="44"> | <a class="gs-member-name" href="#ficha-{{ m.id }}">{{ m.name.es }}</a> | {{ m.program.es }} | {{ m.interests.es }} |
{%- endfor %}

## Invitados/as

| Foto | Nombre | Pertenencia | Tema |
|---|---|---|---|
{%- for m in site.data.members.guests %}
| <img class="gs-member-photo" src="{{ m.photo | relative_url }}" alt="Foto pendiente" width="44" height="44"> | <a class="gs-member-name" href="#ficha-{{ m.id }}">{{ m.name.es }}</a> | {{ m.affiliation.es }} | {{ m.topic.es }} |
{%- endfor %}

{% for m in site.data.members.coordinators %}
<div id="ficha-{{ m.id }}" class="gs-member-modal">
  <a href="#" class="gs-member-modal__backdrop" aria-label="Cerrar ficha"></a>
  <div class="gs-member-modal__card" role="dialog" aria-modal="true">
    <a href="#" class="gs-member-modal__close" aria-label="Cerrar">&times;</a>
    <img class="gs-member-modal__photo" src="{{ m.photo | relative_url }}" alt="Foto de {{ m.name }}">
    <h3>{{ m.name }}</h3>
    <p class="gs-member-modal__role">{{ m.role.es }}</p>
    <p class="gs-member-modal__field"><strong>Contacto:</strong> <a href="mailto:{{ m.email }}">{{ m.email }}</a></p>
  </div>
</div>
{% endfor %}

{% for m in site.data.members.participants %}
<div id="ficha-{{ m.id }}" class="gs-member-modal">
  <a href="#" class="gs-member-modal__backdrop" aria-label="Cerrar ficha"></a>
  <div class="gs-member-modal__card" role="dialog" aria-modal="true">
    <a href="#" class="gs-member-modal__close" aria-label="Cerrar">&times;</a>
    <img class="gs-member-modal__photo" src="{{ m.photo | relative_url }}" alt="Foto pendiente">
    <h3>{{ m.name.es }}</h3>
    <p class="gs-member-modal__field"><strong>Carrera / pertenencia:</strong> {{ m.program.es }}</p>
    <p class="gs-member-modal__field"><strong>Intereses:</strong> {{ m.interests.es }}</p>
  </div>
</div>
{% endfor %}

{% for m in site.data.members.guests %}
<div id="ficha-{{ m.id }}" class="gs-member-modal">
  <a href="#" class="gs-member-modal__backdrop" aria-label="Cerrar ficha"></a>
  <div class="gs-member-modal__card" role="dialog" aria-modal="true">
    <a href="#" class="gs-member-modal__close" aria-label="Cerrar">&times;</a>
    <img class="gs-member-modal__photo" src="{{ m.photo | relative_url }}" alt="Foto pendiente">
    <h3>{{ m.name.es }}</h3>
    <p class="gs-member-modal__field"><strong>Pertenencia:</strong> {{ m.affiliation.es }}</p>
    <p class="gs-member-modal__field"><strong>Tema:</strong> {{ m.topic.es }}</p>
  </div>
</div>
{% endfor %}
