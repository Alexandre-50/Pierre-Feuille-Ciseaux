#include <stdio.h>
#include <stdlib.h>
#include <time.h>
#include <string.h>
#include <unistd.h>
#include <windows.h>

typedef struct Joueur
{
    int scoreJoueur;
    char Nom[20];
}t_Joueur;

void Color(int couleurDuTexte,int couleurDeFond) // fonction d'affichage de couleurs
{
    HANDLE H=GetStdHandle(STD_OUTPUT_HANDLE);
    SetConsoleTextAttribute(H,couleurDeFond*16+couleurDuTexte);
}

int NouvellePartie(t_Joueur joueur,int scoreOrdi,int choixJoueur,int choixOrdi,int nbPartie,int numeroPartie)
{
    do{
        printf("Veuillez saisir le nombres de parties\n");
        scanf("%d",&nbPartie);
    }while(nbPartie>3);
    fflush(stdin);
    printf("Veuillez saisir le nom du Joueur\n");
    gets(joueur.Nom);
    Color(4,0);
    printf("1 : Pierre\n");
    Color(7,0);
    Color(1,0);
    printf("2 : Feuille\n");
    Color(7,0);
    Color(2,0);
    printf("3 : Ciseaux\n");
    Color(7,0);
    for(numeroPartie=1;numeroPartie<=nbPartie;numeroPartie++)
    {
        do{
            printf("Veuillez choisir une action\n");
            scanf("%d",&choixJoueur);
            switch(choixJoueur)
            {
                case 1:
                    printf("Pierre\n");
                    printf("VS\n");
                    if(choixOrdi==1)
                    {
                        printf("Pierre\n");
                        printf("Egalite\n");
                    }
                    if(choixOrdi==2)
                    {
                        printf("Feuille\n");
                        printf("L'ordi gagne\n");
                        scoreOrdi=scoreOrdi+1;
                    }
                    if(choixOrdi==3)
                    {
                        printf("Ciseaux\n");
                        printf("%s gagne\n",joueur.Nom);
                        joueur.scoreJoueur=joueur.scoreJoueur+1;
                    }
                    break;
                case 2:
                    printf("Papier\n");
                    printf("VS\n");
                    if(choixOrdi==1)
                    {
                        printf("Pierre\n");
                        printf("%s gagne\n",joueur.Nom);
                        joueur.scoreJoueur=joueur.scoreJoueur+1;
                    }
                    if(choixOrdi==2)
                    {
                        printf("Feuille\n");
                        printf("Egalite\n");
                    }
                    if(choixOrdi==3)
                    {
                        printf("Ciseaux\n");
                        printf("L'ordi gagne\n");
                        scoreOrdi=scoreOrdi+1;
                    }
                    break;
                case 3:
                    printf("Ciseaux\n");
                    printf("VS\n");
                    if(choixOrdi==1)
                    {
                        printf("Pierre\n");
                        printf("L'ordi gagne\n");
                        scoreOrdi=scoreOrdi+1;
                    }
                    if(choixOrdi==2)
                    {
                        printf("Papier\n");
                        printf("%s gagne\n",joueur.Nom);
                        joueur.scoreJoueur=joueur.scoreJoueur+1;
                    }
                    if(choixOrdi==3)
                    {
                        printf("Ciseaux\n");
                        printf("Egalite\n");
                    }
                    break;
            }
        }while(choixJoueur>3);
    }
    sleep(2);
    printf("\n");
    printf("Score de %s : %d\n",joueur.Nom,joueur.scoreJoueur);
    printf("Score de l'ordi est : %d\n",scoreOrdi);
    if(joueur.scoreJoueur>scoreOrdi)
    {
        printf("%s a gagner la partie\n",joueur.Nom);
    }
    else if(scoreOrdi>joueur.scoreJoueur)
    {
        printf("L'ordi a gagne la partie\n");
    }
    else if(joueur.scoreJoueur==scoreOrdi)
    {
        printf("Personne ne gagne, egaliter pour les 2 joueurs\n");
    }
    printf("\n");
    return 0;
}
int menu()
{
    int choixMenu=0;
    do{
        printf("Bienvenue dans le Jeu Pierre Feuille Ciseaux\n");
        printf("1.Nouvelle Partie\n");
        printf("2.Affichage Regles\n");
        printf("3.Quitter le Jeu\n");
        printf("Que choissisez vous ?\n");
        scanf("%d",&choixMenu);
    }while(choixMenu<1 || choixMenu>3);
    return choixMenu;
}

void AffichageRegles(char c,FILE *Regles)
{
    Regles=fopen("Regles.txt","r");
    while((c=fgetc(Regles))!=EOF)
    {
        printf("%c",c);
    }
    fclose(Regles);
}
int main()
{
    t_Joueur Joueur;
    srand(time(NULL));
    int choixJoueur=0;
    Joueur.scoreJoueur=0;
    int scoreOrdi=0;
    int actionOrdi=0;
    int numeroPartie=1;
    int nbPartie=0;
    int choixMenu=0;
    FILE *regles;
    char c;
    actionOrdi=rand()%(3)+1;
    do{
        choixMenu=menu();
        switch(choixMenu)
        {
            case 1:
                NouvellePartie(Joueur,scoreOrdi,choixJoueur,actionOrdi,nbPartie,numeroPartie);
                break;
            case 2:
                printf("Voici les regles\n");
                AffichageRegles(c,regles);
                break;
            case 3:
                printf("Adieu\n");
                return 0;
                break;
        }
    }while(choixMenu!=3);
}
