# PowerLine Communication (PLC)

PLC permet d'établir une connection entre deux appareils sur un réseau électrique

Principe : On module le signal portant les données sur la signal de la ligne a sous tension pour ensuite le démoduler à l'arrivé

![](attachments/Pasted%20image%2020230607094238.png)

Caractéristiques :
- Les opérateurs électrique transmettent des signaux sur le réseau électrique (exemple, basculement du mode nuit)
- Réseau électrique n'est pas conçu pour transmettre de l'information (difficile de transmettre de l'information)
- Utilise une bande de fréquence spécifique
- Se module a l'aide de ASK, FSK, SQPSK, ou QAM
- Utilise un mécanisme de multi porteuses de type [OFDM](4G.md)