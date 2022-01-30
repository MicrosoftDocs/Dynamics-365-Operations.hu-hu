---
title: Szállítói fizetési javaslatok automatizálása
description: Ez a témakör azt mutatja be, hogy a beszállítóikat ismétlődő ütemezéssel kifizető szervezetek, hogyan automatizálják a szállítói kifizetési javaslatok létrehozásának folyamatát.
author: kweekley
ms.date: 04/08/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 262034
ms.assetid: 9db38b3f-26b3-436e-8449-7ff243568a18
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-04-08
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 1c5012fdc4f3bfab3f91adfee1eab758dd9c1a0f
ms.sourcegitcommit: 5aecb04178e45e1fdea032b3ef3ce338332005dc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/12/2022
ms.locfileid: "7966715"
---
# <a name="automate-vendor-payment-proposals"></a>Szállítói fizetési javaslatok automatizálása

[!include [banner](../includes/banner.md)]

A beszállítóikat ismétlődő ütemezéssel kifizető szervezetek, immár automatizálják a szállítói kifizetési javaslatok létrehozásának folyamatát. A szállítói fizetési javaslat automatizálásai a következő adatokat határozzák meg:

- A kifizetési javaslatok futtatásakor
- Milyen kritériumok alapján kell kijelölni a kifizetendő számlákat
- Milyen szállítói kifizetési naplóba menti a program a az eredményül kapott kifizetéseket

A fizetési javaslat automatizálások nem adják fel automatikusan a kifizetéseket. Így továbbra is használhatók a létrehozott kifizetések jóváhagyására használt ellenőrzési és munkafolyamatok.

> [!NOTE]
> A funkció használatához engedélyezni kell a Szállítói fizetési javaslat automatizálási **szolgáltatását** a Funkciókezelésben. 

## <a name="define-the-occurrence-of-vendor-payment-proposals"></a>Szállítói kifizetési javaslatok gyakoriságának meghatározása

A szállítói kifizetési javaslat automatizálásai használja a Folyamatautomatizálási keretrendszert használja. A különböző üzleti folyamatok ezt a keretrendszert használják egy kiválasztott folyamatok ismétlődésének meghatározásához. A szállítói kifizetési javaslatok esetében az automatizálás a **Kötelezettségek \> Fizetési beállítások \> Folyamatautomatizálás** helyen érhető el.

Először használja az **Új folyamat létrehozása** automatizálási beállítást, majd válassza a **Szállítói kifizetési javaslat** elemet. A varázsló végigvezeti a szállítói kifizetési javaslat beállításának folyamatán.

## <a name="general-page"></a>Általános lap

A varázsló **Általános** lapján írja be a létrehozandó szállítói kifizetési javaslat nevét. Ha például az összes belföldi szállítót hétfőnként csekken fizeti, írjon be egy jól leíró nevet, például **Belföldi\_Csekk**. A megadott név jelenik meg a folyamatautomatizálás heti nézetében a **Szállítói kifizetések** munkaterületen.

Ezután határozza meg a létrehozott kifizetési napló tulajdonosát. A tulajdonos általában a Kötelezettségek (AP) kifizetési adminisztrátora, aki a kifizetés naplóért felelős annak létrehozása után.

A lap további beállításai általánosak, és a szállítói kifizetési javaslat ehhez a verziójához tartozó előfordulási minta meghatározására használhatók. Ha például, ha az előfordulás csekkes kifizetések hétfőn, definiálhatja, hogy az hetente fusson, és a futtatás napjaként kiválaszthatja a hétfőt. Megadhatja egy korai ütemezési időpontot is (például 2:00), hogy a folyamatautomatizálás a következő munkanap kezdete előtt befejeződjön.

Fontos, hogy megértse, hogy a varázsló segítségével azt határozza meg, hogy mikor dolgozza fel a program a szállítói kifizetési javaslatot. Nem határozza meg, hogy mikor történik a szállítói kifizetések létrehozása, kinyomtatása és feladása. A heti nézetben a szállítói kifizetési javaslatok automatizálása azokon a napokon fog megjelenni, amelyeket az előfordulási mintánál kiválasztott.

Az **Általános** lap egyéb mezőivel kapcsolatos további tudnivalókat lásd a folyamatautomatizálás dokumentációjában.

## <a name="vendor-payment-proposal-page"></a>Szállítói kifizetési javaslat oldal

A varázsló következő lapja a **Szállítói kifizetési javaslat** lap. A kifizetendő szállítói számlák kiválasztásához használt feltételek meghatározására szolgál. Általánosságban ugyanazok a lehetőségek találhatók a kifizetési javaslatban, mint a szállítói kifizetési naplóban. Van azonban néhány kivétel. Például a lapon szereplő összes dátumot relatív dátumként kell meghatározni, mivel a fizetési javaslat dátuma a javaslat minden futtatása alkalmával változik.

### <a name="journal-name"></a>Napló neve

A **Naplónév** mező határozza meg, hogy melyik naplóban jönnek létre a szállítói kifizetések. A szállítói fizetési javaslat automatizálásának eredménye a megadott naplóban hozza létre a kifizetéseket, de a napló nem lesz feladva.

### <a name="from-date-and-to-date"></a>„Kezdő” dátum és „záró” dátum

Egy „kezdő” és egy „záró” dátum meghatározása helyett a számlák kiválasztásához fizetési határidő és a készpénzfizetési engedmény dátuma alapján a **Záró dátum meghatározásának kritériuma** és a **Napok helyesbítésének dátuma a záró dátumhoz** mezőkkel határozhatja meg a záró dátumot. A fizetési javaslat automatizálása esetében a „kezdő” dátum koncepciója nem létezik.

Alapértelmezés szerint a **A záró dátum kritériumának meghatározása** beállítás **Nem** értékre van állítva. Ha ezt az alapértelmezett értéket használja, akkor a folyamat futtatása során a folyamat kijelöli az összes kifizetendő számlát, mivel nem lett „befejező” dátum meghatározva.

Ha az **Igen** értékre állítja a **záró dátum kritériumának meghatározása** beállítást, akkor a **Napok helyesbítésének dátuma a záró dátumhoz** mezőt használja a számlák kiválasztása dátumának meghatározásához a fieztéi javaslat futtatását megelőző és követő napok számával. A szám lehet pozitív, negatív vagy 0 (nulla). A rendszer ezután azokat a számlákat fizeti ki, amelyeknél a határidő vagy a készpénzfizetési engedmény dátuma a folyamat futásának dátuma előtt vagy után meghatározott napokra esik. Például az összes olyan számlánál, amelyek pénteken vagy előbb esedékesek, a kifizetési sorozat csekkes kifizetést hoz létre minden szállítóhoz szerdára. Ebben az esetben a **Napok helyesbítésének dátuma a záró dátumhoz** mezőt **2** értékre állítsa. Amikor a kifizetési javaslat előfordulása március 25-én, szerdán fut, akkor az összes olyan számla ki lesz választva kifizetésre, amelyek határideje a vagy a készpénzfizetési engedmény dátuma március 27-én vagy azelőtt van.

### <a name="minimum-payment-date"></a>Minimális kifizetési dátum

A minimális kifizetési dátum határozza meg a kifizetések létrehozásakor használt legkorábbi dátumot. Előbb be kell állítania a **Minimális fizetési határidő kritériumának meghatározása** beállítást **Igen** értékre kell állítania. Ez a beállítás lehetővé teszi a minimális kifizetési dátum funkció használatát. Ha ezt a beállítást **Igen** értékre állítja a **Napok helyesbítésének dátuma a záró dátumhoz** mezőt használja minimális kifizetési dátum meghatározásához a fizetési javaslat futtatását megelőző és követő napok számával. A szám lehet pozitív, negatív vagy 0 (nulla). Például a kifizetési sorozat szerdán generál kifizetést, úgy hogy az összes olyan kifizetés szerepeljen benne, amelyek a minimális kifizetési dátuma előző hétfő. Ebben az esetben a **Napok helyesbítésének dátuma a minimális fizetési dátumhoz** mezőt **-2** értékre állítsa.

A következő példa bemutatja, hogy hogyan működnek együtt a „záró” dátum és a minimális fizetési dátum mezői. A fizetési javaslat automatizálása úgy van beállítva, hogy szerdán fusson. A **Napok helyesbítésének dátuma a záró dátumhoz** mező **1** értékre van állítva, hogy a „záró”dátumot a fizetési határidő alapján határozza meg. A **Napok helyesbítésének dátuma a minimális fizetési dátumhoz** mező **-2** értékre van állítva. Ha a fizetési folyamatok automatizálása március 25-én, szerdán kezdődik, akkor az összes, március 26-án vagy azt megelőzően esedékes számla szerepelni fog a kifizetési javaslatban. A kifizetési javaslatok generálása a következő módon történik:

- A március 23-án vagy azt megelőzően esedékes összes számlának március 23-án lesz a kifizetési dátuma.
- A március 24-én vagy esedékes számláknak március 24-én lesz a kifizetési dátuma.
- A március 25-én vagy esedékes számláknak március 25-én lesz a kifizetési dátuma.
- A március 26-én vagy esedékes számláknak március 26-én lesz a kifizetési dátuma.

### <a name="summarized-payment-date"></a>Összesített kifizetés dátuma

Az összesített fizetési dátum csak akkor használatos, ha az **Időszak** mező **Összes** értékre van állítva a számlák fizetési módjához. Ha az **Időszak** mező értéke **Összesen** értékre van állítva a fizetési módjaihoz, akkor az **Összesített fizetési dátum kritérium** beállítást **Igen** értékre kell állítania. Ha ezt a beállítást **Igen** értékre állítja a **Helyesbítés napok számával az összesített fizetési dátumhoz** mezőt használja az összesített kifizetési dátum meghatározásához a fizetési javaslat futtatását megelőző és követő napok számával. A szám lehet pozitív, negatív vagy 0 (nulla). Például a sorozat Szerdán generálja a kifizetéseket, és a vállalat szerdán egy összesített kifizetést szeretne létrehozni. Ebben az esetben a **Helyesbítés napok számával az összesített fizetési dátumhoz** mezőt **0** értékre állítsa.

### <a name="records-to-include"></a>Belefoglalandó rekordok

Szűrőbeállítások továbbra is meghatározhatók a kifizetési javaslathoz. Ha meg van adva egy szűrő, a szűrési feltételek nem jelennek meg a varázsló lapján. Ezeket azonban a szűrő újbóli megnyitásával lehet megtekinteni.

A javaslat fennmaradó mezői ugyanúgy működnek, mint a szállítói kifizetési napló kifizetési javaslatában. A többi mezővel kapcsolatos további tudnivalókat lásd: [Szállítói kifizetések létrehozása fizetési javaslat használatával](create-vendor-payments-payment-proposal.md).

> [!NOTE]
> Néhány ország-/régióspecifikus mező, illetve néhány Állami szektorhoz kapcsolódó mező még nem érhető el a szállítói fizetési javaslat automatizálásában.

Azt ajánljuk, hogy a szükségletei alapján mérje fel, hogy az automatizálás előnyös lesz-e a szervezete számára.

## <a name="view-the-results-of-a-vendor-payment-proposal-automation"></a>A szállítói kifizetési javaslat automatizálása eredményeinek megtekintése

Miután létrehozta a szállítói kifizetési javaslat automatizálási sorozatát, az egyes fizetések előfordulásai megjelennek a folyamatok automatizálásának heti nézetében. A szállítói kifizetésekhez a folyamatok automatizálása heti nézet hozzá lett adva a **Szállítói kifizetések** munkaterülethez és a **Feldolgozás automatizálása** laphoz.

[![A folyamatautomatizálás heti nézete a Szállítói kifizetések munkaterületen.](./media/vendor-payment-proposal-1.png)](./media/vendor-payment-proposal-1.png)

A **Szállítói kifizetések** munkaterület a folyamatok automatizálásának heti nézete csak a szállítói fizetési javaslat automatizálásait jeleníti meg. Megjeleníti az aktuális hétre vonatkozó összes kifizetési előfordulást, minden olyan jogi személyhez, amelyhez a bejelentkezett felhasználó rendelkezik biztonsági engedélyekkel. Ha például az AP kifizetési adminisztrátor felelős a USMF és a USSI vállalatok kifizetéseiért, akkor a szállítói kifizetési javaslat automatizálását a két vállalathoz látja, de más vállalatok esetében nem.

[![Folyamatautomatizálás heti nézete az USMF és USSI vállalatokhoz.](./media/vendor-payment-proposal-2.png)](./media/vendor-payment-proposal-2.png)

Minden előfordulás azt a vállalatot jeleníti meg amelyben a kifizetési napló létre lett vagy létre lesz hozva. Ha a kifizetéseket központosított kifizetésekkel hozzák létre, akkor az a vállalat jelenik meg, amelyben a kifizetések létre lesznek hozva. Az előfordulás nem feltétlenül mutatja meg, hogy mely vállalatok számlái lesznek kifizetve.

Az egyes előfordulások neve is megjelenik a fizetési javaslat azonosításának megkönnyítéséhez.

Ezenkívül megjelenik az egyes előfordulások állapota is. A következő állapotok használatosak:

- **Ütemezett** – A kifizetési javaslat be van ütemezve, de még nem futott le.
- **Hiba** – A fizetési javaslat már lefutott, de hiba történt. A hibákat az **Eredmények megtekintése** gombbal lehet megtekinteni.
- **Befejeződött** – A kifizetési javaslat sikeresen lefutott. A kifizetéseket a **Kifizetések megtekintése** megtekintése hivatkozással lehet megtekinteni. Ez a hivatkozás megnyitja az előfordulás által létrehozott kifizetési naplót.

A kifizetések létrehozása után a naplóban megtekintheti a kifizetési összegeket. Minden összeg a tranzakció pénznemében van megadva. Ha például a kifizetési napló mind az USA dollárban, mind a kanadai dollárban tartalmaz kifizetéseket, akkor a program megjeleníti az összes kifizetést az egyes pénznemekhez. 

A kifizetési napló törölhető, miután a folyamat-automatizáláson keresztül létre lett hozva. Ha egy kifizetést teljesen törölnek, a következő események történnek:

- A folyamat automatizálásának állapota a hétre továbbra is **Befejeződött** marad.
- A folyamat eltávolítja a kifizetés végösszegeit, és a **Kifizetések megtekintése** hivatkozást az **Eredmények megtekintése** gombra cseréli.
- Az eredmények megtekintésekor egy üzenet jelenik meg, amely jelzi, hogy az eredeti napló törölve lett.

A kifizetés törlésekor a számlák újra nyitottak lesznek a kifizetéshez. Ezután új előfordulást lehet létrehozni a számlák ismételt kifizetéséhez.

## <a name="edit-a-vendor-payment-proposal-automation"></a>Szállítói fizetési javaslat automatizálásának szerkesztése

A folyamat-automatizálási keretrendszer segítségével szerkesztheti a fizetési javaslathoz létrehozott kifizetést, sorozatot és a és előfordulásokat. A sorozatot a **Folyamatautomatizálás** oldalról vagy a folyamatautomatizálás heti nézetéből lehet szerkeszteni. Ha például az AP-vezető úgy dönt, hogy a belföldi szállítók számára az összes csekket szerdán szeretné generálni hétfő helyett, akkor a heti nézet egyik előfordulását megkeresheti, és kiválaszthatja a **Megtekintés/szerkesztés – Sorozat** elemet. Ha szerkeszt egy sorozatot, a rendszer megkérdezi, hogy meg kell-e változtatni az összes előfordulást, vagy csak az új előfordulásokat. A már **Befejezett** állapotú, illetve **Hibás** állapotú múltbeli előfordulások nem módosulnak.

Lehetőség van új előfordulás hozzáadására vagy meglévő előfordulás módosítására is. Például a következő fizetési javaslat úgy van ütemezve, hogy január 1-jén, szerdán fusson, azonban ez munkaszüneti nap. Az előfordulást a **Folyamatautomatizálás** oldalról vagy a folyamatautomatizálás heti nézetéből módosíthatja. Megnyílik egy lap, amelyen látható az ütemezés részletezése és a fizetési javaslat feltételei. Itt szerkesztheti az ütemezett időt és dátumot. A fizetési javaslat feltételeit is szerkesztheti, ha változtatások szükségesek. Ha például a január 1-ről január 2-re módosítja a kifizetési esemény ütemezési dátumát módosítja, előfordulhat, hogy a „befejező” dátumhoz képest relatív dátumokat is módosítania kell.

Egy előfordulást vagy egy sorozatot le is lehet tiltani. Ha le szeretne tiltani egy előfordulást, és felfüggeszteni a feldolgozást, válassza ki a folyamat automatizálása heti nézetét, majd válassza a **Letiltás** elemet. Sorozatot a **Folyamatautomatizálás** oldalon lehet letiltani.

## <a name="security-for-payment-proposal-automations"></a>Szállítói fizetési javaslatok automatizálásának biztonsága

A következő feladatok és jogosultságok lettek hozzáadva a szállítói kifizetési javaslatok automatizálásához. Ezek a feladatok és jogosultságok az alapértelmezett biztonsági beállítások, de a szervezet igényei alapján módosíthatók. Ha például nem csak az AP vezető, hanem az AP kifizetési ügyintéző is szerkeszthet és létrehozhat az ütemezett ismétlődést, akkor rendelje hozzá az **Ütemezés előfordulásának karbantartása** feladatot az AP kifizetési ügyintéző szerepkörrel rendelkező személyhez.

| Feladatkör                              | Szerep                                                                       | Jogosultságok |
|-----------------------------------|----------------------------------------------------------------------------|------------|
| Ütemezési sorozatok karbantartása          | Kötelezettségkezelő vezető                                                   | Ez a kötelezettség jogosultságot biztosít fizetési javaslat automatizálási sorozat és előfordulás létrehozására és karbantartására a következő jogosultságokon keresztül:<ul><li>Ütemezési előfordulások karbantartása</li><li>Ütemezési sorozatok karbantartása</li><li>ProcessScheduleOccurrenceListMaintain</li><li>Az előfordulások heti nézetének megtekintése</li></ul> |
| Ütemezési előfordulások lekérdezése | Kötelezettségek kifizetési ügyintéző, kötelezettségek központi kifizetési ügyintéző | Ez a kötelezettség jogosultságot biztosít fizetési javaslat automatizálási sorozat és előfordulás megtekintésére a következő jogosultságokon keresztül:<ul><li>Ütemezési előfordulások megtekintése</li><li>Az előfordulások heti nézetének megtekintése</li></ul> |
| Ütemezési sorozatok lekérdezése      | None                                                                       | Ez a kötelezettség jogosultságot biztosít a sorozat és előfordulás beállításainak megtekintésére a következő jogosultságokon keresztül:<ul><li>Ütemezési előfordulások megtekintése</li><li>Az előfordulások listaoldalának megtekintése</li><li>Az előfordulások heti nézetének megtekintése</li></ul>|
| Ütemezési előfordulások karbantartása     | None                                                                       | Ez a feladatkör a következő jogosultságok révén ad jogosultságokat egy előfordulás létrehozásához és karbantartásához:<ul><li>Ütemezési előfordulások karbantartása</li><li>Az előfordulások heti nézetének megtekintése</li></ul> |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
