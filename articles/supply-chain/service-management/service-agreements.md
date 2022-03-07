---
title: Szolgáltatási szerződések kialakítása és megkötése – áttekintés
description: A szolgáltatási szerződések segítségével meghatározhatja, hogy milyen erőforrásokat használ egy átlagos szervizlátogatás során, és ezeket hogyan számlázza a vevőnek.
author: kamaybac
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 955e360a1c0d6aec51e82598737c847b190e5e1d
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2022
ms.locfileid: "7985861"
---
# <a name="develop-and-establish-service-agreements-overview"></a>Szolgáltatási szerződések kialakítása és megkötése – áttekintés

[!include [banner](../includes/banner.md)]

A szolgáltatási szerződések segítségével meghatározhatja, hogy milyen erőforrásokat használ egy átlagos szervizlátogatás során, és ezeket hogyan számlázza a vevőnek.

Minden szolgáltatási szerződés projektekhez van csatolva, amelyeken keresztül feladhatók és kiszámlázhatók a tranzakciók. A szervizrendelési tranzakciók ugyanakkor közvetlenül a projekten keresztül is kiszámlázhatók, anélkül, hogy a szervizrendelést szolgáltatási szerződéshez kellene csatolniuk. Ha a szervizrendelés csak egyszeri szervizlátogatás miatt jött létre, akkor érdemes ezt az utat választani, mivel a szerviztranzakció feldolgozása így kevesebb erőforrást emészt fel, mint a részletes szolgáltatási szerződési adatok hosszabb ideig tartó nyilvántartása az ügyfélről.

## <a name="service-agreement"></a>Szolgáltatási szerződés

Minden szolgáltatási szerződésben meg kell adnia egy projektet, a szolgáltatási szerződés azonosítóját és szerződéscsoportját. A szolgáltatási szerződések csoportjai a szolgáltatási szerződések rendezésére és csoportosítására szolgálnak.

A szolgáltatási szerződés fejlécének egyes beállításai a csatolt szerződéssorokra vonatkoznak:

-  A szolgáltatási szerződés felfüggesztési állapota. Ha a szolgáltatási szerződés fel van függesztve, akkor nem lehet belőle szervizrendeléseket generálni.
-  A szolgáltatási szerződés időtartama.
-  A szervizrendeléssorok hogyan állnak össze szervizrendelésekké.
-  A szolgáltatási szerződés sablon-e.

A szolgáltatási szerződés fejlécében beállíthatja azokat a szolgáltatási tárgyakat és szervizfeladatokat is, amelyek a szerződében használhatók. Adja meg azokat a szervizfeladatokat és -tárgyakat, amelyeket a szerződés különböző soraihoz kell majd csatolni.

A szolgáltatási szerződés fejlécéből szerződéssorokat illetve szolgáltatássablon-sorokat másolhat az aktuális szolgáltatási szerződésbe.

A programban felfüggesztheti a szolgáltatási szerződéseket, és leállíthatja az egyes szolgáltatásiszerződés-sorokat.

Ha valamelyik szolgáltatásiszerződés-sornál bejelöli a **Felfüggesztve** jelölőnégyzetet, akkor a következők nem lehetségesek:

-    Szervizrendelések automatikus és kézi létrehozása a szolgáltatási szerződésből.

Ha valamelyik szolgáltatásiszerződés-sornál bejelöli a **Leállítva** jelölőnégyzetet, akkor a következők nem lehetségesek:

-    Szervizrendelések automatikus és kézi létrehozása a szolgáltatásiszerződés-sorból.
-    A szolgáltatásiszerződés-sor másolása egy másik szolgáltatási szerződésbe vagy szervizrendelésbe.


> [!NOTE]
> Ha egy szolgáltatási szerződés fel van függesztve, akkor a program minden hozzá tartozó sort leállít, függetlenül attól, hogy a sor milyen állapotban van.

## <a name="service-agreement-lines"></a>Szolgáltatási szerződések sorai

A szolgáltatási szerződések minden egyes sora részletesen leírja a javasolt szervizmunka tartalmát. A sorok a következő beállításokat tartalmazzák:

-  A tranzakció típusa és a tranzakciótípus leírása.
-  A szervizt végrehajtó alkalmazott nevét.
-  A tárgyat, amelyen a szolgáltatási szerződés szerint a szervizt végre kell hajtani.
-  A gyakoriságot, amellyel a munkát végre kell hajtani, és a társított cikk-, költség- és díjtranzakciókat regisztrálni.
-  Az időablakot, amelyen belül a szervizrendelés-sorok egy szervizrendelésbe csoportosíthatók.
-  Szerződéssorok csoportosítására használt szervizfeladatok, amelyek általános szinten összefoglalják a szerviztechnikusok és a vevők számára, hogy milyen szervizfeladatot kell elvégezni.
-  A sor le van-e állítva. Ha egy sor le van állítva, akkor ahhoz nem hozható létre szervizrendelés.
-  Projektbeállítások, például a kategória és a sortulajdonság.

## <a name="related-topics"></a>Kapcsolódó témakörök

[Szolgáltatási szerződések létrehozása](create-service-agreements.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]