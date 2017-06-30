---
title: "Költségbejegyzések"
description: "Ez a cikk tájékoztat a költségbejegyzésekről és a létrehozásuk idejéről. Egy költségbejegyzés egy olyan rekord, amely feljegyzi egy adott esemény költségét és mennyiségét."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19131
ms.assetid: dd2663d8-bcc0-47b1-b36d-57433143487c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 1045ecbf7080f12bc60336609180173544e4e0eb
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017


---

# <a name="cost-entries"></a>Költségbejegyzések

[!include[banner](../includes/banner.md)]


Ez a cikk tájékoztat a költségbejegyzésekről és a létrehozásuk idejéről. Egy költségbejegyzés egy olyan rekord, amely feljegyzi egy adott esemény költségét és mennyiségét.

A költségbejegyzések olyan készlettranzakciók aggregációja, amelyek aktív pénzügyi készletdimenziókon lettek rögzítve.

## <a name="examples"></a>Példák
### <a name="example-1-no-cost-entries-are-created"></a>1. példa: Nincsenek költségbejegyzések létrehozva

Egy átmozgatási naplóesemény regisztrálásra kerül. Az esemény áthelyezi az A cikk egyik részét A helyről B helyre. A helykészlet dimenziója nem képezi a költségobjektum részét. Emiatt az esemény két készlettranzakciót hoz létre, de nem költségtételeket nem jön létre.

### <a name="example-2-cost-entries-are-created"></a>2. példa: Költségbejegyzések létrehozva

Egy átmozgatási naplóesemény regisztrálásra kerül. Az esemény egy darab A cikket visz át az 1. telephelyről a 2. telephelyre. A telephely készletdimenziója az önköltségi objektum részének tekintendő. Emiatt az esemény két készlettranzakciót és költségtételt hoz létre.

### <a name="example-3-one-cost-entry-is-created"></a>3. példa: Egy költségbejegyzés jön létre

Egy termék-bevételezési esemény kerül regisztrálásra egy beszerzési rendeléshez. Az esemény 100 darabot regisztrál A cikkből 10,00 USD egységköltség mellett. Mivel az A cikk sorozatszámot alkalmaz a készletkezelés céljának nyomon követéséhez, egy egyedi sorozatszám jön létre minden egyes bevételezett cikkhez. Emiatt az esemény két 100-as készlettranzakciót és egy költségtételt hoz létre.

## <a name="cost-entries-page"></a>Költségbejegyzések oldal
Az új **Költségbejegyzések** lap lehetővé teszi a mennyiségek és a költségek regisztrációjának megtekintését és felügyeletét. Ezen lap a **Készlettranzakció** és a **Készletkiegyenlítési** lapokat egészíti ki. A rekordok időrendi sorrendben kerülnek regisztrálásra egy adott eseményhez. Ezért gyorsan megkeresheti és szabályozhatja az összesített költségeket egy adott eseményre vagy a dokumentumhoz kapcsolódó összes eseményre vonatkozóan. Egy példa:

-   Egy termék-bevételezési esemény kerül regisztrálásra az A termékhez. 100 darab kerül bevételezésre 10,00 USD egységköltséggel.
-   Néhány nappal a számlaesemény regisztrálását követően a költség 11,00 USD összegre nő. Emiatt a teljes összeg 1100 USD lesz. Egy második bizonylat jön létre az 100 USD értékű eltérés számlázásához.
-   Néhány nappal később 15,00 USD vegyes költség kerül regisztrálásra a beszerzési rendeléshez a szállítási költségek fedezésére.

| Bizonylat  | Dátum       | Hivatkozás      | Szám | Adagazonosító  | Mennyiség | Összeg  |
|---------|------------|----------------|--------|---------|---------------|----|
| 00001   | 2015/01/01 | Beszerzési rendelés | 100001 | 0000101 | 100,00   | 1000.00 |
| 00002   | 2015/01/20 | Beszerzési rendelés | 100001 | 0000101 |          | 100,00  |
| 00003   | 2015/01/31 | Kiigazítás     | 100001 | 0000101 |          | 1500   |

A **Költségtételek** lap lehetővé teszi a dokumentumazonosító és a dátum alapján történő szűréseket. 

> [!NOTE]
> A költségtételek csak a [költségobjektumok](cost-object.md) vagy a kiadott termékek esetében érhetők el.

<a name="see-also"></a>Lásd még
--------

[Költségobjektumok](cost-object.md)




