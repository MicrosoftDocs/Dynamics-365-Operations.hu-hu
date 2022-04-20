---
title: Műveletkérő üzenetek
description: A műveletkérő üzenet olyan, a rendszer által létrehozott üzenet, amely javaslatot tesz egy létező tervezett vagy megerősített rendelés módosítására.
author: t-benebo
ms.date: 03/18/2022
ms.topic: article
ms.search.form: ReqGroup, MCRSalesOrderMessages, MCRSalesTableDetailedStatus, TAMItemVendRebateGroup, TAMVendRebate, TAMVendRebateAgreementLineInfoPart, TAMVendRebateGroup, TAMVendRebateTable, TAMVendRebateTrans, ReqTransActionListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19411
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: e6df6cfd038383b3eeaa3659e0af3e469429f81e
ms.sourcegitcommit: 197e6ddee84522fd587c6e4ee4f9089101e301c2
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2022
ms.locfileid: "8570254"
---
# <a name="action-messages"></a>Műveletkérő üzenetek

[!include [banner](../includes/banner.md)]

A műveletküldető üzenet olyan, a rendszer által generált üzenet, amely javaslatot tesz egy létező tervezett, jóváhagyott vagy jóváhagyott rendelés módosítására.

Az alaptervezés számítása által művelet üzenetek jönnek létre a módosult szükségletekre válaszul. Például egy értékesítési rendelés szállítási dátuma vagy mennyisége azután módosul, hogy már létrehozott egy beszerzési rendelést, hogy teljesíteni tudja az adott értékesítési rendelés iránti igényt. Ebben az esetben az alaptervezés számítása egy vagy több olyan műveletküzenetet generál, amelyek a beszerzési rendelés frissítését javasolják. Eldöntheti, hogy megtörténjenek-e a javasolt módosítások.

Beállíthatja, hogy hogyan számítsák ki a műveleti üzeneteket ahhoz a fedezeti csoporthoz, amelyhez egy cikket csatol.

## <a name="select-action-messages"></a>Műveletkérő üzenetek kijelölése

A **Fedezeti csoportok** lapon kiválaszthatja azokat a művelet üzeneteket, amelyeket szeretné ha a rendszer létrehozna, és azokat a fedezeti csoportokat vagy elemeket, amelyek az üzenetekre vonatkoznak. A következő táblázat felsorolja a kiválaszthat kívánt műveletküzenetet.

| Üzenet | Leírás |
|---|---|
| Előleg | A rendszer szükség szerint műveletkértes üzeneteket hoz létre a rendelések korábbi dátumra való áthelyezéséhez. Az Előleg **árrés** mezőben adhatja meg, hogy legfeljebb hány nap lehet egy bevételezés és egy kiadás között előzetes művelet nélkül. |
| Halasztás | A rendszer szükség szerint műveletkértes üzeneteket hoz létre a rendelések későbbi dátumra való áthelyezéséhez. Az Árrés **elhalasztása** mezőben adhatja meg, hogy legfeljebb hány nap lehet egy bevételezés és egy kiadás között halasztás nélkül. |
| Csökkentés | A rendszer akkor generál műveletkezési üzeneteket, amikor a termelési rendeléseket, a beszerzési rendeléseket és az egyéb bevételezési tranzakciókat csökkenteni kell, hogy megelőzzék a készletszintek többletét. |
| Növelés | A rendszer akkor generál műveletkezési üzeneteket, amikor a termelési rendeléseket, a beszerzési rendeléseket és az egyéb bevételezési tranzakciókat meg kell növelni a készlethiány elkerülése érdekében. |
| Származtatott műveletek | A bevételezési tranzakciókhoz létrehozott műveletküzenetek bármely származtatott követelménybe át lesznek ásva, és a követelményeknek megfelelő bevételezési tranzakciókhoz létrejönnek a szükséges műveletküzenetek. |

A következő szakaszok néhány részletes helyzetet nyújtanak.

## <a name="increase-and-decrease-actions-with-product-default-order-quantities"></a>Műveletek növelése és csökkentése az alapértelmezett termékrendelési mennyiségekkel

A cikkek **alapértelmezett rendelési** beállításai lapon minimális rendelési mennyiséget, maximális rendelési mennyiséget és több értéket lehet beállítani. A rendszer ezt követően figyelembe veszi ezeket a beállításokat, amikor műveleteket javasol, hogy a javaslatok soha ne okoznak alultelékeket.

Például van egy olyan cikk **, amely az Alapértelmezett rendelés beállításai lapon a következő beállításokat** tartalmazza:

- **Minimális rendelési mennyiség:** *0*
- **Maximális rendelési mennyiség:** *90*
- **Többszörös:** *20*

Ha 60 mennyiségű cikkre van igény, az alaptervezés egy 60 mennyiségű tervezett beszerzési rendelést hoz létre. Ha az igény 30-al nő, az alaptervezés 40-es emelést javasol, mivel a 20 többszörösét be fogja tartani, és soha nem okoz alul- és alulpótlást.

## <a name="action-messages-for-orders-related-to-safety-stock"></a>A biztonsági készlethez kapcsolódó rendelésekhez kapcsolódó műveletküzenetek

Az olyan rendelésekhez küldött műveletküzenetek, amelyekhez biztonsági készlet van rendelve, soha nem javasolják a biztonsági készlethez szükséges mennyiség alatti mennyiség csökkentését. Más szóval, ha olyan rendelés van, amely biztonsági készletet és vevői igényt szállít, és a kereslet csökken vagy törlődik, akkor az alaptervezés a tervezett rendelés csökkentését javasolja a csökkentett igényű rendeléssel. Ugyanakkor soha nem javasol a szükséges biztonsági készletnél kisebb értéket.

A rendszer nem fogja javasolni a biztonsági készlet rendelkezésre állásának elhalasztását, mivel a feltételezés az, hogy a biztonsági készletet a szükséges időben és a szükséges dátumon kell megadni.

### <a name="advance-and-postpone-actions-related-to-boms"></a>Az AKK-okkal kapcsolatos műveletek előzetes vagy elhalasztása

Az anyagjegyzékek összetevőihez kapcsolódó műveleteket a szülő cikkek műveletei előtt kell alkalmazni, mivel ez hatással lehet a magasabb szintű anyagjegyzékekkel kapcsolatos további rendelésekre. Ezután újra kell futtatnia az alaptervezést ahhoz, hogy újraszámtassa és javasolja a megfelelő műveleteket.

Például a következő helyzet van:

- A termelés *típusú végleges jó FG* *anyagjegyzéke* nyersanyagot is tartalmaz.*·*
- A mai dátum január 21..
- Az FG *már létező, kiadott termelési* rendelése január 25-re van ütemezve.
- A meglévő termelési rendelés támogatása érdekében az alaptervezés tervezett beszerzési rendelést hozott létre a szükséges nyersanyag-anyaggal.*·* A rendelés követelménydátuma január 25-e.
- A mai napon létrejön egy új értékesítési rendelés az *FG* számára. A követelménydátum a mai dátum (január 21.).
- Január 21-e le van zárva szállításra *az RM naptárban*, de a január 22-e nyitva van.

Az alaptervezés futtatásakor előzetes műveletküzeneteket generál, amelyek javasolják az előzőleg ütemezett termelés áthelyezését, hogy teljesíteni tudja a mai rendelést.

- Az új igénynek való megfeleltetése *érdekében javasolja az FG* termelési rendelésének január 21-ére való áthelyezését. (Ez a javaslat a lezárás dátumának figyelembe véve nélkül teszi ezt a javaslatot a következőre: *RM*.)
- Mivel *még mindig szükséges az RM* a termelési rendeléshez, a tervezett beszerzési rendelést is javasolja. Azonban most az RM naptárat *ellenőrzi*. Ezért javasolja az *RM* tervezett beszerzési rendelésének január 22-re való áthelyezését (mivel a január 21-e le van zárva).

Amint látható, *a szükséges nyersanyag-RM* *most túl későn érkezik meg az FG ütemezett termeléséhez*. Ezért előbb alkalmaznia kell az *előzetes* műveletet a tervezett beszerzési rendelésre az RM számára, majd újra futtatnia kell az alaptervezést. Ezen a ponton az alaptervezés egy *új műveletk üzenetet generál, amely javasolja az FG* termelési rendelésének január 22-re való áthelyezését.
