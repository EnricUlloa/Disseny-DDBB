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

Este diagrama es relevante porque muestra cómo se relacionan las diferentes entidades en la gestión de conciertos.
