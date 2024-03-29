---
title: Alkalmazotti fejlesztés Power BI tartalom
description: Ez a témakör ismerteti az alkalmazotti fejlesztés Power BI tartalmát.
author: jcart1106
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 307a7ba2b885ba1437d5ef54c2f9d70ef00e2b14
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9284178"
---
# <a name="employee-development-power-bi-content"></a>Alkalmazotti fejlesztés Power BI tartalom

[!include [banner](../includes/banner.md)]

Ez a témakör ismerteti az alkalmazotti **fejlesztés** Microsoft Power BI tartalmát.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Jelentések, amelyek a Power BI-tartalomban szerepelnek
Az **Alkalmazotti fejlesztés** Power BI tartalomban szereplő jelentések táblázatokkal és diagramokkal jelenítenek meg információkat. Az alábbi táblázatban található ezeknek a jelentéseknek az ismertetése.

| Jelentés                        | Tartalom |
|-------------------------------|----------|
| Alkalmazotti fejlesztés áttekintése | További jelentések összefoglalása |
| Alkalmazotti szakértelem elemzése       | Alkalmazotti szakértelemtípusok és alkalmazotti szakértelmek típus szerint |
| Alkalmazotti szakértelmi szint elemzése | Alkalmazotti szakértelmi szintek részleg szerint, alkalmazottak szakértelmi szint és a szakértelem típusa szerint, és legalacsonyabb és legmagasabb szint szakértelem szerint |
| Szakértelemprofil                 | Szakértelemprofil kiválasztott alkalmazott számára |
| Szakértelem-elemzés                | Szakértelem típus és minősítés alapján |
| Teljesítményminősítés-elemzés   | Alkalmazottak legalacsonyabb és legmagasabb feladatminősítés szerint, alkalmazotti minősítések részleg szerint, alkalmazottak minősítés és beosztás típusa szerint, és legmagasabb és legalacsonyabb minősítések beosztás szerint |
| Alkalmazotti teljesítményelemzés | Alkalmazotti minősítések a vezető által kiválasztott minősítésre nézve |

Az e jelentésekben szereplő diagramokat és csempéket szűrheti, a diagramokat és csempéket pedig rögzítheti az irányítópulton. A szűréssel és a Power BI-n történő rögzítéssel kapcsolatos információkért lásd: [Irányítópult létrehozása és konfigurálása](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Adatmodell, illetve entitások ismertetése

| Entitás                   | Tartalom                                                                                                   | Más entitásokkal való kapcsolatok |
|--------------------------|------------------------------------------------------------------------------------------------------------|-----------------------------------|
| Naptáreltolás          | Naptáreltolások, részletes jelentések                                                                          | Korábbi pozíció hozzárendelése, Pozíciótrend, Alkalmazotti trend, Felmondott alkalmazott |
| Cég                  | Vállalatok a jelentések szűréséhez                                                                             | Jelenlegi kompenzáció, Jelenlegi alkalmazott, Felmondott alkalmazott, Alkalmazotti trend |
| Aktuális beosztás         | Az aktuális dátum szerinti beosztások, teljes munkaidős egyenérték (FTE), nyitott beosztások és betöltésre váró beosztások | Feladat, pozíció |
| Aktuális alkalmazott         | Az aktuális dátum, kor és létszám szerinti dolgozók                                                         | Vállalat, Földrajzi elhelyezkedés, Alkalmazott neve, Közvetlen felettes, Alkalmazott beosztása, Demográfia, Feladat, Alkalmazás, Beosztás |
| Dátum                     | Napok, hetek, hónapok és évek                                                                             | Korábbi pozíció hozzárendelése, Pozíciótrend, Alkalmazotti trend, Felmondott alkalmazott |
| Demográfia             | Születési idő, nemek, etnikaum és családi állapot                                                   | Aktuális alkalmazott, Munkaviszonya megszűnt, Alkalmazott, Alkalmazotti trend |
| Alkalmazás               | Kezdő dátum, záró dátum és átállási dátum                                                                  | Jelenlegi kompenzáció, Jelenlegi alkalmazott, Felmondott alkalmazott, Alkalmazotti trend |
| Földrajzi hely      | Város, megye, irányítószám és állam vagy megye                                                           | Jelenlegi kompenzáció, Jelenlegi alkalmazott, Felmondott alkalmazott, Alkalmazotti trend |
| Munka                      | Funkció, típus és a cím                                                                                  | Jelenlegi pozíció, jelenlegi alkalmazott |
| Korábbi betöltött pozíció | Kijelölés oka, kezdő dátum, záró dátum és feladat                                                           | Naptár ennyi nappal később,, Dátum, Munkakör, Pozíció |
| Pozíció                 | Részleg, FTE, beosztás, beosztás típusa és cím                                                        | Jelenlegi pozíció, jelenlegi alkalmazott |
| Pozíciótrend           | Beosztások az idők során, FTE és feladat                                                                          | Naptár ennyi nappal később,, Dátum, Munkakör, Pozíció |
| Közvetlen felettes               | Keresztnév, vezetéknév és teljes név                                                                       | Jelenlegi kompenzáció, Jelenlegi alkalmazott, Felmondott alkalmazott, Alkalmazotti trend |
| Megszüntetett munkaviszonyú alkalmazott      | Kilépett dolgozók, kiléptetés dátuma, cím, beosztás és feladat                                             | Vállalat, Földrajzi elhelyezkedés, Alkalmazott neve, Közvetlen felettes, Naptáreltolás, Dátum, Alkalmazott beosztása, Demográfia, Alkalmazás, Feladat, Beosztás |
| Alkalmazott neve            | Keresztnév, vezetéknév és teljes név                                                                       | Jelenlegi dolgozó, Felmondott alkalmazott, Alkalmazotti trend |
| Alkalmazott beosztása           | Cím és szolgálati idő dátuma                                                                                   | Jelenlegi kompenzáció, Jelenlegi alkalmazott, Felmondott alkalmazott, Alkalmazotti trend |
| Alkalmazotti trend           | Túlórázó dolgozók, létszám, vállalat és beosztás                                                        | Vállalat, Földrajzi elhelyezkedés, Alkalmazott neve, Közvetlen felettes, Naptáreltolás, Dátum, Alkalmazott beosztása, Demográfia, Alkalmazás, Feladat |
| Munka                      | Funkció, típus és a cím                                                                                  | Aktuális alkalmazott, Aktuális beosztás, Alkalmazotti trend, Feladathoz előnyben részesített képesség, Korábbi betöltött pozíció, Pozíciótrend, Megszüntetett munkaviszonyú alkalmazott |
| Munkakörhöz előnyben részesített képesség      | Fontosság, minősítés, szakértelem és szakértelem szintje                                                                 | Munka |
| Alkalmazotti szakértelem elemzése  | Tanúsított, szint, szint dátuma és szakértelem                                                                    | Alkalmazott neve, Szakértelem |
| Teljesítmény              | Minősítési, leírás és minősítési modell                                                                      | Aktuális alkalmazott, Aktuális beosztás, Alkalmazotti trend, Feladathoz előnyben részesített képesség, Korábbi betöltött pozíció, Pozíciótrend, Megszüntetett munkaviszonyú alkalmazott |
| Szakértelem                    | Szakértelem, szakértelem típusa és minősítés                                                                              | Alkalmazotti szakértelem elemzése, Feladathoz előnyben részesített szakértelem |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
