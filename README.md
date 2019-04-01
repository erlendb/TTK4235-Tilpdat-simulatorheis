Med denne greia kan du bruke heissimulatoren fra TTK4145 (https://github.com/TTK4145/Simulator-v2) på tilpdatheisen.
Bygger på driveren fra TTK4145  (https://github.com/TTK4145/driver-c)

1) Last ned SimElevatorServer.exe fra https://github.com/TTK4145/Simulator-v2/releases/tag/v1.5
2) Last ned elev.h og elev.c herfra
3) Lagre de gamle elev.c og elev.h i heisprogrammet ditt et lurt sted og bruk de du lastet ned herfra istedenfor.

4) Kjør SimElevatorServer.exe. Et eller annet sted står det "Disconnected". La simulatorvinduet stå åpent.
5) Kompiler heisprogrammet ditt med de nye filene og kjør det. Nå skal det stå "Connected" i simulatoren.

Inne i simulatoren kan du "trykke" på bestillingsknapper med qwerty (opp), asdf (ned), zxcv (inni heisen). Det står mer om det på https://github.com/TTK4145/Simulator-v2

Du må bytte tilbake til de gamle elev.c og elev.h når du skal bruke heisen på sal.
Elev.h og elev.c som du laster ned herfra bruker ikke io.c og io.h, så det kan hende du må ta vekk noen #include "io.h"-greier.
