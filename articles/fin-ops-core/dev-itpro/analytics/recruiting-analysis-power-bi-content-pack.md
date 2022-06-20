---
title: Toborzás Power BI tartalom
description: Ez a témakör a toborzási tartalmat írja Power BI le.
author: jcart1106
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmRecruitmentWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 263934
ms.assetid: 38e6827b-0819-473c-bc47-821a1ec482b8
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: d3240b92993986b32a739b7a6e5c7f7c2df3ed71
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8890096"
---
# <a name="recruiting-power-bi-content"></a>Toborzás Power BI tartalom

[!include [banner](../includes/banner.md)]

Ez a témakör a toborzási **tartalmat írja** Microsoft Power BI le. Leírja, hogy hogyan kell hozzáférni a Power BI-jelentésekhez, és információkat nyújt a tartalomcsomag összeállításához előzőleg használt entitásokkal és adatmodellekkel kapcsolatban.

## <a name="accessing-the-power-bi-content"></a>A Power BI tartalom elérése
A **Toborzás** Power BI tartalom a **Toborzás kezelése** munkaterületen látható.

## <a name="reports-and-visuals-in-the-recruitment-management-workspace"></a>Jelentések és megjelenítések a Toborzás kezelése munkaterületen
A **Toborzás kezelése** munkaterület tartalmaz egy **Elemzés** lapot. Ez a lap a beágyazott toborzási Power BI-tartalmat tartalmazza. A tartalom egy áttekintő lapból és további, részletesek adatokat tartalmazó fülekből áll. Az alábbi táblázatban található a füleken megjelenő jelentések ismertetése.

| Jelentés               | Tartalom |
|----------------------|----------|
| Toborzás áttekintése | Összegzi a többi jelentést |
| Pályázóelemzés   | A pályázók száma összesen, pályázók munka szerint, pályázóforrások, női és férfi pályázók aránya és pályázók hely szerint |
| Pályázó állapota     | Pályázók típus és állapot szerint és a pályázó állapota |
| Toborzási elemzés  | Nettó felvételi arány, felvételig tartó napok átlagos száma, rossz felvételek százaléka, toborzási költségek, toborzási projektek száma, alkalmazottak és pályázók aránya, pályázók és nyitott pozíciók aránya toborzási projekt szerint |

## <a name="understanding-the-data-model-and-entities"></a>Adatmodell, illetve entitások ismertetése
Az e jelentésekben szereplő diagramokat és csempéket szűrheti, a diagramokat és csempéket pedig rögzítheti az irányítópulton. A szűréssel és a Power BI-n történő rögzítéssel kapcsolatos információkért lásd: [Irányítópult létrehozása és konfigurálása](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

A következő táblázat mutatja az entitásokat, amelyeken a **Toborzás** Power BI-csomag alapul.

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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]