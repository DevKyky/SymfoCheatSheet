# Symphony
[Symfony Doc](https://symfony.com/doc/5.4/index.html)

_PhpStorm est l'IDE utilisé pour cette CheatSheet._

## Wampserver

- Télécharger et installer Wampserver
- Télécharger la dernière mise à jour de Wamp
- Télécharger la dernière mise à jour de PhpMyAdmin

Lien : [Wampserver](https://wampserver.aviatechno.net/)

## Composer

- Télécharger et installer composer

Lien : [Composer](https://getcomposer.org/)

## Installer Symfony

Ouvrez un terminal est entrer cette commande :
```sh
composer create-project symfony/website-skeleton <nom_du_projet> 5.4.*
```

Lors de l'installation, indiquez non (n) pour la configuration de Docker.

## Configuration du projet

Une fois l'installation du projet terminé, il faut installer quelques plugins.
Pour cela `Ctrl Alt S` puis aller dans `Plugins` pour accéder au Marketplace et installer :

- Symfony Support
- .env files support
- PHP Annotations

Il faudra ensuite relancer PhpStorm.

Une fois PhpStorm relancé, vous pouvez installer l'Apache-Pack avec composer.
Pour cela, ouvrez un terminal (il faut que vous soyez à la racine du projet) puis exécutez cette commande :
```sh
composer req symfony/apache-pack
```
Répondez oui (y) lors de l'installation.

Dernière étape, en faisant `Ctrl Alt S`, rendez-vous dans `PHP > Symfony` puis :

- Cliquez sur "enable Plugin for this Project"
- Remplacez "app" dans App Directory par "src"
- Décochez l'ensemble des options dans "Code Folding"
- (Apply > OK)

Dernier point, cliquez sur la version PHP en bas à droite de l'IDE et sélectionnez `Disable synchronization with composer.json` puis recliquez sur la version PHP pour mettre la version `8.1`.

Maintenant, en allant sur localhost (grâce à Wamp), vous devriez avoir accès à votre projet en allant sur :
```sh
localhost/<nom_du_projet>/public
```

Vous devriez y voir une page d'accueil Symphony.

## Les commandes

Quelques commandes de base :

| Action              | Commande                        |
|---------------------|---------------------------------|
| Créer un controller | php bin/console make:controller |
| Créer une entity    | php bin/console make:entity     |
| Créer un form       | php bin/console make:form       |

### Fixture

Pour ajouter des données facilement et rapidement en BDD.
Installation avec `composer require --dev orm-fixtures`.

### Fausses données avec Faker

Installation avec `composer req fzaninotto/Faker`.

### Base de données

