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
        <div class="uk-width-3-4@m">
            <div>
                <h4 id="tips">Consejos</h4>
                <h4 id="quests">Misiones</h4>
                <h4 id="sanctuaries">Santuarios</h4>
                <h4 id="temples">Templos</h4>
                <h4 id="gears">Equipo</h4>
                <div class="uk-grid uk-margin-remove uk-padding-remove">
                    {% for gear in gears %}

                        {% assign gear-id = gear-id | plus: 1 %}
                        <div class="uk-width-4-5@m uk-margin-remove uk-padding-remove">
                            <div class="uk-card uk-card-default uk-padding-remove uk-margin-remove" uk-toggle="target: #gear-{{gear-id}}-body">
                                <div class="uk-grid uk-padding-remove">
                                    <div class="uk-width-3-4">
                                        <p class="uk-margin-remove uk-padding-small">
                                            <strong>{{gear.name}}</strong>
                                        </p>
                                    </div>
                                    <div class="uk-width-1-1 uk-card-media-right uk-cover-container">
                                            <img src="{{gear.icon}}">
                                    </div>
                                </div> 
                                <div id="gear-{{gear-id}}-body" class="uk-card-body  uk-padding-remove" hidden>
                                    
                                    <p class="uk-padding-small">
                                        {{gear.description}}
                                    </p>

                                    <strong>Adquisición:</strong> {{gear.adquisition}}
                                    
                                    <table class="uk-table uk-table-divider uk-text-center uk-light uk-padding-small">
                                        <thead class="uk-dark">
                                            <tr>
                                                <th>
                                                    Nivel
                                                </th>
                                                <th>
                                                    Estadísticas
                                                </th>
                                                <th>
                                                    Materiales
                                                </th>
                                            </tr>
                                        </thead>
                                        <tbody>
                                            <tr>
                                                <td class="uk-background-primary">
                                                </td>
                                                <td class="uk-background-primary">
                                                    
                                                    <img src="https://throyd.github.io/cruzzeta/images/tloz-totk/UI_Armor_Icon.png" width="16" height="16">  
                                                    {{gear.stats-level-0:}}
                                                </td>
                                                <td class="uk-background-primary">
                                                    {{gear.material-stats-level-0}}
                                                </td>
                                            </tr>
                                            <tr>
                                                <td class="uk-background-primary">
                                                    <img src="https://throyd.github.io/cruzzeta/images/tloz-totk/UI_Key_Item_Icon.png"  width="16" height="16">
                                                </td>
                                                <td class="uk-background-primary">
                                                    <img src="https://throyd.github.io/cruzzeta/images/tloz-totk/UI_Armor_Icon.png" width="16" height="16">  
                                                    {{gear.stats-level-1}}
                                                </td>
                                                <td class="uk-background-primary">






                                                   {% assign crude-materials = gear.materials-level-1  | split: ", "%}

                                                    {% for crude-material in crude-materials %}
                                                    {% assign baked-materials = crude-material | split: " x "%}
                                                        
                                                        {% for baked-material in baked-materials %}
                                                            {{baked material}}-
                                                        {% endfor %}

                                                        REAL BAKED: <br>
                                                        {% for material in baked-materials limit:1 %}
                                                            {{material}} x
                                                        {% endfor %}  
                                                                                                                                               {% for quantity in baked-materials limit:1 offset: 1 %}
                                                            {{quantity}} x
                                                        {% endfor %}  

                                                        {% endfor %}                                             
                                                


























                                                   
                                                </td>
                                            </tr>
                                            <tr>
                                                <td class="uk-background-primary">
                                                    <img src="https://throyd.github.io/cruzzeta/images/tloz-totk/UI_Key_Item_Icon.png"  width="16" height="16">
                                                    <img src="https://throyd.github.io/cruzzeta/images/tloz-totk/UI_Key_Item_Icon.png"  width="16" height="16">                                                    
                                                </td>
                                                <td class="uk-background-primary">
                                                    <img src="https://throyd.github.io/cruzzeta/images/tloz-totk/UI_Armor_Icon.png" width="16" height="16">  
                                                    {{gear.stats-level-2}}
                                                </td>
                                                <td class="uk-background-primary">
                                                    {{gear.materials-level-2}}
                                                </td>
                                            </tr>
                                            <tr>
                                                <td class="uk-background-primary">
                                                    <img src="https://throyd.github.io/cruzzeta/images/tloz-totk/UI_Key_Item_Icon.png"  width="16" height="16">
                                                    <img src="https://throyd.github.io/cruzzeta/images/tloz-totk/UI_Key_Item_Icon.png"  width="16" height="16">
                                                    <img src="https://throyd.github.io/cruzzeta/images/tloz-totk/UI_Key_Item_Icon.png"  width="16" height="16">
                                                </td>
                                                <td class="uk-background-primary">
                                                    <img src="https://throyd.github.io/cruzzeta/images/tloz-totk/UI_Armor_Icon.png" width="16" height="16">  
                                                    {{gear.stats-level-3}}
                                                </td>
                                                <td class="uk-background-primary">
                                                    {{gear.materials-level-3}}
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