---
game-id: id: TLOZ-TOTK
title: Página principal de la guía
type: guide
navigation: main-page
---
Esto es la guía

<div class="uk-grid">
<div class="uk-width-3-4@m uk-card uk-card-default uk-card-body uk-text-center">GUIDE</div>
<div class="uk-width-1-4@m uk-card uk-card-default uk-card-body uk-text-center uk-position-z-index" uk-sticky="end: !.uk-height-large; offset: 80">Stick to the top</div>
</div>

{% assign tips = site.articles | find_exp:"item", "item.game-id == page.game-id" | "item.type == guide" | "item.navigation == tip" %}
{% assign tips = site.articles | find_exp:"item", "item.game-id == page.game-id" | "item.type == guide" | "item.navigation == mission" %}
{% assign tips = site.articles | find_exp:"item", "item.game-id == page.game-id" | "item.type == guide" | "item.navigation == sanctuary" %}
{% assign tips = site.articles | find_exp:"item", "item.game-id == page.game-id" | "item.type == guide" | "item.navigation == temple" %}
{% assign tips = site.articles | find_exp:"item", "item.game-id == page.game-id" | "item.type == guide" | "item.navigation == gear" %}

<h4>Consejos</h4>
<h4>Misiones</h4>
<h4>Santuarios</h4>
<h4>Templos</h4>
<h4>Equipo</h4>
