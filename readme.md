
# Symphony

[Documentation](https://symfony.com/doc/current/index.html) de Symfony.

## Installation de l'environnement

### Wampserver
Lien : [Wampserver](https://wampserver.aviatechno.net/)

Téléchargez et mettez à jour Wamp. Pensez également à télécharger et installer la dernière version de PhpMyAdmin afin de pouvoir profiter de PHP 8.

**Attention** : pour installer les addons afin de mettre à jour Wamp, il est nécessaire d'avoir au préalable installer et exécuté Wamp au moins une fois.

### (Optionnel) Symfony CLI

__Installer [Scoop](https://scoop.sh/) avec un terminal PowerShell__

```
> Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
> irm get.scoop.sh | iex
```

Une fois l'installation terminée, exécutez la commande suivante :

```
scoop install symfony-cli
```

Symfony CLI permet d'utiliser un serveur web local tout comme wamp. La syntaxe est également différente puisqu'à la place d'utiliser `php bin/console` vous pourrez utiliser `symfony console`.

Pour démarrer le serveur, utilisez `symfony serve -d`.

### Composer

Lien : [Composer](https://getcomposer.org/)

Télécharger et installer composer.

**Attention** : installez Composer qu'une fois l'installation de Wamp et de votre version PHP terminée afin de pouvoir sélectionnez la bonne version de PHP.

## Installer Symfony

Ouvrez un terminal est entrer cette commande :

```
composer create-project symfony/website-skeleton <nom_du_projet> 6.2.*
// OU
symfony new <nom_du_projet> --version="6.2.*" --webapp
```

Dans l'exemple ci-dessus, la version demandée est la dernière de la 6.2, mais il est possible d'indiquer n'importe quelle version. Référez-vous à la [documentation](https://symfony.com/releases) pour voir les autres versions.

Il se peut qu'une fois l'installation terminée, vous ayez besoin d'installer l'Apache Pack afin de pouvoir profiter du *profiler* : `composer require symfony/apache-pack`.

## Configuration du projet

Voici quelques plugins recommandés avec l'IDE PhpStorm.
(`Ctrl Alt S` puis aller dans `Plugins` pour accéder au Marketplace et installer)

- Symfony Support
- .env files support
- PHP Annotations

Dernière étape, toujours avec l'IDE PhpStorm, `Ctrl Alt S`, rendez-vous dans `PHP > Symfony` puis :

- Cliquez sur `enable Plugin for this Project`
- Remplacez "app" dans App Directory par `src`
- Décochez l'ensemble des options dans `Code Folding`
- `Apply` > `OK`

### Tester l'installation

Pour voir si l'installation fonctionne correctement, vérifiez si l'application se lance correctement.

```
// Wamp
localhost/<nom_du_projet>/public

// Symfony CLI
http://127.0.0.1:8000
```

## Les commandes

### I. Commandes basiques

| Action              | Commande                        |
|---------------------|---------------------------------|
| Créer un controller | php bin/console make:controller |
| Créer une entity    | php bin/console make:entity     |
| Créer un form       | php bin/console make:form       |

(`symfony console make:*command*` avec Symfony CLI)

### II. Fixture

[Documentation](https://symfony.com/bundles/DoctrineFixturesBundle/current/index.html)

`composer require --dev orm-fixtures`.

### III. Générer de fausses données avec Faker

[Documentation](https://faker.readthedocs.io/en/master/index.html)

`composer req fzaninotto/Faker`

### IV. Base de données

| Action              | Commande                        |
|---------------------|---------------------------------|
| Créer une BDD | php bin/console d:d:c |
| Supprimer la BDD | php bin/console d:d:d |
| Mettre à jour le schéma de la BDD    | php bin/console d:s:u --force     |
| Vérifier le mapping       | php bin/console d:s:v       |
| Utiliser les fixtures en écrasant les données existantes       | php bin/console d:f:l       |
| Utiliser les fixtures sans écraser les données existantes       | php bin/console d:f:l --append       |

(`symfony console *command*` avec Symfony CLI)

## PHP Unit

[Documentation](https://symfony.com/doc/current/testing.html)

```
composer require --dev symfony/test-pack
```

## Webpack Encore

[Documentation](https://symfony.com/doc/current/frontend/encore/installation.html)

- React :
	- Composants avec [UX React](https://symfony.com/bundles/ux-react/current/index.html)
	-  [API](https://symfony.com/doc/current/frontend/encore/reactjs.html)

- Vue.js
	- Composants avec [UX Vue](https://symfony.com/bundles/ux-vue/current/index.html)
	- [API](https://symfony.com/doc/current/frontend/encore/vuejs.html) 
