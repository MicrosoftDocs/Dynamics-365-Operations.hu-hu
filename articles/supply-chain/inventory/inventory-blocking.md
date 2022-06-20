---
title: Készletzárolás
description: A cikk tájékoztatást nyújt a készletzárolásról, amely a minőség-ellenőrzési eljárás része a Supply Chain Management megoldásban. A készletzárolás segítségével megakadályozhatja a cikkek felhasználását vagy feldolgozását.
author: yufeihuang
ms.date: 03/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventBlocking, InventQualityOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2094
ms.assetid: 1968e32f-eff9-4c17-8f7f-a870f0c38fbc
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f7a16c41b56b30098945a6fbdb02577624b6e173
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8857808"
---
# <a name="inventory-blocking"></a>Készletzárolás

[!include [banner](../includes/banner.md)]

A cikk tájékoztatást nyújt a készletzárolásról, amely a minőség-ellenőrzési eljárás része a Supply Chain Management megoldásban. A készletzárolás segítségével megakadályozhatja a cikkek felhasználását vagy feldolgozását.

Készletcikkeket a következő módokon zárolhat:

- Manuálisan
- Minőségi rendelés létrehozásával
- Minőségi rendelést generáló folyamat használatával
- Készletállapot zárolásának használatával

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

|Beállítás |Felhasználói művelet |Eredmény |
|----|---|---|
| A minőségi társítás megadja, hogy a beszerzési rendelés szállítólevelének feladásakor minőségi rendelést kell generálni. A minőségi rendelés cikkmintavételi beállítása alapján a beszerzési rendelés sorában szereplő mennyiség 10 %-át kell ellenőrizni. Emellett, mivel a **Teljes zárolás** jelölőmező be van jelölve a cikkmintavételi beállításokban, a beszerzési rendelés sorának teljes mennyiségét zárolni kell a vizsgálat idejére, a vizsgálatra küldött mennyiségtől függetlenül. | A csomagjegyzék feladásra kerül. | Minőségi rendelés generálódik. A cikk beszerzési rendelési mennyiségének 10%-át elküldik vizsgálatra. A beszerzési rendelés sorának teljes mennyisége zárolásra kerül. |

## <a name="blocking-items-by-using-inventory-status-blocking"></a>Cikkek zárolása a készletállapot zárolásának használatával

Megadhatja, hogy mely készletállapotok zároló állapotok, a **Készletzárolás** paraméter használatával, a **Készletállapotok** oldalon.  Készletállapotok nem használhatók zároló állapotokként termelési rendelések, értékesítési rendelések, átmozgatási rendelések, kimenő tranzakciók vagy projektintegráció esetén. Kimenő munka esetén mindig elérhető készletállapotú cikkeket használjon. Ha **Törött** állapotú cikkekkel futtat alaptervezést, a rendszer hiányzónak fogja tekinteni őket, és automatikusan feltölti a készletet.

## <a name="take-care-when-blocking-items-that-use-both-inventory-status-blocking-and-quality-order-blocking"></a>A készletállapot zárolását és a minőségi rendelés zárolását egyaránt használó cikkek blokkolásakor körültekintően járjon el

Létrehozhat olyan minőségi rendelést, amely olyan készlettel van társítvam amelynek a készletállapota esetében a **Készletzárolás** paraméter engedélyezve van. Ebben az esetben a minőségi rendelés egy külön készletzárolási rekordot hoz létre a készletállapot által létrehozott rekordon felül. Mivel a minőségi rendelés készletzárolásának **Várt bevételezések** paramétere engedélyezett lesz, ezért egy további *Megrendelt készlet* tranzakciót generál, amelyet a készletállapota is blokkol. Ez a kombináció problémákhoz vezethet a generált készlettranzakciók jelentésének megismerése során, mivel úgy fog megjelenni, mintha a teljes blokkolt mennyiség meghaladná a teljes aktuális készletmennyiséget. Vizsgáljuk meg például a 10 darab A0001 cikk bevételezési példa tranzakcióit egy 1 darabos mintavételezésből álló minőségi rendeléssel. A viselkedés attól is függ, hogy engedélyezve van-e a **Rendelt cikkek foglalása** beállítás a **Készlet- és raktárkezelési paraméterek** lapon.

>[!NOTE]
>Ha együtt használja a készletállapot-zárolást és a minőségi rendeléseket, kifejezetten ajánljuk, hogy engedélyezve legyen a **Rendelt cikkek foglalása** beállítás.

### <a name="example-with-reserve-ordered-items-enabled"></a>Példa a „Rendelt cikkek foglalása” beállítás engedélyezésével

Ha a **Rendelt cikkek foglalása** engedélyezve van, minden készletzárolási tranzakció *Foglalt tényleges* vagy *Foglalt rendelt* állapotú lesz.

| Készlettranzakció hivatkozása | Fogadás | Kiadás | Mennyiség | Hely | Raktár | Készlet állapota | Helyszín | Azonosítótábla | Megjegyzés |
|---|---|---|---|---|---|---|---|---|---|
| Beszerzési rendelés | Beszerezve | | 10 db | 2 | 24 | Zárolás | RECV | receiptLp1 | | 
| Készletzárolás | | Foglalt tényleges | -9 db | 2 | 24 | Zárolás | | | A készletállapot zárolása által generált tranzakció |
| Készletzárolás | | Foglalt tényleges | -1 db | 2 | 24 | Zárolás | RECV | receiptLp1 | A minőségi rendelés mintavételi zárolása által generált tranzakció |
| Készletzárolás | Megrendelve | | 1 db | 2 | 24 | Zárolás | RECV | receiptLp1 | A minőségi rendelés mintavételi zárolásából várt bevételezések |
| Készletzárolás | | Foglalt rendelt | 1 db | 2 | 24 | Zárolás | | | A készletállapot zárolása által generált tranzakció

### <a name="example-with-reserve-ordered-items-disabled"></a>Példa a „Rendelt cikkek foglalása” beállítás letiltásával

Ha a **Rendelt cikkek foglalása** le van tiltva, a várt bevételezéseket nem lehet lefoglalni, mert *Rendelt* állapotúak, így valamilyen zárolás *Megrendelve* állapotú marad.

| Készlettranzakció hivatkozása | Fogadás | Kiadás | Mennyiség | Hely | Raktár | Készlet állapota | Helyszín | Azonosítótábla | Megjegyzés |
|---|---|---|---|---|---|---|---|---|---|
| Beszerzési rendelés | Beszerezve | | 10 db | 2 | 24 | Zárolás | RECV | receiptLp1 | |
| Készletzárolás | | Foglalt tényleges | -9 db | 2 | 24 | Zárolás | | | A készletállapot zárolása által generált tranzakció |
| Készletzárolás | | Foglalt tényleges | -1 db | 2 | 24 | Zárolás | RECV | receiptLp1 | A minőségi rendelés mintavételi zárolása által generált tranzakció |
| Készletzárolás | Megrendelve | | 1 db | 2 | 24 | Zárolás | RECV | receiptLp1 | A minőségi rendelés mintavételi zárolásából várt bevételezések |
| Készletzárolás | | Megrendelt | 1 db | 2 | 24 | Zárolás | RECV | receiptLp1 | A készletállapot zárolása által generált tranzakció

Figyelje meg a két eset tranzakcióállapota és dimenziói közötti különbséget. Ezért javasoljuk, hogy engedélyezze a **Rendelt cikkek foglalása** lehetőséget.

### <a name="disable-expected-receipts-from-quality-orders-that-sample-blocked-inventory-feature"></a>A blokkolt készlet funkciót mintaként tartalmazó minőségi rendelésekből várt bevételezések letiltása

A készletállapot miatt blokkolt minőségi rendelések esetén a készlettranzakciók egyszerűsítése érdekében a rendszer olyan funkciót biztosít, amely letiltja az ilyen minőségi rendelésekből várható bevételezéseket. Mivel a várható bevételezést azonnal blokkolja a készletállapot zárolása, a módosítás miatt nem csökken az aktuális készlet.

Ez a funkció alapértelmezés szerint ki van kapcsolva. A rendszergazdák úgy *kapcsolhatják*[be és kapcsolhatják ki, hogy a Szolgáltatáskezelés munkaterületén keresi meg a minőségi rendelésekből származó olyan várt bevételezések letiltása lehetőséget, amelyeknél a szolgáltatás blokkolt készlet funkcióját](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) mintaként használhatja.

## <a name="additional-resources"></a>További erőforrások

[Készletzárolás létrehozása és karbantartása](tasks/create-maintain-inventory-blocking.md)

[Minőségkezelési folyamatok](quality-management-processes.md)

[Áru minőségének ellenőrzése](tasks/inspect-quality-goods.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]