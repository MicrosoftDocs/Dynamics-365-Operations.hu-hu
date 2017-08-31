---
title: "Juttatások Power BI-tartalom"
description: "Ez a témakör a Juttatások Power BI-tartalmat ismerteti. Leírja, hogy hogyan kell hozzáférni a jelentésekhez, és információkat nyújt a tartalomcsomag összeállításához előzőleg használt entitásokkal és adatmodellekkel kapcsolatban."
author: jcart1106
manager: AnnBe
ms.date: 05/24/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, UnifiedOperations, Talent, Core
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 815d8ecfe85c1000667d2d289c05c1e98b8b8c76
ms.contentlocale: hu-hu
ms.lasthandoff: 06/13/2017

---

# <a name="benefits-power-bi-content"></a>Juttatások Power BI-tartalom

[!include[banner](../includes/banner.md)]

Ez a témakör a **Juttatások** Microsoft Power BI-tartalmat ismerteti. Leírja, hogy hogyan kell hozzáférni a jelentésekhez, és információkat nyújt a tartalomcsomag összeállításához előzőleg használt entitásokkal és adatmodellekkel kapcsolatban.

## <a name="accessing-the-power-bi-content"></a>Power BI-tartalom elérése
A **Juttatások** Power BI-tartalom a **Juttatáskezelés** munkaterületen jelenik meg, amennyiben a következő termékek valamelyikét használja:

- Microsoft Dynamics 365 for Finance and Operations, Enterprise kiadás, 2017. júliusi frissítés
- Microsoft Dynamics 365 for Talent

## <a name="reports-that-are-included-in-the-power-bi-content"></a>A Power BI-tartalomhoz tartozó jelentések
A **Juttatások** Power BI-tartalomban szereplő jelentések táblázatokkal és diagramokkal jelenítenek meg információkat. Az alábbi táblázatban található ezeknek a jelentéseknek az ismertetése.

| Jelentés                       | Tartalom                                                                                       |
|------------------------------|------------------------------------------------------------------------------------------------|
| Juttatás bejegyzése – áttekintés  | A leggyakrabban és legritkábban regisztrált csomag, alkalmazottcsoport szerinti regisztráció és kiválasztott lehetőségek a juttatási csomagnál |
| Alkalmazotti juttatások            | Alkalmazotti részvétel kijelölt juttatás alapján                                                        |
                                                                                             
Az e jelentésekben szereplő diagramokat és csempéket szűrheti, a diagramokat és csempéket pedig rögzítheti az irányítópulton. A szűréssel és a Power BI-n történő rögzítéssel kapcsolatos információkért lépjen az [Irányírópult létrehozására és konfigurálása](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards) lehetőségre.

## <a name="extending-the-power-bi-content"></a>Power BI-tartalom kibővítése
A Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban található tartalomcsomagok révén nagyszerű elemzési lehetőségeket nyújthat azoknak a személyeknek, akik nem jelentkeztek be a Finance and Operations szolgáltatásba. Ezek a tartalomcsomagok módosíthatók, hogy más jelentéseket vagy megjelenítéseket is tartalmazhassanak, majd a tartalomcsomagok elemzés céljából közzétehetők a Power BI.com-bérlőjénél.

A **Juttatások** Power BI-tartalom a Közös eszközök tárában található az LCS szolgáltatásban. A tartalom letöltésére és szervezeténél való megvalósítására vonatkozó további információért lásd: [Power BI-tartalom az LCS megoldásban a Microsofttól és a partnerektől](power-bi-content-microsoft-partners.md). Ha meg szeretne tekinteni egy demót, amely bemutatja a Power BI-tartalmak megvalósítását, lásd a [Power BI-tartalom a Microsofttól és az Ön partnereitől a Dynamics Lifecycle Services szolgáltatásban](https://mix.office.com/watch/9puyb1b2xs1w) című részt (Office Mix).

>[!NOTE]
>A Lifecycle Services szolgáltatásban rendelkezésre álló .pbix-fájlok csak a Finance and Operations szolgáltatásra érvényesek.

## <a name="understanding-the-data-model-and-entities"></a>Adatmodell, illetve entitások ismertetése
A következő adatokkal tölthetők ki a jelentések a **Juttatások** Power BI-tartalomban. Ez a táblázat megjeleníti azokat az entitásokat, amelyeken a tartalom alapul.

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
| Megszüntetett munkaviszonyú alkalmazott      | Kilépett alkalmazottak, kiléptetés dátuma, cím, beosztás és feladat                                           | Vállalat, Kompenzáció, Földrajzi hely, Alkalmazott neve, Közvetlen felettes, Naptár ennyi nappal később, Dátum, Alkalmazott beosztása, Demográfia, Alkalmazás, Munkakör, Pozíció, Juttatások |
| Juttatások                 | Hatálybalépés, juttatási lehetőség, juttatási konstrukció és juttatási típus                                             | Jelenlegi név, Felmondott alkalmazott, Alkalmazotti trend |
| Alkalmazott neve            | Keresztnév, vezetéknév és teljes név                                                                       | Jelenlegi kompenzáció, Jelenlegi alkalmazott, Felmondott alkalmazott, Alkalmazotti trend |
| Alkalmazott beosztása           | Cím és szolgálati idő dátuma                                                                                   | Jelenlegi kompenzáció, Jelenlegi alkalmazott, Felmondott alkalmazott, Alkalmazotti trend |
| Alkalmazotti trend           | Túlórázó dolgozók, létszám, vállalat és beosztás                                                        | Vállalat, Kompenzáció, Földrajzi hely, Alkalmazott neve, Közvetlen felettes, Naptár ennyi nappal később, Dátum, Alkalmazott beosztása, Demográfia, Alkalmazás, Munkakör, Juttatások |

Ezeket az entitásokat számított mértékek létrehozására használták az adatmodellben. E kiszámított mértékek aztán a fő teljesítménymutatók (KPI-k) és a tartalomban használt jelentések kiszámításához használatosak. Ha szeretné felvenni a további számításokat a jelentésekbe és irányítópultokba, töltse le és módosítsa a .pbix-fájlt a LCS-ből. Ez a fájl azon alapértelmezett adatmodell, amelyet a tartalom létrehozásához használtak. Miután elvégezte a módosításokat, szervezeti tartalmi csomagot és a felvett adatokat tartalmazó irányítópultot hozhat létre.

