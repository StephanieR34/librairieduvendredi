# cloud_natif_bibliotheque_virtuelle

pour voir le resultat
https://librarysteph.azurewebsites.net/api/books?

**Main.py (Script upload) :**

Pour upload le livre dans le blob , lui donner un titre, lui ajouter l'auteur, un url et les mots que le livre contient.

Pour l'activer 'python main.py upload "chemin du fichier"'




**Blob trigger final :**

Se déclenche à chaque action. Via la def main qui se connecte à la base de données (MYSQL) et compte le nombre de mots et les insère dans la colonne 'nombre de mots'.

Pour l'activer : F5 en local ou la flèche dans Azure pour deploy.






**HTTP TRIGGER INIT 1 (route api/books) :**

Pour afficher la liste des livres via la def main reliée à la database. Est relié avec la page HTML ' index 1' pour lister les livres en liens cliquables.

Pour l'activer : F5 en local ou la flèche dans Azure pour deploy.






**HTTP TRIGGER INIT 2 (route api/books/titre):**

Via le liens cliquable, récupère les informations dans la database, va afficher les informations du livre (titre, l'auteur, URL, liste de mots que le livre contient).

Est relié avec la page HTML ' index 2' qui affiche les infos du livre et permet de télécharger le livre (via lien cliquable).

Pour l'activer : F5 en local ou la flèche dans Azure pour deploy.






**Variables d'environnement :**

Servent à cacher des informations sensibles, elles sont à rentrer dans votre pc et sur Azure (fonction> Paramètres> Configuration> Nouveaux paramètres d'APP).


configuration = {

  'host': correspond à l'url de la base de donnée,
  
  'user': correspond à l'identifiant de connection à la bd ,
  
  'password': ici le mots de passe de connection a la bd,
  
  'database':le nom de votre base de donné,
  
  'client_flags': [mysql.connector.ClientFlag.SSL],
  
  'ssl_ca': le chemin d'accés/lien du certificat nécessaire pour communiquer via le protocole SSL
  
}


storage = {

    'account': le nom de vore blob de stockage,
    
    'key' : la clé d'acces a celui ci ,
    
    'container': le nom du conteneur.
    
}



**MYSQL :**

N'oubliez pas d'entrer votre adresse IP sur Azure, à chaque fois que vous vous connectez sur un nouveau réseau.

