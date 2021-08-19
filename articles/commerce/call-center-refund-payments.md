---
title: Visszatérítési fizetések feldolgozása hívásközpontoknál
description: Ez a témakör bemutatja, hogyan generálja a program a kifizetések visszatérítését a hívásközpontokon keresztül a visszatérítések létrehozása, illetve a rendelések vagy rendeléssorok érvénytelenítése esetén.
author: hhainesms
ms.date: 01/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 93eff7a54f9d3851c59b83a28d3aa61a8de7bc41f2a845be21c8bf4d1c6401d4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6731031"
---
# <a name="refund-payment-processing-in-call-centers"></a>Visszatérítési fizetések feldolgozása hívásközpontoknál

Ez a témakör bemutatja, hogyan generálja a program a kifizetések visszatérítését a hívásközpontokon keresztül a visszatérítések létrehozása, illetve a rendelések vagy rendeléssorok érvénytelenítése esetén.

Az a felhasználó, aki visszárurendelést hoz létre egy vevőnek hívásközponti felhasználóként a Microsoft Dynamics 365 Commerce alkalmazásban, a **Visszárurendelés** lapon létrehozza a kezdeti visszáru-jóváhagyást (RMA). Az RMA határozza meg, hogy a vevő milyen termékeket szeretne visszaküldeni vagy kicserélni, és létrehoz egy kapcsolt visszárurendelést, amely a **Visszaküldött rendelés** rendeléstípussal rendelkezik. Ez a kapcsolt visszaküldött rendelés a visszaküldött készlet feladásának, valamint a feladott jóváírások és kifizetés-visszatérítések nyomon követésére használható.

Ha a hívásközponti csatorna **Rendeléskiegészítés engedélyezése** beállítása **Igen**, az RMA-t létrehozó hívásközponti felhasználónak a **Befejezés** lehetőség kiválasztásával futtatnia kell a rendelésfeldolgozási folyamatot a **Visszárurendelés** lapon. A **Befejezés** függvény a visszáru számított visszatérítését adja meg, amely ismerteti az esedékes visszatérítési összeget. Ezenkívül a helyesen konfigurált függvény módszeres módon létrehoz egy visszatérítési fizetési sort a visszaküldött rendeléssel szemben.

A hívásközponti logika határozza meg a visszatérítési fizetési sor fizetési módját az eredeti rendeléshez használt fizetési mód alapján. Ha a létrehozott visszárurendelés nem kapcsolódik eredeti rendeléshez, akkor a rendszerparaméterből származó alapértelmezett fizetési módot alkalmazza a rendszer.

## <a name="how-a-call-center-determines-which-payment-method-to-apply-to-a-return-order"></a>Hogyan határozza meg a hívásközpont a visszárurendelésre alkalmazandó fizetési módot?

A hívásközpont az eredeti rendelés fizetési módja alapján határozza meg a visszárurendelésre alkalmazandó fizetési módot. Ez a folyamat az eredeti fizetési módokon a következőképpen működik:

- **Normál** (készpénz) vagy **Csekk** – ha a létrehozott visszárurendelés olyan eredeti rendelésre hivatkozik, amelyet a normál (készpénzes) vagy csekkfizetési típus használatával fizettek ki, akkor a hívásközponti alkalmazás a **Hívásközponti visszatérítési módok** lapján található konfigurációkra hivatkozik. Ez a lap lehetővé teszi a szervezetek számára, hogy a rendelés pénzneme szerint meghatározzák, hogyan adták ki a vevőknek az eredetileg a normál vagy csekkes fizetéstípussal kifizetett rendelések visszatérítését. A **Hívásközponti visszatérítési módok** lap lehetőséget nyújt a szervezeteknek annak kiválasztására is, hogy a rendszer által létrehozott visszatérítési csekket küldik-e a vevőnek, vagy vevői számlajóváírást hoznak-e létre a belső vevői számlaegyenleggel szemben. Ilyen helyzetekben a hívásközponti logika a visszárurendelés pénznemére hivatkozik, majd az ahhoz a pénznemhez a **Kiskereskedelmi fizetési mód** értékével hoz létre visszatérítési fizetési sort a visszáruértékesítési rendelésen. Később a pénznemhez kapcsolva létezik egy kinnlevőségek (AR) vevői fizetési napló, amely a leképezett kinnlevőségek fizetési módot használja.

    A következő ábra egy olyan helyzetet mutat be, amikor a vevő az USD pénznemhez kapcsolódó értékesítési rendelésből küld vissza termékeket, és amelyeket eredetileg a normál vagy csekkes fizetéstípussal fizettek ki. Ebben az esetben a rendszer létrehoz egy visszatérítési csekket, és a vevő ezen kapja meg a visszatérítést. A **REF-CHK** kinnlévőségek fizetési módot visszatérítési csekkes fizetéstípusként állították be.

    ![Hívásközponti visszatérítési módok konfigurálása normál kifizetésekhez és eredeti kifizetések ellenőrzése.](media/callcenterrefundmethods.png)

- **Hitelkártya** – amikor a létrehozott visszárurendelés olyan eredeti rendelésre hivatkozik, amelyet hitelkártyával fizettek ki, akkor a visszatérítés hívásközponti logikája ugyanezt az eredeti hitelkártyát alkalmazza a visszárurendelésre is.
- **Hűségkártya** – amikor a létrehozott visszárurendelés olyan eredeti rendelésre hivatkozik, amelyet vevői hűségkártyával fizettek ki, akkor a visszatérítés hívásközponti logikája ugyanezt a hűségkártyát alkalmazza a visszárurendelésre is.
- **Ajándékutalvány** (belső) – amikor a létrehozott visszárurendelés olyan eredeti rendelésre hivatkozik, amelyet a Dynamics 365 Commerce által kiadott ajándékutalvánnyal fizettek ki (belső ajándékutalvány funkció), akkor a visszatérítés hívásközponti logikája ugyanezen ajándékutalvány számát alkalmazza a visszárurendelésre is.
- **Ajándékutalvány** (külső) – ha a létrehozott visszárurendelés olyan eredeti rendelésre hivatkozik, amelyet külső külső fél által kibocsátott ajándékutalvánnyal fizettek ki, akkor a visszatérítés hívásközponti logikája a **Hívásközponti paraméterek** oldal **RMA/Visszáru** lapján megadott alapértelmezett visszáru-kifizetési módot alkalmazza.

Ha bármilyen ok miatt az eredeti rendelés fizetéstípusa ismeretlen, vagy ha az eredeti rendelés kifizetésére több fizetési módot használtak, akkor a hívásközponti logika a **Hívásközponti paraméterek** oldal **RMA/Visszáru** lapján megadott alapértelmezett visszáru-kifizetési módot alkalmazza.

A következő ábra a **Hívásközponti paraméterek** oldal **RMA/Visszáru** lapján látható **Fizetési mód** mezőt mutatja.

![A Hívásközponti paraméterek oldal RMA/Visszáru lapján látható Fizetési mód mező.](media/callcenterrefundparameters.png)

> [!NOTE]
> A korábban ismertetett visszatérítés-feldolgozási szabályok olyan rendelésekre és rendeléssorokra is vonatkoznak, amelyeket a hívásközponti felhasználók a Commerce központi felületén érvénytelenítenek. Ha egy rendelés vagy rendeléssor érvénytelenítése túlfizetést okoz, akkor a program ugyanezeket a szabályokat fogja használni a visszatérítési fizetési sorok generálása érdekében.

A visszárurendelések általában meghatározott folyamaton haladnak át, ahol bevételezik (vagy selejtezik) a készletet, a visszárurendelésre szállítólevelet adnak fel, majd egy számlafeladási folyamatot futtatnak a visszárurendelésre. A visszárurendelés a visszárurendelés létrehozási folyamatához kapcsolódik és rendszerszerűen ekkor jön létre. A tipikus helyzetekben a kifizetés-visszatérítéseket csak a visszárurendelés számlájának feladása után adják ki a vevőnek.

### <a name="what-happens-when-an-invoice-is-posted-on-a-return-sales-order"></a>Mi történik, ha számlát adnak fel egy visszárurendelésre?

Az alábbi forgatókönyvek bemutatják, hogy mi történik, ha számlát adnak fel egy visszárurendelésre:

- Ha a visszárurendelés visszatérítésének kifizetése hitelkártyához kapcsolódik, további logikára van szükség a számla feladásakor. Ez a logika arra felszólítja a fizetés feldolgozóját, hogy a vevő hitelkártyájára térítse meg a kifizetést. Egy visszatérítési vevői kifizetési bizonylat szintén létrejön, és módszeres feladásra kerül a vevő számlájára. Ezt a kifizetési naplót a visszárurendelés jóváírási bizonylata szerint egyenlíti ki a rendszer.
- Ha a kiadandó visszatérítési fizetés csekkes kifizetési típusú, létrejön egy kinnlévőségi fizetési módot használó vevői kifizetési bizonylat, és manuálisan fel kell adni vagy ki kell nyomtatni, mielőtt a kifizetési bizonylatot feladják a vevői számlára. A visszatérítési csekk feldolgozásához a felhasználók a Kinnlevőségek között található **Vevői kifizetési napló** lapot, vagy a Retail és Commerce speciális **Visszatérítési csekkek feldolgozása** lapot használják.
- Ha a kiadandó visszatérítés belső ajándékutalványos vagy hűségkártya fizetési típushoz kapcsolódik, a visszárurendelés számlázásakor a rendszer létrehoz egy visszatérítési fizetési bizonylatot, és feladja a vevői számlára. Ez a számlázási lépés hozzáadja a visszatérítési összeget is a vevő belsőleg nyomon követett ajándékutalvány-egyenlegére vagy a hűségpontok egyenlegére.
- Ha a visszárurendeléshez a **Vevő** funkciót (például vevői számlát) használó fizetési mód kapcsolódik, a rendszer figyelmen kívül hagyja a hitelkeret-ellenőrzést a kifizetés feldolgozásakor. Ebben a környezetben nem jön létre vagy nincs feladva kifizetési bizonylat. Ha visszárurendelésen vevői kifizetéstípust használnak, a számlafeladási folyamat által létrehozott jóváírási bizonylat szolgál a vevő jóváírási bizonylataként, és jelzi a vevő kinnlévőségi egyenlegére történő visszatérítést.

## <a name="advance-credit"></a>Előzetes jóváírás

Amikor egy felhasználó hívásközponti felhasználóként dolgozza fel a visszárurendeléseket egy olyan hívásközpontban, ahol a **Rendeléskiegészítés engedélyezése** beállítása **Igen**, akkor kivétel léphet fel a visszatérítési fizetések korábban ismertetett feladási folyamata alól, ha a visszárurendelést létrehozási hívásközponti felhasználó az **Előleg-jóváírás** lehetőséget **Igen** értékre állítja a **Hívásközponti paraméterek** lap **RMA/Visszáru** lapján. Ebben az esetben a kifizetés visszatérítése közvetlenül a visszárurendelés sikeres elküldése után történik a **Visszáru összegzése** lapon a **Küldés** funkcióval. A rendszer azonnal létrehoz egy előlegfizetési bizonylatot a vevő számlájára, annak ellenére, hogy magát a visszárurendelést még nem számlázták ki. Ez a megközelítés olyan helyzetekben alkalmazható, amikor egy szervezetnek a vevőknek szolgáltatási problémák miatt előzetesen kell visszatérítést kiállítania, és nem akarja előírni, hogy a visszaküldött készlet a visszatérítések kiadása előtt beérkezzen.

## <a name="replacement-orders"></a>Csererendelések

Visszárurendelés kibocsátotta esetén a **Csererendelés funkcióval** új értékesítési rendelést lehet létrehozni a vevő számára. Ez a megközelítés csere esetén használható. A **Csererendelés funkció** egy másik értékesítési rendelést hoz létre az elküldendő új cikkekhez, de a **Hívásközponti paraméterek** oldal **RMA/Visszáru** lapján található kereszthivatkozás kapcsolatot teremt a csererendelés, az RMA és a visszárurendelés között.

A csererendelésre vonatkozó kifizetések feldolgozásakor a szervezeteknek két lehetőségük van:

- A visszárurendelés visszatérítése a vevőnek az eredeti fizetési mód alapján, majd külön kifizetés beszedése a csererendelésért. A lehetőség használatához nincs szükség további konfigurációra.
- Állítsa a **Jóváírás alkalmazása** lehetőséget **Igen** értékre a **Hívásközponti paraméterek** oldal **RMA/Visszatérítés** lapján. Ebben az esetben a vevői fizetési mód rendszerszerűen lesz alkalmazva a visszárurendelésre és a csererendelésre is. Ezzel a beállítással megakadályozhatja a külső visszatérítési fizetések kibocsátását. Ezenkívül megakadályozza a tranzakció kifizetésének feldolgozását is. Ez hasznos lehet olyan esetekben, amikor egyenértékű cserét is feldolgoznak, és a szervezet inkább azt a jóváírási bizonylatot használja, amelyet a csererendelés által létrehozott számla kifizetésére a visszárurendelés számlázásakor generál. Ha a **Jóváírás alkalmazása** beállítása **Igen**, a szervezetnek manuálisan kell a jóváírást a csererendelés számlájával szemben kiegyenlíteni, miután mindkét pénzügyi bizonylatot generálta.

Az **Igen** beállítás a **Jóváírás alkalmazása** beállításnál csak akkor érvényes, ha a visszárurendelés csererendeléshez kapcsolódik. Ebben az esetben a visszatérítés és a csererendelés kifizetésének szisztematikus kifizetésére használt vevői fizetési módot a **Hívásközponti paraméterek** oldal **RMA/Visszatérítés** lapjának **Jóváírások alkalmazása fizetési mód** mezője határozza meg. Ebben a mezőben csak a **Vevő** funkció fizetéstípusának kifizetése választható ki.

> [!NOTE]
> Az olyan visszárurendelések esetén, amelyekhez nincs kapcsolt csererendelés, a **Jóváírás alkalmazása** **Igen** beállítása nem lesz hatással a visszárurendelési fizetési logikára, mivel ez a beállítás csak a csererendelésre vonatkozik.

![A Hívásközponti paraméterek oldal RMA/Visszáru lapján látható Jóváírások alkalmazása fizetési mód mező.](media/callcenterrefundparameters1.png)

> [!IMPORTANT]
> Ha a csererendeléseket létrehozó felhasználók azt tervezik, hogy a **Jóváírás alkalmazása** lehetőséget használják, akkor nem kell futtatniuk a visszárurendelés **Befejezés** függvényét, mielőtt a **Jóváírás alkalmazása** lehetőséget **Igen** értékre állítják. A **Befejezés** függvény futtatása után a program kiszámítja és alkalmazza a visszatérítési kifizetést a visszárurendelésre. Ha azt követően próbálja **Igen** értékre állítani a **Jóváírás alkalmazása** lehetőséget, hogy már kiszámította és alkalmazta a visszatérítési fizetést, a rendszer nem indítja el a visszatérítési fizetés újraszámítását, és nem alkalmazza a **Jóváírások alkalmazása fizetési mód** mezőben kiválasztott fizetési módot. Ha ebben a környezetben a **Jóváírás alkalmazása** lehetőséget kell használni, a felhasználónak törölnie kell a csererendelést és az RMA-t, majd elölről kell kezdenie, és új RMA-t kell létrehoznia. Ezúttal a felhasználónak gondoskodnia kell arról, hogy a **Befejezés** függvény futtatása előtt a **Jóváírás alkalmazása** beállítás **Igen** értékre legyen állítva.

## <a name="payment-overrides-for-call-center-returns"></a>Hívásközponti visszáruk kifizetés-felülbírálásai

Bár a hívásközponti logika szisztematikusan határozza meg a visszatérítési fizetési módot a témakörben korábban ismertetett módon, előfordulhat, hogy a felhasználók időnként felül szeretnék bírálni ezeket a kifizetéseket. Például egy felhasználó szerkesztheti vagy eltávolíthatja a meglévő visszatérítési kifizetési sorokat, és új kifizetési sorokat alkalmazhat. A rendszer által kiszámított visszatérítési kifizetéseket csak azok a felhasználók módosíthatják, akik megfelelő felülbírálási engedélyekkel rendelkeznek. Ezek az engedélyek a Kiskereskedelem és kereskedelem rendszer **Engedélyek felülbírálása** lapján konfigurálhatók. Visszatérítési kifizetés felülbírálása esetén a felhasználót egy olyan biztonsági szerepkörhöz kell kapcsolni, ahol az **Alternatív fizetés engedélyezése** beállítás **Igen** értékre van állítva az **Engedélyek felülbírálása** lapon.

![Alternatív fizetési beállítás engedélyezése az Engedélyek felülbírálása lapon.](media/overridepermissions.png)

Másik lehetőségként a szervezet a **Fizetés felülbírálatának engedélyezése** lehetőséget **Igen** értékre állíthatja a **Hívásközponti paraméterek** oldal **RMA/Visszatérítés** lapján. Ebben az esetben a **Biztonsági felülbírálat kódja** mezőben ki kell választani egy biztonsági felülbírálati kódot. A biztonsági felülbírálati kód egy alfanumerikus kód, amelyet külsőleg kell kezelni, mert a felhasználók a beállítás után nem látják azt a Commerce központi felületén. A biztonsági felülbírálati kódot csak a szervezet néhány kulcsfontosságú, megbízható tagja ismeri. Ha a **Fizetés felülbírálatának engedélyezése** beállítás értéke **Igen**, ha a megfelelő szerepkör-engedélyekkel nem rendelkező felhasználók megpróbálják megváltoztatni a visszárurendelés fizetési módját, lehetőségük van arra, hogy beírják a biztonsági felülbírálati kódot. Ha nem ismerik a kódot, vagy ha egy felettesük vagy vezetőjük nem tudja beírni a kódot helyettük az oldalon, nem tudják felülbírálni a visszáru-kifizetési módot.

> [!NOTE]
> Ha a biztonsági felülbírálati kód elveszett vagy elfelejtették, a szervezetnek alaphelyzetbe kell állítania egy új biztonsági felülbírálati kód meghatározásával, amelyet a **Hívásközpontok paraméterei** oldal **RMA/Visszáru** lapjának **Biztonsági felülbírálati kód** mezőjében.

![A Hívásközponti paraméterek oldal RMA/Visszáru lapján látható Fizetés-felülbírálati paraméterek mező.](media/overridepaymentparameter.png)

> [!IMPORTANT]
> Mielőtt a szervezetek megpróbálják felülbírálni a hitelkártyás fizetéstípusokat használó visszatérítéseket, ellenőrizniük kell, hogy a hitelkártya-feldolgozójuk engedélyezi-e a kapcsolat nélküli visszatérítéseket. Számos feldolgozó esetében a visszatérítéseket az eredeti kártyára kell visszafizetni. Ha olyan kártyára próbál visszatérítést kifizetni, amelyet korábban nem rögzítettek, az feladási hibákat okozhat a feldolgozónál.

## <a name="additional-resources"></a>További erőforrások

[Fizetési módok hívásközpontoknál](work-with-payments.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]