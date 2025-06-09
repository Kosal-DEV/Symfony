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
    #[Route('/hello', name: 'hello')]
    public function index(): Response
    {
        return new Response('Hello World !');
    }
}
```
- La route `/hello` appelle la méthode `index()`.
- Cette méthode retourne une réponse avec le texte **Hello World !**.

**Voici ce que ça donne sur une page**
