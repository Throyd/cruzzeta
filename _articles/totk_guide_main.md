---
game-id: TLOZ-TOTK
title: Página principal de la guía
type: guide
category: main-page
---
Esto es la guía
<div class="uk-grid">
<div class="uk-width-3-4@m uk-card uk-card-default uk-card-body uk-text-center">
{% assign tips = site.articles | find_exp:"item", "item.game-id == page.game-id" | "item.type == guide" | "item.category == tip" %}
{% assign tips = site.articles | find_exp:"item", "item.game-id == page.game-id" | "item.type == guide" | "item.category == mission" %}
{% assign tips = site.articles | find_exp:"item", "item.game-id == page.game-id" | "item.type == guide" | "item.category == sanctuary" %}
{% assign tips = site.articles | find_exp:"item", "item.game-id == page.game-id" | "item.type == guide" | "item.category == temple" %}
{% assign tips = site.articles | find_exp:"item", "item.game-id == page.game-id" | "item.type == guide" | "item.category == gear" %}

<h4 id="tips">Consejos</h4>
<h4 id="quests">Misiones</h4>
<h4 id="sanctuaries">Santuarios</h4>
<h4 id="templeS">Templos</h4>
<h4 id="gears">Equipo</h4>
asd
as
das
d
sad
as
d
asd
sa
ds
ad
sa
d
ad
a
d
sa
ds
ad
as
da
d
sad
sa
ds
ad
a
d
sad
sa
dsa
d
sa
dsa
ds
ad
sa
d
sad
sa
ds
ad
sa
dsad
as
</div>
<div class="uk-width-1-4@m uk-card uk-card-default uk-card-body uk-text-center uk-position-z-index" uk-sticky="end: !.uk-height-large; offset: 80">
    <a href="#tips">Consejos</a>
    <a href="#quests">Misiones</a>
    <a href="#sanctuaries">Santuarios</a>
    <a href="#temples">Templos</a>
    <a href="#gears">Equipo</a></div>
</div>




