---
game-id: TLOZ-TOTK
name: Página principal de la guía
type: guide
category: main
---
<h3>Página principal de la guía</h3>
{% assign guides-game-not-filtered = site.articles | where_exp: "item", "item.game-id == page.game-id" %}
{% assign guides-type-not-filtered = guides-game-not-filtered | where_exp: "item", "item.type == 'guide'" %}
{% assign tips = guides-type-not-filtered | where_exp: "item", "item.category == 'tips'" %}
{% assign quests = guides-type-not-filtered | where_exp: "item", "item.category == 'quests'" %}
{% assign sanctuaries = guides-type-not-filtered | where_exp: "item", "item.category == 'sanctuaries'" %}
{% assign temples = guides-type-not-filtered | where_exp: "item", "item.category == 'temples'" %}
{% assign gears = guides-type-not-filtered | where_exp: "item", "item.category == 'gears'" %}
{% assign gear-id = 0 %}
<div>
    <div class="uk-grid">
        <div class="uk-width-4-5@m uk-grid-small">
            <div>
                <h4 id="tips">Consejos</h4>
                <h4 id="quests">Misiones</h4>
                <h4 id="sanctuaries">Santuarios</h4>
                <h4 id="temples">Templos</h4>
                <section>
                    <h4 id="gears">Equipo</h4>
                    <div uk-filter="target: .js-filter">
                        <ul class="uk-subnav uk-subnav-pill">
                            <li class="uk-active" uk-filter-control><a href="#">Todos</a></li>
                            <li uk-filter-control="[data='head']"><a href="#">Cabeza</a></li>
                            <li uk-filter-control="[data='chest']"><a href="#">Pecho</a></li>
                            <li uk-filter-control="[data='legs']"><a href="#">Piernas</a></li>
                        </ul>
                        <ul class="js-filter uk-text-center uk-grid-small" uk-grid>
                            {% for gear in gears %}
                            <li data="{{gear.slot}}">
                                <div class="uk-card uk-card-default uk-card-body">{{gear.name}}</div>
                            </li>
                            {% endfor %}
                        </ul>
                    </div>
                </section>
            </div>
        </div>
        <div class="uk-width-1-5@m uk-first@m">
            <div class="uk-card uk-card-default uk-card-body uk-text-center uk-position-z-index" uk-sticky="end: !.uk-height-large; offset: 80">
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
                        <a href="#gears">Equipo</a>
                    </li>
                </ul>
            </div>
        </div>
    </div>
</div>