TASK 0

Citesc comanda si path-ul ( la nevoie ) fiind alocat dinamic
Acesta este creat intr-un while pentru a simula o aplicatie, iesirea fiind doar prin comanda quit

TASK 1
Pentru Task 1 am creat functia edit si save, acestea reprezentand functionalitatile pe care le descriu

Incepem cu functia edit, care returneaza o structura mai exact structura bmp fiindca
avem nevoie sa salvez in memorie "imaginea" dupa structura BMP-ului
(structura bmp_fileheader, bmp_infoheader si vectorul pixelilor)

In functie deschid fisierul de la path, creez o variabila cu structura "bmp"
dupa citesc din fisier exact numarul de biti al structurii bmp_fileheader, respectiv bmp_infoheader, 
aici se introduce in variabilele din structura ceea ce este nevoie pentru fiecare (dupa structura bmp-ului), 
avem nevoie de acestea pentru ca dupa sa putem crea imaginea ca fisier si sa-l putem vizualiza.

Dupa am o functie unde citesc vectorul pixelilor (bitmap-ul), aici este mai special deoarece la citire trebuie 
sa ignoram padding-ul acesta creand un rand ca un multiplu de 4, stiind de aceasta informatie, 
ne folosim de o impartire cu float la 4 (float) si o rotunjesc la numarul mai mare cum ar fi 2.2 -> 3, 
dupa inmultesc la ca ti biti are un pix si aflam marimea randului cu padding in biti, 
iar apoi fara padding e doar inaltimea inmultit la cati biti are un pix.

Dupa aceasta aloc memoria pentru vectorul cu pixeli (bitmap) aceasta fiind inaltimea inmultit cu randul fara padding.

Dupa se incepe citirea din fisier si introducerea in vector
cu ajutorul pointerilor
pozitionam un pointer la inceputul vectorului bitmap
dupa aceasta luam fiecare rand si-l introducem in vectorul bitmap folosim o functie pentru a lua fiecare rand din fisier 
fara padding si citim unde e pozitionat pointerul din vector randul.
dupa pozitionam pointerul la urmatorul rand(imaginar fiindca nu folosim matrice, ci un vector).

la save deschidem/cream fisierul unde introducem informatiile fileheaderului si infoheaderului dupa care, ci bitmapul.

Bitmapul e introdus, introducand fiecare rand impreuna cu padding


Task 2

Functia insert
Deschidem fisierul, cream in memorie bmp-ul pe care-l inseram, dupa aceasta se citeste y,x, apoi inseram bitmap-ul in cel initila deschis. 
La inserare trebuie sa avem grija sa nu treaca peste inaltimea si lungimea imaginii initiale astfel avem niste decizii care schimba 
pana la cat merge i-ul si cat sa copieze din fisier.