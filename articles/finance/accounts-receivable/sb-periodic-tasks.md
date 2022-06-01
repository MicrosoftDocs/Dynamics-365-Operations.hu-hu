---
title: Ismétlődő feladatok az ismétlődő szerződés számlázásában
description: Ez a témakör az ismétlődő szerződés számlázása során elérhető ismétlődő feladatokat ismerteti.
author: JodiChristiansen
ms.date: 04/29/2022
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
ms.openlocfilehash: 80f65d82881bb000f626c4225b3eac7dd1a2a44a
ms.sourcegitcommit: 1877696fa05d66b6f51996412cf19e3a6b2e18c6
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/20/2022
ms.locfileid: "8786983"
---
# <a name="periodic-tasks-in-recurring-contract-billing"></a>Ismétlődő feladatok az ismétlődő szerződés számlázásában

Ez a témakör az ismétlődő szerződés számlázása során elérhető ismétlődő feladatokat ismerteti.

## <a name="generate-invoice"></a>Számla létrehozása

A Számla **létrehozása lapon** **·** **tömeges** havi ismétlődő számlákat hozhat létre az Összes számlázási ütemezés és a Számlázási adatok megtekintése lapon beállított adatok alapján. Számla létrehozásakor az értékesítési rendelési feldolgozási sor cikkleírása frissül a cikk leírásával, valamint a számlázás ütemezési sorához tartozó számlázási kezdő és záró dátummal.

## <a name="generate-invoice-batch-processing"></a>Számla létrehozása kötegelt feldolgozás

Ismétlődő számlák **ismétlődő kötegelt feldolgozáson** keresztüli létrehozásához használja a Számla kötegelt feldolgozásának létrehozása lapot. A rendelkezésre álló paraméterek **ugyanazok**, mint a Számla létrehozása lapon található paraméterek, de egy kötegfolyamatba menthetők, és többször is futtathatók.

## <a name="price-update"></a>Ár frissítése

Az Árfrissítés segédprogrammal egyetlen műveletben frissítheti több cikk árát több számlázási ütemezésben. Az árak megadott százalék vagy meghatározott összeg alapján frissíthetők. A sorok listája csak a cikkek aktuális egységáraiból áll. Nem mutatja az árakat az árfrissítés után.

Jegyezze fel az árfrissítési segédprogrammal kapcsolatos következő pontokat:

- Ha már létrejött egy adott évre vonatkozó értékesítési rendelés (azaz a cikkek ki vannak számlázva), akkor ez nem befolyásolja a sorelemek árát.
- Az Árfrissítés segédprogram **az** **Aktív vagy Avárasztott állapotú sorelemekhez használható.** A készleten lévő cikkeknél az **Ütemezés** **beállítása** beállítást Nem beállításra kell állítani a visszatartott tétel beállításakor.
- Az Árfrissítés segédprogram nem használható olyan sorelemekhez, amelyek felhasználási cikkek, amelyek eszkalációt, mérföldkőszámlázást vagy bevétel-felosztást használnak.

### <a name="price-update-example"></a>Példa az árfrissítésre

Létrejön a számlázási ütemezés, és új elem jön létre. Az egységár nem $750. A cikk első évét 2021. december 15-én fizetik ki. A számlázási ütemezés 2022. január 1-től december 31-ig tart.

A megújításkor a Számla **létrehozása** folyamat létrehozza a 2022-es évre vonatkozó értékesítési rendelést. Az Árfrissítés segédprogram futtatása után az ár automatikusan módosul új $750 új $800.

A 2022-es értékesítési rendelésre és számlázási ütemezésre nincs hatással, és az egységár $750 marad, mivel a 2022-es számlázási ütemezés már ki van számlázva. A számlázási ütemezés 2023-as sorát és soradatokat $800, mivel a 2023-as számlázási ütemezés még nincs számlázva.

### <a name="update-prices--flat-pricing-method"></a>Árak frissítése - lakásárazás módja

Ha a árral árazási módszert alkalmazott cikkek árát frissíti, az ár növeléséhez megadhat egy százalékos értéket vagy összeget.

A flat priceing módszert alkalmazott cikkekhez az árfrissítési segédprogram futtatásához kövesse ezeket a lépéseket.

1. Az Árfrissítési **segédprogram** lapon válassza a Lakás **árképzés** módszerét.
2. A Növelése **módszer mezőben** válassza ki a cikkek árának frissítéséhez használt növelő módszert.
3. A kiválasztott növelő módtól függően **a** **Százalék mezőben vagy az Összeg mezőben adja meg a százalékos értéket.**
4. A **FastTab** **gombra** kattintva adja hozzá az adatszűrőket a rekordokhoz a Szűrő gombbal.
5. A rekordok **tartományának** megtekintéséhez válassza a Nézet előnézetét.
6. Ha nem szeretne feldolgozni néhány sort, jelölje meg őket, majd válassza az Eltávolítás **lehetőséget**.
7. Válassza ki az **OK** lehetőséget.

### <a name="update-prices--standard-pricing-method"></a>Árak frissítése - Szokásos árképzési módszer

Ha egy cikk ára módosult a cikkrekordban, akkor az valamennyi számlázási ütemezési sorra frissíthető, ha a cikk a normál árképzési módszert használja.

1. Az Árfrissítési **segédprogram** lapon válassza ki a Szokásos **árképzési** módszert.
2. A **FastTab** **gombra** kattintva adja hozzá az adatszűrőket a rekordokhoz a Szűrő gombbal.
3. A rekordok **tartományának** megtekintéséhez válassza a Nézet előnézetét.
4. Ha nem szeretne feldolgozni néhány sort, jelölje meg őket, majd válassza az Eltávolítás **lehetőséget**.
5. Válassza ki az **OK** lehetőséget.

## <a name="mass-hold-processing"></a>Tömeges várakoztatás feldolgozása

A Tömeges hold **lapon** alkalmazhatja egyszerre több számlázási ütemezésre a holdbeállításokat.

Ha csak egy számlázási ütemezést vagy egy számlázási ütemezési sort is fel kell függesni, akkor nyissa **meg** az Összes számlázási ütemezés lapot, és válassza a Hely a lenyomva **gombra való lehetőséget**. A hold eltávolításához használja a Hold **eltávolítása lapot**.

### <a name="put-billing-schedules-on-hold"></a>Számlázási ütemezések berakodva

Ha több számlázási ütemezést is fel kell függesni, kövesse ezeket a lépéseket.

1. A Tömeges hold **oldalon** állítsa be **a** Folyamat beállításmezőt a Hold **alkalmazása beállításhoz**.
2. Az Okkód **mezőben** válasszon egy okkódot.
3. Az Ütemezés beállítása **:**

    - **Igen** – ha Igen beállítást adja **meg**, a Hold dátuma **mezőben adjon meg egy holddátum-dátumot**. A program a hold dátuma utáni számlázási ütemezés minden sorát eltávolítja.
    - **Nem** – a számlázási ütemezés sorai nem módosulnak. Csak az állapot módosul. A rendszer "Visszatartott"re **frissíti**.

4. A **FastTab** **gombra** kattintva adja hozzá az adatszűrőket a rekordokhoz a Szűrő gombbal.
5. A rekordok **tartományának** megtekintéséhez válassza a Nézet előnézetét.
6. Ha nem szeretne feldolgozni néhány sort, jelölje meg őket, majd válassza az Eltávolítás **lehetőséget**.
7. Válassza ki az **OK** lehetőséget.

Ha visszatér a számlázási ütemezések listájához, láthatja, **hogy a számlázási ütemezések állapota "Várjon" állapotra változott**.

### <a name="remove-a-hold-from-several-billing-schedules"></a>Több számlázási ütemezés<a2/&a3><a2/&;

1. A Tömeges hold **oldalon** állítsa be **a Folyamat beállításmezőt** a Hold eltávolítása **beállításhoz**.
2. Az Okkód **mezőben** adja meg az okkódot.
3. A Dátum **eltávolítása mezőben** válassza ki azt a dátumot, amikortól el kell távolítani a visszatartott 500 000 000 000 000 000 000 00
4. Állítsa be **az Újrabehozási dátum** **és a Halasztás** dátuma mezőket a szükséges szerint. A halasztás dátuma minden olyan sorhoz hozzá van adva, amely halasztható.
5. A **FastTab** **gombra** kattintva adja hozzá az adatszűrőket a rekordokhoz a Szűrő gombbal.
6. A rekordok **tartományának** megtekintéséhez válassza a Nézet előnézetét.
7. Ha nem szeretne feldolgozni néhány sort, jelölje meg őket, majd válassza az Eltávolítás **lehetőséget**.
8. Válassza ki az **OK** lehetőséget.

> [!NOTE]
> A hold **eltávolításához** **be kell állítania az Ismétlődő szerződés számlázási paraméterei oldalon a <a0/&; felhasználói csoport felülbírálati értékét.**

Például egy számlázási sor 2022. február 1-jén kezdő dátummal, 2022. február 28-i záró dátummal rendelkezik. A számlázási összeg $200. A **Hold dátuma** mező 2022. február 10-re van állítva. Ebből következően a februári időszak úgy módosul, hogy ne legyen február 10-e utáni dátum. Az új időszak február 1-től február 9-ig tart, és az összeg $64.29 (napi proráción keresztül). A február 10-jén vagy azt követően ütemezett összes sor törlődik.

Ha a **Visszatartott** eltávolítása folyamat befejeződött, **és** a Dátum eltávolítása mező 2022. február 10-re van állítva, két számlázási időszak lesz. Az első számlázási időszak február 1-től február 9-ig tart, és az összeg $64.29. A második számlázási időszak február 10-től február 28-ig tart, és az összeg $135.71.

## <a name="mass-termination-processing"></a>Tömeges felmondás feldolgozása

A tömeges felmondási **lapon** az éppen látható számlázási ütemezési sorokat a felmondás dátumának megadásával lehet megszüntetni.

Ha bevétel- és költség halasztásokat használ, azok a számlázási ütemezések, amelyekben a Felmondás dátuma mező be van állítva az ütemezés módosítására az Összes számlázási ütemezés lapon, **·** **·** **visszatérítésre** jogosult.

A több elemfelosztási (MEA) funkciót is felhasználó számlázási ütemezések nem jelennek meg a tömeges **felmondási oldalon**. Az egyes számlázási ütemezéseket akkor is megszakíthatja, ha a számlázási ütemezés felmondási funkcióit használja.

> [!NOTE]
> A Számla létrehozása köteg létrehozásában jelenleg **szereplő** számlázási ütemezéssorok nem érhetők el ebben a folyamatban.

További tájékoztatás az egyes mezőkről és a folyamatokról: [Számlázási ütemezések megszüntetése](terminate-billing-schedule.md).

## <a name="mass-archive-process"></a>Tömeges archiválási folyamat

A Tömeges archívum **lapon** archiválhatja a számlázási ütemezéseket. Csak a kimondott számlázási ütemezések archiválhatók.

A számlázási ütemezés archiválását követően a következő események történnek:

- Az állapot Archivált **állapotúra változik**.
- A számlázási ütemezések véglegesen zárolva vannak.
- A számlázási ütemezés sorai már nem érhetők el a lekérdezési lapokon.

> [!NOTE]
> A számlázási ütemezés archiválási művelete állandó, ezért nem sztornírozható.

A számlázási ütemezések archiválásához kövesse ezeket a lépéseket.

1. A Tömeges archív **lap** **Számlázás záró dátuma mezőjében** adja meg a számlázás záró dátumát. Ha minden elmondott számlázási ütemezést meg kell tekinteni, hagyja üresen ezt a mezőt.
2. A **FastTab** **gombra** kattintva korlátozhatja a megjelenő rekordokat a Rekordok mezőben.
3. A nézet **előnézetének kiválasztása**.
4. Ha egyes rekordokat nem szeretne archiválni, jelölje meg őket, majd válassza az Eltávolítás **lehetőséget**.
5. Válassza az **OK** gombra az oldal rekordjainak archiválásához.

## <a name="mass-stubbing-process"></a>Tömeges csekkszelvényezési folyamat

A tömeges **időkorlátozás lapon** minden kiválasztott számlázási ütemezéssort számlázandóként (szelvény) vagy nem számlázhatóként (sztornózó szelvényként) jelöl meg. A korábban egy másik rendszerben számlázva számlázható importált számlázási ütemezéssorok esetén a legtöbb esetben a leszelvényezés vagy a rövidítés sztornírozása történik. A számlázott számlázási ütemezések sorai elkábultnak jelennek meg, és nem hoznak létre számlát a vevő számára.

### <a name="stub-records"></a>Szelvényrekordok

1. A Tömeges elkábítás **lap** **Folyamatbeállítások** mezőjében válassza a **Szelvény lehetőséget.**
2. A Kivágási **dátum** mezőben állítson be egy erre a dátumra vonatkozó dátumot, amely meghatározza azokat a sorokat, amelyekre alkalmazni szeretné a folyamatot. Csak azok a rekordok jelennek meg, amelyekhez a számlázás kezdő dátuma a megadott kezdési dátum vagy az előtti dátum.
3. A **nézet előnézetének** kiválasztásával megtekintheti a szelvénybe szelvényként kívánt sorokat.
4. Ha ki szeretne zárni egy sort a folyamatból, jelölje meg, majd válassza az Eltávolítás **lehetőséget**.
5. Folyamat **kiválasztása** a sorok megcsonkításához.

### <a name="reverse-stub-records"></a>Szelvényrekordok sztornírozata

1. A Folyamat **beállításai lap Tömeges elkábítás** mezőjében válassza **a** Szelvény sztornírozása **lehetőséget**.
2. A Kivágási **dátum** mezőben állítson be egy erre a dátumra vonatkozó dátumot, amely meghatározza azokat a sorokat, amelyekre alkalmazni szeretné a folyamatot. Csak azok a rekordok jelennek meg, amelyekhez a számlázás kezdő dátuma a megadott kezdési dátum vagy az előtti dátum.
3. A nézet **előnézetének** kiválasztásával megtekintheti a sztornírozni kívánt sorokat.
4. Ha ki szeretne zárni egy sort a folyamatból, jelölje meg, majd válassza az Eltávolítás **lehetőséget**.
5. Folyamat **kiválasztása a** sorok sztornírozása érdekében.

## <a name="update-completion-date-process"></a>Teljesítési dátum frissítési folyamata

A Frissítés befejezésének **dátuma lapon** frissítheti több számlázási ütemezés vagy felhasználó meghatározott mérföldkőelemekre vonatkozó befejezési dátumát. A készültségi százalék módszerrel **a mérföldkősablonok elemeinek készültségi százalékát is frissítheti**.

1. A Frissítés befejezésének **dátuma** lapon kattintson a Mérföldkő-feldolgozásra **,** és válassza a Frissítés százalékos **értéke lehetőséget**.
2. A Százalék **összege mezőbe** írja be a teljes befejezett százalékot.
3. Válassza ki a mérföldkősablonhoz kapcsolódó cikkszámot.
4. A **FastTab** **·** **elemet** is beleveendő rekordokban a Szűrő elemet választva szűrő feltételként kiválaszthat egy konkrét záró felhasználói fiókot, **·** **számlázási** ütemezési számot vagy cikkszámértéket.
5. A **módosítás feldolgozásához kattintson az OK** gombra. Ha befejeződött a feldolgozás, egy új sor kerül a mérföldkő-felosztásba. Ez a sor a mérföldkősablonban megadott százalékos arányt jelöli.

## <a name="unbilled-revenue-mass-processing"></a>Számlázatlan bevétel tömeges feldolgozása

A Nem **számlázatlan** bevétel tömeges feldolgozási lapon hozhatja létre a nem számlázandó bevételnapló-bejegyzést, vagy megkétlizálja a naplóbejegyzést egy vagy több kiválasztott számlázási ütemezéshez vagy számlázási részletsorhoz.

- **Naplóbejegyzés létrehozása** – nem számlázandó bevételnapló-bejegyzések létrehozása több számlázási ütemezési sorhoz. A Gyors **be tartalmazni** **kívánt** rekordok szűrőgombjával kiválaszthatja a listában megjelenő rekordok tartományát. A lista csak azokat a számlázási ütemezési sorokat jeleníti meg, amelyekhez még nem készült számlázatlan bevételnapló-bejegyzés. Létrejönnek a kezdő naplóbejegyzések. Halasztott cikkekhez a halasztás ütemezései is létrejönnek.
- **Szelvénynapló bejegyzése** – jelölje meg a számlázási ütemezésnek azt a sorát, amelyekhez a nem számlázandó naplóbejegyzések már létre vannak hozva. Ez a beállítás akkor használható, ha a nem könyvelt naplóbejegyzést már fel lett adva egy másik rendszerben. A nem számlázandó bevételnaplót rövidítettként jelöli meg, és nem ad fel tranzakciót a főkönyvbe.
- **Szelvénynapló bejegyzésének sztornírozása** – a már feldolgozott szelvénynapló-bejegyzések sztornírozása. Ha hiba történt a **Csekknapló** bejegyzésének feldolgozása közben, **ezzel** a beállítással törli a jelölést a számlázási ütemezés sorának Tarolt jelölőnégyzetből.
- **Számlakivonat-részletsor** – akkor használja ezt a folyamatot, amikor egy külső rendszerben fel lett használva a számlázatlan bevétel, és a számlázási adatok egy része már számlázva lett. Ezzel a folyamattal gondoskodik arról, hogy a megfelelő összeg jelenjen meg a nem számlázandó bevételi számlákon.
- **Stornószámlázás részletsorának sztornírozata** – a **szelvényszámlázás minden sorműveletét sztornírozhatja**.

A **Naplónév mező** használatos **a** Napló létrehozása bejegyzésnek a főkönyvbe való feladásakor.

> [!NOTE]
> A szelvény folyamata nem ad fel összegeket a főkönyvbe. A **Naplónév** mező nem érhető el minden szelvény- és sztornírozási szelvényfolyamatnál.

### <a name="unbilled-revenue-stub-example"></a>Nemszámlázandó bevételszelvény – példa

A számlázási ütemezés egy évre van beállítva 2021. októbertől 2022 szeptemberéig. A nemszámlázatlan bevétel már fel lett feldolgozva egy külső rendszerben. A számlázási ütemezés kilenc hónapja már számlázva van. Az egyes számlázási időszakokat összegként kell $250. Az év elején a nem könyvelt bevételhez feladott teljes összeget $3,000. Kilenc hónap után $2,250 már számlázva lett, és $750 nem számlázatlan bevétel marad.

Ha olyan számlázási ütemezést kell beállítani, amelyben még csak három hónapnyi be nem számlázatlan bevétel marad, kövesse ezeket a lépéseket.

1. **A Számlázási adatok** megtekintése lapon hozzon létre számlázási ütemezést a 2021. októbertől 2022. szeptemberig, az S0001 cikkszámhoz és havi $250 időszakhoz.
2. Válassza **a Naplóbejegyzés létrehozása a** számlázási ütemezéshez lehetőséget. Az összeg $3,000 a nem könyvelt bevételbe lesz feladva.
3. Jelölje **ki a Cikl; számlázási részletsort**, majd adja meg a 2022. júniusi tranzakciódátumot (kilenc hónap). A számlázási ütemezés sorai nem jelennek meg az előnézetben. Az érintett sorok a tranzakció dátumán alapulnak.
4. Válassza ki az **OK** lehetőséget.

Az első kilenc hónap, amelyről számlát lehetett kiszámlázni, el lett tásva.

[![Számlázási részletsorok szelvényének megtekintése](./media/01_View-billing-detail-stub.png)](./media/01_View-billing-detail-stub.png)

A $3,000 sztornírozása a nemszámlázatlan bevételből történt, és $750 bevételből származó bevételt feladja a feladásra. A nemszámlázatlan **bevételfeladások megtekintéséhez válassza a Nem könyvelt** **bevétel** naplóbejegyzések auditálását a sor részleteit tartalmazó lap Megújítások lapján.

[![Nemszámlázandó bevételnapló-bejegyzés ellenőrzése.](./media/02_Unbilled-rev-journal-audit.png)](./media/02_Unbilled-rev-journal-audit.png)

> [!NOTE]
> A nem számlázható bevételnapló-bejegyzés bármely megújítási időszakhoz létre lehet hozva, feltéve, hogy az előző időszak összes számlázási részletsorát kiszámlázták. Például egy számlázási ütemezési sor havi számlázási gyakorisággal rendelkezik egy 12 hónapos időszakra, januártól 2021 decemberig. A sornak három fogalma van: az első, a második feltétel (2022. januártól decemberig), és egy harmadik feltétel (januártól 2023. decemberig). Miután a számlát létrehozták a 2021-es első 12 hónap minden számlázási részletsorához, a második időszakra is létre lehet hozva a nem számlázott bevétel naplóbejegyzését.
>
> A nem számlázandó bevétel szolgáltatást igénybe vevő halasztási cikkek esetén a számlázási sor és az engedménysorok feldolgozása meg lesz folyamatban. Ilyen cikkek esetén létrejön a nem számlázandó bevételnapló bejegyzése, valamint a számlázási sorhoz és az engedménysorhoz a halasztás ütemezése.
>
> A nem halasztható cikkekhez és a halasztható cikkekhez létrehozott naplóbejegyzések jóváírást adnak fel a különböző bevételi számlákra.
