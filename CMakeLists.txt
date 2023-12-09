cmake_minimum_required(VERSION 3.23)
project(Pierre_Feuille_Ciseaux)

set(CMAKE_CXX_STANDARD 14)

add_executable(Pierre_Feuille_Ciseaux
        .gitignore
        "Jeu Principal.c"
        Regles.txt)
