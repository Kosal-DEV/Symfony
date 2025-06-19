<h1 align="center">Les controllers en symfony</h1>

### ✨ C'est quoi un controller ?
En Symfony, un controller (ou contrôleur) est une classe PHP qui contient des méthodes chargées de traiter une requête HTTP et de retourner une réponse HTTP.

Autrement dit, c’est le cœur de la logique métier d’une page web ou d'une fonctionnalité dans ton application. Il fait le lien entre l’utilisateur (via l’URL/la requête) et le système (base de données, affichage, etc.).

*Exemple simple de controller :*
```php
// src/Controller/HelloController.php

namespace App\Controller;

use Symfony\Bundle\FrameworkBundle\Controller\AbstractController;
use Symfony\Component\HttpFoundation\Response;
use Symfony\Component\Routing\Annotation\Route;

class HelloController extends AbstractController
{
    #[Route('/', name: 'accueil')]
    public function index(): Response
    {
        return new Response('Hello World !');
    }
}
```
- La route `/` appelle la méthode `index()` qui est exécutée au niveau de la page d'accueil.
- Cette méthode retourne une réponse avec le texte **Hello World !**.
- `AbstractController` donne accès à des méthodes utiles comme `render()`, `redirectToRoute()`...

**Voici ce que ça donne sur une page** ⬇️

![helloWorld](https://github.com/Kosal-DEV/Symfony/blob/main/symfony/Exemple-helloWorld.png?raw=true)

### 🚦 Qu’est-ce qu’une route en Symfony ?

Une route en Symfony fait le lien entre une URL et une méthode de contrôleur. Elle permet de dire :

"Quand l’utilisateur va sur cette adresse, exécute ce code."

#### *Exemple*
```php
use Symfony\Component\Routing\Annotation\Route;

class HomeController extends AbstractController
{
    #[Route('/', name: 'home')]
    public function index(): Response
    {
        return new Response('Bienvenue sur la page d’accueil !');
    }
}
```
- `#[Route('/', name: 'home')]`
- `/` = URL (racine du site),
- `name: 'home'` = nom de la route (utile pour les liens internes),
- `index()` = méthode exécutée,
- `Response(...)` = ce que la page va afficher.

### 🔧 Ajouter des paramètres dans l’URL
```php
    #[Route('/article/{id}', name: 'article_show')]
    public function show($id): Response
    {
        return new Response("Voici la page article n°$id");
    }
```
- Si on appelle /article/12 → Symfony passe `12` à `$id`.

#### *Voici ce que ça donne sur une page* ⬇️
![parametre](https://github.com/Kosal-DEV/Symfony/blob/main/symfony/Route-parametre.png?raw=true)

### ✅Les contraintes :
En Symfony, requirements permet de définir des contraintes (ou règles) sur les paramètres d’une route.
```php
#[Route('/article/{id}', name: 'article_show', requirements: ['id' => '\d+'])]
public function show(int $id): Response {
    return new Response("Article numéro $id");
}
```
- `{id}` est un paramètre dynamique dans l’URL.

requirements: `['id' => '\d+']` signifie :
- le paramètre `id` doit être un ou plusieurs chiffres (`\d+`).
- Si tu vas sur `/article/abc` → Symfony renvoie une erreur 404 car `abc` ne respecte pas la contrainte.

### 🔗 C'est quoi un slug ?

En Symfony (et en développement web en général), un slug est une version "propre" et lisible d’un texte, souvent utilisée dans une URL pour représenter un titre ou un nom.

#### *Exemple*
Le titre :
`"10 Astuces pour Symfony !"`

Le slug correspondant serait :
`10-astuces-pour-symfony`

### ✅ Pourquoi utiliser un slug ?

✔️ Améliore le référencement (SEO)

✔️ Rend l'URL plus lisible

✔️ Permet d’identifier une ressource sans exposer son ID

En symfony tu peux inclure un slug dans une route :
```php
#[Route('/article/{slug}', name: 'article_show')]
public function show(string $slug): Response
{
    // Récupérer l’article via le slug, par exemple depuis la base de données
}
```
Et dans l'URL tu aurais :
`/article/10-astuces-pour-symfony`

### 🖼️ La méthode render() en Symfony

La méthode `render()` permet d’afficher une **vue Twig** à partir d’un contrôleur.

#### 📌 Exemple :
```php
use Symfony\Bundle\FrameworkBundle\Controller\AbstractController;
use Symfony\Component\HttpFoundation\Response;
use Symfony\Component\Routing\Annotation\Route;

class HomeController extends AbstractController
{
    #[Route('/accueil', name: 'home')]
    public function index(): Response
    {
        return $this->render('home/index.html.twig', [
            'message' => 'Bienvenue sur Symfony !',
        ]);
    }
}
```

❗Pour en apprendre d'avantage sur le moteur de template twig [cliquez ici]()
