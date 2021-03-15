---
title: Költséggazdálkodási Power BI-tartalom
description: Ez a témakör azt ismerteti, mit tartalmaz a Kiadáskezelés Power BI-tartalomcsomag.
author: panolte
manager: AnnBe
ms.date: 03/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: TrvExpenseWorkspace, ExpenseWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kfend
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: d580502a08c2c176a000616abc3513cc45bd58a6
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/16/2021
ms.locfileid: "5016452"
---
# <a name="expense-management-power-bi-content"></a>Költséggazdálkodási Power BI-tartalom

[!include [banner](../includes/banner.md)]

Ez a témakör azt ismerteti, mit tartalmaz a Kiadáskezelés Power BI-tartalom. 

## <a name="overview"></a>Áttekintés
Két Power BI tartalomcsomagok, és a 8.1-es és későbbi verzióban a Költséggazdálkodás modulban használhatók. 
- Azoknak az alkalmazottaknak, akik a költségjelentések nyújtanak be készült egy személyes irányítópult. 

  Az irányítópult úgy van kialakítva hogy az egyének rendelkezésére bocsássa a legfontosabb információikat az el nem küldött és elküldött összegekről, valamint elérhetővé tegye a kiadási tranzakciók előzményeivel kapcsolatos információkat. A személyes irányítópult egyetlen lapon tartalmazz a legfontosabb adatokat a felhasználó számára.

- Rendelkezésre áll egy adminisztrátori irányítópult a kötelezettségek foglakozó ügyintézők és a vezetők számára. Az irányítópult célja a az alkalmazotti kiadások megfelelő nyomon követése és jelentése. Biztosít fontos költségmérőszámokat, például a be nem küldött költségek útiköltség és átlagos költségjelentések összege. Tranzakciós adatokat használ, és összesített nézeteket nyújt a költségkezelésről minden vállalatnál. Lebontást is kínál alkalmazottanként pénzügyidimenzió-adatok hozzáadásának lehetőségével. Az Adminisztrátori költség analitika tartalma a következő: 
  - Egy áttekintőlap a kiadási összegekre vonatkozó kulcs mérőszámokról és információkat vázlat állapotú, folyamatban lévő és kész költségjelentésekről. 
  - Egy alkalmazotti statisztikai lapot ahol át lehet tekinteni egy alkalmazott egyéni részleteit idő, a költség típusa és a statisztikai csoport szerint. 
  - Egy alkalmazotti összehasonlítás lapot, ahol több alkalmazott összehasonlítása lehetséges időben. 

Minden összeg a vállalat pénznemében van megadva. Az összes vállalatra vonatkozó adatok láthatók, de ha szükséges vállalati szűrő is hozzáadható. 

## <a name="accessing-the-power-bi-content"></a>A Power BI tartalom elérése
Az Expense Admin Dashboard.pbix és Expense Personal Dashboard.pbix Power BI tartalmakat a Shared assets könyvtárban találja Microsoft Dynamics Lifecycle Services (LCS) megoldásban. A tartalom letöltésére és szervezeténél való megvalósítására vonatkozó további információért lásd: [Power BI-tartalom az LCS megoldásban a Microsofttól és a partnerektől](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/12/12/power-bi-content-from-microsoft-and-your-partners/).
A tartalom elérhető a Költségkezelés munkaterületen beágyazott Power Bi tartalomként. Minden költség tulajdonosa a személyes kötségeket saját maga is elérheti, miközben csak a Kötelezettségek ügyintézők és a vezetők férhetnek hozzá az Adminisztrátori tartalmakhoz az összes felhasználó költségadatainak megtekintéséhez.

## <a name="refreshing-the-power-bi-content"></a>A Power BI tartalom frissítése
A Költséggazdálkodás Power BI tartalomhoz szükséges a TrvBiExpenseMeasurement mérőszám és BudgetActivityMeasure mérőszám frissítése az Entitástárból. 

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Mérőszámok, amelyek a Power BI tartalomban szerepelnek
A tartalom jelentési oldalak készletét tartalmazza. Minden oldal több metrikát tartalmaz, amelyek diagramok, mozaikok, táblázatok formájában jeleníthetők meg. Az alábbi táblázatban a Power BI tartalom megjelenítési formáinak áttekintése található.

**Személyes költségek elemzése**

| Jelentéslap | Megjelenítés                             |
|-------------|-------------------------------------------|
| Költségeim | Útiköltség összege                         |
|             | Folyamatban lévő költségjelentések                |
|             | Szám el nem küldött költségek               |
|             | Kifizetendő személyes költségek              |
|             | Be nem küldött összeg                        |
|             | Beküldött összeg                          |
|             | Visszatérítésre váró összeg             |
|             | Költségjelentések összegekkel és az állapottal   |
|             | Beküldött de nem jóváhagyott költségjelentések.  |
|             | Költségek költségtípus szerint                     |
|             | Költségek kereskedők szerint                      |
|             | Költségek feldolgozott költségek szerint            |
|             | Költségek projekt szerint                       |
|             | Tranzakció teljes összege az időben        |

**Adminisztratív költségek elemzése**

| Jelentéslap         | Megjelenítés                           |           
|---------------------|-----------------------------------------|
| Költségek áttekintése    | Vázlat költségösszegek                   |
|                     | Vázlat költségsorok száma           |
|                     | Vázlat költségsorok                     |
|                     | A költségjelentésbeli irányelvmegsértések        |
|                     | Kinnlevőség összege                      |
|                     | Beküldött de nem jóváhagyott költségek       |
|                     | Jóváhagyott költségek                       |
|                     | Összes költség összege                    |
|                     | Költségjelentés összegzések                |
|                     | Költségek költségtípus szerint                   |
|                     | Költségek kereskedők szerint                    |
|                     | Költségek munkavállalók szerint                   |
|                     | Költségek;s projekt                     |
| Alkalmazottak összehasonlítása | Költségösszegek                         |
|                     | Költségösszegek idővel alkalmazottanként   |
| Alkalmazotti statisztikák | Költségjelentések költségtípus szerint            |
|                     | Személyes kiadások                       |
|                     | Költségjelentések statisztikai csoport szerint     |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]