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
        <div class="uk-width-3-4">
            <div>
                <h4 id="tips">Consejos</h4>
                <h4 id="quests">Misiones</h4>
                <h4 id="sanctuaries">Santuarios</h4>
                <h4 id="temples">Templos</h4>
                <h4 id="gears">Equipo</h4>
                <div class="uk-grid uk-margin-remove uk-padding-remove">
                    {% for gear in gears %}

                        {% assign gear-id = gear-id | plus: 1 %}
                        <div class="uk-width-1-2 uk-margin-remove uk-padding-remove">
                            <div class="uk-card uk-card-default uk-padding-small uk-margin-remove" uk-toggle="target: #gear-{{gear-id}}-body">
                                <div>
                                    <div class="uk-width-2-4 uk-match">
                                        <p class="uk-margin-remove-bottom">
                                            <strong>{{gear.name}}</strong>
                                        </p>
                                    </div>
                                    <div class="uk-width-1-4">
                                        <div class="uk-flex-last@s uk-card-media-right uk-cover-container">
                                            <img src="{{gear.icon}}" uk-cover>
                                        </div>
                                    </div>
                                </div> 
                                <div id="gear-{{gear-id}}-body" class="uk-card-body uk-muted uk-padding-small" hidden>

                                    <p>{{gear.description}}</p>
                                    
                                    <table class="uk-table uk-table-middle uk-table-divider">
                                        <thead>
                                            <tr>
                                                <th class="uk-width-small">Nivel</th>
                                                <th>Estadísticas</th>
                                                <th>Materiales</th>
                                            </tr>
                                        </thead>
                                        <tbody>
                                            <tr>
                                                <td></td>
                                                <td>{{stats-level-0:}}</td>
                                                <td>{{material.stats-level-0}}</td>
                                            </tr>
                                            <tr>
                                                <td>
                                                    <img src="https://github.com/Throyd/cruzzeta/blob/main/_images/tloz-totk/UI_Key_Item_Icon.png?raw=true" width:"16">
                                                    <img src="https://github.com/Throyd/cruzzeta/blob/main/_images/tloz-totk/UI_Key_Item_Icon.png?raw=true" width:"16">
                                                    
                                                </td>
                                                <td>
                                                <img src="https://github.com/Throyd/cruzzeta/blob/main/_images/tloz-totk/UI_Armor_Icon.png?raw=true" width:"16">  {{gear.stats-level-1}}
                                                </td>
                                                <td>
                                                    {{material.stats-level-1}}
                                                </td>
                                            </tr>
                                        </tbody>
                                    </table>

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






