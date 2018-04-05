---
title: "Munkaerő-mutatók Power BI-tartalom"
description: "Ez a témakör a Munkaerő-mutatók Power BI-tartalmat ismerteti. Leírja, hogy hogyan kell hozzáférni a jelentésekhez, és információkat nyújt a tartalomcsomag összeállításához előzőleg használt entitásokkal és adatmodellekkel kapcsolatban."
author: jcart1106
manager: AnnBe
ms.date: 12/19/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: HcmWorkforceWorkspace
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations, Talent
ms.custom: 264084
ms.assetid: 8e700583-3a7d-4f5f-9ac8-58c4feed1a02
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 17b42ae7e177a42b732654f2952ec5fe35acb1a9
ms.contentlocale: hu-hu
ms.lasthandoff: 03/26/2018

---

# <a name="workforce-metrics-power-bi-content"></a>Munkaerő-mutatók Power BI-tartalom

[!include[banner](../includes/banner.md)]

Ez a témakör a **Munkaerő-mutatók** Microsoft Power BI-tartalmat ismerteti. Leírja, hogy hogyan kell hozzáférni Power BI-jelentésekhez, és információkat nyújt a tartalom összeállításához használt entitásokkal és adatmodellekkel kapcsolatban.

## <a name="accessing-the-power-bi-content"></a>Power BI-tartalom elérése
A **Munkaerő-mutatók** Power BI-tartalom a **Személyzetkezelés** munkaterületen jelenik meg a következő termékek valamelyikének használatakor:

- Microsoft Dynamics 365 for Finance and Operations 
- Microsoft Dynamics 365 for Talent

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>A Power BI-tartalomhoz tartozó metrikák
Az alábbi táblázat felsorolja az egyes jelentésekben megjelenő mutatókat.

| Jelentés                                           | Mutatók                                                                                                                                                                                                            |
|--------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Személyzeti mutatók                                   | További jelentések összefoglalása                                                                                                                           |
| Számláláselemzés – Vállalat, Részleg, Hely | Számlálás vállalat alapján, számlálás részleg alapján, számlálás hely alapján, illetve teljes számlálás                                                                                                                           |
| Számláláselemzés – munkakör, lépés, vezető            | Számlálás munkakör alapján, számlálás lépés alapján, számlálás vezető alapján, illetve teljes számlálás                                                                                                                                      |
| Számlálás trendelemzése                         | Számlálás az idei évre vonatkozóan és az elmúlt évre vonatkozóan vállalat szerint, illetve görgetett számlálás az elmúlt 12 hónapra vonatkozóan                                                                                                                        |
| FTE-elemzés                                     | Teljes teljes munkaidőssel egyenértékű dolgozók (FTE), teljes munkaidőssel egyenértékű dolgozók hozzárendelve összesen, teljes munkaidőssel egyenértékű dolgozók részlegenként, teljes munkaidőssel egyenértékű dolgozók az elmúlt 12 hónapban és teljes munkaidőssel egyenértékű dolgozók feladatok szerint |
| Munkaerő-demográfia                           | Számlálás életkor és nem szerint, számlálás etnikai hovatartozás szerint, számlálás veterán állapot szerint, számlálás családi állapot szerint, a nappalis diákok száma, átlagos szolgálati idő, átlagos életkor, a női és férfi alkalmazottak aránya, valamint az alkalmazottak által beszélt nyelvek |
| Pozícióelemzés                                | Nyitott beosztások részleg szerint, betöltésre váró beosztások, aktív és inaktív beosztások, illetve beosztások részleg szerint                                                                                                   |
| Lemorzsolódáselemzés                               | Lemorzsolódás idén és tavaly, lemorzsolódás, a kilépő alkalmazottak életkor és nem szerint, a távozó személyek átlagos szolgálati ideje, ebben a hónapban kilépő alkalmazottak, illetve távozó személyek ok szerint                                                                   |
| Személyek részleg szerint                             | Alkalmazottak személyzeti számmal részleg, pozíció, valamint a hozzárendelés kezdő és befejező dátuma szerint                                                                                                                       |
| Ledolgozott szolgálati idő elemzése                               | Átlagos szolgálati idő, ledolgozott átlagos évek száma vállalat és szolgálati idő listája szerint                                                                                                                                                              |
| Alkalmazotti évfordulók                           | Évfordulók ebben a hónapban, évfordulók a következő hónap, alkalmazottak ledolgozott évek szerint és évfordulók, szolgálati évek száma részleg szerint                                                                                                                                                                    |
| Alkalmazottak születésnapjai                               | Születésnapok ebben a hónapban, születésnapok a következő hónapban, alkalmazotti születésnapok, valamint születésnapok hónap és részleg szerint                                                                                                                                                                    |
| Tömeges felvételi projektek                               | Tömeges felvételi projektek összesen, tömeges felvételi projektek állapot szerint, tömeges felvételi projektek részleg és tulajdonos szerint, tömeges felvételi projektek munkakörönként, valamint tömeges felvételi projektek                                                                                                                                                                    |

Az e jelentésekben szereplő diagramokat és csempéket szűrheti, a diagramokat és csempéket pedig rögzítheti az irányítópulton. A szűréssel és a Power BI-n történő rögzítéssel kapcsolatos információkért lépjen az [Irányírópult létrehozása és konfigurálása](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards) lehetőségre.

Ügyeljen arra, hogy azt a **Munkaerő-mutatók** Power BI-tartalmat töltse le, amely a Microsoft Dynamics 365 rendszer ön által használt verziójára vonatkozik.

>[!NOTE]
>A Lifecycle Services szolgáltatásban rendelkezésre álló .pbix-fájlok csak a Finance and Operations szolgáltatásra érvényesek.

## <a name="understanding-the-data-model-and-entities"></a>Adatmodell, illetve entitások ismertetése
A következő táblázat mutatja az entitásokat, amelyeken a tartalom alapul.

| Entitás                   | Tartalom                                                                            | Más entitásokkal való kapcsolatok |
|--------------------------|-------------------------------------------------------------------------------------|-----------------------------------|
| Naptáreltolás          | Naptáreltolások, részletes jelentések                                                   | Korábbi pozíció hozzárendelése, Pozíciótrend, Alkalmazotti trend, Felmondott alkalmazott |
| Cég                  | Vállalatok a jelentések szűréséhez                                                      | Jelenlegi kompenzáció, Jelenlegi alkalmazott, Felmondott alkalmazott, Alkalmazotti trend |
| Aktuális beosztás         | Az aktuális dátum szerinti beosztások, teljes munkaidős egyenérték (FTE), nyitott beosztások és betöltésre váró beosztások | Feladat, pozíció |
| Aktuális alkalmazott         | Az aktuális dátum, kor és létszám szerinti dolgozók                                  | Vállalat, Földrajzi elhelyezkedés, Alkalmazott neve, Közvetlen felettes, Alkalmazott beosztása, Demográfia, Feladat, Alkalmazás, Beosztás |
| Dátum                     | Napok, hetek, hónapok és évek                                                      | Korábbi pozíció hozzárendelése, Pozíciótrend, Alkalmazotti trend, Felmondott alkalmazott |
| Demográfia             | Születési idő, nemek, etnikaum és családi állapot                            | Jelenlegi kompenzáció, Jelenlegi alkalmazott, Felmondott alkalmazott, Alkalmazotti trend |
| Alkalmazás               | Kezdő dátum, záró dátum és átállási dátum                                           | Jelenlegi kompenzáció, Jelenlegi alkalmazott, Felmondott alkalmazott, Alkalmazotti trend |
| Földrajzi hely      | Város, megye, irányítószám és állam vagy megye                                    | Jelenlegi kompenzáció, Jelenlegi alkalmazott, Felmondott alkalmazott, Alkalmazotti trend |
| Munka                      | Funkció, típus és a cím                                                           | Jelenlegi pozíció, jelenlegi alkalmazott |
| Korábbi betöltött pozíció | Kijelölés oka, kezdő dátum, záró dátum és feladat                                    | Naptár ennyi nappal később,, Dátum, Munkakör, Pozíció |
| Pozíció                 | Részleg, FTE, beosztás, beosztás típusa és cím                                 | Jelenlegi pozíció, jelenlegi alkalmazott |
| Pozíciótrend           | Beosztások az idők során, FTE és feladat                                                   | Naptár ennyi nappal később,, Dátum, Munkakör, Pozíció |
| Közvetlen felettes               | Keresztnév, vezetéknév és teljes név                                                | Jelenlegi kompenzáció, Jelenlegi alkalmazott, Felmondott alkalmazott, Alkalmazotti trend |
| Megszüntetett munkaviszonyú alkalmazott      | Kilépett dolgozók, kiléptetés dátuma, cím, beosztás és feladat                      | Vállalat, Földrajzi elhelyezkedés, Alkalmazott neve, Közvetlen felettes, Naptáreltolás, Dátum, Alkalmazott beosztása, Demográfia, Alkalmazás, Feladat, Beosztás |
| Alkalmazott neve            | Keresztnév, vezetéknév és teljes név                                                | Jelenlegi dolgozó, Felmondott alkalmazott, Alkalmazotti trend |
| Alkalmazott beosztása           | Cím és szolgálati idő dátuma                                                            | Jelenlegi kompenzáció, Jelenlegi alkalmazott, Felmondott alkalmazott, Alkalmazotti trend |
| Alkalmazotti trend           | Túlórázó dolgozók, létszám, vállalat és beosztás                                 | Vállalat, Földrajzi elhelyezkedés, Alkalmazott neve, Közvetlen felettes, Naptáreltolás, Dátum, Alkalmazott beosztása, Demográfia, Alkalmazás, Feladat |
| Tömeges felvételi projekt        | Tömeges felvételi projektek, projekt tulajdonosa, valamint projekt állapota                     | Vállalat, tömeges felvétel sora |
| Tömeges felvétel sora           | Részleg, foglalkoztatási típus és beosztás                                           | Dátum, munkakör, tömeges felvételi projekt |



