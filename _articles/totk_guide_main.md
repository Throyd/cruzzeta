---
game-id: TLOZ-TOTK
name: Página principal de la guía
type: guide
category: main
---
Esto es la guía
<div class="uk-grid">
<div class="uk-width-3-4@m">
{% assign tips = site.articles | find_exp:"item", "item.game-id == page.game-id" | "item.type == guide" | "item.category == tip" %}
{% assign tips = site.articles | find_exp:"item", "item.game-id == page.game-id" | "item.type == guide" | "item.category == mission" %}
{% assign tips = site.articles | find_exp:"item", "item.game-id == page.game-id" | "item.type == guide" | "item.category == sanctuary" %}
{% assign tips = site.articles | find_exp:"item", "item.game-id == page.game-id" | "item.type == guide" | "item.category == temple" %}
{% assign tips = site.articles | find_exp:"item", "item.game-id == page.game-id" | "item.type == guide" | "item.category == gear" %}

<h4 id="tips">Consejos</h4>
<h4 id="quests">Misiones</h4>
<h4 id="sanctuaries">Santuarios</h4>
<h4 id="temples">Templos</h4>
<h4 id="gears">Equipo</h4>
    a <br/>
    a <br/>
    a <br/>
    a <br/>
    a <br/>
    a <br/>
    a <br/>
    a <br/>
    a <br/>
    a <br/>
    a <br/>
    a <br/>
    a <br/>
    a <br/>
    a <br/>
    v
    a <br/>
    a <br/>
    a <br/>

    a <br/>
    a <br/>
    a <br/>
    a <br/>
    a <br/>
    a <br/>
    a <br/>

    a <br/>
    a <br/>
    a <br/>
    a <br/>
    a <br/>

    a <br/>
    a <br/>
    a <br/>
    a <br/>
    a <br/>
    a <br/>
    a <br/>

    a <br/>
    a <br/>
    a <br/>
    a <br/>
    a <br/>
    a <br/>
    
</div>
<div class="uk-width-1-4@m uk-card uk-card-default uk-card-body uk-text-center uk-position-z-index" uk-sticky="end: !.uk-height-large; offset: 80">
    <ul class="uk-nav-default" uk-nav>
        <li class="uk-active">
            <a href="#tips">Consejos</a>
        </li>
        <li class="uk-active">
            <a href="#quests">Misiones</a>
        </li>
        <li class="uk-active">
            <a href="#sanctuaries">Santuarios</a>
        </li>
        <li class="uk-active">
            <a href="#temples">Templos</a>
        </li>
        <li class="uk-active">
            <a href="#gears">Equipo</a></div>
        </li>
    </ul>
</div>




