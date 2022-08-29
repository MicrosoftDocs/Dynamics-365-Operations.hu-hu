---
title: A Warehouse Management mobilalkalmazás lépéscímeinek és utasításainak testreszabása
description: Ez a témakör azt mutatja be, hogyan lehet egyéni utasításokat létrehozni és látni minden egyes lépéshez, amely a Raktárkezelés mobilalkalmazáshoz van beállítva.
author: Mirzaab
ms.date: 08/09/2022
ms.topic: article
ms.search.form: WHSMobileAppFlowStepListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-08-11
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: faa9bfa320823664603153601c56654170e7e23a
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/23/2022
ms.locfileid: "9334476"
---
# <a name="customize-step-titles-and-instructions-for-the-warehouse-management-mobile-app"></a>A Warehouse Management mobilalkalmazás lépéscímeinek és utasításainak testreszabása

> [!IMPORTANT]
> Az ebben a cikkben leírt funkciók csak az új Raktárkezelés mobilalkalmazásra vonatkoznak. Ezek nem érintik a régi raktár alkalmazást, amely már elavult.

Ez a témakör azt mutatja be, hogyan lehet egyéni utasításokat létrehozni és látni minden lépéshez, amely a Raktárkezelés mobilalkalmazáshoz be van állítva. Ha a raktári dolgozók jól megírt utasításokat kapnak, azonnal elkezdhetik használni az új folyamatokat anélkül, hogy előzetes képzésre lenne szükségük. Ez a funkció a következő előnyöket biztosítja:

- **Gyorsítsa fel a dolgozókat azáltal, hogy minden feladatlépésnél egyszerű utasításokat követhetnek.** A folyamat minden egyes lépése olyan utasításokat tartalmaz, amelyek lehetővé teszik, hogy a frontvonalban dolgozók megértsék a feladatot.
- **Adjon a saját folyamatainak megfelelő utasításokat.** Írja meg saját utasításait az üzleti és raktári folyamatoknak megfelelően. Például a terminológiát a fizikai térhez és a helyi rövidítésekhez igazíthatja.

## <a name="turn-the-warehouse-app-step-instructions-feature-on-or-off"></a>A Raktár alkalmazás lépési funkció be- és kikapcsolása

A funkció használata előtt be kell kapcsolva lennie a rendszeren. Az Ellátásilánc-kezelés 10.0.29-es verziója szerint ez a funkció kötelező, és nem lehet kikapcsolni. Ha 10.0.29-esnél régebbi verziót futtat, *·*[akkor](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) a rendszergazdák be- vagy kikapcsolhatják ezt a funkciót, ha a Szolgáltatáskezelés munkaterületÉn a Raktár alkalmazáslépés funkcióját keresi.

## <a name="step-titles-and-step-instructions-in-the-app"></a>Lépéscímek és lépésutasítások az alkalmazásban

A Warehouse Management mobilalkalmazáson a feladatfolyam minden egyes lépését egy lépésazonosító azonosítja. Ezenkívül minden lépésnek van címe, ikonja és utasítása. (További információért lásd: [Lépésikonok és címek hozzárendelése a Warehouse Management mobilalkalmazáshoz](step-icons-titles.md).)

### <a name="step-titles"></a>Lépéscímek

A *Lépés címe* egy rövid leírás arról, hogy a dolgozónak mit kell tennie egy lépés során. A képernyő tetején nagyméretű szövegként jelenik meg, ahogy az alábbi ábrán látható.

![Példa egy lépés címére a Warehouse Management mobilalkalmazásban](media/wma-step-title.png "Példa egy lépés címére a Warehouse Management mobilalkalmazásban")

> [!TIP]
> A nagy szövegméret miatt a lépések címeit igyekezzen a lehető legrövidebbre fogalmazni. Ellenkező esetben a szöveg elvágódhat. Hosszú címek esetén azonban a dolgozók továbbra is megnyomhatják és lenyomva tarthatják a címet, hogy megnyíljon egy párbeszédpanel, amely a teljes szöveget mutatja.

### <a name="step-instructions"></a>Lépés utasításai

A *lépésutasítás* egy hosszabb leírás, amely több információt tartalmaz arról, hogy a dolgozónak mit kell tennie egy lépés során. Ez egy felugró párbeszédpanelen jelenik meg, ahogy az a következő ábrán látható.

![Példa egy lépésutasításra a Warehouse Management mobilalkalmazásban](media/wma-step-instructions.png "Példa egy lépésutasításra a Warehouse Management mobilalkalmazásban")

A lépés utasítása automatikusan megjelenik, amikor egy lépés megnyílik. A dolgozók a felugró párbeszédpanelen kívül bárhová történő koppintással el is utasíthatják azt. A párbeszédpanel tartalmaz továbbá egy **Ne jelenjen meg újra** jelölőnégyzetet, amelyet a dolgozók bejelölhetnek, hogy az utasítás ne jelenjen meg, amikor legközelebb ugyanazt a feladatot végzik.

## <a name="load-the-default-setup"></a>Az alapértelmezett beállítások betöltése

Amikor először kapcsolja be a *Raktár alkalmazás lépésutasítás* funkcióját, a rendszer nem tartalmaz semmilyen testreszabható lépéscímet vagy utasítást. Ezért az első dolog, amit tennie kell, hogy betölti az alapértelmezett beállításokat. Az alapértelmezett beállítás az összes rendelkezésre álló lépésazonosító szövegét tartalmazza minden támogatott nyelven. Az alapértelmezett beállítás betöltéséhez kövesse az alábbi lépéseket.

1. Menjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz lépések** pontra.
1. A Műveleti ablaktáblán kattintson az **Alapértelmezett beállítás létrehozása** elemre. Az oldal a szokásos lépésekkel van kitöltve.

## <a name="customize-step-titles-and-instructions"></a>A lépések címeinek és utasításainak testreszabása

Ha egy lépés címét és/vagy utasítását tetszőleges számú nyelven szeretné testre szabni, kövesse az alábbi lépéseket.

1. Menjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz lépések** pontra.

    A **Mobileszköz lépései** oldal minden olyan lépést felsorol, amely elérhető az Ön rendszeréhez. Az egyes lépésazonosítók tetszőleges számú mobileszköz menüpontjai között oszthatók meg. Ha egy lépésazonosítót több menüpont osztja meg, ugyanaz a cím és utasítás jelenik meg az összes menüpontban. Azonban létrehozhat felülbírálásokat, amelyekkel testre szabhatja az egyes menüpontok címét és utasításait. (További információért lásd a következő szakaszt.)

    A rács a következő oszlopokat tartalmazza:

    - **Menüelem neve** - Azok a sorok, amelyekben ez az oszlop üres, az alapértelmezett lépéscímet és utasítást használják, amely minden olyan mobileszköz menüelemre vonatkozik, amelyre nincs felülbírálat definiálva. Azok a sorok, amelyekben ez az oszlop egy menüpont nevére van beállítva, csak a megadott menüpontra vonatkozó felülbírálatokkal rendelkeznek.
    - **Lépés azonosítója** - A lépés egyedi azonosítója.
    - **Bevitel címe** - A cím, amely megjelenik, amikor az alkalmazás új információt kér. Az oldalon található mezők általában üresek (azaz nincsenek előre beállított értékeik).
    - **Megerősítés címe** - A cím, amely megjelenik, amikor az alkalmazás megerősítést kér egy, a rendszerben már tárolt értékről. Általában az oldalon lévő mezőknek előre beállított értékei vannak.

1. Keresse meg a **Lépésazonosító** és a **Menüelem neve** értékek azon kombinációját, amelyet szerkeszteni szeretne, és jelölje ki az értéket a **Lépésazonosító** oszlopban. A megnyíló oldal a kiválasztott lépés címének és utasításának összes rendelkezésre álló fordítását felsorolja.
1. Kövesse az alábbi lépések egyikét a szöveg bármely nyelvre történő testreszabásához. Mindkét lehetőség lehetővé teszi a meglévő nyelvek szövegének szerkesztését. Azonban csak az első lehetőség teszi lehetővé új nyelvek szövegének hozzáadását, míg csak a második lehetőség teszi lehetővé a kiválasztott nyelv összes meglévő menüspecifikus felülírásának szövegének megtekintését és szerkesztését.

    - Az eszköztáron válassza a **Hozzáadás** lehetőséget, hogy megnyíljon egy párbeszédpanel, ahol bármely támogatott nyelvhez hozzáadhat vagy szerkeszthet szöveget. Állítsa be a **Hivatkozási nyelv** mezőt arra a nyelvre, amelynek értékeit meg kívánja tekinteni. Az értékek a bal oldali oszlopban láthatók. Állítsa be a **Fordítások nyelve** mezőt arra a nyelvre, amelyet hozzá kíván adni vagy testreszabni. A jobb oldali oszlopban szerkessze a **beviteli cím**, a **beviteli utasítás**, a **megerősítés címe** és a **megerősítési utasítás** mezők értékeit a kívánt módon. Majd kattintson az **OK** lehetőségre.
    - Keresse meg és válassza ki a rácsban azt a sort, ahol a **Nyelv** mezőben a szerkeszteni kívánt nyelv van beállítva. Válassza az eszköztáron a **&lt;nyelvi fordítások&gt; megtekintése e lépésben** lehetőséget, hogy megnyíljon egy párbeszédpanel, ahol szerkesztheti a kiválasztott nyelv összes rendelkezésre álló felülírásának szövegét. A párbeszédpanel egy rácsot tartalmaz, amely sorokat tartalmaz mind a standard szövegek számára (ahol a **Menüelem neve** mező üres), mind az egyes rendelkezésre álló felülbírálható szövegek számára (ahol a **Menüelem neve** mezőbe annak a menüpontnak a neve van beállítva, amelyre a felülbírálás vonatkozik). Szerkessze a **beviteli cím**, a **beviteli utasítás**, a **visszaigazolási cím** és a **visszaigazolási utasítás** mezők értékeit a kívánt módon. Majd kattintson az **OK** lehetőségre.

1. Folytassa a munkát, amíg minden szükséges nyelvhez meg nem határoz minden szükséges címet és utasítást.

## <a name="add-menu-specific-overrides"></a>Menüspecifikus felülbírálások hozzáadása

Ahogy az előző szakaszban említettük, minden lépésazonosítóhoz tetszőleges számú menüspecifikus felülbírálást hozhat létre. Ezt a képességet használhatja az utasítás szerkesztésére és módosítására, hogy az jobban illeszkedjen egy adott menüpont helyi üzleti folyamatához. Ha például az értékesítési komissiózás esetében a vállalat általában nyomtatott dokumentumon adja meg a dolgozóknak a munkaazonosítót, akkor adhat egy utalást arra, hogy a dolgozóknak a munkaazonosító beolvasásával kell kezdeniük a munkát.

Minden felülbírálat egy adott mobileszköz menüpontjára vonatkozik, és tetszőleges számú fordítást tartalmazhat. Ha egy menüponthoz nincs felülbírálat, a menüpont a szabványos szövegeket használja. Ha egy nyelvhez nincs felülíró fordítás definiálva, akkor a standard szövegek kerülnek használatba, még azoknál a menüpontoknál is, ahol más nyelvekhez van felülíró fordítás definiálva.

A felülbírálás létrehozásához és konfigurálásához kövesse az alábbi lépéseket.

1. Menjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz lépések** pontra.
1. Keresse meg és válassza ki a rácsban azt a sort, amelyhez felülbírálást kíván létrehozni.
1. A Műveletpanelen válassza a **Lépéskonfiguráció hozzáadása** lehetőséget.
1. A **Lépéskonfiguráció hozzáadása** legördülő párbeszédpanelen állítsa be a **Menüelem** mezőbe annak a mobileszköz menüpontnak a nevét, amelyre a felülbírálás vonatkozik. Majd kattintson az **OK** lehetőségre.
1. A megjelenő oldalon az új felülbíráláshoz rendelkezésre álló összes szöveg látható. Kezdetben csak egy nyelv jön létre. Az összes többi nyelv továbbra is a szabványos szövegeket fogja használni, hacsak nem adja hozzá ezeket a nyelveket itt. Szerkessze a szövegeket, és szükség szerint adjon hozzá új nyelveket, az előző szakaszban leírtak szerint.
