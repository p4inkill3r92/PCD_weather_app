# Weather App

Acest proiect are ca scop punerea in evidenta a diferitelor tipuri de comunicare dintre o aplicatie de tip Server si mai multe aplicatii de tip Client.
Aplicatia de tip Server va permite comunicarea cu mai multi clienti ordinari si cu un singur client de administrare la un moment dat, prin diferite medii de comunicare (Local socket, INET socket, REST).
In general Aplicatiile de tip client vor face diferite cereri catre aplicatia de tip Server pentru a obtine informatii despre vreme in timp real pentru o anumita locatie aleasa de utilizator, iar aplicatia de tip Server va prelua infomatii despre vreme printr-un request http catre Dark Sky API (https://darksky.net/dev) pe care le va returna clientului.

## Tehnologii si tool-uri utilizate pentru acest proiect:

##### - C/C++/Unix

##### - Google APIs Client Library for C++ (for HTTP requests)

##### - Dark Sky API (https://darksky.net/dev) - ofera informatii despre vreme

##### - Posibil JavaScript (daca timpul va permite pt o interfata grafica in Electron)

## Echipa de implementare:

**Holhos Ioan-Florin** (responsabil pentru partea de server)

- implementare handleri pentru diferite conexiuni/cereri din partea clientilor (Local Socket/INET Socket, HTTP, TCP)

- preluarea informatiilor despre vreme de pe Dark Sky API pentru o anumita locatie (coordonate: latitudine si longitudine) ceruta de client

- implementare REST API pentru gestionarea locatiilor

**Ilin Robert** (responsabil pentru partea de client)

- implementare client cu functia de administrare

- client cu functia de utilizare prin Local Socket/INET Socket

- client pentru gestionarea localitatilor bazat pe Rest

> Cu precizarea ca la unele sarcini de lucru s-ar putea sa lucram amandoi pe partea de client sau pe partea de server in functie de complexitatea problemelor care apar pe parcurs.

## Testare conexiune TCP

> Terminal 1

```
$gcc TCP_server.c -o TCP_server
$./TCP_server
Socket successfully created..
Socket successfully binded..
Server listening...
```

> Terminal 2

```
$gcc TCP_client.c -o TCP_client
$./TCP_client
Socket successfully created..
connected to the server..
Enter the string : ping
```

> Terminal 1

```
From client: ping
	 To client : pong
```

> Terminal 2

```
From Server : pong
Enter the string :
```

## Fetch weather

> Terminal 1

```
$gcc TCP_server.c -lcurl -o TCP_server
$./TCP_server https://api.darksky.net/forecast/32f1f87b5680f82c0b095474b9ce7e66/37.8267,-122.4233 data
```

data => numele fisierului pentru output
