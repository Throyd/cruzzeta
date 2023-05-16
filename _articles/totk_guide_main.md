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


guides-game-not-filtered <br/>
<ul>
{% for guide1 in guides-game-not-filtered %}
<li>{{guide.name}}</li>
{% endfor %}
</ul


guides-type-not-filtered <br/>
<ul>
{% for guide2 in guides-type-not-filtered %}
<li>{{guide.name}}</li>
{% endfor %}
</ul>


TIPS <br/>
<ul>
{% for tip in tips %}
<li>{{tip.name}}</li>
{% endfor %}
</ul>

GEARS <br/>
<ul>
{% for gear in gears %}
<li>{{gear.name}}</li>
{% endfor %}
</ul>


<div>

    <div class="uk-grid">
        <div class="uk-width-3-4">
            <div>
                <h4 id="tips">Consejos</h4>
                <h4 id="quests">Misiones</h4>
                <h4 id="sanctuaries">Santuarios</h4>
                <h4 id="temples">Templos</h4>
                <h4 id="gears">Equipo</h4>
                <div class="uk-grid uk-margin-remove uk-padding-remove">
                    {% for gear in gears %}
                        {% assign gear-id = gear-id + 1 %}
                        <div class="uk-width-1-2">
                            <div class="uk-card uk-card-default" uk-toggle="target: #toggle-usage>
                                <div class="uk-card-header">
                                    <h3 class="uk-card-header">
                                    {{gear.title}}
                                    </h3>
                                </div> 
                                <div id="gear-{{gear-id}}-body" class="uk-card-body">
                                    {{gear.content}}
                                </div>
                            </div>
                       </div>
                    {% endfor %}
                </div>
            </div>
        </div>
        <div class="uk-width-1-4">
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






