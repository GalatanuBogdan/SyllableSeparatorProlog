# Documentația Proiectului Syllables

## Descriere proiect

Acest proiect realizat in cadrul materiei Programare Bazata pe Reguli, reprezintă implementarea unui sistem în Prolog capabil să gestioneze regulile de despărțire în silabe pentru cuvinte din limba română.

## Cerințe

Implementați un sistem în Prolog capabil să:

1. Citească un cuvânt și să afișeze versiunea acestuia despărțită în silabe.
   - Exemplu: `cuvânt` -> `cu-vânt`

2. Sa se verifice corectitudinea daca despartirea unui cuvant in silabe este corecta.
   - Exemplu1: `cre-ion` -> `corect`
   - Exemplu2: `crei-on` -> `incorect`
    
3. Introdusa o multime de silabe, sa se genereze toate combinatiile posibile de cuvinte care respecta regulile de despartire in silabe din limba romana.


## Pasi necesari pentru executia codului in prolog:

1. Instalați Prolog 8.5.20-1 pe sistemul dumneavoastră.

2. Deschideti consola SWI-Prolog in care puteți apela una dintre cele 3 functionalități:
   - 2.1 Despartirea unui cuvant in silabe:
   
     ```prolog
     ?- desparte_in_silabe("cuvant", Silabe).  % -> cu-vant
     ?- desparte_in_silabe("minunat", Silabe).  % -> mi-nu-nat
     ?- desparte_in_silabe("facultate", Silabe).  % -> fa-cul-ta-te
     ```
     "cuvant" poate fi înlocuit de cuvantul dorit pentru despartire.
     
   - 2.2 Verificarea unui cuvant să fie despartit corect in silabe:
   
     ```prolog
     ?- verificare_despartire_corecta("silaba1-silaba2-silaba3-...-silabaN", Cuvant). % exemplu general
     ?- verificare_despartire_corecta("mi-nu-nat", Cuvant). % despartirea in silabe este corecta
     ?- verificare_despartire_corecta("fa-cul-ta-te", Cuvant). % despartirea in silabe este corecta
     ?- verificare_despartire_corecta("fa-culta-te", Cuvant). % despartirea in silabe nu este corecta
     ```
     
     "silaba1-silaba2-silaba3-...-silabaN" reprezintă toate silabele separate prin cratime, care alcătuiesc cuvântul pentru care se dorește verificarea.
     
   - 2.3 Furnizarea tuturor combinatiilor valide din punct de vedere al despartirii in silabe care se pot forma cu o multime de silabe:
   
     ```prolog
     ?- permutare_lista_silabe("silaba1-silaba2-silaba3-...-silabaN", Cuvinte). % exemplu general
     ?- permutare_lista_silabe("u-re-che", Cuvinte). % ureche, uchere
     ?- permutare_lista_silabe("ca-mi-la", Cuvinte). % camila, calami, micala, milaca, lacami, lamica
     ```
     
     "silaba1-silaba2-silaba3-...-silabaN" reprezintă toate silabele separate prin cratime, care alcătuiesc multimea de silabe pentru care se dorește generarea.

## Pasi necesari pentru dechiderea interfatei grafice:
  1. Instalați Python 3.9.13 pe sistemul dumneavoastră.
  2. Rulati de la linia de comanda fisierul main.py folosind comanda:
    - ```
     python .\main.py
    ```

## Motivarea alegerilor de implementare:
  1. Pentru a avea un program bine structurat, pe partea de prolog a fost implementata cate o regula pentru fiecare cerinta in parte dar si pentru fiecare regula gramaticala.
  2. Multimea de silabe este construita cu ajutorul listelor, acestea fiind usor de utilizat.
  3. Se merita specificat ca a fost folosita metoda "permutation" pentru crearea tutoror posibilitatilor de permutare ale silabelor date.
  4. Pentru o usurinta in implementarea interfetei grafice am ales sa folosim libraria tkinter din python
  5. Pentru integrarea prologului in cadrul aplicatiei tkinter am ales sa folosim libraria pyswip din modulul Prolog. Am ales aceasta librarie deoarece libraria este foarte bine documentata aici https://github.com/yuce/pyswip.


## Contribuții

La acest proiect au contribuit:
1. Dobre Roxana
2. Dogaru Simona
3. Ghioc Otilia
4. Galatanu Bogdan
5. Macsim Oana

Intreaga echipa recunoaste contributii speciale din partea Otiliei Ghioc si ale lui Bogdan Galatanu care s-au remarcat prin implicarea deosebita in crearea acestui proiect.

## Licență

Acest proiect este licențiat sub [MIT License](LICENSE).
