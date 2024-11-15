# Exemplu subiect test

Să se scrie un program C# care gestionează rezervările pentru zborul cu avionul pentru o companie aeriană. Pentru un zbor interesează numărul, data, aeroportul sursă și cel destinație și rezervările realizate. Rezervarea se face pe baza adresei de e-mail. Se cunoaște că există 2 tipuri de zboruri:
*	Local: se pot face rezervări pentru maxim 6 persoane, iar prețul rezervării se calculează ca fiind nr. de persoane * 100 +  nr. de bagaje * 25
*	Transatlantic: se pot face rezervări pentru maxim 10 persoane și 10 bagaje, iar prețul rezervării se calculează ca fiind nr. de persoane * 500 +  nr. de bagaje * 50 + 100	

Sarcini:
*	Implementați modelul OO care să reprezinte contextul de mai sus aplicând principiile POO – 6p 
*	Să se creeze compania cu câte un zbor din fiecare categorie și să se adauge cel puțin o rezervare la fiecare zbor – 1p 
*	Să se afișeze toate rezervările cu număr de persoane și valoare rezervării pentru un zbor – 1p 
*	Să se afișeze numărul de pasageri pentru un zbor – 1p 
*	Să se valideze numărul maxim de persoane pe validare – 1p 
*	BONUS: disponibilitatea locurilor pentru un zbor se face prin apelarea unui serviciu extern ce primește numarul zborului și numărul de personae și returnează un bool care indică daca mai sunt locuri, apelarea serviciului poate genera și următoarele excepții: zbor inexistent, serviciu indisponibil  – (1p – 2p) 
