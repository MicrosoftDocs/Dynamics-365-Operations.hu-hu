---
title: "Tanulás Power BI-tartalom"
description: "Ez a témakör ismerteti a tanulás Power BI-tartalmat. Leírja, hogy hogyan kell hozzáférni a jelentésekhez, és információkat nyújt a tartalomcsomag összeállításához előzőleg használt entitásokkal és adatmodellekkel kapcsolatban."
author: jcart1106
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, Talent, Core
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 6e64337f19600b18320550d91c134949c33af7b0
ms.openlocfilehash: bb4a2d6d725f79fe3f095a37b8a37d47339a7966
ms.contentlocale: hu-hu
ms.lasthandoff: 12/01/2017

---

# <a name="learning-power-bi-content"></a>Tanulás Power BI-tartalom

[!include[banner](../includes/banner.md)]

Ez a témakör ismerteti a **Tanulás** Microsoft Power BI-tartalmat. Elmagyarázza, hogy hogyan kell hozzáférni a tartalomhoz, és leírja a tartalom összeállításához használt entitásokkal és adatmodellekkel kapcsolatban.

## <a name="accessing-the-power-bi-content"></a>Power BI-tartalom elérése

A **Tanulás** tartalomcsomagot a Microsoft Dynamics Lifecycle Services (LCS) megosztott eszközök könyvtárban található. A tartalom letöltésére és szervezeténél való megvalósítására vonatkozó további információért lásd: [Power BI-tartalom az LCS megoldásban a Microsofttól és a partnerektől](power-bi-content-microsoft-partners.md). Ha meg szeretne tekinteni egy demót, amely bemutatja a Power BI-tartalmak megvalósítását, lásd a [Power BI-tartalom a Microsofttól és az Ön partnereitől a Dynamics Lifecycle Services szolgáltatásban](https://mix.office.com/watch/9puyb1b2xs1w) című részt (Office Mix).

## <a name="reports-that-are-included-in-the-power-bi-content"></a>A Power BI-tartalomhoz tartozó jelentések

A **Tanulás** Power BI által tartalmazott a jelentések táblázatokkal és diagramokkal jelenítenek meg információkat. Az alábbi táblázatban található ezeknek a jelentéseknek az ismertetése.

| Jelentés                | Tartalom |
|-----------------------|----------|
| Tanulás – áttekintés     | További jelentések összefoglalása |
| Tanfolyamelemzés       | Regisztráció hely szerint, résztvevő állapot szerint, tanfolyamok típus szerint vállalatonként és tanfolyamon való részvételt feladat szerint |
| Regisztráció elemzése | Regisztrációs lista |
| Tanfolyamtípusok          | Tanfolyamtípusok szakértelem szerint |
| Oktatóelemzés   | Tanfolyamok és oktatók aránya, oktatók száma, tanfolyamok oktatók szerint, tanfolyamok oktatónként, valamint tanfolyami napirend oktató szerint |
| Elérhető tanfolyamok       | Tanfolyamok listája |
| Tanfolyamok tervezés        | Tanfolyami napirend |

Az e jelentésekben szereplő diagramokat és csempéket szűrheti, a diagramokat és csempéket pedig rögzítheti az irányítópulton. A szűréssel és a Power BI-n történő rögzítéssel kapcsolatos információkért lépjen az [Irányírópult létrehozására és konfigurálása](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards) lehetőségre.

## <a name="understanding-the-data-model-and-entities"></a>Adatmodell, illetve entitások ismertetése

A **Tanulás** Power BI-tartalom jelentéseinek kitöltésére a következő adatok szolgálnak. Ez a táblázat megjeleníti azokat az entitásokat, amelyeken a tartalom alapul.

| Entitás           | Tartalom                                                         | Más entitásokkal való kapcsolatok |
|------------------|------------------------------------------------------------------|-----------------------------------|
| Naptáreltolás  | Naptáreltolások, részletes jelentések                                | Tanfolyami napirend, Tanfolyamrésztvevők |
| Cég          | Vállalatok a jelentések szűréséhez                                   | Tanfolyami napirend, Tanfolyamrésztvevők |
| Tanfolyam           | Tanfolyam, leírás, oktató neve, hely, szoba és állapot | Tanfolyami napirend, Tanfolyamrésztvevők, Tanfolyamkészség |
| Tanfolyami napirend    | Napirend, tanfolyam, kezdő és záró időpontok                          | Vállalat, naptáreltolás, dátum, tanfolyam |
| Tanfolyamrésztvevők | Név, állapot, feladat és regisztráció dátuma                         | Vállalat, Naptáreltolás, Dátum, Tanfolyam, Demográfia, Alkalmazás, Tanfolyam, Alkalmazott neve, Alkalmazott beosztása, Feladat, Beosztás |
| Tanfolyamkészség     | Szakértelem, szakértelem típusa és szintje                                     | Tanfolyam |
| Dátum             | Napok, hetek, hónapok és évek                                   | Tanfolyami napirend, Tanfolyamrésztvevők |
| Demográfia     | Születési idő, nemek, etnikaum és családi állapot         | Tanfolyami napirend, Tanfolyamrésztvevők |
| Alkalmazás       | Kezdő dátum, záró dátum és átállási dátum                        | Tanfolyami napirend, Tanfolyamrésztvevők |
| Munka              | Funkció, típus és a cím                                        | Tanfolyami napirend, Tanfolyamrésztvevők |
| Pozíció         | Beosztás, cím és teljes munkaidős egyenérték (FTE)                  | Tanfolyami napirend, Tanfolyamrésztvevők |
| Alkalmazott neve    | Keresztnév, vezetéknév és teljes név                             | Tanfolyamrésztvevők |
| Alkalmazott beosztása   | Cím és szolgálati idő dátuma                                         | Tanfolyamrésztvevők |

Ezeket az entitásokat számított mértékek létrehozására használták az adatmodellben. E kiszámított mértékek aztán a fő teljesítménymutatók (KPI-k) és a tartalomban használt jelentések kiszámításához használatosak. Ha szeretné felvenni a további számításokat a jelentésekbe és irányítópultokba, töltse le és módosítsa a .pbix-fájlt a LCS-ből. Ez a fájl azon alapértelmezett adatmodell, amelyet a tartalom létrehozásához használtak. Miután elvégezte a módosításokat, szervezeti tartalmi csomagot és a felvett adatokat tartalmazó irányítópultot hozhat létre.

