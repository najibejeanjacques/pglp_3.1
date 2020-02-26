#Exercice 1

1) Cette classe ne respecte pas le principe SRP, car la classe a deux responsabilités , ces duex responsabiltés sont: 
  -le calcul du salaire
  -l'affichage des coordonnées
(C'est a dire deux raisons valables de changer), or le principe SRP nous dit qu'une classe ne devrait avoir qu'une seule raison de changer.

2) Si la methode de calcul du salire change,alors cela nécessite un changement de la classe Employe afin de prendre en compte la nouvelle méthode de calcul.

3) Si l'affichage est remplacé par le stockage dans un fichier CSV, alors cela nécessiterait aussi une modification de la classe Employe afin de prendre en compte les nouvelles mises a jour.

4)Proposons une solution respectant le principe SRP:
-On crée une classe pour le calcul des salaires:
class CalculSalaire {
    public double calculSalaire() { 
    //traitement pour calcul salaire 
    return valeur;
    };
}

-Puis on crée la classe employé qui extend la classe CalculSalaire:
Si la methode calculSalaire() vient a changer il suffit de faire un extend avec la nouvelle classe puis on redefinie la nouvelle methode.
class  Employe extends CalculSalaire{
   private final String nom;
   private final String adresse;
   
   //On peux redefinir la methode calculSalaire() en cas de changement avec
   @Override
   public double calculSalire()
   { 
        //Définition de la nouvelle methode
   
   }
   
   public void afficheCoordonnees(){ System.out.println(nom+ " , "+adresse;}
   
}
