Alimentation:
-- Une entree Alimentation 5v a connecter sur la carte mere.
-- Un convertisseur 5v/ 3.3v pour avoir un peu de puissance (Pzem, Relais, ect...)
-- Le 3.3v de l'ESP est separe et mis a disposition des entrees/sorties analogiques. (comme Pince DC et AC) 

Les 3 sortie UART sont dispos sur bornier
-- une des entrees a l'option convertisseur RS323/ TTL (UART0) 
-- 3 connecteurs PZEM + une sortie sur bornier (UART2) 
-- une des entree a l'option Linky (UART3) mais dispo aussi sur bornier sans l'option

Une carte PCF8075 pour 16 sortie en bus I2c
-- Possibilite de fixer une carte (4) Relais sur cette carte.
-- 2 sorties supplementaire bus I2c sur borniers

Options pour developpement future: 
-- Deux sorties Sondes Dallas
-- une sortie capteur dht22
-- Une entree Pince DC (J'ai ajoute un filtre RC suite a l'experience du routeur solaire).
-- Deux entrees Pince AC
-- Toutes les GPIOs utilisables sont sorties sur borniers de facon a pouvoir faire evoluer au maximum. 

 
