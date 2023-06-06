# Global System for Mobile communication (GSM)

Le réseau GSM est basé sur le concept de cellule. La porté d'une antenne est séparé en plusieurs sous zone (cellule) qui se caractérise par :
- Sa puissance d'émissioon
- La fréquence de porteuse utilisée 
- Le réseau auquel elle est interconnectée

![](attachments/Pasted%20image%2020230606152618.png)

Il y a deux types de signaux perturbateurs :
- Les interférences (de puissance $I$) due aux signaux émis par les autres stations
- Le bruit (de puissance $N$) provenant principalement du bruit de fond du récepteur
$\rightarrow$ Rapport porteuse à bruit $\frac{C}{N+I}$ permettant de caractérisez l'environnement radio

## Architecture du réseau GSM

![](attachments/Pasted%20image%2020230606153254.png)

L'architecture est composé :
- Le **sous-système radio** qui gère la transmission radio
	- Le mobile
	- La station de base (BTS)
	- Un contrôler de station de base (BSC)
- Le **sous-système réseau** (NSS)
	- Mobile Switching Center (MSC)
	- Home Location Register (HLR)
		-  Contient toutes les informations relative aux abonnées ainsi qu'un certain nombre de données dynamique (position de l'abonné dans le réseau VLR, etc)
	- Authentification Center (AuC)
	- Visitor Location Register (VLR)
	- Equipment Identity Register (EIR)

Etapes d'un échange des informations de signalisation lors d'un appel vers un mobile (viens de ma tête et non du cours) :
1. /
2. Le téléphone demande au MSC de le connecter au telephone portant le MSISDN
3. Le MSC demande au HLR de lui établir la connection avec le téléphone portant Le MSISDN
4. Le HLR (qui connait la position du mobile) envoie un challenge au MSC (du téléphone cible) pour que la cible puisse y répondre à l'aide de sa clef $k_i$
5. La cible répond au HLR et si c'est correct, il lui attribue un TMSI
6. Le HLR donne le TMSI au MSC du demandeur
7. Le MSC du demandeur fait directement le lien avec le MSC de la cible (connection établie)

![](attachments/Pasted%20image%2020230606155103.png)

## Subscriber Identity Module (SIM)

La carte SIM contient beaucoup d'information tel que :
- **Clé $k_i$** qui est une valeur unique, connue de la seule carte SIM et du HLR
- **IMSI** qui est le numéro international de l'abonné
- **MSISDN** qui est le numéro d'appel d'un téléphone GSM
- **TMSI** qui est le numéro attribué temporairement par le réseau à un abonné

## Canal physique

Le GSM utilise une combinaison d'un multiplexage fréquentiel et d'un multiplexage temporel 

Chaque canal de communication est divisé en 8 intervalles de temps de $0,077 [ms]$ chacun. On défini donc une trame élémentaire de 8 intervalles pour une durée de $8 \times 0,577 = 4,615 \ [ms]$

Chaque téléphone peut communiqué pendant son intervalle de 0,077 ms