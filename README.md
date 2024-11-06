# Disseny-DDBB

Este repositorio contiene un diagrama relacional para un festival de musica. <br>
Incluye una carpeta con la imagen del diagrama y una explicacion en el README. <br>
<br>
Este diagrama fue realizado usando la aplicacion [drawio.com](https://www.drawio.com/). <br>

## Expliacion del diagrama

<img src="disseny DDBB/Captura de pantalla 2024-11-06 172746.png" alt="Captura diagrama" style="width:100%"><br><br>

El diagrama representa un modelo entidad-relacion (ER) para la gestión de conciertos. Este diagrama contiene 6 entidades, 6 interrelaciones y cada entidad tiene sus respectivos atributos. Tambien hay una interrelacion que cuenta con sus atributos. <br>

## Atributos

1. RECINTE: <br>
    - Atributos: Nom (Clau primaria), MetresEscenari, MetresEspectadors, AforamentMaxim, Lavabos y EscenariCobert. <br>

2. CONCERT: <br>
    - Atributos: IDConcert (Clau primaria), HoraInici, HoraFi, Preu y Data. <br>

3. GRUP: <br>
    - Atributos: Nom (Clau primaria), Pais, Components y Preu. <br>

4. PERSONA: <br>
    - Atributos: Usuari (Clau primaria), Contrasenya, DNI, Mail, Nom, DataNaixement y Cognoms. <br>

5. PARCELA: <br>
    - Atributos: Numero (Clau primaria), MetresQuadrats y Preu. <br>

6. CARRER: <br>
    - Atributos: Codi (Clau primaria) y Nom. <br>

7. Accedir (Interrelacion): <br>
    - Atributos: Data y Hora. <br>

## Relaciones

1. RECINTE: <br>
    - Relaciones: Realitza (1 a N (muchos)) con CONCERT y Accedir (N (muchos) a M (muchos)) con PERSONA. <br>

2. CONCERT: <br>
    - Relaciones: Realitza (1 a N) con RECINTE y Realitza (1 a N) con GRUP. <br>

3. GRUP: <br>
    - Relaciones: Realitza (1 a N) con CONCERT y Substituir (N a M) con GRUP. <br>

4. PERSONA: <br>
    - Relaciones: Accedir (N a M) con RECINTE y Llogar (1 a 1) con PARCELA. <br>

5. PARCELA: <br>
    - Relaciones: Llogar (1 a 1) con PERSONA y Conte (1 a N) con CARRER. <br>

6. CARRER: <br>
    - Relaciones: Conte (1 a N) con PARCELA. <br>

## Cardinalidad

1. Realitza (Recinte - Concert) <br>
    - Un Recinte pot tenir molts Concerts (1 a N) y cada Concert es realitza en un sol Recinte (N a 1). <br>

2. Realitza (Grup - Concert) <br>
    - Un Grup pot actuar en molts Concerts (1 a N) y cada Concert té un sol Grup (N a 1). <br>

3. Substituir (Grup - Substituir) <br>
    - Un Grup pot tenir diversos Substituis (1 a N) y un Substituit pot estar disponible per substituir diversos Grups (N a N). <br>
    - Restricció de participació: <br>
        - Participació opcional per a Grup: No tots els gurps tenen substituits ni poden ser substituïts. <br>
        - Participació opcional per a Substitut: No tots els grups poden substituit a altres.

4. Conte (Carrer - Parcela) <br>
    - Un carrer pot contenir moltes Parcel·les (1 a N) y cada Parcel·la pertany a un sol Carrer (N a 1). <br>

5. Llogar (Persona - Parcel·la) <br>
    - Una Persona pot llogar com a màxim una Parcel·la (1 a 1) y una Parcel·la pot estar llogada per una sola Persona (1 a 1).

6. Accedir (Persona - Recinte) <br>
    - Una Persona pot accedir a un Recinte diverses vegades (N a N) y un Recinte pot rebre múltiples visites de diferents Persones (N a N). <br>

Este diagrama es relevante porque muestra cómo se relacionan las diferentes entidades en la gestión de conciertos. <br>
