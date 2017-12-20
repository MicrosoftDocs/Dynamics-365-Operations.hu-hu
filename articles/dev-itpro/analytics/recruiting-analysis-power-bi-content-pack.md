---
title: "Toborzási Power BI-tartalom"
description: "Ez a témakör ismerteti a Toborzási Power BI-tartalmat. Leírja, hogy hogyan kell hozzáférni a jelentésekhez, és információkat nyújt a tartalomcsomag összeállításához előzőleg használt entitásokkal és adatmodellekkel kapcsolatban."
author: jcart1106
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 263934
ms.assetid: 38e6827b-0819-473c-bc47-821a1ec482b8
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 6e64337f19600b18320550d91c134949c33af7b0
ms.openlocfilehash: 22138ab34243aa5f8c74f785ce3aaf68b27b9622
ms.contentlocale: hu-hu
ms.lasthandoff: 12/01/2017

---

# <a name="recruiting-power-bi-content"></a>Toborzási Power BI-tartalom

[!include[banner](../includes/banner.md)]

Ez a témakör ismerteti a **Toborzási** Microsoft Power BI-tartalmat. Leírja, hogy hogyan kell hozzáférni Power BI-jelentésekhez, és információkat nyújt a tartalom összeállításához használt entitásokkal és adatmodellekkel kapcsolatban.

## <a name="accessing-the-power-bi-content"></a>Power BI-tartalom elérése
A **Felvétel** Power BI-tartalom a **Toborzás kezelése** munkaterületen látható. 

## <a name="reports-and-visuals-in-the-recruitment-management-workspace"></a>Jelentések és megjelenítések a Toborzás kezelése munkaterületen
A **Toborzás kezelése** munkaterület tartalmaz egy **Elemzés** lapot. Ez a lap a beágyazott toborzási Power BI-tartalmat tartalmazza. A tartalom egy áttekintő lapból és további, részletesek adatokat tartalmazó fülekből áll. Az alábbi táblázatban található a füleken megjelenő jelentések ismertetése.

| Jelentés               | Tartalom |
|----------------------|----------|
| Toborzás áttekintése | Összegzi a többi jelentést |
| Pályázóelemzés   | A pályázók száma összesen, pályázók munka szerint, pályázóforrások, női és férfi pályázók aránya és pályázók hely szerint |
| Pályázó állapota     | Pályázók típus és állapot szerint és a pályázó állapota |
| Toborzási elemzés  | Nettó felvételi arány, felvételig tartó napok átlagos száma, rossz felvételek százaléka, toborzási költségek, toborzási projektek száma, alkalmazottak és pályázók aránya, pályázók és nyitott pozíciók aránya toborzási projekt szerint |

## <a name="understanding-the-data-model-and-entities"></a>Adatmodell, illetve entitások ismertetése
Az e jelentésekben szereplő diagramokat és csempéket szűrheti, a diagramokat és csempéket pedig rögzítheti az irányítópulton. A szűréssel és a Power BI-n történő rögzítéssel kapcsolatos információkért lépjen az [Irányírópult létrehozására és konfigurálása](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards) lehetőségre.

A következő táblázat mutatja a **Felvétel** entitásokat, amelyeken a Power BI-csomag alapul.

| Entitás               | Tartalom                                                         | Más entitásokkal való kapcsolatok |
|----------------------|------------------------------------------------------------------|-----------------------------------|
| Pályázó            | Pályázók, felvett pályázók, nettó felvételi arány és költségek          | Pályázó neve, vállalat, naptáreltolás, dátum, földrajzi elhelyezkedés, demográfiai adatok, feladat, média, toborzási projekt |
| Pályázó neve       | Pályázó utóneve, vezetékneve és teljes neve                   | Kérelmező, a pályázó alkalmazott, pályázó munkaviszonya megszűnt |
| Naptáreltolás      | Naptáreltolások, részletes jelentések                                | Kérelmező, a pályázó alkalmazott, pályázó munkaviszonya megszűnt |
| Cég              | Vállalatok a jelentések szűréséhez                                   | Kérelmező, a pályázó alkalmazott, pályázó munkaviszonya megszűnt |
| Dátum                 | Napok, hetek, hónapok és évek                                   | Kérelmező, a pályázó alkalmazott, pályázó munkaviszonya megszűnt |
| Demográfia         | Születési idő, nemek, etnikaum és családi állapot         | Kérelmező, a pályázó alkalmazott, pályázó munkaviszonya megszűnt |
| A pályázó alkalmazott   | Pályázó, teljesítmény, kezdődátum és pályázó típusa           | Vállalat, naptáreltolás, dátum, földrajzi elhelyezkedés, pályázó neve, foglalkoztatás, teljesítmény, feladat, média, toborzási projekt |
| Alkalmazás           | Kezdő dátum, záró dátum és átállási dátum                        | Kérelmező, a pályázó alkalmazott, pályázó munkaviszonya megszűnt |
| Földrajzi hely  | Város, megye, irányítószám és állam vagy megye                 | Kérelmező, a pályázó alkalmazott, pályázó munkaviszonya megszűnt |
| Munka                  | Funkció, típus és a cím                                        | Kérelmező, a pályázó alkalmazott, pályázó munkaviszonya megszűnt |
| Média                | Pályázók forrása                                             | Kérelmező, a pályázó alkalmazott, pályázó munkaviszonya megszűnt |
| Teljesítmény          | Minősítési, leírás és minősítési modell                            | Kérelmező, a pályázó alkalmazott, pályázó munkaviszonya megszűnt |
| Toborzási projekt  | Projekt leírása, projekt állapota és nyitott pozíciók                | Kérelmező, a pályázó alkalmazott, pályázó munkaviszonya megszűnt |
| A pályázó munkaviszonya megszűnt | Megszűnt pályázók, ok, teljesítmény és a megszűnés dátuma | Vállalat, naptáreltolás, dátum, földrajzi elhelyezkedés, teljesítmény, demográfiai adatok, foglalkoztatás, média, toborzási projekt, pályázó neve |

Ezeket az entitásokat számított mértékek létrehozására használták. E kiszámított mértékek aztán a fő teljesítménymutatók (KPI-k) és a tartalomban használt jelentések kiszámításához használatosak. Ha szeretné felvenni a további számításokat a jelentésekbe és irányítópultokba, töltse le és módosítsa a Recruiting.pbix fájlt a Microsoft Dynamics Lifecycle Services (LCS) rendszerből. Ez a fájl azon alapértelmezett adatmodell, amelyet a tartalom létrehozásához használtak. Miután elvégezte a módosításokat, szervezeti tartalmi csomagot és a felvett adatokat tartalmazó irányítópultot hozhat létre.

