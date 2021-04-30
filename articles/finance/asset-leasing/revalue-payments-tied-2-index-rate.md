---
title: Referencia-kamatlábhoz kapcsolt lízingdíjfizetések újraértékelése
description: Ez a témakör azt a kiigazítást ismerteti, amely a kötelezettség használatijog-eszköz (ROU) lízingeléséhez történik, amikor a változó lízingfizetések a referencia-kamatláb változása miatt változnak.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseIndexRevaluation
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: f2adddbfdc43fa52bf9a585636ada1b0a63a6be0
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2021
ms.locfileid: "5880838"
---
# <a name="revalue-lease-payments-that-are-linked-to-an-index-rate"></a>Referencia-kamatlábhoz kapcsolt lízingdíjfizetések újraértékelése

[!include [banner](../includes/banner.md)]

Ez a témakör azt a kiigazítást ismerteti, amely a lízingkötelezettség használatijog-eszköz (ROU) lízingeléséhez történik, amikor a változó lízingfizetések a referencia-kamatláb változása miatt változnak. A lízingkötelezettség és a ROU-eszköz korrekciója történik az új kifizetési összegek könyvelése érdekében. A könyvelési standardok kodifikációs témaköre 842 (ASC 842) szerint, ami a standard az általánosan elfogadott könyvelési alapelveknél az Egyesült Államokban (US GAAP), csak a változó kifizetések változnak a kifizetések emelkedése vagy csökkenésekor a referencia-kamatláb változása miatt, kivéve, ha a pénzforgalomban további változások vannak. Ezek a további változások magukban foglalhatják a lízingfeltételeknek a kamatlábakhoz kapcsolódó módosítását. További információ: ASC 842-10-55-225 és a nemzetközi pénzügyi jelentési standard 16 (IFRS 16) 42 (b) bekezdése.

## <a name="adjust-lease-payments"></a>Lízingdíjfizetések módosítása

Kövesse az alábbi lépéseket a referencia-kamatlábhoz kapcsolt lízingdíjfizetések újraértékeléséhez.

1. A lízingindex újraértékelési folyamatának futtatásához nyissa meg az **Eszközlízing \> Időszakos \> Referencia-kamatláb újraértékelés** lehetőséget.

    Megjelenik a **Referencia-kamatláb újraértékelés** lap, amely az összes futtatott korábbi lízingindex-újraértékelési folyamatot megjeleníti. A jelen oldalon található információk tartalmazzák a számsorozat beállításából létrehozott folyamatazonosítót, a jogi személyt, a módosított lízingkönyvek számát, az IFRS 16 lízingek teljes kötelezettségkiigazítását, valamint az ASC 842 lízingekkel kiigazított összes változó kifizetést.

2. Az újraértékelés futtatásához a műveletablakban válassza a **Lízingindex újraértékelése** lehetőséget.

    Megjelenik az **Index újraértékelési paraméterei** párbeszédpanel. Itt szűrheti és kiválaszthatja, hogy mely lízingeket, lízingcsoportokat vagy egyéb feltételeket kell használni az újraértékelendő lízingek kiválasztásakor. Ezenkívül a **Futtatás a háttérben** fülön beállíthatja az index újraértékelési folyamatot úgy, hogy az kötegben fusson.

4. Válassza ki a háttérfeldolgozásban szerepeltetni kívánt lízingek kiválasztásához tartozó szűrőket, majd kattintson az **OK** gombra.

    Megjelenik a **Referencia-kamatláb újraértékelési előnézet** párbeszédpanel, amely megjeleníti az újraértékelendő lízingeket. Bemutatja továbbá az eszköz- és forráskiigazításokat, illetve a változó kifizetési kiigazításokat.
    
5. A lízingek újraértékelésének megakadályozásához válassza ki az **újraértékelendő** lízingeket. Ha nem választ ki lízingeket, a lízingek át lesznek értékelve. Ha befejezte a munkát, az **OK** gombra kattintva újraértékelheti a lízingdíjfizetéseket.
6. Egy adott index újraértékelési folyamathoz létrehozott tranzakciók megtekintéséhez jelölje ki a folyamatazonosítót, majd válassza a **Tranzakciók** lehetőséget.

    Megjelenik egy párbeszédpanel, amely a feldolgozás során létrehozott tranzakciók részleteit jeleníti meg.

> [!NOTE]
> Csak azok a lízingek értékelhetők újra, amelyek újraértékelési dátuma a rendszerdátumra vagy az előttre esik. A rendszer automatikusan figyelmen kívül hagy minden olyan lízinget, amelynek átértékelési dátuma későbbi a rendszerdátumnál.

## <a name="asc-842-leases--index-revaluation"></a>ASC 842 lízingek – Index újraértékelés

A lízing újraértékelési folyamat ASC 842 lízingre gyakorolt hatásainak megtekintéséhez nyissa meg a lízing fizetési ütemezését. Az oldalon csak az újraértékelési dátumon vagy azt követően végrehajtott változó kifizetések láthatók az index átértékelése miatt. Az amortizációs és az értékcsökkenési ütemezés változatlan marad. Ha változó fizetéssel rendelkező számlát hoz létre, a változó fizetés megterhelése a Változó fizetési feladási számlára kerül. A változó fizetési összeg hozzáadódik a közvetlenül a szállítónak feladott jóváírási tételhez, vagy a Bizonylatkötelezettségek számlára, a lízingkönyv beállításától függően.

A lízing részletei oldalon a fizetési ütemezés sorai automatikusan frissülnek egy új sokkal, amely az új referencia-kamatlábat jelzi. Ezenkívül egy oszlop is mutatja, hogy a sort manuálisan vagy az indexátértékelési folyamaton keresztül hozták-e létre.

## <a name="ifrs-16-leases--index-revaluation"></a>IFRS 16 lízingek – Index újraértékelés

A lízing újraértékelési folyamat IFRS 16 lízingre gyakorolt hatásainak megtekintéséhez nyissa meg a kiigazított lízing lízingrészleteit. A **Lízing időtartama** és az **Eszköz hasznos élettartama** mezőket frissítették, hogy tükrözzék a kezdő dátumtól vagy módosítási dátumtól az újraértékelési dátumig történő idő múlását. Ezenkívül a fizetési ütemezés sorai frissültek, hogy tükrözzék a lízingre vonatkozó új kifizetéseket, az új referencia-kamatlábat és a sor létrehozásának módját.

Megtekintheti az átértékelési dátummal kezdődő újonnan létrehozott fizetési ütemezést, és megjelenítheti a teljes frissített kifizetési összeget. Új lízingkötelezettség-amortizációs ütemezés és eszközértékcsökkenési ütemezés is létrejött, hogy tükrözze a kiigazított kifizetési ütemezést.

A naplóbejegyzés automatikusan feladta a helyesbítő naplóbejegyzést a számlára az index újraértékeléshez kapcsolódó lízingkifizetések változására.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
