# How to set-up Boostrap in a Symfony project
## Requirements
#### Node.js
*Check if node is installed*

    node -v

#### npm or yarn
*Check if npm is installed*

    npm -v

*Check if yarn is installed*

    yarn --version

## Install Webpack encore, node-modules and bootstrap css
*in a terminal, in your project directory*

#### Encore

    composer require symfony/webpack-encore-bundle

#### Node-modules

    npm install

**or**

    yarn add

### Node-sass and Bootstrap

 #### Node-sass

    npm install node-sass

**or**

    yarn add node-sass

 #### Bootstrap

    npm install bootstrap --dev

**or**

    yarn add bootstrap --dev

 #### Node-sass loader

    npm add sass-loader@^8.0.0

**or**

    yarn add sass-loader@^8.0.0

## Config 

- Uncomment line 57 of 'webpack.config.js' file

- Rename assets/css/app.css to app.scss

Add this line to assets/js/app.js :

    import '../css/app.scss'

Add these lines inside 'src/templates/base.html.twig' 

    {{ encore_entry_link_tags('app') }}
    {{ encore_entry_script_tags('app') }}

In the corresponding blocks, as follows : 

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

#### Then, compile with

    npm run dev

**or**

    yarn encore dev

## Install Javascript components

### Javascript Bootstrap 
*Matching the following HTML import*

    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/js/bootstrap.min.js" integrity="sha384-wfSDF2E50Y2D1uUdj0O3uMBJnjuUD4Ih7YwaYd1iqfktj0Uod8GCExl3Og8ifwB6" crossorigin="anonymous"></script>

*install*

    npm install --save bootstrap-star-rating

**or**

    yarn add --save bootstrap-star-rating

### Jquery
*Matching the following HTML import*

    <script src="https://code.jquery.com/jquery-3.4.1.slim.min.js" integrity="sha384-J6qa4849blE2+poT4WnyKhv5vZF5SrPo0iEjwBvKU7imGFAV0wwj1yYfoRSJoZ+n" crossorigin="anonymous"></script>

*install*

    npm install --save jquery 

**or**

    yarn add --save jquery

### poppers.js
*Matching the following HTML import*

    <script src="https://cdn.jsdelivr.net/npm/popper.js@1.16.0/dist/umd/popper.min.js" integrity="sha384-Q6E9RHvbIyZFJoft+2mJbHaEWldlvI9IOYy5n3zV9zzTtmI3UksdQRVvoxMfooAo" crossorigin="anonymous"></script>

*install*

    npm install --save popper.js

**ou**

    yarn add --save popper.js


## Config

#### Add to assets/js/app.js the following code block

    // Import Bootstrap JQuery
    const $ = require('jquery');
    require('bootstrap');
    // Import Bootstrap JS
    require('bootstrap-star-rating');

### Enjoy your navbar :D