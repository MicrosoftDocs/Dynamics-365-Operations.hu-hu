---
title: Költségösszetevő-dimenziók
description: A költségkönyvelés egyik alapvető elemeként a költségösszetevő-dimenziók használhatók a kategorizáláshoz és a költségmozgások nyomon követéséhez.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMDimension
audience: Application User
ms.reviewer: roschlom
ms.custom: 223204
ms.assetid: 1eda0e62-760b-4737-9dfd-3c3c38d80c1a
ms.search.region: global
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 2fa602d01cadecbf24c2433360f7b2a8ebb0854a
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2021
ms.locfileid: "6355155"
---
# <a name="cost-element-dimensions"></a>Költségösszetevő-dimenziók

[!include [banner](../includes/banner.md)]

A költségkönyvelés egyik alapvető elemeként a költségösszetevő-dimenziók használhatók a kategorizáláshoz és a költségmozgások nyomon követéséhez. 

Egy költségösszetevő a számlatükör valamely költségfüggő elemének felel meg. Alapvetően ez bármely olyan elem lehet egy üzletág legalacsonyabb szintjén, ahová költségek bekerülhetnek. A költségösszetevők fogalma mindent lefed a főkönyvi számláktól az összes, költségfüggő erőforrásig. A költségkönyvelés jelenleg támogatja a főkönyvi számlákat.

## <a name="two-types-of-cost-elements"></a>Kétféle típusú költségösszetevők
A költségösszetevőknek két típusa van: az elsődleges költségösszetevők és a másodlagos költségösszetevők. A következő táblázat a két típus közötti különbséget ismerteti.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Elsődleges költségösszetevők</strong></td>
<td><strong>Másodlagos költségösszetevők</strong></td>
</tr>
<tr class="even">
<td>Az elsődleges költségösszetevők a pénzügyi könyvelésből a költségkönyvelésbe menő költségeket jelentik. A költségösszetevők szerkezete a főkönyv eredménykimutatási szzerkezetének felel meg, ahol egy költségösszetevő egy fő számlának felel meg. Nem minden fő számla jelenik meg feltétlenül költségösszetevőként - ez attól függ, hogy mik a vállalat igényei. Elsődleges költségösszetevők közé páldául a következők tartoznak:
<ul>
<li>Eladott áruk beszerzési értéke (COG)</li>
<li>Közvetett anyagköltségek</li>
<li>Személyi költségek</li>
<li>Energiaköltségek</li>
</ul></td>
<td>A másodlagos költségösszetevők a belső költségfolyamatokat jelentik, mivel ezeket a költségeket csak a költségkönyvelésben hozzák létre és használják. Arra szolgálnak hogy a költség forrását vissza lehessen keresni. Ezek a költségösszetevők költségfelosztásokban és többletköltség-számításokhoz használatosak. Másodlagos költségösszetevők közé páldául a következők tartoznak:
<ul>
<li>Gyártási költségek</li>
<li>Gyártás, anyagok és marketing rezsije</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="cost-element-dimensions-and-cost-element-dimension-members"></a>Költségösszetevő-dimenziók és költségösszetevő-dimenziótagok
A költségösszetevőket *költségösszetevő-dimenzióknak* nevezik. Az egyes dimenzióértékeket *költségösszetevő-dimenziótagoknak* nevezik. Vegyünk például egy Egyesült Államokbeli számlatükör-szerkezetet (számlatükör), amely a kötelezően előírt jelentéskészítés alapja. Ez a számlatükör költségösszetevő-dimenzióként használatos. A számlák, amelyek elsődleges költségösszetevők, a költségkönyvelésben költségösszetevő-dimenziótagokként jelennek meg. Az alábbi képernyőképen látható példa a fő számlákat ábrázolja költségösszetevő-dimenzióként, ahol a tényleges fő számlák a költségösszetevő-dimenziótagok. 

[![A Fő számlákat költségösszetevő-dimenzióként bemutató képernyőkép.](./media/cost-element-dimensions.png)](./media/cost-element-dimensions.png)

## <a name="import-cost-element-dimension-members-through-data-connectors"></a>A költségösszetevő-dimenziótagok importálása adatcsatolókon keresztül
Ahhoz, hogy megkönnyítse a költségösszetevő-dimenziók beállítását a költségkönyvelésben, használhat olyan adatcsatolókat, amelyeket előre vagy egyedileg készítenek el az elsődleges költségösszetevők lekéréséhez egy vagy több forrásrendszerből.

## <a name="implementation-considerations"></a>Kivitelezési szempontok
Mivel a költségösszetevők a legalacsonyabb szintű költségadatokat jelentik, gondoskodnia kell arról, hogy a vezetői jelentések létrehozásához szükségesek összes költségösszetevő legyen figyelembe véve, amikor a költségösszetevők szerkezetét létrehozza. Nehézkes lehet megfelelő számú költségösszetevőt találni a költségkontrollhoz. Ha több ezer költségösszetevő van, az megnehezítheti az egyes költségösszetevők szabályozását. Másik lehetőségként a költségösszetevőket csoportosíthatja, és a költségkontrollt összesített szinten kezelheti.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]