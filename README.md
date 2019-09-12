# Simulator for tilpdat-heislab

Med denne greia kan du teste heiskoden din i simulator, så du slipper å sitte på sal med den fysiske heisen.

Testet og funker på Linux. Kan ikke garantere noe på Windows.

## Hvordan bruke simulatoren
1. Last ned simulatoren (Linux: SimElevatorServer. Windows: SimElevatorServer.exe)

2. Åpne terminalen i mappen der du lagret SimElevatorServer. Kjør kommandoen `chmod +x SimElevatorServer` for å gjøre det mulig å kjøre simulatoren som et program. Dette trenger du bare å gjøre én gang.

3. Kjør kommandoen `./SimElevatorServer` i terminalen for å starte simulatoren.

4. Last ned elev.h og elev.c. Disse filene må du bruke i heisprogrammet ditt istedenfor de gamle elev.h og elev.c som du hadde fra før.

5. Kompiler heisprogrammet ditt (`make`) med de nye filene og kjør det (`./heis`). Hvis heisprogrammet kjører som det skal og alt funker, så skal det nå stå "Connected" i simulatorvinduet. Bruk tastene qwe, sdf og zxcv for å "trykke" på bestillingsknappene i heisen.

6. Wooho, kjør heis og vær glad.

## Hvordan bytte mellom simulator og heisen på sal

For å kjøre heisen **i simulator** må det stå følgende øverst i både elev.c og elev.h:
~~~c
#define SIMULATOR
~~~

For å kjøre heisen **på sal** må det stå følgende øverst i både elev.c og elev.h:
~~~c
#define SAL
~~~

`SIMULATOR` og `SAL` er to konstanter som kan defineres. Både elev.c og elev.h inneholder kode for både simulator og for sal. Hvilken av konstantene du definerer avgjør hvorvidt kode for simulator eller kode for sal blir kompilert (se etter `#ifdef SIMULATOR` og `#ifdef SAL` i elev.c og elev.h hvis du er nysgjerrig).

## Litt mer info om simulatoren

Inne i simulatoren kan du "trykke" på bestillingsknapper med qwe (opp), sdf (ned), zxcv (inni heisen).

Teknisk info og bedre bruksanvisning for simulatoren finner du på https://github.com/TTK4145/Simulator-v2

For å avslutte simulatoren kan du trykke `ctrl+c`.

## Litt mer info om driveren

elev.c og elev.h er satt opp på følgende måte:

~~~c
#define SIMULATOR   // #define SIMULATOR hvis du skal kjøre heisen i simulator
//#define SAL       // #define SAL hvis du skal kjøre heisprogrammet i heisen på sanntidssal.


#ifdef SIMULATOR

  // Her ligger driveren for simulatoren.
  // Denne koden kjøres hvis du har satt inn #define SIMULATOR øverst i fila.

#endif //#ifdef SIMULATOR

#ifdef SAL

  // Her ligger driveren for den fysiske heisen på sal.
  // Denne koden kjøres hvis du har satt inn #define SAL øverst i fila.

#endif //#ifdef SAL
~~~


## Takk til

Dette repoet tar utgangspunkt i simulatoren og driveren fra TTK4145:
* https://github.com/TTK4145/Simulator-v2
* https://github.com/TTK4145/driver-c

SimElevatorServer og SimElevatorServer.exe som er lagt med i dette repoet er versjon v1.5 fra TTK4145/Simulator-v2.
