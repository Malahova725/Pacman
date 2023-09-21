# Pacman

    Mai întâi am inclus câteva biblioteci:
        #include <iostream>: Am inclus această bibliotecă pentru a lucra cu intrarea și ieșirea de date.
        #include <stdio.h>: Această linie include o bibliotecă pentru funcțiile standard de intrare și ieșire.
        #include <windows.h>: Această linie include o bibliotecă Windows pentru lucrul cu fereastra consolei.
        #include <string>: De asemenea, am adăugat o bibliotecă pentru lucrul cu șiruri de caractere.
        #include <vector>: Această linie include o bibliotecă pentru lucrul cu vectori (tablouri dinamice).

    Apoi, am specificat compilatorului că voi folosi spațiul de nume std cu ajutorul următoarei linii:
        using namespace std;: Aceasta permite să folosesc obiecte și funcții standard fără a scrie std:: înaintea lor.

    Apoi am definit harta jocului:
        char map[18][32]: Acest tablou reprezintă harta jocului, în care fiecare caracter reprezintă un element al hărții (perete, spațiu liber, erou etc.).

    Există funcția ShowMap(), care afișează starea curentă a hărții jocului în consolă.

    Există, de asemenea, funcția gotoxy(short x, short y), care mută cursorul consolei la coordonatele specificate (x, y).

    Am creat clasa entity, care reprezintă o entitate pe hartă (cum ar fi eroul sau inamicul). Entitatea are coordonate (x, y) și metode pentru a se deplasa și a se desena.

    Am definit, de asemenea, structurile walk și target:
        walk este folosită pentru a implementa algoritmul de căutare a drumului (BFS) și conține informații despre deplasare.
        target este folosită pentru a stoca coordonatele țintei.

    Am declarat vectori:
        vector<target> walk_queue;: Vector pentru stocarea traseului.
        vector<walk> BFSArray;: Vector pentru stocarea informațiilor despre deplasare în timpul căutării drumului.

    Funcția AddArray(int x, int y, int wc, int back) adaugă un punct în vectorul BFSArray în timpul căutării drumului.

    Funcția FindPath(int sx, int sy, int x, int y) găsește un drum de la coordonatele de început (sx, sy) la coordonatele țintă (x, y) folosind algoritmul BFS.

    Funcția main() este funcția principală a programului, unde începe execuția codului.
        Jocul oferă opțiunea de a selecta nivelul de dificultate.
        Apoi, jocul începe cu afișarea hărții, eroului și țintei.
        Jucătorul controlează eroul cu ajutorul tastelor săgeată, încercând să colecteze puncte și să evite ținta.
        Când jucătorul pierde (ținta ajunge la erou), este afișat un scor.
