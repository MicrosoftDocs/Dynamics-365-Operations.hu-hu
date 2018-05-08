---
title: "Kompenzáció Power BI-tartalom"
description: "Ez a témakör a Kompenzáció Power BI-tartalmat ismerteti. Leírja, hogy hogyan kell hozzáférni a jelentésekhez, és információkat nyújt a tartalomcsomag összeállításához előzőleg használt entitásokkal és adatmodellekkel kapcsolatban."
author: jcart1106
manager: AnnBe
ms.date: 12/19/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: HcmCompensationWorkspace
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 93c005d4b85b56f77ddd488c91e477970f4ccd07
ms.contentlocale: hu-hu
ms.lasthandoff: 03/26/2018

---

# <a name="compensation-power-bi-content"></a>Kompenzáció Power BI-tartalom

[!include [banner](../includes/banner.md)]

Ez a témakör a **Kompenzáció** Microsoft Power BI-tartalmat ismerteti. Leírja, hogy hogyan kell hozzáférni a jelentésekhez, és információkat nyújt a tartalomcsomag összeállításához előzőleg használt entitásokkal és adatmodellekkel kapcsolatban.

## <a name="accessing-the-power-bi-content"></a>Power BI-tartalom elérése
A **Kompenzáció** Power BI-tartalom a **Kompenzációkezelés** munkaterületen jelenik meg, amennyiben a következő termékek valamelyikét használja:

- Microsoft Dynamics 365 for Finance and Operations
- Microsoft Dynamics 365 for Talent

## <a name="reports-that-are-included-in-the-power-bi-content"></a>A Power BI-tartalomhoz tartozó jelentések
A **Kompenzáció** Power BI-tartalomban szereplő jelentések táblázatokkal és diagramokkal jelenítenek meg információkat. Az alábbi táblázatban található ezeknek a jelentéseknek az ismertetése.

| Jelentés                     | Tartalom |
|----------------------------|----------|
| Kompenzációáttekintés      | További jelentések összefoglalása |
| Kompenzációelemzés      | Órabéres és bérezéses alkalmazottak vállalatonként, összes alkalmazott kompenzációs csomagonként, férfi és női alkalmazottak kompenzációs csomagonként, valamint alkalmazotti kompenzáció részlegenként |
| Pozíció szerinti fizetéselemzés      | Legmagasabb és legalacsonyabb órabér és fizetés, a legmagasabb és legalacsonyabb javadalmazású pozíciók, valamint teljes munkaidős és részmunkaidős pozíciók |
| Kompenzációs csomag elemzése | Alkalmazotti részvétel kijelölt juttatás alapján |

Az e jelentésekben szereplő diagramokat és csempéket szűrheti, a diagramokat és csempéket pedig rögzítheti az irányítópulton. A szűréssel és a Power BI-n történő rögzítéssel kapcsolatos információkért lépjen az [Irányírópult létrehozására és konfigurálása](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards) lehetőségre.


## <a name="understanding-the-data-model-and-entities"></a>Adatmodell, illetve entitások ismertetése
A következő adatokkal tölthetők ki a jelentések a **Kompenzáció** Power BI-tartalomban. Ez a táblázat megjeleníti azokat az entitásokat, amelyeken a tartalom alapul.

| Entitás                   | Tartalom                                                                                                   | Más entitásokkal való kapcsolatok |
|--------------------------|------------------------------------------------------------------------------------------------------------|-----------------------------------|
| Naptáreltolás          | Naptáreltolások, részletes jelentések                                                                          | Korábbi pozíció hozzárendelése, Pozíciótrend, Alkalmazotti trend, Felmondott alkalmazott |
| Cég                  | Vállalatok a jelentések szűréséhez                                                                             | Jelenlegi kompenzáció, Jelenlegi alkalmazott, Felmondott alkalmazott, Alkalmazotti trend |
| Kompenzáció             | Fizetési díjalap és időbeli gyakoriság                                                                           | Jelenlegi kompenzáció, Jelenlegi alkalmazott, Felmondott alkalmazott, Alkalmazotti trend |
| Aktuális kompenzáció     | Fizetési díjalap és gyakoriságát az aktuális dátum szerint                                                              | Vállalat, Kompenzáció, Demográfia, Munkakör, Pozíció |
| Aktuális beosztás         | Az aktuális dátum szerinti beosztások, teljes munkaidős egyenérték (FTE), nyitott beosztások és betöltésre váró beosztások | Feladat, pozíció |
| Aktuális alkalmazott         | Az aktuális dátum, kor és létszám szerinti dolgozók                                                         | Vállalat, Kompenzáció, Földrajzi hely, Alkalmazott neve, Közvetlen felettes, Alkalmazott beosztása, Demográfia, Munkakör, Alkalmazás, Pozíció, Juttatások |
| Dátum                     | Napok, hetek, hónapok és évek                                                                             | Korábbi pozíció hozzárendelése, Pozíciótrend, Alkalmazotti trend, Felmondott alkalmazott |
| Demográfia             | Születési idő, nemek, etnikaum és családi állapot                                                   | Jelenlegi kompenzáció, Jelenlegi alkalmazott, Felmondott alkalmazott, Alkalmazotti trend |
| Alkalmazás               | Kezdő dátum, záró dátum és átállási dátum                                                                  | Jelenlegi kompenzáció, Jelenlegi alkalmazott, Felmondott alkalmazott, Alkalmazotti trend |
| Földrajzi hely      | Város, megye, irányítószám és állam vagy megye                                                           | Jelenlegi kompenzáció, Jelenlegi alkalmazott, Felmondott alkalmazott, Alkalmazotti trend |
| Munka                      | Funkció, típus és a cím                                                                                  | Jelenlegi pozíció, jelenlegi alkalmazott |
| Korábbi betöltött pozíció | Kijelölés oka, kezdő dátum, záró dátum és feladat                                                           | Naptár ennyi nappal később,, Dátum, Munkakör, Pozíció |
| Pozíció                 | Részleg, FTE, beosztás, beosztás típusa és cím                                                        | Jelenlegi pozíció, jelenlegi alkalmazott |
| Pozíciótrend           | Beosztások az idők során, FTE és feladat                                                                          | Naptár ennyi nappal később,, Dátum, Munkakör, Pozíció |
| Közvetlen felettes               | Keresztnév, vezetéknév és teljes név                                                                       | Jelenlegi dolgozó, Felmondott alkalmazott, Alkalmazotti trend |
| Megszüntetett munkaviszonyú alkalmazott      | Kilépett alkalmazottak, kiléptetés dátuma, cím, beosztás és feladat                                             | Vállalat, Kompenzáció, Földrajzi hely, Alkalmazott neve, Közvetlen felettes, Naptár ennyi nappal később, Dátum, Alkalmazott beosztása, Demográfia, Alkalmazás, Munkakör, Pozíció, Juttatások |
| Juttatások                 | Hatálybalépés, juttatási lehetőség, juttatási konstrukció és juttatási típus                                             | Jelenlegi név, Felmondott alkalmazott, Alkalmazotti trend |
| Alkalmazott neve            | Keresztnév, vezetéknév és teljes név                                                                       | Jelenlegi kompenzáció, Jelenlegi alkalmazott, Felmondott alkalmazott, Alkalmazotti trend |
| Alkalmazott beosztása           | Cím és szolgálati idő dátuma                                                                                   | Jelenlegi kompenzáció, Jelenlegi alkalmazott, Felmondott alkalmazott, Alkalmazotti trend |
| Alkalmazotti trend           | Túlórázó dolgozók, létszám, vállalat és beosztás                                                        | Vállalat, Kompenzáció, Földrajzi hely, Alkalmazott neve, Közvetlen felettes, Naptár ennyi nappal később, Dátum, Alkalmazott beosztása, Demográfia, Alkalmazás, Munkakör, Juttatások |



