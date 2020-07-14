# Installer Bootstrap dans un projet Symfony
## Prérequis
#### Node.js
*Verifier que node est installé*

    node -v

#### npm ou yarn
*Verifier que npm est installé*

    npm -v

*Verifier que yarn est installé*

    yarn --version

## Installation Webpack encore, node-modules et bootstrap css
*dans un terminal, dans le dossier de votre projet*

#### Encore

    composer require symfony/webpack-encore-bundle

#### Node-modules

    npm install

**ou**

    yarn add

### Node-sass et Bootstrap

 #### Node-sass

    npm install node-sass

**ou**

    yarn add node-sass

 #### Bootstrap

    npm install bootstrap --dev

**ou**

    yarn add bootstrap --dev

 #### Node-sass loader

    npm add sass-loader@^8.0.0

**ou**

    yarn add sass-loader@^8.0.0

## Configuration 

- Décommenter la ligne 57 du fichier 'webpack.config.js'

- Renommer le fichier qui se trouve dans assets/css/app.css en app.scss

Ajouter au fichier qui se trouve dans assets/js/app.js cette ligne:

    import '../css/app.scss'

Ajouter dans le fichier src/templates/base.html.twig les lignes

    {{ encore_entry_link_tags('app') }}
    {{ encore_entry_script_tags('app') }}

dans les blocs correspondants, comme suit : 

    <html>
    <head>
        <meta charset="UTF-8">
        <title>{% block title %}Welcome!{% endblock %}</title>
            {% block stylesheets %}
                {{ encore_entry_link_tags('app') }}
            {% endblock %}
    </head>
    <body>
        {% block body %}{% endblock %}
            {% block javascripts %}
                {{ encore_entry_script_tags('app') }}
            {% endblock %}
    </body>
    </html>

#### Enfin, compiler avec 

    npm run dev

**ou**

    yarn encore dev

## Installation composants Javascript

### Javascript Bootstrap 
*correspondant à l'import HTML suivant*

    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/js/bootstrap.min.js" integrity="sha384-wfSDF2E50Y2D1uUdj0O3uMBJnjuUD4Ih7YwaYd1iqfktj0Uod8GCExl3Og8ifwB6" crossorigin="anonymous"></script>

*installation*

    npm install --save bootstrap-star-rating

**ou**

    yarn add --save bootstrap-star-rating

### Jquery
*correspondant à l'import HTML suivant*

    <script src="https://code.jquery.com/jquery-3.4.1.slim.min.js" integrity="sha384-J6qa4849blE2+poT4WnyKhv5vZF5SrPo0iEjwBvKU7imGFAV0wwj1yYfoRSJoZ+n" crossorigin="anonymous"></script>

*installation*

    npm install --save jquery 

**ou**

    yarn add --save jquery

### poppers.js
*correspondant à l'import HTML suivant*

    <script src="https://cdn.jsdelivr.net/npm/popper.js@1.16.0/dist/umd/popper.min.js" integrity="sha384-Q6E9RHvbIyZFJoft+2mJbHaEWldlvI9IOYy5n3zV9zzTtmI3UksdQRVvoxMfooAo" crossorigin="anonymous"></script>

*installation*

    npm install --save popper.js

**ou**

    yarn add --save popper.js


## Configuration

#### Ajouter au fichier app.js le code suivant

    // Import Bootstrap JQuery
    const $ = require('jquery');
    require('bootstrap');
    // Import Bootstrap JS
    require('bootstrap-star-rating');

### Enjoy la navbar :D 