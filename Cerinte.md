﻿## Cerință laborator 1 [Clase si obiecte]

Creați o aplicație consolă care prin intermediul unui meniu în linie de comandă să perimită crearea unui șir de studenți și afișarea lui. Un student va avea cel puțin următoarele atribute: first name, last name, registration number, anul de studiu, lista de discipline. Disciplina va contine doar numele. Pentru a converti un șir de caractere la o valoare de tip `int` folosiți metoda `TryParse`.

## Cerință laborator 2 [Încapsulare. Interfață (publică) și implementare (privată)]

Realizarea unui program OO in C# care să permită calcularea mediei unui student pentru o disciplină. Se vor urma pașii:
- crearea clasei Student (se poate folosi clasa de la lucrarea anterioară)
- crearea clasei catalog care trebuie să permită, adăugarea unei note pentru un student pentru o disciplină, calcularea mediei pentru un student pentru o disciplină, a mediei anuale, respectiv a mediilor multianuale
- realizarea unui meniu în linie de comandă care sa permită:
    * crearea unui student
    * notarea unui student la o disciplină
    * calcularea mediei pentru o disciplină / anuală / multianuală și salvarea lor în catalog
    * afișarea mediei pentru o disciplină / anuală / multianuală, pentru un student
    * afișarea unui tabel cu mediile pentru o disciplină / anuale / multianuale ale studenților

Pentru a proiecta corect interfețele încercați să răspundeți la întrebările: 
* Ce funcționalitate trebuie să fie apelate din exteriorul clasei?
* Care este interfața minimală pentru clasa Catalog?
* Pot să modific implementarea fără a modifica interacțiunea dintre meniul în linie de comandă și clasa Catalog?

## Cerință laborator 3 [Moștenirea]

Crearea unei ierarhii de clase care să modeleze diferitele tipuri de colete furnizate de o companie de transport. 

Există trei tipuri de colete, cu costuri și timpi de livrare diferite: 
* Pachetul de bază: costă 5 EUR pe kilogram și este livrat în 5 zile. Dacă greutatea pachetului este mai mare de 10 kilograme, este necesară încă o zi. 
* Pachet avansat: costă 6 EUR per kilogram cu o taxă suplimentară de 2 EUR. Pachetul se livrează în 2 zile.  
* Pachet peste noapte: Livrat a doua zi și costă 10 EUR pe kilogram. 

În metoda principală, trebuie să se poată introduce pachete de toate tipurile într-o Lista. La sfârșit, trebuie tipărite toate pachetele într-o buclă.


## Cerință laborator 4 [Polimorfism - Suprascriere]

Trebuie creată o ierarhie de clase care să modeleze polițele de asigurare de viață și auto ale unei companii de asigurări. 

Ambele polițe se caracterizează prin următoarele: 
* numele persoanei asigurate
* vârsta persoanei asigurate
* durata în zile a poliței

În plus, polița auto depinde și de vârsta vehiculului. Suprascrierea se va folosi pentru a implementa metoda de calcul pentru fiecare din cele două tipuri de polițe.

Pentru asigurarea de viață se va folosi formula de calcul: `vârsta_persoanei_asigurate + 0.001 * perioada_acoperita`

Pentru asigurarea auto se va folosi formula de calcul: `0.05 * perioada_acoperită + 10 * vârsta_mașinii – vârsta_persoanei_asigurate`

În metoda principală se vor crea câteva polițe de asigurare și se va afișa prețul fiecărei polițe.

## Cerință laborator 5 [Compoziția]

Creați o aplicație care se va ocupa de rezervarea apartamentelor (în stil AirBnB). 
Trebuie să gestionați următoarele informații: 
* Apartamente: 
    - Adresă
    - Capacitate (nr. maxim persoane) 
    - Preț pe zi 
* Rezervări: 
    - Numele și prenumele persoanei care a făcut rezervarea 
    - Data începerii 
    - Durata 
    - O listă cu persoanele care se vor caza
Persoană: 
    - Nume și prenume 
    - Anul nașterii

Creați o interfață de utilizare în linie de comandă care se va ocupa de următoarele operațiuni: * Adăugarea unei noi rezervări 
* Căutarea unei rezervări pe baza numelui persoanei
* Listare toate rezervările 

Pentru simplitate apartamentele vor fi pre populate din cod, **NU** vor fi gestionate prin intermediul interfeței în linie de comandă. De asemenea, tot pentru simplitate, nu se va ține cont de faptul că un apartament este rezervat de mai multe ori.

Adăugați o nouă funcționalitate aplicației care să permită calcularea taxelor pentru o rezervare pentru o anumită țară.

Pentru aceasta se vor urma pașii:
* definire interfață `ITaxCalculator`
* implementare calculatoare de taxe pentru România (19% din valoarea), Franța (25% din valoarea rezervării pentru sume ce depășesc 1000euro, 10% din valoarea rezervării pentru sumele ce sunt sub acest prag) și Italia (2 euro / zi și 9% din valoarea rezervării)
* modificare constructor `Reservation` pentru a permite injectarea calculatorului de taxe
* adăugare metodă `calculateTax` în clasa `Reservation`
* modificare interfață pentru a permite alegerea tării și afișarea taxelor după ce a fost făcută o rezervare


## Cerință laborator 6 [Validarea datelor. Tratarea excepțiilor]

Creați o aplicație care se va ocupa de preluarea datelor pentru rezervarea apartamentelor (în stil AirBnB) și implementați pentru fiecare câmp regulile de validare indicate. Trebuie să gestionați următoarele informații: 
* Rezervări: 
    - Numele și prenumele persoanei care a făcut rezervarea, maxim 30 de caractere
    - Data începerii, mai mare sau egală cu data curentă
    - Durata, număr întreg, pozitiv, maxim 60 de zile
    - O listă cu persoanele care se vor caza, lista nu poate fi goală
    - Codul de identificare al apartamentului, 4 caractere, începe cu litera A, care este urmată de 3 cifre
Persoană: 
    - Nume și prenume, maxim 30 de caractere 
    - Anul nașterii, mai mic sau egal cu anul curent

Modificați aplicația astfel încât disponibilitatea apartamentului să fie confirmată prin apelarea unui serviciu web care pe baza codului apartamentului, a datei rezervării și a perioadei, returnează o valoare care indică daca apartamentul este disponibil pentru acea perioadă. Apelare serviciului web va fi simulată printr-o metodă care aleator poate răspunde că apartamentul este liber sau nu. De asemenea metoda va arunca tot în mod aleator excepții care să indice următoare posibile erori:
* serviciul web nu este disponibil
* apartamentul nu există
* cererea nu este autorizată

Pentru gestionarea câmpurilor de tip data și pentru aflarea datei curente se va folosi tipul `DateOnly`.
Pentru generarea de numere aleatoare se va folosi clasa `Random`.