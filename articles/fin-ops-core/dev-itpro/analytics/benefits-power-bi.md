---
title: Juttatások Power BI tartalom
description: Ez a témakör a juttatások tartalmát írja Power BI le.
author: jcart1106
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.search.form: HcmBenefitWorkspace
ms.openlocfilehash: ed1fd0b86e44d022a4858e3b5bc61c83a8efd395
ms.sourcegitcommit: 3c4dd125ed321af8a983e89bcb5bd6e5ed04a762
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/28/2022
ms.locfileid: "9206657"
---
# <a name="benefits-power-bi-content"></a>Juttatások Power BI tartalom

[!include [banner](../includes/banner.md)]

Ez a témakör a juttatások tartalmát **írja** Microsoft Power BI le. Leírja, hogy hogyan kell hozzáférni a jelentésekhez, és információkat nyújt a tartalomcsomag összeállításához előzőleg használt entitásokkal és adatmodellekkel kapcsolatban.

## <a name="accessing-the-power-bi-content"></a>A Power BI tartalom elérése
A **Juttatások** Power BI-tartalom a **Juttatáskezelés** munkaterületen jelenik meg, amennyiben a következő termékek valamelyikét használja:

- Microsoft Dynamics 365 Pénzügy
- Microsoft Dynamics 365 Human Resources

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Jelentések, amelyek a Power BI-tartalomban szerepelnek
A **Juttatások** Power BI-tartalomban szereplő jelentések táblázatokkal és diagramokkal jelenítenek meg információkat. Az alábbi táblázatban található ezeknek a jelentéseknek az ismertetése.

| Jelentés                      | Tartalom                                                                                       |
|-----------------------------|------------------------------------------------------------------------------------------------|
| Juttatás bejegyzése – áttekintés | A leggyakrabban és legritkábban regisztrált csomag, alkalmazottcsoport szerinti regisztráció és kiválasztott lehetőségek a juttatási csomagnál |
| Alkalmazotti juttatások           | Alkalmazotti részvétel kijelölt juttatás alapján                                                        |

Az e jelentésekben szereplő diagramokat és csempéket szűrheti, a diagramokat és csempéket pedig rögzítheti az irányítópulton. A szűréssel és a Power BI-n történő rögzítéssel kapcsolatos információkért lásd: [Irányítópult létrehozása és konfigurálása](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Adatmodell, illetve entitások ismertetése
A **Juttatások** Power BI-tartalom jelentéseinek kitöltésére a következő adatok szolgálnak. Ez a táblázat megjeleníti azokat az entitásokat, amelyeken a tartalom alapul.

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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
