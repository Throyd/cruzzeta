                <section class="uk-margin-bottom">
                    <h4 id="gears">Equipo</h4>
                    <div uk-filter="target: .js-filter">
                        <div class="uk-grid-small uk-grid-divider uk-child-width-auto" uk-grid>
                            <div>
                                <ul class="uk-subnav uk-subnav-pill" uk-margin>
                                    <li class="uk-active" uk-filter-control><a href="#">Todos</a></li>
                                </ul>
                            </div>
                            <div>
                                <ul class="uk-subnav uk-subnav-pill uk-margin-small">
                                    <li uk-filter-control="filter: [data-slot='head']; group: data-slot"><a href="#">Cabeza</a></li>
                                    <li uk-filter-control="filter: [data-slot='chest']; group: data-slot"><a href="#">Pecho</a></li>
                                    <li uk-filter-control="filter: [data-slot='legs']; group: data-slot"><a href="#">Piernas</a></li>
                                </ul>
                            </div>
                        </div>
                        <div class="uk-grid-small uk-grid-divider uk-child-width-auto" uk-grid>    
                            <div>
                                <ul class="uk-subnav uk-subnav-pill" uk-margin>
                                    {% for set in sets %}
                                        <li uk-filter-control="filter: [data-set='{{set}}']; group: data-set"><a href="#">{{set}}</a></li>
                                    {% endfor %}
                                </ul>
                            </div>
                        </div>
                        <ul class="js-filter uk-grid-small" uk-grid uk-scrollspy="cls: uk-animation-fade; target: .uk-card; delay: 500; repeat: false">
                            {% for gear in gears %}
                            <li class="uk-width-1-3@m" data-slot="{{gear.slot}}" data-set="{{gear.set}}">
                            {% assign gear-id = gear-id | plus: 1 %}
                                <div class="uk-card uk-card-default" uk-toggle="target: #gear-{{gear-id}}-body">
                                    <div class="uk-grid uk-padding-remove uk-grid-match">
                                        <div class="uk-width-3-4" style="height: 110px">
                                            <p class="uk-margin-remove uk-padding-small">
                                                <strong>{{gear.name}}</strong>
                                            </p>
                                        </div>
                                        <div class="uk-width-1-4 uk-card-media-right uk-cover-container">
                                                    <img src="{{gear.icon}}" uk-tooltip="{{gear.name}}" uk-cover>
                                            </div>
                                        </div> 
                                        <div id="gear-{{gear-id}}-body" class="uk-card-body  uk-padding-remove" hidden>
                                            <p class="uk-padding-small">
                                                {{gear.description}}
                                            </p>
                                            <p class="uk-padding-small">
                                                <strong>Adquisición:</strong> {{gear.adquisition}}
                                            </p>
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
                                                                {% for material-id in baked-materials limit:1 %}
                                                                    {% assign materials = site.articles | where_exp: "item", "item.material-id == material-id" %} 
                                                                    {% for material in materials %}
                                                                        <img src="{{material.icon}}" alt="{{material.name}}" height="18" width="18" uk-tooltip="{{material.name}}">
                                                                        x
                                                                    {% endfor %}
                                                                {% endfor %}  
                                                                {% for quantity in baked-materials limit:1 offset: 1 %}
                                                                    {{quantity}} <br />
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
                                                            {% assign crude-materials = gear.materials-level-2  | split: ", "%}
                                                            {% for crude-material in crude-materials %}
                                                            {% assign baked-materials = crude-material | split: " x "%}
                                                                {% for material-id in baked-materials limit:1 %}
                                                                    {% assign materials = site.articles | where_exp: "item", "item.material-id == material-id" %} 
                                                                    {% for material in materials %}
                                                                        <img src="{{material.icon}}" alt="{{material.name}}" height="18" width="18" uk-tooltip="{{material.name}}">
                                                                        x
                                                                    {% endfor %}
                                                                {% endfor %}  
                                                                {% for quantity in baked-materials limit:1 offset: 1 %}
                                                                    {{quantity}} <br />
                                                                {% endfor %}  
                                                            {% endfor %}    
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
                                                            {% assign crude-materials = gear.materials-level-3  | split: ", "%}
                                                            {% for crude-material in crude-materials %}
                                                            {% assign baked-materials = crude-material | split: " x "%}
                                                                {% for material-id in baked-materials limit:1 %}
                                                                    {% assign materials = site.articles | where_exp: "item", "item.material-id == material-id" %} 
                                                                    {% for material in materials %}
                                                                        <img src="{{material.icon}}" alt="{{material.name}}" height="18" width="18" uk-tooltip="{{material.name}}">
                                                                        x
                                                                    {% endfor %}
                                                                {% endfor %}  
                                                                {% for quantity in baked-materials limit:1 offset: 1 %}
                                                                    {{quantity}} <br />
                                                                {% endfor %}  
                                                            {% endfor %}    
                                                        </td>
                                                    </tr>                                           
                                                </tbody>
                                            </table>
                                        </div>
                                    </div>
                            </li>
                            {% endfor %}
                        </ul>
                    </div>
                </section>