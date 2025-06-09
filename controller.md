<h1 align="center">Les controllers en symfony</h1>

### ✨ C'est quoi un controller ?
En Symfony, un controller (ou contrôleur) est une classe PHP qui contient des méthodes chargées de traiter une requête HTTP et de retourner une réponse HTTP.

Autrement dit, c’est le cœur de la logique métier d’une page web ou d'une fonctionnalité dans ton application. Il fait le lien entre l’utilisateur (via l’URL/la requête) et le système (base de données, affichage, etc.).

*Exemple simple de controller :*
```symfony
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

**Voici ce que ça donne sur une page**
![helloWorld](https://github.com/Kosal-DEV/Symfony/blob/main/symfony/Exemple-helloWorld.png?raw=true)

### 🚦 Qu’est-ce qu’une route en Symfony ?

Une route en Symfony fait le lien entre une URL et une méthode de contrôleur. Elle permet de dire :

"Quand l’utilisateur va sur cette adresse, exécute ce code."

#### *Exemple*
```symfony
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
```symfony
    #[Route('/article/{id}', name: 'article_show')]
    public function show($id): Response
    {
        return new Response("Voici la page article n°$id");
    }
```
- Si on appelle /article/12 → Symfony passe `12` à `$id`.
