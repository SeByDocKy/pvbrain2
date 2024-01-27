# Carte Option `Fil_Pilote`
Pour en savoir d'avantage sur la carte Optionel `Fil_Pilote`, rendez-vous sur le Github de [![Static Badge](https://img.shields.io/badge/Dackara-black?logo=git&style=flat)](https://github.com/Dackara/Fil_Pilote).

![alt text](https://github.com/Dackara/Fil_Pilote/blob/main/Image/Photo/IMG_3848.JPG)

## Le Fil Pilote, qu'est-ce que c'est ? A quoi ça sert ?
Le "Fil Pilote" est un système Français inventé dans les années 80/90 pour piloter de façon centralisée et par plages horaires, les thermostats des systèmes de chauffage.

A la suite d'une concertation entre les grandes marques françaises d'appareils de chauffage, cette technologie est devenue un "standard de marché" pour les logements neufs construits à partir de 1995.

À l’aube des années 2000, la norme RT2000, rend sa présence obligatoire (par la réception de 4 ordres de contrôle) dans les logement neuf.

Peut de temps après, le protocole d'origine à 4 ordres évoluera pour un contrôle à 6 ordres, les deux dernier n'étant eux, pas obligatoire.

Le Fil Pilote permet ainsi, d'adapter au mieux, la production de chaleur, au moment d'occupation du logement. Une économie d'énergie d'environ 20% étant alors génralement constaté.

## Mais alors ? Comment ça fonctionne ?
Le principe est simple : Par un fil dédié à cet usage, les radiateurs électriques, reçoivent sous forme de signaux électriques de faible intensité, des ordres simples pour contrôler leur état.

La régulation et la mesure de température reste cependant toujours réalisée par le thermostat de chaque appareil. 
- Fil pilote 4 ordres : Confort, éco, hors gel, arrêt
- Fil pilote 6 ordres (protocole défini par le GIFAM) : Confort, confort -1°C, confort -2°C, éco, hors gel, arrêt

> [!NOTE]
> ### La norme "Fil Pilote" :
> - Les ordres sont générés et pris en compte par rapport au neutre
> - Signaux électriques (tension efficace) : 230 volts, +115 volts, -115 volts / 0,1 Ampère max
> - Le standard GIFAM encadre l'impédance d'entrée des récepteurs entre 100k et 500 kilo ohms, ce qui permet de relier de nombreux appareils de chauffage sur la même ligne. Souvent de 10 à 20 selon les caractéristiques du matériel émetteur. Par exemple, un programmateur pouvant délivrer 30 mA peut commander environ 15 thermostats d'impédance 200 K ohms.
> - Les signaux "confort -1°C" et "confort -2°C" correspondent à des périodes de présence du 230 volts alternatifs de 3 et 7 secondes espacées de périodes d'absence de signal d'environ 5 minutes. Pour des raisons techniques, la prise en compte de ces ordres peut demander un délai de 5 minutes. Quand un récepteur 4 ordres reçoit ces ordres spéciaux, il les ignore et reste en mode confort.
>
>   - __Confort :__ température de consigne en usage normal réglable de 7 à 30 °C par l'utilisateur
>   - __Eco ou réduit :__ température de confort abaissée de 3,5°C
>   - __Hors gel :__ régulation réglée sur 7 à 8°C
>   - __Arrêt :__ mise à l'arrêt de l'appareil (ou délestage)

![alt text](https://github.com/Dackara/Fil_Pilote/blob/main/Image/3D_View.png)