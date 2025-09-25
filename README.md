Question 1.1 :

I'l y'a une en-tête celle-ci : response.end("<html><h1>My first server!<h1></html>");
Dans l'en-tête de la page il y'a uniquement le style

Question 1.2 :

Une en-tête à changer celle-ci : response.setHeader("Content-Type","application/json")
Il y'a également une nouvelle celle-ci : Content-Type: application/json

Question 1.3 :

Je reçois l'erreur : "Error: ENOENT: no such file or directory, open 'C:\Users\gay\Cours\devweb-tp5\index.html'"

Question 1.4 :

Le code d'erreur affichée est : ENOENT (no such file or directory)

Pour vérifier l'erreur j'utilise error.code === "ENOENT"

Question 1.5 :

Voici ma nouvelle fonction en async :

async function requestListener(_request, response) {
  response.setHeader("Content-Type", "text/html");
  try {
    const contents = await fs.readFile("index.html", "utf8");
    response.writeHead(200);
    return response.end(contents);
  } catch (error) {
    console.error(error);
    if (error && error.code === "ENOENT") {
      response.writeHead(500);
      return response.end("<html><p>500: INTERNAL SERVER ERROR - index.html not found</p></html>");
    }
    response.writeHead(500);
    return response.end("<html><p>500: INTERNAL SERVER ERROR</p></html>");
  }
}

Question 1.6 :

La commande npm install cross-env --save a ajouté cross-env dans les dépendances de package.json, et npm install nodemon --save-dev a ajouté nodemon dans les dépendances de développement ainsi que mis à jour node_modules/ et package-lock.json.

Question 1.7 :

http-dev lance le serveur avec nodemon en mode développement, alors que http-prod l’exécute avec node en mode production.

Question 1.8 :

/index.html et /random.html renvoient 200, tandis que / et /dont-exist renvoient 404.

Question 2.1:

Express : https://expressjs.com

http-errors : https://github.com/jshttp/http-errors

loglevel : https://www.npmjs.com/package/loglevel

morgan : https://www.npmjs.com/package/morgan

Question 2.2 :

