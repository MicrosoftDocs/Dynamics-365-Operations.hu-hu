---
title: Common Data Service-entitások
description: A Microsoft Dynamics 365 Human Resources a Common Data Service használatával biztosítja a bővíthetőségi és az integrációs eseteket.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 85dd95e8209fff28f214986f7960372db200351b
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009327"
---
# <a name="common-data-service-entities"></a>Common Data Service-entitások

A Microsoft Dynamics 365 Human Resources a Common Data Service használatával biztosítja a bővíthetőségi és az integrációs eseteket.

A Common Data Service eltávolításával kapcsolatban a következő témakör tartalmaz további tájékoztatást: [Mi a Common Data Service?](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).

A Human Resources rendszerhez a következő erőforrások állnak rendelkezésére a Common Data Service szolgáltatásban.

## <a name="benefit-entities"></a>Juttatási egységek

**Juttatás számítási gyakorisága**

| **Mezők**        | **Adattípus** | **Szükséges** | **Kereshető** |
|-------------------|---------------|--------------|----------------|
| Leírás       | Text          |              | X              |
| Gyakoriság ellenőrzése | Értékkészlet    | X            | X              |
| Megváltoztatható      | Két lehetőség   |              | X              |
| Név              | Text          | X            | X              |


**Juttatás számítási mértéke**

| **Mezők**  | **Adattípus** | **Szükséges** | **Kereshető** |
|-------------|---------------|--------------|----------------|
| Leírás | Text          |              | X              |
| Név        | Text          | X            | X              |
| Szint típusa    | Értékkészlet    | X            | X              |


**Juttatás számítási mértékének részletei**

| **Mezők**                             | **Adattípus**  | **Szükséges** | **Kereshető** |
|----------------------------------------|----------------|--------------|----------------|
| Juttatás számítási mértékének részletei | Text           | X            | X              |
| Számítási díj azonosítója                    | Keresés         | X            | X              |
| Hozzájárulási módszer                    | Értékkészlet     | X            | X              |
| Hatályos                              | Csak dátum      | X            | X              |
| Munkáltatói hozzájárulás                  | Tizedesérték |              | X              |
| Lejárat                             | Csak dátum      | X            | X              |
| Dolgozó levonása                        | Tizedesérték |              | X              |


**Juttatás típusa**

| **Mezők**           | **Adattípus** | **Szükséges** | **Kereshető** |
|----------------------|---------------|--------------|----------------|
| Párhuzamos regisztráció | Értékkészlet    |              | X              |
| Leírás          | Text          |              | X              |
| Név                 | Text          | X            | X              |
| Bérlista-kategória      | Értékkészlet    |              | X              |


**Juttatási konstrukció**

| **Mezők**                               | **Adattípus**  | **Szükséges** | **Kereshető** |
|------------------------------------------|----------------|--------------|----------------|
| Hátralékkorlátozási módszer                      | Értékkészlet     |              | X              |
| Juttatás típusa                             | Keresés         | X            | X              |
| Hozzájárulás-korlátozási módszer                | Értékkészlet     |              | X              |
| Hozzájárulási módszer                      | Értékkészlet     |              | X              |
| Pénznem                                 | Keresés         |              | X              |
| Levonás prioritása                       | Egész szám   |              | X              |
| Alapértelmezett hozzájárulási korlát összege        | Pénznem       |              | X              |
| Alapértelmezett hozzájárulás-korlátozási összeg (alap) | Pénznem       |              | X              |
| Alapértelmezett hozzájárulási korlát időszaka        | Értékkészlet     |              | X              |
| Alapértelmezett levonási korlát összege           | Pénznem       |              | X              |
| Alapértelmezett levonáskorlátozási összeg (alap)    | Pénznem       |              | X              |
| Alapértelmezett levonási korlát időszaka           | Értékkészlet     |              | X              |
| Leírás                              | Text           |              | X              |
| Árfolyam                            | Tizedesérték |              | X              |
| További bérlistafuttatás                | Két lehetőség    |              | X              |
| Bejelentendő az Affordable Care Act értelmében.        | Két lehetőség    |              | X              |
| Hátralék létrehozva                      | Két lehetőség    |              | X              |
| Bruttósított                              | Két lehetőség    |              | X              |
| Elsődleges                               | Két lehetőség    |              | X              |
| Név                                     | Text           | X            | X              |
| Bérlista hatása                           | Értékkészlet     |              | X              |
| Nyugdíjazás típusa                          | Értékkészlet     |              | X              |


**Foglalkoztatási entitás**

| **Mezők**                     | **Adattípus**  | **Szükséges** | **Kereshető** |
|--------------------------------|----------------|--------------|----------------|
| Dolgozó módosított kezdési dátuma     | Dátum és idő  |              | X              |
| Cég                        | Keresés         | X            | X              |
| Felmondási összeghez tartozó munkáltatói egység | Tizedesérték |              | X              |
| Értesítéshez tartozó munkáltatói egység        | Értékkészlet     |              | X              |
| Munkaviszony záró dátuma            | Dátum és idő  |              | X              |
| Foglalkoztatási szám              | Text           | X            | X              |
| Foglalkoztatás kezdő dátuma          | Dátum és idő  |              | X              |
| Utolsó munkában töltött nap              | Dátum és idő  |              | X              |
| Áttérés dátuma                | Dátum és idő  |              | X              |
| Érvényesség kezdete                     | Dátum és idő  | X            | X              |
| Érvényesség vége                       | Dátum és idő  |              | X              |
| Dolgozó                         | Keresés         | X            | X              |
| Dolgozónak járó felmondási összeg           | Tizedesérték |              | X              |
| Dolgozó kezdési dátuma             | Dátum és idő  |              | X              |
| Dolgozó típusa                    | Értékkészlet     | X            | X              |
| Értesítéshez tartozó dolgozói egység          | Értékkészlet     |              | X              |

## <a name="worker-entities"></a>Dolgozói entitások

**Etnikum**

| **Mezők**         | **Adattípus** | **Szükséges** | **Kereshető** |
|--------------------|---------------|--------------|----------------|
| Leírás        | Text          |              | X              |
| Etnikum neve | Text          | X            | X              |


**Nyelv**

| **Mezők**    | **Adattípus** | **Szükséges** | **Kereshető** |
|---------------|---------------|--------------|----------------|
| Leírás   | Text          |              | X              |
| Nyelv neve | Text          | X            | X              |


**Veteránállapot**

| **Mezők**           | **Adattípus** | **Szükséges** | **Kereshető** |
|----------------------|---------------|--------------|----------------|
| Leírás          | Text          |              | X              |
| Védett veterán | Két lehetőség    |              | X              |
| Nyelv neve        | Text          | X            | X              |


**Dolgozó**

| **Mezők**                | **Adattípus** | **Szükséges** | **Kereshető** |
|---------------------------|---------------|--------------|----------------|
| Születési dátum                 | Csak dátum     |              | X              |
| Leírás               | Text          |              | X              |
| 1. e-mail-cím           | E-mail-cím         |              | X              |
| 2. e-mail-cím           | E-mail-cím         |              | X              |
| Facebook-azonosító         | Text          |              | X              |
| Utónév                | Text          |              | X              |
| Teljes név                 | Text          |              | X              |
| Nem                    | Értékkészlet    |              | X              |
| Létrehozás                | Text          |              | X              |
| E-mailes kapcsolattartás engedélyezve  | Két lehetőség   |              | X              |
| Telefonos kapcsolattartás engedélyezve  | Két lehetőség   |              | X              |
| Vezetéknév                 | Text          |              | X              |
| LinkedIn-azonosító         | Text          |              | X              |
| Vezető                   | Keresés        |              | X              |
| Második utónév               | Text          |              | X              |
| Mobiltelefonszám              | Telefonszám         |              | X              |
| Office Graph-azonosító   | Text          |              | X              |
| Elsődleges e-mail-cím     | E-mail-cím         |              | X              |
| Elsődleges telefonszám         | Telefonszám         |              | X              |
| Szakma                | Text          |              | X              |
| 1. közösségi hálózat          | Értékkészlet    |              | X              |
| 2. közösségi hálózat          | Értékkészlet    |              | X              |
| 1. közösségi hálózatbeli azonosító | Text          |              | X              |
| 2. közösségi hálózatbeli azonosító | Text          |              | X              |
| Forrás                    | Értékkészlet    | X            | X              |
| Állapot                    | Értékkészlet    | X            | X              |
| 1. telefonszám               | Telefonszám         |              | X              |
| 2. telefonszám               | Telefonszám         |              | X              |
| 3. telefonszám               | Telefonszám         |              | X              |
| Twitter-azonosító          | Text          |              | X              |
| Felhasználó                      | Keresés        |              | X              |
| Webhely URL-címe               | URL-cím           |              | X              |
| Dolgozó száma             | Text          | X            | X              |
| Dolgozó típusa               | Értékkészlet    | X            | X              |
| Yomi utónév           | Text          |              | X              |
| Yomi teljes név            | Text          |              | X              |
| Yomi vezetéknév            | Text          |              | X              |
| Yomi második utónév          | Text          |              | X              |


**Dolgozó címe**

| **Mezők**           | **Adattípus**  | **Szükséges** | **Kereshető** |
|----------------------|----------------|--------------|----------------|
| Cím száma       | Text           | X            | X              |
| Cím típusa         | Értékkészlet     | X            | X              |
| Város                 | Text           |              | X              |
| Ország vagy régió    | Text           |              | X              |
| Megye               | Text           |              | X              |
| Faxszám                  | Telefonszám          |              | X              |
| Preferált         | Két lehetőség    |              | X              |
| Földrajzi szélesség             | Tizedesérték |              | X              |
| 1. sor               | Text           |              | X              |
| 2. sor               | Text           |              | X              |
| 3. sor               | Text           |              | X              |
| Földrajzi hosszúság            | Tizedesérték |              | X              |
| Irányítószám          | Text           |              | X              |
| Postafiók száma      | Text           |              | X              |
| Szállítási mód kódja | Egész szám   |              | X              |
| Állam vagy tartomány    | Text           |              | X              |
| 1. telefonszám          | Telefonszám          |              | X              |
| 2. telefonszám          | Telefonszám          |              | X              |
| 3. telefonszám          | Telefonszám          |              | X              |
| UPS-zóna             | Text           |              | X              |
| UTC-eltérés           | Egész szám   |              | X              |
| Dolgozó               | Keresés         | X            | X              |


**Dolgozói személyes adat**

| Mezők                             | Adattípus    | Kötelező | Kereshető |
|------------------------------------|--------------|----------|------------|
| Születési település                         | Text         |          | X          |
| Szülőország vagy -régió            | Értékkészlet   |          | X          |
| Születési dátum                          | Csak dátum    |          | X          |
| Állampolgárság (ország vagy régió)      | Értékkészlet   |          | X          |
| Elhalálozás dátuma                      | Csak dátum    |          | X          |
| Rokkant veterán igazolási dátuma | Csak dátum    |          | X          |
| Végzettség                          | Text         |          | X          |
| Etnikum                     | Keresés       |          | X          |
| Kivándorlás záró dátuma                  | Csak dátum    |          | X          |
| Kivándorlás kezdő dátuma                | Csak dátum    |          | X          |
| Apa szülőországa vagy -régiója     | Értékkészlet   |          | X          |
| Nem                             | Értékkészlet   |          | X          |
| Rokkant                        | Két lehetőség  |          | X          |
| Rokkant veterán                | Két lehetőség  |          | X          |
| Kivándorlókra vonatkozó szabályok alkalmazandók    | Két lehetőség  |          | X          |
| Nappali tagozatos hallgató               | Két lehetőség  |          | X          |
| Családi állapot                     | Értékkészlet   |          | X          |
| Katonai szolgálat záró dátuma          | Csak dátum    |          | X          |
| Katonai szolgálat kezdő dátuma        | Csak dátum    |          | X          |
| Anya szülőországa vagy -régiója     | Értékkészlet   |          | X          |
| Állampolgárság országa vagy régiója      | Értékkészlet   |          | X          |
| Anyanyelv                    | Keresés       |          | X          |
| Eltartott személyek száma               | Egész szám |          |            |
| Veteránállapot                     | Keresés       |          | X          |
| Dolgozó                             | Keresés       | X        | X          |
| Dolgozó személyzeti száma      | Text         | X        | X          |


**Dolgozói bankszámla**

| **Mezők**                 | **Adattípus** | **Szükséges** | **Kereshető** |
|----------------------------|---------------|--------------|----------------|
| Számlatulajdonos             | Text          |              | X              |
| Számla azonosítója     | Text          |              | X              |
| Cím leírása        | Text          |              | X              |
| Bankszámla típusa          | Értékkészlet    |              | X              |
| Bank helykódja         | Text          |              | X              |
| Bankfiók neve                | Text          |              | X              |
| Bankfiók száma              | Text          |              | X              |
| Város                       | Text          |              | X              |
| Ország vagy régió          | Text          |              | X              |
| Megye                     | Text          |              | X              |
| Leírás                | Text          |              | X              |
| Körzet neve              | Text          |              | X              |
| E-mail-cím                      | Text          |              | X              |
| Kiterjesztés                  | Text          |              | X              |
| Faxszám                        | Text          |              | X              |
| IBAN                       | Text          |              | X              |
| 1. sor                     | Text          |              | X              |
| 2. sor                     | Text          |              | X              |
| 3. sor                     | Text          |              | X              |
| Mobiltelefonszám               | Text          |              | X              |
| Személy neve             | Text          |              | X              |
| Irányítószám                | Text          |              | X              |
| Postafiók száma            | Text          |              |                |
| Útvonalszám             | Text          |              | X              |
| Útvonalszám típusa        | Értékkészlet    |              | X              |
| Állam vagy tartomány          | Text          |              | X              |
| SWIFT-kód                 | Text          |              | X              |
| Telefonszám                  | Text          |              | X              |
| Telexszám               | Text          |              | X              |
| Webhely URL-címe                | Text          |              | X              |
| Dolgozó                     | Keresés        | X            | X              |
| Dolgozó bankszámlaszáma | Text          |              | X              |
| Dolgozó bankszámlaszáma | Text          | X            | X              |

**Dolgozói fix kompenzáció**

| Mezők                                | Adattípus      | Kötelező | Kereshető |
|---------------------------------------|----------------|----------|------------|
| Cég                               | Keresés         | X        | X          |
| Kompenzáció típusa                     | Értékkészlet     |          | X          |
| Pénznem                              | Keresés         |          | X          |
| Érvényesség dátuma                        | Csak dátum      |          | X          |
| Esemény                                 | Keresés         | X        | X          |
| Árfolyam                         | Tizedesérték |          | X          |
| Lejárat dátuma                       | Csak dátum      |          | X          |
| Sor száma                           | Tizedesérték |          | X          |
| Fizetési gyakoriság                         | Keresés         | X        | X          |
| Fizetési díjalap                              | Pénznem       |          | X          |
| Fizetési díjalap (alap)                       | Pénznem       |          | X          |
| Konstrukció                                  | Keresés         | X        | X          |
| Beosztás                              | Keresés         | X        | X          |
| Folyamat típusa                          | Értékkészlet     | X        | X          |
| Hivatkozási pont beállítási sora            | Keresés         |          | X          |
| Dolgozó                                | Keresés         | X        | X          |
| Dolgozói fix kompenzáció száma      | Text           | X        | X          |

**Dolgozó személyazonosító száma**

| Mezők                 | Adattípus   | Kötelező | Kereshető |
|------------------------|-------------|----------|------------|
| Leírás            | Text        |          | X          |
| Bejegyzéstípus             | Text        |          | X          |
| Lejárat dátuma        | Csak dátum   |          | X          |
| Azonosítószám  | Text        | X        | X          |
| Azonosító típusa    | Keresés      | X        | X          |
| Elsődleges             | Két lehetőség |          | X          |
| Kiadás dátuma             | Csak dátum   |          | X          |
| Kibocsátó hatóság         | Keresés      | X        | X          |
| Dolgozó                 | Keresés      | X        | X          |


## <a name="position-entities"></a>Beosztásentitások

**Feladat beosztása**

| **Mezők**               | **Adattípus**  | **Szükséges** | **Kereshető** |
|--------------------------|----------------|--------------|----------------|
| Aktiválás               | Dátum és idő  |              | X              |
| Elérhető hozzárendeléshez | Dátum és idő  |              | X              |
| Részleg                | Keresés         |              | X              |
| Leírás              | Text           |              | X              |
| Teljes munkaidővel egyenértékű     | Tizedesérték |              | X              |
| Állás                      | Keresés         | X            | X              |
| Feladat beosztásának száma      | Text           | X            | X              |
| Szülőfeladat beosztása      | Keresés         |              | X              |
| Beosztás típusa            | Keresés         |              | X              |
| Megszüntetés               | Dátum és idő  |              | X              |
| Beosztás                    | Értékkészlet     |              | X              |
| Érvényesség kezdete               | Dátum és idő  | X            | X              |
| Érvényesség vége                 | Dátum és idő  |              | X              |


**Beosztás típusa**

| **Mezők**         | **Adattípus** | **Szükséges** | **Kereshető** |
|--------------------|---------------|--------------|----------------|
| Osztályozás     | Értékkészlet    |              | X              |
| Leírás        | Text          |              | X              |
| Beosztástípus neve | Text          | X            | X              |


**Beosztáshoz rendelt dolgozó**

| **Mezők**                        | **Adattípus** | **Szükséges** | **Kereshető** |
|-----------------------------------|---------------|--------------|----------------|
| Feladat pozíciója                      | Keresés        | X            | X              |
| Beosztás dolgozói hozzárendelési száma | Text          | X            | X              |
| Érvényesség kezdete                        | Text          | X            | X              |
| Érvényesség vége                          |               |              | X              |
| Dolgozó                            |               | X            | X              |

## <a name="job-entities"></a>Feladat entitásai

**Munka**

| **Mezők**                   | **Adattípus**  | **Szükséges** | **Kereshető** |
|------------------------------|----------------|--------------|----------------|
| Korlátlan beosztások engedélyezése    | Két lehetőség    |              | X              |
| Teljes munkaidőssel egyenértékű | Tizedesérték |              | X              |
| Leírás                  | Text           |              | X              |
| Munkaköri leírás              | Text           |              | X              |
| Beosztás funkciója                 | Keresés         |              | X              |
| Feladattípus                     | Keresés         |              | X              |
| Beosztások maximális száma  | Egész szám   |              | X              |
| Név                         | Text           | X            | X              |
| Beosztás                        | Értékkészlet     |              | X              |
| Érvényesség kezdete                   | Dátum és idő  | X            | X              |
| Érvényesség vége                     | Dátum és idő  |              | X              |


**Beosztás**

| **Mezők**        | **Adattípus** | **Szükséges** | **Kereshető** |
|-------------------|---------------|--------------|----------------|
| Leírás       | Text          | X            | X              |
| Beosztás funkciójának neve | Text          | X            | X              |


**Feladattípus**

| **Mezők**    | **Adattípus** | **Szükséges** | **Kereshető** |
|---------------|---------------|--------------|----------------|
| Leírás   | Text          | X            | X              |
| Mentességi állapot | Értékkészlet    | X            | X              |
| Feladattípus neve | Text          | X            | X              |

## <a name="leave-and-absence-entities"></a>Szabadság- és távollétentitások

**Szabadság regisztrációja**

| **Mezők**            | **Adattípus** | **Szükséges** | **Kereshető** |
|-----------------------|---------------|--------------|----------------|
| Elhatárolási dátum alapja    | Csak dátum     | X            | X              |
| Elhatárolás kezdő dátuma    | Csak dátum     | X            | X              |
| Egyéni dátum           | Csak dátum     | X            | X              |
| Elhatárolás felfüggesztve  | Két lehetőség   |              | X              |
| Szabadság regisztrációs száma | Text          | X            | X              |
| Szabadságterv            | Keresés        | X            | X              |
| Kezdő dátum            | Csak dátum     | X            | X              |
| Szintalap            | Értékkészlet    | X            | X              |
| Dolgozó                | Keresés        | X            | X              |


**Szabadság banki tranzakciója**

| **Mezők**                    | **Adattípus**  | **Szükséges** | **Kereshető** |
|-------------------------------|----------------|--------------|----------------|
| Összeg                        | Tizedesérték | X            | X              |
| Cég                       | Keresés         | X            | X              |
| Szabadság banki tranzakciójának száma | Text           | X            | X              |
| Szabadságterv                    | Keresés         |              | X              |
| Szabadság típusa                    | Keresés         | X            | X              |
| Tranzakció dátuma              | Csak dátum      | X            | X              |
| Tranzakció száma            | Tizedesérték | X            | X              |
| Tranzakció típusa              | Értékkészlet     | X            | X              |
| Dolgozó                        | Keresés         | X            | X              |


**Szabadságterv**

| **Mezők**        | **Adattípus** | **Szükséges** | **Kereshető** |
|-------------------|---------------|--------------|----------------|
| Könyvelés gyakorisága | Értékkészlet    | X            | X              |
| Cég           | Keresés        | X            | X              |
| Leírás       | Text          |              | X              |
| Szabadság típusa        | Keresés        | X            | X              |
| Név              | Text          | X            | X              |
| Kezdő dátum        | Csak dátum     | X            | X              |


**Szabadságkérelem**

| **Mezők**           | **Adattípus** | **Szükséges** | **Kereshető** |
|----------------------|---------------|--------------|----------------|
| Megjegyzés              | Text          | X            | X              |
| Cég              | Keresés        | X            | X              |
| Szabadságkérelem száma | Text          |              | X              |
| Kérelem dátuma         | Dátum és idő | X            | X              |
| Állapot               | Értékkészlet    | X            | X              |
| Dolgozó               | Keresés        | X            | X              |


**Szabadságkérelem részletes adatai**

| **Mezők**                  | **Adattípus**  | **Szükséges** | **Kereshető** |
|-----------------------------|----------------|--------------|----------------|
| Összeg                      | Tizedesérték | X            | X              |
| Szabadság dátuma                  | Dátum és idő  | X            | X              |
| Szabadságkérelem               | Keresés         | X            | X              |
| Szabadságkérelem részletes adatai | Text           | X            | X              |
| Szabadság típusa                  | Keresés         | X            | X              |


**Szabadság típusa**

| **Mezők**      | **Adattípus** | **Szükséges** | **Kereshető** |
|-----------------|---------------|--------------|----------------|
| Cég         | Keresés        | X            | X              |
| Leírás     | Text          |              | X              |
| Bevételkód    | Keresés        |              | X              |
| Szabadságtípus neve | Text          | X            | X              |


**Munkanaptár**

| **Mezők**  | **Adattípus** | **Szükséges** | **Kereshető** |
|-------------|---------------|--------------|----------------|
| Cég     | Keresés        | X            | X              |
| Leírás | Text          |              | X              |
| Név        | Text          | X            | X              |


**Munkanaptár napja**

| **Mezők**               | **Adattípus** | **Szükséges** | **Kereshető** |
|--------------------------|---------------|--------------|----------------|
| Naptári dátum            | Csak dátum     | X            | X              |
| Cég                  | Keresés        |              | X              |
| Állapot                   | Text          |              | X              |
| Munkanaptár            | Keresés        | X            | X              |
| Munkanaptár napjának száma | Text          | X            | X              |


**Munkanaptári ünnep**

| **Mezők**  | **Adattípus** | **Szükséges** | **Kereshető** |
|-------------|---------------|--------------|----------------|
| Név        | Text          |              | X              |
| Leírás | Text          | X            | X              |


**Munkanaptári ünnepsor**

| **Mezők**                        | **Adattípus** | **Szükséges** | **Kereshető** |
|-----------------------------------|---------------|--------------|----------------|
| Ünnep dátuma                      | Csak dátum     | X            | X              |
| Név                              | Text          |              | X              |
| Munkanaptári ünnep             | Keresés        | X            | X              |
| Munkanaptár ünnepsorának száma | Text          | X            | X              |


**Munkanaptár időintervalluma**

| **Mezők**                         | **Adattípus** | **Szükséges** | **Kereshető** |
|------------------------------------|---------------|--------------|----------------|
| Cég                            | Keresés        |              | X              |
| Befejezés ideje                           | Egész szám  |              | X              |
| Kezdési idő                         | Egész szám  |              | X              |
| Munkanaptár                      | Keresés        | X            | X              |
| Munkanaptár napja                  | Keresés        | X            | X              |
| Munkanaptár időintervallumának száma | Text          | X            | X              |

## <a name="organization-entities"></a>Szervezeti entitások

**Vállalat**

| **Mezők**   | **Adattípus** | **Szükséges** | **Kereshető** |
|--------------|---------------|--------------|----------------|
| Vállalat kódja | Text          | X            | X              |
| Név         | Text          | X            | X              |


**Részleg**

| **Mezők**        | **Adattípus** | **Szükséges** | **Kereshető** |
|-------------------|---------------|--------------|----------------|
| Részleg száma | Text          | X            | X              |
| Leírás       | Text          |              | X              |
| Név              | Text          | X            | X              |
| Szülőrészleg | Keresés        |              | X              |


**Pénznem**

| **Mezők**         | **Adattípus**  | **Szükséges** | **Kereshető** |
|--------------------|----------------|--------------|----------------|
| Pénznemkód      | Text           | X            | X              |
| Pénznem neve      | Text           | X            | X              |
| Pénznem pontossága | Egész szám   | X            | X              |
| Pénznemszimbólum    | Text           | X            | X              |
| Entitás képe       | Kép          |              |                |
| Árfolyam      | Tizedesérték | X            | X              |
| Szervezet       | Keresés         | X            | X              |
| Állapot             | Értékkészlet     |              | X              |

## <a name="payroll-entities"></a>Bérlistaentitás

**Fizetési ciklus**

| **Mezők**  | **Adattípus** | **Szükséges** | **Kereshető** |
|-------------|---------------|--------------|----------------|
| Leírás | Text          | X            | X              |
| Gyakoriság   | Értékkészlet    | X            | X              |
| Név        | Text          | X            | X              |


**Fizetési időszak**

| **Mezők**           | **Adattípus** | **Szükséges** | **Kereshető** |
|----------------------|---------------|--------------|----------------|
| Alapértelmezett fizetési dátum | Csak dátum     |              | X              |
| Leírás          | Text          |              | X              |
| Fizetési ciklus            | Keresés          | X            | X              |
| Fizetési időszak száma    | Text          | X            | X              |
| Időszak záró dátuma      | Csak dátum     | X            | X              |
| Időszak kezdő dátuma    | Csak dátum     | X            | X              |
| Állapot               | Értékkészlet    |              | X              |


**Bérlista bevételkódja**

| **Mezők**              | **Adattípus** | **Szükséges** | **Kereshető** |
|-------------------------|---------------|--------------|----------------|
| Leírás             | Text          | X            | X              |
| Felvétel a fizetési típusba | Értékkészlet    | X            | X              |
| Produktív           | Két lehetőség   | X            | X              |
| Név                    | Text          |              | X              |
| Mennyiség egysége           | Értékkészlet    |              | X              |
| FMLA-órák nyomon követése        | Két lehetőség   |              | X              |


**Adórégió**

| **Mezők**        | **Adattípus** | **Szükséges** | **Kereshető** |
|-------------------|---------------|--------------|----------------|
| Város              | Text          |              | X              |
| Ország vagy régió | Text          |              | X              |
| Megye            | Text          |              | X              |
| Név              | Text          | X            | X              |
| Állam vagy tartomány | Text          |              | X              |


**Fizetési időszak juttatásszámítási gyakorisága**

| **Mezők**                                      | **Adattípus** | **Szükséges** | **Kereshető** |
|-------------------------------------------------|---------------|--------------|----------------|
| Juttatás számítási gyakorisága                   | Keresés        | X            | X              |
| Fizetési időszak juttatásszámítási gyakoriságának száma | Text          | X            | X              |
| Fizetési időszak                                      | Keresés        | X            | X              |


**Bankszámla kifizetései**

| **Mezők**                       | **Adattípus**  | **Szükséges** | **Kereshető** |
|----------------------------------|----------------|--------------|----------------|
| Összeg                           | Pénznem       |              | X              |
| Összeg (alap)                    | Pénznem       |              | X              |
| Bankszámla                     | Keresés         | X            | X              |
| Bankszámla kifizetéseinek száma | Text           | X            | X              |
| Cég                          | Keresés         | X            | X              |
| Pénznem                         | Keresés         |              | X              |
| Árfolyam                    | Tizedesérték |              | X              |
| Fennmaradó                     | Két lehetőség    |              | X              |
| Prioritás                         | Egész szám   |              | X              |

**Személyazonosító kiállító hatósága**

| **Mezők**           | **Adattípus** | **Szükséges** | **Kereshető** |
|----------------------|---------------|--------------|----------------|
| Cím leírása  | Text          |              | X              |
| Cím 1. sora       | Text          |              | X              |
| Cím 2. sora       | Text          |              | X              |
| Cím 3. sora       | Text          |              | X              |
| Város                 | Text          |              | X              |
| Ország vagy régió    | Értékkészlet    |              | X              |
| Megye               | Text          |              | X              |
| Leírás          | Text          |              | X              |
| E-mail-cím                | Text          |              | X              |
| Kiterjesztés            | Text          |              | X              |
| Faxszám                  | Text          |              | X              |
| Kibocsátó hatóság neve  | Text          | X            | X              |
| Mobiltelefonszám         | Text          |              | X              |
| Oldal                 | Text          |              | X              |
| Irányítószám          | Text          |              | X              |
| Postafiók száma      | Text          |              | X              |
| SMS                  | Text          |              | X              |
| Állam vagy tartomány    | Text          |              | X              |
| Telefonszám            | Text          |              | X              |
| Telex                | Text          |              | X              |
| Webhely URL-címe          | Text          |              | X              |

**Dolgozó személyazonosító típusa**

| **Mezők**                        | **Adattípus**  | **Szükséges** | **Kereshető** |
|-----------------------------------|----------------|--------------|----------------|
| Megengedett értékek                    | Értékkészlet     |              | X              |
| Ország vagy régió                 | Text           |              | X              |
| Leírás                       | Text           |              | X              |
| Rögzített hossz                      | Egész szám   |              | X              |
| Azonosítószám formátuma      | Text           |              | X              |
| Típus                              | Értékkészlet     |              | X              |
| Dolgozó személyazonosító típusa | Text           | X            | X              |

## <a name="fixed-compensation-entities"></a>Fix kompenzációs entitások

**Fix kompenzációs konstrukció**

| **Mezők**                  | **Adattípus** | **Szükséges** | **Kereshető** |
|-----------------------------|---------------|--------------|----------------|
| Cég                     | Keresés        | X            | X              |
| Kompenzációs rács           | Keresés        |              | X              |
| Pénznem                    | Keresés        | X            | X              |
| Leírás                 | Text          | X            | X              |
| Érvényesség dátuma              | Csak dátum     | X            | X              |
| Lejárat dátuma             | Csak dátum     | X            | X              |
| Felvételi szabály                   | Értékkészlet    | X            | X              |
| Név                        | Text          | X            | X              |
| Tartományon kívüliség tűréshatára      | Értékkészlet    | X            | X              |
| Fizetési gyakoriság               | Keresés        | X            | X              |
| Ajánlás engedélyezve      | Két lehetőség   | X            | X              |
| Hivatkozási pont sorának beállítása  | Keresés        |              | X              |
| Típus                        | Értékkészlet    | X            | X              |

**Kompenzációs rács**

| **Mezők**                  | **Adattípus** | **Szükséges** | **Kereshető** |
|-----------------------------|---------------|--------------|----------------|
| Cég                     | Keresés        | X            | X              |
| Pénznem                    | Keresés        |              | X              |
| Leírás                 | Text          | X            | X              |
| Érvényesség dátuma              | Csak dátum     |              | X              |
| Lejárat dátuma             | Csak dátum     |              | X              |
| Név                        | Text          | X            | X              |
| Referenciapont-beállítás       | Keresés        | X            | X              |
| Típus                        | Értékkészlet    | X            | X              |

**Kompenzációs szint**

| **Mezők**      | **Adattípus** | **Szükséges** | **Kereshető** |
|-----------------|---------------|--------------|----------------|
| Leírás     | Text          |              | X              |
| Név            | Text          | X            | X              |
| Típus            | Értékkészlet     | X            | X              |

**Kompenzáció - fizetés gyakorisága**

| **Mezők**                  | **Adattípus**   | **Szükséges** | **Kereshető** |
|-----------------------------|-----------------|--------------|----------------|
| Éves átváltási tényező    | Tizedesérték  |              | X              |
| Cég                     | Keresés          | X            | X              |
| Leírás                 | Text            |              | X              |
| Óránkénti átváltási tényező    | Tizedesérték  |              | X              |
| Havi konverziós tényező   | Tizedesérték  |              | X              |
| Név                        | Text            | X            | X              |
| Időszak                      | Értékkészlet      |              | X              |
| Heti átváltási tényező    | Értékkészlet      |              | X              |


**Kompenzációs hivatkozási pont beállítása**

| **Mezők**          | **Adattípus**   | **Szükséges** | **Kereshető** |
|---------------------|-----------------|--------------|----------------|
| Cég             | Keresés          | X            | X              |
| Kompenzáció típusa   | Értékkészlet      | X            | X              |
| Leírás         | Text            | X            | X              |
| Név                | Text            | X            | X              |

**Kompenzációs hivatkozási pont beállítási sora**

| **Mezők**            | **Adattípus**   | **Szükséges** | **Kereshető** |
|-----------------------|-----------------|--------------|----------------|
| Cég               | Keresés          | X            | X              |
| Leírás           | Text            | X            | X              |
| Sor száma           | Tizedesérték  | X            | X              |
| Név                  | Text            | X            | X              |
| Referenciapont-beállítás | Keresés          | X            | X              |

**Kompenzációs régió**

| **Mezők**      | **Adattípus** | **Szükséges** | **Kereshető** |
|-----------------|---------------|--------------|----------------|
| Leírás     | Text          | X            | X              |
| Név            | Text          | X            | X              |

**Kompenzációs struktúra**

| **Mezők**                    | **Adattípus**   | **Szükséges** | **Kereshető** |
|-------------------------------|---------------  |--------------|----------------|
| Összeg                        | Pénznem        |              | X              |
| Összegalap                   | Pénznem        |              | X              |
| Cég                       | Keresés          | X            | X              |
| Kompenzációs struktúra száma | Text            | X            | X              |
| Pénznem                      | Keresés          |              | X              |
| Árfolyam                 | Tizedesérték  |              | X              |
| Rács                          | Keresés          | X            | X              |
| Szint                         | Keresés          | X            | X              |
| Hivatkozási pont               | Keresés          | X            | X              |
| Hivatkozási pont sorának beállítása    | Keresés          | X            | X              |

**Rögzített kompenzációs esemény**

| **Mezők**            | **Adattípus**   | **Szükséges** | **Kereshető** |
|-----------------------|-----------------|--------------|----------------|
| Cég               | Keresés          | X            | X              |
| Leírás           | Text            | X            | X              |
| Eseménytípus            | Értékkészlet      | X            | X              |
| Aktív             | Két lehetőség     | X            |                |
| Név                  | Text            | X            | X              |

## <a name="entity-relationship-models"></a>Entitáskapcsolati modellek

### <a name="worker"></a>Dolgozó
![Dolgozó](./media/HCMCommon-worker-entity-diagram.png)

### <a name="job-and-job-position"></a>Feladat és feladat beosztása
![Feladat és feladat beosztása](./media/HCMCommon-job-and-job-position-entity-diagram.png)

### <a name="benefits"></a>Előnyök
![Előnyök](./media/HCMCommon-benefits-entity-diagram.png)

### <a name="compensation"></a>Kompenzáció
![Kompenzáció](./media/HCMCommon-compensation-entity-diagram.png)

### <a name="leave"></a>Kilépés
![Kilépés](./media/HCMCommon-leave-entity-diagram.png)

### <a name="work-calendar"></a>Munkanaptár
![Munkanaptár](./media/HCMCommon-work-calendar-entity-diagram.png)
