# Disseny-DDBB

Aquest repositori conté un diagrama relacional per un festival de musica. <br>
Inclou una carpeta amb la imatge del diagrama i una explicació en el README. <br>
<br>
Aquest diagrama ha estat realitzat utilitzant l'aplicació [drawio.com](https://www.drawio.com/). <br>

## Expliació del diagrama

<img src="disseny DDBB/Captura de pantalla 2024-11-06 172746.png" alt="Captura diagrama" style="width:100%"><br><br>

El diagrama representa un model entitat-relació (ER) per la gestió de concerts. Aquest diagrama conté 6 entitatd, 6 interrelacions i cada entitat te els seus respectius atributs. Tambe hi ha una interrelacio que te els seus atributs. <br>

## Atributs

1. RECINTE: <br>
    - Atributs: Nom (Clau primaria), MetresEscenari, MetresEspectadors, AforamentMaxim, Lavabos i EscenariCobert. <br>

2. CONCERT: <br>
    - Atributs: IDConcert (Clau primaria), HoraInici, HoraFi, Preu i Data. <br>

3. GRUP: <br>
    - Atributs: Nom (Clau primaria), Pais, Components i Preu. <br>

4. PERSONA: <br>
    - Atributs: Usuari (Clau primaria), Contrasenya, DNI, Mail, Nom, DataNaixement i Cognoms. <br>

5. PARCELA: <br>
    - Atributs: Numero (Clau primaria), MetresQuadrats i Preu. <br>

6. CARRER: <br>
    - Atributs: Codi (Clau primaria) i Nom. <br>

7. Accedir (Interrelacio): <br>
    - Atributs: Data i Hora. <br>

## Relacions

1. RECINTE: <br>
    - Relacions: Realitza (1 a N (molts)) amb CONCERT i Accedir (N (molts) a M (molts)) amb PERSONA. <br>

2. CONCERT: <br>
    - Relacions: Realitza (1 a N) amb RECINTE i Realitza (1 a N) amb GRUP. <br>

3. GRUP: <br>
    - Relacions: Realitza (1 a N) amb CONCERT i Substituir (N a M) amb GRUP. <br>

4. PERSONA: <br>
    - Relacions: Accedir (N a M) amb RECINTE i Llogar (1 a 1) amb PARCELA. <br>

5. PARCELA: <br>
    - Relacions: Llogar (1 a 1) amb PERSONA i Conte (1 a N) amb CARRER. <br>

6. CARRER: <br>
    - Relacions: Conte (1 a N) amb PARCELA. <br>

## Cardinalitat

1. Realitza (Recinte - Concert) <br>
    - Un Recinte pot tenir molts Concerts (1 a N) i cada Concert es realitza en un sol Recinte (N a 1). <br>

2. Realitza (Grup - Concert) <br>
    - Un Grup pot actuar en molts Concerts (1 a N) i cada Concert té un sol Grup (N a 1). <br>

3. Substituir (Grup - Substituir) <br>
    - Un Grup pot tenir diversos Substituis (1 a N) i un Substituit pot estar disponible per substituir diversos Grups (N a N). <br>
    - Restricció de participació: <br>
        - Participació opcional per a Grup: No tots els gurps tenen substituits ni poden ser substituïts. <br>
        - Participació opcional per a Substitut: No tots els grups poden substituit a altres.

4. Conte (Carrer - Parcela) <br>
    - Un carrer pot contenir moltes Parcel·les (1 a N) i cada Parcel·la pertany a un sol Carrer (N a 1). <br>

5. Llogar (Persona - Parcel·la) <br>
    - Una Persona pot llogar com a màxim una Parcel·la (1 a 1) i una Parcel·la pot estar llogada per una sola Persona (1 a 1).

6. Accedir (Persona - Recinte) <br>
    - Una Persona pot accedir a un Recinte diverses vegades (N a N) i un Recinte pot rebre múltiples visites de diferents Persones (N a N). <br>

Aquest diagrama es rellevant perque mostra com es relacionen les diferents entitats en la gestió de concerts. <br>