# KEGA Projekt - Laboratórium aplikovaných technológií umelej inteligencie

## Zameranie projektu
Projekt sa zameriava na vybudovanie moderného laboratória aplikovaných technológií umelej
inteligencie pre priemysel. Laboratórium bude pozostávať z 5 rôznych pracovísk zameraných na
spracovanie obrazu, videa a zvuku pre priemyselné aplikácie. Pracoviská sú navrhnuté tak, aby mohli
byť nezávislé od operačného systému (Linux, Windows) a softvéru pre HNS (Matlab, Python, ...).
Laboratórium budú využívať študenti 3. ročníka bakalárskeho štúdia a študenti 1. a 2. ročníka
inžinierskeho štúdia na vybraných predmetoch a študenti bakalárskych, diplomových, individuálnych
a tímových prác, ale aj doktorandi. Plánujeme nasledovné pracoviská:

## Pracovisko 3 - Detekcia objektov v priemyselnej prevádzke pomocou hlbokých neurónových sietí
Počítačová zostava s výkonnou grafickou kartou, kvalitná hĺbková kamera, Nvidia Jetson
(Edge zariadenie), priemyselný riadiaci systém, existujúci robot (UR). Pracovisko pre detekciu
objektov pomocou hlbokého učenia vhodné napr. pre účely bin picking, pick & place.

### Detekcia objektov pomocou hlbokého učenia

Detekcia objektov predstavuje jednu z významných oblastí počítačového videnia, ktorej cieľom je automatická identifikácia a lokalizácia objektov v digitálnych obrazoch. 
Na rozdiel od klasifikácie obrazov, pri ktorej sa určuje príslušnosť celého obrazu k určitej triede, detekcia objektov umožňuje súčasne rozpoznať viacero objektov a určiť ich polohu pomocou ohraničujúcich obdĺžnikov (*bounding boxes*). 
V súčasnosti sa na riešenie tejto úlohy využívajú predovšetkým metódy hlbokého učenia založené na konvolučných neurónových sieťach (CNN) a vizuálnych transformeroch. M
edzi najznámejšie detektory patria **YOLO, SSD, Faster R-CNN a DETR**, ktoré sa odlišujú architektúrou, spôsobom detekcie a výpočtovou náročnosťou.

**Cieľom úlohy** je navrhnúť a experimentálne overiť vybrané modely hlbokého učenia na detekciu objektov v digitálnych obrazoch. 
V rámci riešenia sa realizuje príprava a anotácia obrazových dát, trénovanie alebo dotrénovanie predtrénovaných detektorov a následné vyhodnotenie ich úspešnosti. 
Pozornosť sa bude venovať porovnaniu jednotlivých modelov z hľadiska kvality detekcie pomocou metrík **Precision, Recall a mAP (mean Average Precision)**, ako aj ich výpočtovej náročnosti a rýchlosti spracovania obrazu.

#### Dataset detekcia defektov na podložkách - 4 typy defektov (jamka - circular_cavity, šrabanec - scratch, zárez – burr, prevýšenie materiálu - excess_material):
[Klasifikacia_defekty_Podložky](https://drive.google.com/drive/folders/1PVE357M-8uburXtl5kFwjo_nowSup1Xx?usp=drive_link)

Detekcia defektov pomocou YOLO detektora

[Detekcia_defekty_Podložky](https://drive.google.com/drive/folders/1QcswFcZ1FPBEZM2TyV8x0bvTimcJgAfQ?usp=drive_link)

[Detekcia_defekty_Podložky_Roboflow](https://universe.roboflow.com/hemorrhagesegmentation/tp26_detection)

**Priemyselné datasety**
Dataset povrchových defektov oceľového pásu  – NEU Surface defect Dataset
Klasifikácia defektov oceľového plechu, 6 skupín (valcované okuje (RS), škvrny (Pa), praskliny (Cr), jamkovitý povrch (PS), inklúzie (In) a škrabance (Sc))
( [Dataset_NEU_DET](https://www.kaggle.com/datasets/rdsunday/neu-urface-defect-database) )

Magnetic Tile Defect Dataset
Dataset na namierený na kontrolu kvality produktov v továrňach na magnetické dlaždice v provincii Zhejiang v Číne, najväčšej výrobnej základni magnetických dlaždíc na svete. 
Na zmiernenie ľudskej práce bolo navrhnutých mnoho techník spracovania obrazu, ktoré sa pokúšajú o vykonanie takýchto kontrolných úloh. 
Pri automatickej detekcii poškodenia magnetických dlaždíc sa vyskytlo niekoľko úzkych miest, vrátane zložitosti textúry, rozmanitosti tvarov defektov a náhodnosti svetelných podmienok na magnetických dlaždiciach. 
Cieľové defekty sú praskliny, zlomy a strapce.
( [Dataset_Magnetic_Tile](https://www.kaggle.com/datasets/alex000kim/magnetic-tile-surface-defects) )

GC10-DET - Metallic Surface Defect Detection
Detekcia defektov kovových povrchov je nevyhnutný a nevyhnutný proces na kontrolu kvality priemyselných výrobkov. 
Vzhľadom na obmedzený rozsah údajov a kategórie defektov však existujúce súbory údajov o defektoch vo všeobecnosti nie sú k dispozícii na nasadenie detekčného modelu. 
Na riešenie tohto problému prispievame novým súborom údajov s názvom GC10-DET na detekciu defektov kovových povrchov vo veľkom meradle. 
Súbor údajov GC10-DET má veľké výzvy, pokiaľ ide o kategórie defektov, počet obrázkov a rozsah údajov. 
( [Dataset_GC10_DET](https://www.kaggle.com/datasets/alex000kim/gc10det/data) )

AL10-DET (Aluminum 10 Defect Detection Dataset) 
je dataset určený na detekciu povrchových defektov hliníkových profilov pomocou metód objektovej detekcie.
AL10-DET obsahuje snímky povrchu extrudovaných hliníkových profilov získané v priemyselných výrobných podmienkach.
( [Dataset_AL10_DET](https://www.kaggle.com/datasets/arcanine9/al10-det/data) )

Dosiahnuté výsledky:
- Szépvölgyi, Porovnanie detektorov na priemyselných datasetov, Projekt HNS, 2025, [Vysledky_HNS_Projekt_Szépvölgyi](document/Prezentacia_Szepvolgyi_Porovnanie_detektorov.pdf)

- Mihálik, Testovanie vnútorných štruktúr materiálov metódami UI, DP FEI STU Bratislava, 2026, [Prezentacia_DP_Mihalik_Detekcia_defektov_zvarov_ultrazvuk](document/Prezentacia_DP_Mihalik_Detekcia_defektov_zvarov_ultrazvuk.pdf)

Literatúra:
- S. Kajan, M. Trebuľa, F. Duchoň, Z. Kovaríková, M. Kováč and J. Pavlovičová, "Weld Defect Recognition and Detection from Video Using Deep Learning Methods," 2025 Cybernetics & Informatics (K&I), Mikulov na Morave, Czech Republic, 2025, pp. 1-5, doi: 10.1109/KI64036.2025.10916449. [Kajan_kol_Weld_Defect_Recognition](https://ieeexplore.ieee.org/document/10916449)

- Körösi L., Kajan S., Berki M., Skirkanič J., Lúčny M., Melichar A., Mihálik J., From Detection to Action: Implementing Deep Learning Inference in PLC Systems via Docker Services,
IFAC-PapersOnLine, Volume 58, Issue 9, 2024, [Korosi_kol_Detection_Action](https://doi.org/10.1016/j.ifacol.2024.07.365)
- 