---
title: Halasztások ütemezése bevétel- és kiadás halasztásokban
description: Ez a témakör a halasztások bevételi és kiadási halasztásokkal kapcsolatos ütemezéseit ismerteti.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 953347500f83a4a16f43331b572d2029027a5f59
ms.sourcegitcommit: d0e99545d722c924db57ae2bd06f72154a1f1f97
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/08/2022
ms.locfileid: "8557970"
---
# <a name="deferral-schedules"></a>Halasztási ütemezések

A halasztások ütemezései a tranzakció feladása után jön létre.

A Halasztások **ütemezésének** **összes** ütemezése vagy az Aktív halasztás ütemezése lapon áttekintheti a halasztás ütemezésének részletes adatait. A megjelenő információk a halasztás ütemezésének típusától (sor vagy esemény alapú) és a tranzakció típusától függnek. Tartalmazza a halasztás ütemezési sorait és a halasztás ütemezésének teljes összegét. A lap használatával módosítható a halasztás ütemezése.

## <a name="recognize-revenue"></a>Bevétel megjelenítése

> [!NOTE]
> - Ha egy halasztás-ütemezés bevételét is fel kell ismerni, először az 1. lépésben kell kezdeni.
> - Ha több ütemezésből is fel kell ismerni a bevételt, a 2. lépéstől induljon.

1. Az Összes halasztás **ütemezése lapon,** **az Ütemezési sorok rácsban válassza ki azokat a sorokat, amelyekre fel szeretné ismerni,** majd válassza a Felismerés lehetőséget **.**
2. Az Felismerés **feldolgozása lapon** állítsa be **az Felismerési művelet** mezőt a Felismerési **napló létrehozása beállításhoz**.
3. A Cutoff **Date mezőben** válassza ki a megfelelő dátumot. A feldolgozás csak olyan sorokat fog tartalmazni, amelyek záró dátuma korábbi vagy megegyezik a kiválasztott záró dátummal.
4. Válassza **a Szűrő** lehetőséget, és adjon hozzá adatszűrőket úgy, hogy a lista csak a kívánt rekordtartományt tartalmazza.
5. A sorok **megtekintéséhez válassza** a Nézet előnézetét.
6. A sorok listájában válassza ki azokat a sorokat, amelyek nem kíván feldolgozni, majd válassza az Eltávolítás **lehetőséget**.
7. Válassza ki, hogy összegezni szeretné-e az felismerési napló bejegyzését.
8. A Tranzakció **dátuma szakaszban** felülbírálhatja a tranzakció dátumát egy megadott dátummal a tranzakció feldolgozásához. A tranzakció dátuma meg lehet adni a lezárt időszakokhoz.
9. Ha a feldolgozást köteg részeként kell eltenni, válassza a Köteg **lehetőséget**. A Kötegelt **feldolgozás párbeszédpanelen** állítsa be a köteg paramétereit, **majd az OK** **gombra történő visszatéréshez térjen vissza a Felismerés feldolgozása lapra**. Az árbevétel-felismerés feldolgozása később, a köteg feldolgozásakor történik meg.
10. Folyamat **kiválasztása**. Ha nem ad hozzá tranzakciót egy köteghez, akkor a folyamat minden sort azonnal feldolgoz. Ellenkező esetben a köteg feldolgozásakor a sorok feldolgozása történik meg.

## <a name="modify-a-schedule"></a>Ütemezés módosítása

Halasztás ütemezését a következő lépések szerint módosíthatja.

1. Válassza ki **a halasztás ütemezését a Minden halasztás ütemezése** lapon, majd válassza a Könyvelés módosítása **\> ütemezést**.
2. Az Ütemezés **módosítása** lapon módosítsa a módosítani kívánt beállításokat. A halasztás ütemezésétől függően nem lehet módosítani az összes lehetőséget.
3. Az Előnézet **lehetőséget** választva megtekintheti a halasztás ütemezésének módosításait.
4. Válassza ki az **OK** lehetőséget.

### <a name="straight-line-deferral-schedules"></a>Straight line halasztás ütemezései

Ha a halasztás ütemezése nem ismerhető fel vagy nem külsőleg feladott sorok, a teljes halasztás ütemezését módosíthatja, a kezdő dátummal együtt.

Ha a halasztási ütemezésben bármilyen sor fel van ismerve vagy külsőleg fel van adva, és ön módosítja a halasztási ütemezést, akkor a halasztási ütemezés így kapott viselkedése az újraszámítási dátumtól és a halasztás záró dátumától függ. Alapértelmezés szerint az első nem felismert időszak határozza meg a halasztás záró dátumát.

A felismerés dátumának alkalmazáshoz válasszon a következő értékek közül az Ütemezés **kezdete mezőben**: 
- **Bejedés** – az összes elismert sor újraszámítása utáni összeg.
- **Sztornírozás** – az újraszámítási dátum után minden sort sztorníroz a megadott naplónév és feladási dátum alkalmazásával. Az újraszámítás dátuma utáni összeg ezután újra lesz számálva.

Sablon használata esetén a rendszer figyelmen kívül hagyja az kihagyott időszakokat, és a sablont csak a záró dátum kiszámítására használja.

### <a name="event-based-deferral-schedules"></a>Eseményalapú halasztások ütemezései

Halasztások ütemezése esetén minden fel nem ismert sort módosíthat.

Ha a halasztás ütemezésében bármilyen sor fel van ismerve vagy külsőleg feladott, akkor a halasztás ütemezésének sablonja és felosztási típusa nem módosítható. Ha módosít egy meglévő halasztás-ütemezést, **akkor** az Egységenkénti külön események létrehozása mező értéke nem módosítható.

Ha egy sort ismer fel vagy külsőleg ad fel, **akkor be van jelölve az Elismerve** jelölőnégyzet.

## <a name="modify-a-deferral-or-recognition-account"></a>Halasztás vagy felismerési számla módosítása

Ha módosítani szeretné a halasztás vagy a halasztás-felismerés számláját, kövesse ezeket a lépéseket.

1. Válassza ki **a halasztás ütemezését a Minden halasztás ütemezése** lapon, majd válassza a Könyvelés **módosítása \> számla lehetőséget**.
2. A Számla **módosítása** lapon válassza ki a módosítani kívánt számlát (halasztás, rövid távú vagy felismerés).
3. Az Új **számla mezőben** válassza ki az új számlát.
4. Annak beállítása, hogy a számla módosításai helyesbítési naplóbejegyzéseket hozzanak-e létre.
5. Ha az előző lépésben **Igen** beállítást adja meg, **válassza ki a napló nevét a Napló neve** mezőben, **majd adja meg a tranzakció dátumát a Tranzakció dátuma mezőben**.
6. Válassza ki az **OK** lehetőséget.

## <a name="put-a-deferral-schedule-on-hold"></a>Halasztás ütemezésének berakodva

Ha a halasztás ütemezését fel kell függesni, kövesse ezeket a lépéseket.

1. Válassza ki **a halasztás ütemezését a Minden halasztás ütemezése** lapon, **\> majd válassza a Hely hold lehetőséget**.
2. A Hely **által visszatartott** lapon adja meg, hogy az egyenleget a halasztott számláról vagy a hold számláról szeretné áthozni.
3. Ha az egyenleg átvitelét választotta, **válassza ki a napló nevét a Napló neve** mezőben, **válassza ki a hold számlát a** Visszatartott számla mezőben, **és adja meg a tranzakció dátumát a Tranzakció dátuma mezőben**.
4. Válassza ki az **OK** lehetőséget.

## <a name="remove-a-hold-from-a-deferral-schedule"></a>Halasztás ütemezésének<a2/<a2/<a2/<a2

Ha el szeretne távolítani egy halasztás-ütemezést egy elhalasztásból, kövesse ezeket a lépéseket.

1. Az Összes **halasztás ütemezése** listán válassza ki a halasztás ütemezését, majd válassza a Hold – Eltávolítási **\> hold lehetőséget**.
2. A Napló **neve mezőben** válassza ki a napló nevét.
3. Adja meg **a tranzakció** dátumát a Tranzakció dátuma mezőben.
4. Válassza ki az **OK** lehetőséget.

## <a name="cancel-unrecognized-amounts"></a>Fel nem ismert összegek érvénytelenítése

> [!NOTE]
> Minden olyan sor, amely már felismert vagy külsőleg fel lett adva, ki van zárva ebből a folyamatból.

Ha egy halasztás ütemezésében törölni kell a fel nem ismert összegeket, kövesse ezeket a lépéseket.

1. A Minden halasztás ütemezése **lapon válassza ki a halasztás ütemezését,** **majd válassza a Fel nem ismert összegek érvénytelenített törlése lehetőséget \>.**
2. Válassza ki **a Mégse ismeretlen** összeg lapon, hogy kíván-e érvénytelenítési bejegyzéseket létrehozni.
3. Ha az érvénytelenítési bejegyzések létrehozása beállítást választotta, **válassza ki a napló nevét a Napló neve** mezőben, **válassza** ki az érvénytelenítési számlát az Érvénytelenítési számla mezőben, **és adja meg a tranzakció dátumát a Tranzakció dátuma mezőben**.
4. Válassza ki az **OK** lehetőséget.

## <a name="cancel-a-completed-schedule"></a>Befejezett ütemezés visszavonása

A Minden halasztás **ütemezése** lapon sztornírozhatja a felismert vagy külsőleg feladott összegeket, és törölheti a halasztás ütemezését, hogy megakadályozza a további felismerést.

Ha a teljes halasztás ütemezését törölni kell, kövesse ezeket a lépéseket.

1. Válassza ki **a halasztás ütemezését a Minden halasztás ütemezése** lapon, **\> majd válassza a Kész ütemezés megszakítása lehetőséget**.
2. A Teljes **ütemezés visszavonása** lapon válassza ki, hogy kíván-e érvénytelenítési bejegyzéseket létrehozni.
3. Ha az érvénytelenítési bejegyzések létrehozása beállítást választotta, **válassza ki a napló nevét a Napló neve** mezőben, **válassza** ki a számlát az Érvénytelenítési számla mezőben, **és adja meg a tranzakció dátumát a Tranzakció dátuma mezőben**.
4. Válassza ki az **OK** lehetőséget.

## <a name="reverse-transactions"></a>Tranzakciók sztornírozása

> [!NOTE]
> - Ha egy halasztás-ütemezés árbevétel-kimutatását sztornírozni kell, először az 1. lépésben kell kezdeni.
> - Ha több ütemezés árbevétel-kimutatását sztornírozni kell, a 2. lépéstől induljon.

1. Az Összes **halasztás** **ütemezése** lapon, az Ütemezési sorok rácsban válassza ki azokat a sorokat, amelyekről el szeretné ismertíteni a sorokat, majd válassza a Sztornírozás **lehetőséget.**
2. Állítsa a **Felismerés feldolgozása** lapon az Felismerés **művelet** mezőjét a Sztornírozó **felismerési napló beállításra**.
3. A Cutoff **Date mezőben** válassza ki a megfelelő dátumot. A feldolgozás csak olyan sorokat fog tartalmazni, amelyek záró dátuma korábbi a megadott záró dátumnál, vagy megegyezik a megadott dátummal.
4. Válassza **a Szűrő** lehetőséget, és adjon hozzá adatszűrőket úgy, hogy a lista csak a kívánt rekordtartományt tartalmazza.
5. A sorok **megtekintéséhez válassza** a Nézet előnézetét.
6. A sorok listájában válassza ki azokat a sorokat, amelyek nem kíván feldolgozni, majd válassza az Eltávolítás **lehetőséget**.
7. A **Név** és **leírás mezők** automatikusan frissülnek az alapértelmezett naplónévvel és leírással. Az értékeket szükség szerint módosíthatja. Azt is be lehet választani, hogy összegezni szeretné-e az felismerési napló bejegyzését.
8. A Tranzakció **dátuma szakaszban** felülbírálhatja a tranzakció dátumát egy megadott dátummal a tranzakció feldolgozásához. A tranzakció dátuma meg lehet adni a lezárt időszakokhoz.
9. Ha a feldolgozást köteg részeként kell eltenni, válassza a Köteg **lehetőséget**. A Kötegelt **feldolgozás párbeszédpanelen** állítsa be a köteg paramétereit, **majd az OK** **gombra történő visszatéréshez térjen vissza a Felismerés feldolgozása lapra**. A sztornírozási árbevétel-felismerés feldolgozása később, a köteg feldolgozásakor történik meg.
10. Válassza ki az **OK** lehetőséget. Ha nem ad hozzá tranzakciót egy köteghez, akkor a folyamat minden sort azonnal feldolgoz. Ellenkező esetben a köteg feldolgozásakor a sorok feldolgozása történik meg.

## <a name="apply-or-unapply-a-credit-note"></a>Jóváírás alkalmazása vagy az alkalmazás elutasítása

A következő lépések szerint alkalmazhatja a jóváírást.

> [!NOTE]
> Ha az Értékesítési rendelés tranzakció halasztás lapján hoz létre jóváírást, és a Meglévő ütemezés beállítása Igen beállításra van állítva, akkor **a** **·** **jóváírás** feladása esetén a rendszer automatikusan alkalmazza a jóváírást az ütemezésre.

1. A Halasztás **ütemezése** lapon válassza ki a halasztás ütemezését.
2. A Jóváírás-helyesbítések **listán** válasszon egy sort, majd válassza az Alkalmaz **lehetőséget**.
3. A Jóváírások **alkalmazása (halasztások)** **·** **lapon** adja meg az újraszámítási dátumot az Újraszámítási dátum mezőben és a Záró dátum mezőben a záró dátumot.
4. A Fejléc **listáról** válassza ki azt az értékesítési **rendelést**, amelyhez jóváírások vannak.
5. A Sorok **listán** válassza ki a sort.
6. Válassza ki az **OK** lehetőséget.
7. Válassza ki az **Igen** lehetőséget.

> [!NOTE]
> Ha a különböző számlák több egyes cikkére is jóváírást kell alkalmazni, meg kell ismételnie ezeket a lépéseket.

A jóváírások alkalmazásának az alábbi lépésekkel lehet megszabadulni.

1. A Halasztás **ütemezése** lapon válassza ki a halasztás ütemezését.
2. A Jóváírás-helyesbítések **listán** válassza ki a számlát, majd válassza a Nem **alkalmazással lehetőséget**.
3. Válassza ki az **Igen** lehetőséget.

## <a name="fields"></a>Mezők

A **Minden halasztás ütemezése** lap a következő mezőket tartalmazza.

| Mezők | Leírás |
|--------|-------------|
| **Fejléc** | |
| **Ütemezés** | |
| Foglalás típusa | Az eseményalapú halasztások felosztási típusa: **százalék** vagy **összeg**. |
| Átsorolás dátuma | <p>Az a legutóbbi dátum, amikor a halasztási ütemezés rövid távú újraosztályozata fel lett feldolgozva. Ez a dátum minden alkalommal frissül, amikor a halasztás **ütemezésében** az Esemény rövid távú átsorolást használja.</p>Ez a mező csak akkor érhető el, ha a görgető időszakok vagy a rögzített éves rövid távú halasztás módszer van használatban. |
| **Számla** | |
| Halasztási számla | A halasztott összeghez használt számla. |
| Elszámolási számla | Az összeg elismerésére használt számla. |
| Elszámolás típusa | A felismerés típusa. |
| Felosztás típusa | Az elosztás típusa. |
| **Tranzakció** | |
| Létrehozás forrása | A forrás, amelyből a tranzakció létrejött. |
| Tranzakció típusa | A tranzakció típusa. |
| Értékesítési rendelés | Az értékesítési rendelés száma. |
| Számla | A számla száma. |
| Cikk | A cikkszám. |
| **Számlázási ütemezés** | |
| Számlázási ütemezés száma | A megfelelő számlázási ütemezés száma. |
| Számlázási sor állapota | A megfelelő számlázási ütemezési sortétel állapota. |
| Külső hivatkozások | A számlázási ütemezésből származó külső hivatkozások adatai: **külső és** sorszám **·**. |
| Összegek | <p>A halasztás ütemezésének végösszegei:</p><ul><li>**Hosszú távú** – a hosszú távú halasztott összegek összege. Ez az érték csak **akkor** **·** **érhető** el, ha a Rövid távú halasztás módszer mezőjében a Nincs érték van beállítva a Bevételi és költség halasztások paraméterei lapon, vagy ha a rövid távú összeg nagyobb nullánál.</li><li>**Rövid távú** – a rövid távú halasztott összegek összege. Ez az érték csak **akkor** **·** **érhető** el, ha a Rövid távú halasztás módszer mezőjében a Nincs érték van beállítva a Bevételi és költség halasztások paraméterei lapon, vagy ha a rövid távú összeg nagyobb nullánál.</li><li>**Felismerhetetlen** – az összes sor el nem ismert összegének összege.</li><li>**Rövidített** – a külsőleg feladott összegek összege minden sorban.</li><li>**Elismerve** – az összes sor elismert összegének összege.</li><li>**Külsőleg feladva és elismerve** – a külsőleg feladott és elismert összegek összege minden sorban.</li><li>**Teljes összeg** – az összes sor összegének összege.</li></ul> |
| **Ütemezési sorok** | |
| Sor | A sor sorszáma. |
| Halasztás kezdő dátuma | A halasztás ütemezésének kezdő dátuma. |
| Halasztás záró dátuma | A halasztás ütemezésének záró dátuma. |
| Összeg | A halasztás összege. |
| Külső feladás | Ez az érték jelzi, hogy a sor külső feladásra került-e. |
| Elszámolva | Ez az érték jelzi, hogy a sort felismerték-e. |
| Napló kötegszáma | Az a kötegszám, amely az összeget ismerte fel. |
| Esemény leírása | Az esemény leírása. Ez a mező csak esemény alapú halasztások ütemezése esetén érhető el. |
| **Jóváírás-kiigazítások** | |
| Számla | <p>A számla száma.</p><p>Az érték jelzi a jóváírás-korrekciónak azt a számláját, amely már alkalmazva van a halasztás ütemezésére.</p> |
| Kiegyenlített összeg | A halasztás ütemezésében már alkalmazott jóváírás-korrekció összege. |
| Alkalmazás dátuma | A jóváírás-korrekció alkalmazásának dátuma. |
| **Korrekció** | A helyesbítési értékek csak akkor jelennek meg, ha a halasztási ütemezéshez jóváírás feldolgozása történt. Ha nem történt jóváírás feldolgozása, ezek az értékek rejtve maradnak. |
| Kiigazítás összege | Az eredeti összegként kiszámított *teljes* módosítási összeg – *ütemezési összeg*. |
| Eredeti záró dátum | A halasztás ütemezésének eredeti záró dátuma. |
| Eredeti ütemezésösszeg | Az eredeti halasztás ütemezésének összege. |
