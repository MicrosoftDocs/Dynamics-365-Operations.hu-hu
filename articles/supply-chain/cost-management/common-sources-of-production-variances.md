---
title: A termelési különbözetek gyakori okai
description: Ez a cikk a termelési eltérések különböző formáinak forrásait ismerteti.
author: JennySong-SH
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventCostTrans, ProdCalcVarianceTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 79753
ms.assetid: 14ac7db4-fb40-43c1-bb0d-1d51fc91d24f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8b0f7a66c00540216887c7913e7f094c819b693a
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/03/2022
ms.locfileid: "8673998"
---
# <a name="common-sources-of-production-variances"></a>A termelési különbözetek gyakori okai

[!include [banner](../includes/banner.md)]

Ez a cikk a termelési eltérések különböző formáinak forrásait ismerteti. 

Íme, néhány tipikus példa az **adag méret** eltéréseire:

-   A termelési rendelés helyes mennyisége eltér az elszámolóár számításához használt mennyiségtől. A mennyiség adja az állandó költségek amortizációjának alapját.
-   A termelési rendelés állandó költségeinek értéke nem egyenlő az elszámolási ár számításánál használt állandó értékekkel. A termelési rendelés során alkalmazott állandó értékek több okból is eltérőek lehetnek. Az állandó költségek például reflektálhatnak a következő tényezőkre:
    -   A termelési anyagjegyzék (BOM) vagy az útvonal manuális változtatásaira
    -   Az eltérő anyagjegyzék verzió vagy az eltérő útvonal verzió választására a termelési rendelés során
    -   A cikkhez rendelt anyagjegyzék verzió vagy útvonal verzió tervezett műszaki módosításaira

Íme, néhány tipikus példa a **termelési ár** eltéréseire:

-   Az útvonal tervezési művelet jelentett felhasználási költség kategóriája (illetve a költség kategória ára) nem egyezik meg, az alap költségszámítás során alkalmazott költség kategóriával.
-   A költségkategória árához tartozó önköltség eltér az elszámolóár számításában használt költségkategória árától.

Íme, néhány tipikus példa a **termelési mennyiség** eltéréseire:

-   Többet vagy kevesebbet ad ki egy összetevő anyagból.
-   Alá- vagy fölé jelenti az útvonaltervezés idejét.
-   A rendelendő mennyiséghez képest többet, vagy kevesebbet rendel a megfelelő mennyiségnél a fő cikkből. Az összetevők kiadása és a műveletek jelentése azonban, a termelési rendelés mennyiségi rendelésétől függ.

Íme, néhány tipikus példa a **termékhelyettesítés** eltéréseire:

-   Olyan összetevő anyagot ad ki, amely nem szerepel a termelési anyagjegyzékben.
-   Manuálisan hozzáad a termelési anyagjegyzékhez és felhasználtként jelent egy összetevőt.
-   Jelenti egy cikk felhasználását, azonban nem adja azt hozzá manuálisak a termelési anyagjegyzékhez.
-   Manuálisan hozzáad egy műveletet a termelési útvonalhoz és teljesítettként jelenti a műveletet.
-   A termelési rendelés létrehozásakor, az alap költségszámításban használt anyagjegyzéktől eltérő anyagjegyzéket választ.
-   A termelési rendelés létrehozásakor, az alap költségszámításban használt útvonal verziótól eltérő útvonal verziót választ.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]