---
title: Főkönyvek konfigurálása
description: Ez a témakör a jogi személyek főkönyvi konfigurálásokkal kapcsolatos információit tartalmazza. Információkat tartalmaz a pénznemek, pénzügyi naptárak, számlatükör és az egyes jogi személyekkel használandó számlastruktúrák kiválasztásáról.
author: kweekley
ms.date: 09/24/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: Ledger
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-09
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: aad10770750d2614da804380a7bba03d348e8c9a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826203"
---
# <a name="configure-ledgers"></a>Főkönyvek konfigurálása

[!include [banner](../includes/banner.md)]

Ez a témakör a jogi személyek főkönyvi konfigurálásokkal kapcsolatos információit tartalmazza. Információkat tartalmaz a pénznemek, pénzügyi naptárak, számlatükör és az egyes jogi személyekkel használandó számlastruktúrák kiválasztásáról.

## <a name="selecting-the-chart-of-accounts"></a>A számlatükör kiválasztása

A Microsoft Dynamics 365 Finance minden jogi személye esetében konfigurálni kell a főkönyv részleteit. A **Főkönyv** lapon kiválaszthatja az adott jogi személyhez használandó számlatükröt és számlastruktúrákat. A számlatükör és a számlastruktúrák megosztásához konfigurálja a jogi személyek **Főkönyv** lapját, hogy mindegyikhez ugyanazt a számla- és számlastruktúrát használja. A konfiguráció egy részét az egyes jogi személyekben is megoszthatja, és minden jogi személyben specifikus konfigurációkkal rendelkezik.

Ha a jogi személyeknek különböző számlatükörrel vagy fiókstruktúrával kell rendelkezniük, a jogi személy felülbírálási funkciója hasznos lehet. Ha ugyanazt a számla- és számlastruktúrákat több jogi személyhez használja, majd a kivételeket jogi személyek felülbírálásain keresztül kezeli, egyszerűsítheti a karbantartást az idő múlásával.

Egy jogi személy számlatükörének konfigurálásához nyissa meg a **Főkönyv \> Főkönyv beállítása \> Főkönyv** lehetőséget. A **Főkönyv** oldalon válassza ki a **Számlatükör** lehetőséget, majd a listából válassza a használandó számlatükröt. Ne feledje, hogy a számlatükör nem módosítható, miután kiválasztott egy értéket, és tranzakciókat adott fel a jogi személyben.

A számlatükör és a fő számlák tervezéséről és konfigurálásáról a [Számlatükör megtervezése](plan-chart-of-accounts.md) című témakörben talál további információt.

## <a name="selecting-account-structures"></a>A számlastruktúrák kiválasztása

A Dynamics 365 Finance-ben lévő minden jogi személy beállítható egy vagy több számlastruktúra használatára. Minden számlastruktúra meghatározza a tranzakciók feladásakor engedélyezett pénzügyi dimenziókat, valamint a fő számlák és pénzügyi dimenziók kombinációit. Ugyanazokat a számlastruktúrákat több jogi személyben is használhatja.

Vegye figyelembe, hogy ha több számlastruktúrával rendelkezik, csak azokat a számlastruktúrákat választhatja ki, amelyek nem rendelkeznek átfedésben lévő fő számlák és pénzügyi dimenziók kombinációival. Az egyik számlastruktúra például úgy van konfigurálva, hogy 1000 és 1999 között adjon hozzá egy üzleti egységet a fő számlákhoz. Egy másik számlastruktúrában hozzáadta a Részleg pénzügyi dimenzióját az 1-gyel kezdődő fő számlákhoz. Ebben az esetben csak az egyik számlastruktúra adható hozzá ugyanabban a jogi személyben.

A főkönyv számlastruktúráinak konfigurálásához a **Főkönyv** lapon lévő **Számlastruktúrák** gyorslapon válassza a **Hozzáadás** lehetőséget, majd válasszon egy számlastruktúrát a listában, és kattintson a **Kiválasztás** lehetőségre. Eltarthat néhány percig a fiókstruktúrák hozzáadása és mentése. Ne feledje, hogy a kiválasztott számlastruktúráknak aktívnak kell lenniük. Ellenkező esetben a számlastruktúrák részletei nem lesznek hatékonyak azokban a jogi személyekben, ahol kapcsolódnak.

Számlastruktúra eltávolításához a **Főkönyv** lap **Számlastruktúrák** gyorslapon válassza az **Eltávolítás** lehetőséget. Vegye figyelembe, hogy ha eltávolít egy számlastruktúrát a főkönyvből, akkor nem távolítja el azokat a tranzakciókat, amelyeket az adott számlastruktúra konfigurációjával adtak fel.

A fiókstruktúrák beállításáról a [Fiókstruktúrák konfigurálása](configure-account-structures.md) című témakörben talál további információt.

## <a name="configuring-calendars-for-the-ledger"></a>Naptárak konfigurálása a főkönyvhöz

A főkönyv másik összetevője a pénzügyi naptár. Minden jogi személyhez ki kell választani egy pénzügyi naptárat. Ugyanazokat a pénzügyi naptárakat több jogi személyben is használhatja. Amikor pénzügyi naptárat választ a főkönyvhöz, a program másolatot készít. Ezt a példányt főkönyvi naptárnak nevezzük. A főkönyvi naptár lehetővé teszi az egyes időszakok és modulok állapotának kiválasztását.

A kijelölt jogi személy naptárának eléréséhez és frissítéséhez a **Főkönyv** lapon válassza a **Főkönyvi naptár** lehetőséget.

A naptár kijelöléséhez válassza a **Pénzügyi naptárak** lehetőséget, majd a listában jelölje ki a naptárat. Ha a tranzakciók jogi személyben történő feladása után módosítja a pénzügyi naptárat, akkor a **Főkönyvi időszakok újraszámítása** lehetőséget kell választania. Ezután a megjelenő párbeszédpanelen frissítheti a naptárban szereplő időszakok főkönyvi egyenlegét. Azt javasoljuk, hogy futtassa a **Főkönyvi időszakok újraszámítása** folyamatot a **Köteg** módban, és akkor futtassa, ha nem kritikus folyamatok történnek a rendszerben. A tranzakciók számától és a pénzügyi dimenziókombinációktól függően ez a folyamat eltarthat egy ideig.

Ha jogi személyhez nincs kiválasztva pénzügyi naptár, hibaüzenet jelenik meg, amikor tranzakciót próbál feladni az adott jogi személyben.

További tudnivalókért lásd: [Pénzügyi naptárak, pénzügyi évek és időszakok.](../budgeting/fiscal-calendars-fiscal-years-periods.md).

## <a name="using-a-balancing-financial-dimension"></a>Kiegyenlítő pénzügyi dimenzió használata

Miután kiválasztotta a számlatükröt, és hozzáadott egy vagy több számlastruktúrát, tetszés szerint kiválaszthat egyetlen pénzügyi dimenziót, amelyet kiegyenlítő pénzügyi dimenzióként szeretne használni. A kiválasztott dimenziónak minden számlastruktúrában léteznie kell. Annak is kiegyenlítőnek kell lennie az összes könyvelési tételben. Más szóval a megbízásoknak és a jóváírásoknak meg kell egyezniük a fő számla és a kiegyenlítő pénzügyi dimenzió esetében. A rendszer automatikusan létrehoz tranzakciókat a tételek kiegyenlítésére, az **Automatikus tranzakció számlák** lap **Egységközi - terhelés** és **Egységközi - jóváírás** mezőkben megadott fő számlák alapján.

A kiegyenlítő tételekről további információt a [Kiegyenlített naplók az egységközi könyveléshez](example-balanced-journals-interunit-accounting.md) című témakörben talál.

## <a name="configuring-currencies-for-the-ledger"></a>Pénznemek konfigurálása a főkönyvhöz

A **Főkönyv** lap a tranzakciók főkönyvbe történő feladásakor használt pénznemek szabályozására és meghatározására is szolgál. Meg kell adnia az összes bizonylat főkönyvi **Könyvelési pénznem** oszlopában használt könyvelési pénznemet. Ezenkívül a **Jelentési pénznem** oszlopban tetszés szerint kiválaszthat egy második pénznemet is. Ha kiválaszt egy jelentési pénznemet, akkor minden tranzakció az adott pénznemben lesz rögzítve a főkönyv **Jelentési pénznem** oszlopában az összes bizonylaton.

Ha a tranzakciók feladása más pénznemben történik, a rendszer automatikusan átváltja a tranzakció összegét a tranzakciók pénzneméből a bizonylaton lévő könyvelési pénznemre és jelentési pénznemre. A **Főkönyv** lap **Könyvelési pénznem árfolyamtípusa** mezőjében válassza ki a bizonylaton szereplő könyvelési pénznemre átváltandó árfolyamokhoz a tranzakció pénzneméről a könyvelési pénznemre konfigurált árfolyam típusát. Ha egy jelentési pénznemet választott, akkor a **Jelentési pénznem árfolyamtípusa** mezőt is be kell állítania, hogy milyen árfolyamot kell használni a tranzakció pénznemének a bizonylaton lévő jelentés pénznemére történő átváltáshoz.

Ha költségvetési funkciót használ, beállíthatja a **Költségvetés árfolyamtípusa** mezőt is, hogy jelezze a költségvetési tranzakciók egyik pénznemből a másikba történő átváltásához használandó árfolyamot.

Ha két pénznemet használ, vagy ha közös pénznemet használ, de a tranzakciókat más pénznemben adja fel, akkor a **Főkönyv** lap **Számlák a pénznem átértékeléséhez** gyorslapján. Ezen a gyorslapon megadhatja az alapértelmezett nem realizált nyereség- és nem realizált veszteségszámlákat, amelyeket a program alapértelmezés szerint a tranzakciók feladásakor használ, ha nincs megadva számla a **Pénznem átértékelési számlák** lapon. (A **Pénznemátértékelési számlák** lap az egyes pénznemek realizált és nem realizált nyereségének és veszteségének különböző számláinak konfigurálására szolgál.)

A realizált nyereség és veszteség a befejezett tranzakciókból származó nyereség és veszteség. Ezeket az eredménykimutatásban kell elszámolni. A nem realizált nyereség és veszteség olyan nyereség és veszteség, amely megvalósult, de a tranzakció nem fejeződött be. Más szóval könyvelt például egy számlát, de a számla még nincs kiegyenlítve és kifizetve. A nem realizált nyereséget és veszteséget a mérlegben kell elszámolni.

A pénznemek használatával kapcsolatos további tudnivalókat lásd: [Kettős pénznem](dual-currency.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]