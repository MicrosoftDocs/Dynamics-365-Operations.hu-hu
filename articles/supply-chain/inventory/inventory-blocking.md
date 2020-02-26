---
title: Készletzárolás
description: A témakör tájékoztatást nyújt a készletzárolásról, amely a minőség-ellenőrzési eljárás része a Supply Chain Management megoldásban. A készletzárolás segítségével megakadályozhatja a cikkek felhasználását vagy feldolgozását.
author: perlynne
manager: AnnBe
ms.date: 01/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventBlocking, InventQualityOrderTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2094
ms.assetid: 1968e32f-eff9-4c17-8f7f-a870f0c38fbc
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e1a870936619d07db01d5a8fe83b3fab73693187
ms.sourcegitcommit: e5a3c85a322a9216b8f176536d664fef40ae0bec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/17/2020
ms.locfileid: "2971487"
---
# <a name="inventory-blocking"></a>Készletzárolás

[!include [banner](../includes/banner.md)]

A témakör tájékoztatást nyújt a készletzárolásról, amely a minőség-ellenőrzési eljárás része a Supply Chain Management megoldásban. A készletzárolás segítségével megakadályozhatja a cikkek felhasználását vagy feldolgozását.

Készletcikkeket a következő módokon zárolhat:
-   Manuálisan
-   Minőségi rendelés létrehozásával
-   Minőségi rendelést generáló folyamat használatával
-   Készletállapot zárolásának használatával

## <a name="blocking-items-manually"></a>Cikkek manuális zárolásával
Egy cikk adott mennyiségét a **Készlet zárolása** oldalon létrehozott tranzakcióval zárolhatja. Csak az aktuális készletben elérhető cikkeket lehet manuálisan zárolni. Manuálisan zárolt mennyiségeknél el kell döntenie, hogy a várt bevételezések is szerepelhetnek-e (várt aktuális mennyiségként) a tervezési tevékenységben. A várt bevételezések olyan zárolt cikkek, amelyek az ellenőrzés befejezése után várhatóan bekerülnek az aktuális készletbe. A várt dátumot megtarthatja manuálisan. Alapértelmezés szerint a **Várt bevételezések** beállítás van megadva olyan cikkeknél, amelyek a minőségi rendelésen keresztül zárolva vannak. Manuálisan zárolt mennyiségek zárolását feloldhatja a **Készletzárolás** oldalon, a tranzakció törlésével.

## <a name="blocking-items-by-creating-a-quality-order"></a>Cikkek zárolása minőségi rendelés létrehozásával
Megadhat cikkeket, amelyeket a minőségi rendelés létrehozásával ellenőrizni kell a **Minőségi rendelések** oldalon. A minőségi rendelés létrehozásakor a cikk megadott mennyisége zárolásra kerül. A mintavételi terv, amely egy minőségi rendeléshez van társítva, csak az ellenőrzendő cikkek mennyiségét szabályozza, nem a zárolt mennyiséget. A minőségi rendelésen megadott mennyiség a zárolt mennyiség, függetlenül a mintavételi terv által megadott mennyiségtől, melyet ellenőrzésre kell küldeni.

> [!NOTE]
> Az Alaptervezés nem támogatja a köteg lejárati dátuma és a készletállapot blokkolása funkciók használatát. Ennek hatására az Alaptervezés során az aktuális készletből dupla kivétel következhet be. A lejárt kötegek blokkolására azt ajánljuk, hogy a készlet állapota helyett kötegdiszpozíciós kódokat használjon.

## <a name="blocking-items-by-using-a-process-that-generates-a-quality-order"></a>Cikkek zárolása minőségi rendelést generáló folyamat használatával
Ha egy minőségi folyamat meghatározza, hogy egy cikket felül kell vizsgálni, akkor a cikkmennyiség automatikusan zárolásra kerül. Így ha egy minőségi rendelés automatikusan létrejön, akkor a minőségi rendeléshez hozzárendelt mintavételi terv nem csak a vizsgálandó mennyiséget, hanem a zárolt mennyiséget is meghatározza. Ha a **Teljes zárolás** opció a **Cikkmintavétel** képernyőn meg van jelölve, akkor például a beszerzési rendelés sorának teljes mennyisége zárolásra kerül a vizsgálathoz, a mintavételi mennyiségtől függetlenül.
### <a name="example"></a>Példa

A következő példában minőségi rendelés generálódik egy beszerzési rendelés szállítólevelének feladása során. A **Minőségi társítások** képernyőn meghatározta, hogy a beszerzési rendelés szállítólevele van beállítva a minőségi rendelést kiváltó folyamatként.

|Beállítás                                                                     |Felhasználói művelet                 |Eredmény             |
|--------------------------------------------------------------------------|----------------------------|-------------------|
| A minőségi társítás megadja, hogy a beszerzési rendelés szállítólevelének feladásakor minőségi rendelést kell generálni. A minőségi rendelés cikkmintavételi beállítása alapján a beszerzési rendelés sorában szereplő mennyiség 10 %-át kell ellenőrizni. Emellett, mivel a **Teljes zárolás** jelölőmező be van jelölve a cikkmintavételi beállításokban, a beszerzési rendelés sorának teljes mennyiségét zárolni kell a vizsgálat idejére, a vizsgálatra küldött mennyiségtől függetlenül. | A csomagjegyzék feladásra kerül. | Minőségi rendelés generálódik. A cikk beszerzési rendelési mennyiségének 10%-át elküldik vizsgálatra. A beszerzési rendelés sorának teljes mennyisége zárolásra kerül. |

## <a name="blocking-items-by-using-inventory-status-blocking"></a>Cikkek zárolása a készletállapot zárolásának használatával
Megadhatja, hogy mely készletállapotok zároló állapotok, a **Készletzárolás** paraméter használatával, a **Készletállapotok** oldalon.  Készletállapotok nem használhatók zároló állapotokként termelési rendelések, értékesítési rendelések, átmozgatási rendelések, kimenő tranzakciók vagy projektintegráció esetén. Kimenő munka esetén mindig elérhető készletállapotú cikkeket használjon. Ha **Törött** állapotú cikkekkel futtat alaptervezést, a rendszer hiányzónak fogja tekinteni őket, és automatikusan feltölti a készletet.



<a name="additional-resources"></a>További erőforrások
--------

[Készletzárolás létrehozása és karbantartása](tasks/create-maintain-inventory-blocking.md)

[Minőségkezelési folyamatok](quality-management-processes.md)

[Áru minőségének ellenőrzése](tasks/inspect-quality-goods.md)
