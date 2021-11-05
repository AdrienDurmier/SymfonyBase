# SymfonyBase
Base de travail pour un projet Symfony

Documentation [https://www.youtube.com/watch?v=Q0gBWIvzuEw](https://www.youtube.com/watch?v=Q0gBWIvzuEw)

## Création du projet
    symfony new MonProjet –full

## Installation de Webpack Encore
    composer require symfony/webpack-encore-bundle
    yarn install


## Mettre à jour les fichiers
Changer l’extension de assets/styles/app.css en scss  
Modifier assets/styles/app.js en mettant à jour l’extension  
Activer le Sass loader en décommentant la ligne 59:  .enableSassLoader()  

## Installer SASS Loader
    yarn add sass-loader

## Modifier le template de base
Documentation: [https://symfony.com/doc/current/frontend/encore/simple-example.html](https://symfony.com/doc/current/frontend/encore/simple-example.html)  
Ajouter/décommenter cette ligne dans le block stylesheets  
    {{ encore_entry_link_tags('app') }}

Ajouter/décommenter cette ligne dans le block javascripts  
    {{ encore_entry_script_tags('app') }}

## Builder
En fonction de l’environnement:
* yarn encore dev
* yarn encore dev --watch
* yarn encore production

Troubleshooting:  
Si vous avez l'erreur
    Install sass (or node-sass) to use enableSassLoader()  
Alors
    yarn add sass –dev  

## Installation de PostCss
Documentation: [https://symfony.com/doc/current/frontend/encore/postcss.html](https://symfony.com/doc/current/frontend/encore/postcss.html)
    yarn add postcss-loader autoprefixer –dev (avec 2 tirets)
Créer le fichier postcss.config.js à la racine et insérer ce code:
```
module.exports = {
    plugins: {
        // include whatever plugins you want
        // but make sure you install these via yarn or npm!

        // add browserslist config to package.json (see below)
        autoprefixer: {}
    }
}
```

## Installer Bootstrap
Documentation: [https://getbootstrap.com/docs/5.1/getting-started/webpack/](https://getbootstrap.com/docs/5.1/getting-started/webpack/)  
    yarn add bootstrap OU npm install bootstrap
On peut vérifier la version dans package.json  
Ajouter cette ligne de le fichier assets/app.js :  import 'bootstrap'  
Créer le fichier assets/styles/custom.scss  (on pourra modifier les variables de bootstrap dedans)
Modifier le fichier apps.scss en ne mettant que  
```
    @import "custom";
    @import "~bootstrap/scss/bootstrap";
```
builder (yarn encore dev)
