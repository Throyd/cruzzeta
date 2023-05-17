---
game-id: TLOZ-TOTK
name: Página principal de la guía
type: guide
category: main
---
{% assign guides-game-not-filtered = site.articles | where_exp: "item", "item.game-id == page.game-id" %}
{% assign guides-type-not-filtered = guides-game-not-filtered | where_exp: "item", "item.type == 'guide'" %}
{% assign tips = guides-type-not-filtered | where_exp: "item", "item.category == 'tips'" %}
{% assign quests = guides-type-not-filtered | where_exp: "item", "item.category == 'quests'" %}
{% assign sanctuaries = guides-type-not-filtered | where_exp: "item", "item.category == 'sanctuaries'" %}
{% assign temples = guides-type-not-filtered | where_exp: "item", "item.category == 'temples'" %}
{% assign gears = guides-type-not-filtered | where_exp: "item", "item.category == 'gears'" %}
{% assign sets = gears | map: 'set' | uniq %}
{% assign gear-id = 0 %}
{% include totk_guide_main.html %}