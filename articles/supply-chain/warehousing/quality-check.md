---
title: Minőség-ellenőrzés
description: Ez a témakör a minőségellenőrzés funkcióról nyújt tájékoztatást. Ez a funkció lehetővé teszi a raktári dolgozók számára, hogy minőséggel kapcsolatos villámellenőrzést végezzenek, miközben átveszik a cikkeket a bejövő dokkoló területen.
author: mirzaab
manager: tfehr
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: c270426a228ac58652f1f60d6fe99d4886071fa6
ms.sourcegitcommit: 4a981ee4be6d7e6c0e55541535d386bce2565cba
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/27/2020
ms.locfileid: "3621438"
---
# <a name="quality-check"></a>Minőség-ellenőrzés

[!include [banner](../includes/banner.md)]

A *Minőségellenőrzés* funkció lehetővé teszi a raktári dolgozók számára, hogy minőséggel kapcsolatos villámellenőrzést végezzenek, miközben átveszik a cikkeket a bejövő dokkoló területen. Ezek a villámellenőrzések akkor hasznosak, amikor a dolgozók a csomagolást vagy a cikk más könnyen felismerhető részeit ellenőrzik. A funkció útmutatást ad a dolgozókat, hogyan tudják egy pillantással eldönteni, hogy van-e valami szembetűnő hiba vagy sérülés, mielőtt a készletet az eltárolás helyére vinnék.

Ez a funkció a szokásos minőségellenőrzési folyamat alternatívája. Nagyobb rugalmasságot és gyorsabb feldolgozást kínál.

Amikor ezt a funkciót használja, a következő módon történik az érkezés és a minőség ellenőrzése:

1. Amikor egy szállítmány beérkezik, a raktári dolgozó feljegyzi az érkezést. A dolgozó beszkenneli a rendszámtáblát a hely regisztrációjához.
1. A dolgozó elvégez egy gyors minőségellenőrzést, és feljegyzi az adott rendszámtábla (megfelelt vagy nem felelt meg) eredményét.
1. Az alábbi műveletek egyike történik:

    - Ha a minőségellenőrzésen megfelelt, akkor elfogadják a rendszámtáblát, és a szokásos módon egy bevételezési hely irányítják.
    - Ha a minőségellenőrzésen nem felelt meg, akkor elutasítják a rendszámtáblát, és a meglévő eltárolási munkát átirányítják egy másik helyre további ellenőrzés céljából. Létrejön egy új minőségi rendelés. Ha meg szeretné tekinteni a meg nem felelt minőségellenőrzésből létrehozott minőségi rendelést, menjen a **Készletkezelés \> Időszakos feladatok \> Minőségkezelés \> Minőségi rendelések** elemre.

Ezt a folyamatot úgy is be lehet állítani, hogy az összes beolvasott rendszámtábla rögtön a minőségellenőrzési helyre kerüljön át.

## <a name="turn-on-the-quality-check-feature"></a>A Minőségellenőrzési funkció bekapcsolása

A funkció használata előtt be kell kapcsolnia a saját rendszerében a *Minőségellenőrzés* funkciót. A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához. A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:

- **Modul:** *Raktárkezelés*
- **Funkció neve:** *Minőségellenőrzés*

## <a name="set-up-the-feature-for-the-example-scenario"></a>A funkció beállítása a példaforgatókönyvhöz

Ez a szakasz iránymutatásokat és egy példát mutat be azzal kapcsolatban, hogy hogyan kell beállítani a *Minőségellenőrzés* funkciót, illetve hogyan kell előkészíteni mintaadatokat a témakörben később bemutatott példaforgatókönyvben.

### <a name="make-sample-data-available"></a>A mintaadatok elérhetővé tétele

Ha ezt a [példaforgatókönyvet](#example-scenario) az itt megadott mintaadatok és értékek alapján kívánja elvégezni, akkor egy olyan rendszert kell használnia amelynél a szokásos [bemutatóadatok](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) telepítve vannak. Emellett az **USMF** jogi személyt is ki kell választani a kezdés előtt.

### <a name="quality-check-template"></a><a name="quality-template"></a>Minőség-ellenőrzési sablon

A minőségellenőrzési sablon határozza meg, hogy a beérkezéskor milyen szabályok vonatkoznak a minőséggel kapcsolatos villámellenőrzések során.

1. Lépjen a **Raktárkezelés \> Beállítás \> Munka \> Minőségellenőrzési sablonok** elemre.
1. Válassza az **Új** lehetőséget egy sablon rácshoz való hozzáadásához.
1. Állítsa be a következő értékeket az új sablon meghatározásához:

    - **Minőségellenőrzési sablon neve:** *Dokkellenőrzés*

        Adjon meg egy nevet, amely azonosítja a sablonhoz alkalmazott szabályokat.

    - **Elfogadási irányelv:** *Felhasználó kérése*

        Határozza meg, hogy a felhasználókat meg kell-e kérni a készlet minőségének elfogadására vagy elutasítsására, vagy a minőséget automatikusan el kell-e utasítani. A választható lehetőségek az *Automatikus elutasítás* és a *Felhasználó kérése*.

    - **Minőségfeldolgozási irányelv:** *Minőségi rendelés létrehozása*

        Válassza ki a készlet minőségének elutasításakor használandó irányelvet. Ehhez a következő lehetőségek állnak rendelkezésre:

        - *Csak munka létrehozása* – Hozzon létre csak munkát a készlet mozgatásának megkönnyítéséhez.
        - *Minőségi rendelés létrehozása* – Hozzon létre minőségi rendelést a minőségi tesztek megkönnyítéséhez.

    - **Tesztcsoport:** *Doboz*

        Határozza meg a létrehozott minőségi rendelésben használandó tesztcsoportot. A tesztcsoportok a **Készletkezelés** modulban állíthatók be.

        Hagyja kikapcsolva a **Romboló szöveg** lehetőséget a tesztcsoportnál. Ex a lehetőség határozza meg, hogy a tesztcsoportban szereplő tesztek eredményeként a mintát tönkreteszik-e vagy sem. Ha egy romboló tesztet használ, a rendszer létrehoz egy készlettranzakciót, ha a cikkhez létrehoznak egy minőségi rendelést. Az új készlettranzakció előrejelzi mennyiségi teszthez való készlet csökkenését. Készletcsökkenés akkor megy végre, ha a minőségi rendelést az ellenőrzési lépéssel fejezi be. A készlettranzakciót minőségi rendelésként azonosítja a rendszer.

### <a name="work-class--quality-check"></a><a name="work-class"></a>Munkaosztály – Minőségellenőrzés

A munkaosztályokkal irányítható és/vagy korlátozható azon munkarendeléssorok típusa, amelyeket a raktári dolgozók feldolgozhatnak egy mobileszközön.

1. Ugorjon a **Raktárkezelés \> Beállítás \> Munka \> Munkaosztályok** pontra.
1. Válassza az **Új** lehetőséget egy munkaosztály létrehozásához.
1. A fejlécben állítsa be a következő értékeket:

    - **Munkaosztály azonosítója:** *Minőségellenőrzés*

        Adjon meg egy nevet, amely azonosítja a munkaosztályt.

    - **Leírás:** *Minőségellenőrzés*

        Adjon meg egy rövid leírást, amely jelzi, hogy mire használható a munkaosztály.

    - **Munkarendelés típusa:** *Minőség a minőségellenőrzésben*

        Válassza ki, hogy milyen típusú munkarendelést hoz létre a munkaosztály. A minőségellenőrzési munka beállításakor mindig válassza a *Minőség a minőségellenőrzésben* lehetőséget.

1. Az **Érvényes betárolási helytípusok** gyorslapon hagyja üresen a **Hely típusa** mezőt.

    Ha kiválaszt egy helytípust, akkor korlátozza azon helyeket, ahol a cikkeket a betárolásuk után ki lehet tárolni. Akkor használja ezt a mezőt, ha egy helyutasítás a hely feloldására tesz kísérletet, vagy amikor egy raktári dolgozó manuálisan meghatározza a mobileszköz-menüpont helyét.

A munkaosztályokkal és azok létrehozásával kapcsolatos további tudnivalókat lásd: [Munkaosztály létrehozása](tasks/create-work-class.md).

### <a name="work-template"></a>Munkasablon

A munkasablonokkal megadhatja a műveleteket, amiket el kell végezni a raktárban. Általában a raktári műveletek két egymást követő műveletből állnak: egy raktári dolgozó felveszi az aktuális készletet az egyik helyen, majd lerakja a készletet egy másik helyen. A minőségellenőrzés munkasablonja meghatározza a minőségellenőrzések munkafolyamatait.

#### <a name="purchase-orders"></a>Beszerzési rendelések

1. Lépjen a **Raktárkezelés \> Beállítás \> Munka \> Munkasablonok** elemre.
1. A fejlécben állítsa át a **Munkarendelés típusa** mezőt *Beszerzési rendelések* értékre.
1. A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.
1. Olyan munkasablonr válasszon ki, amelynek tartalmaznia kell egy minőségellenőrzési lépést. Válassza az **Áttekintés** szakaszban a **Munkasablon** mezőben lévő *51 Igénylés, beszerzési rendelés* lehetőséget.
1. A **Munkasablon részletei** szakaszban figyelje meg, hogy a rácsnak két meglévő sora van: egy *Kitárolásra* és egy *Eltárolásra*.
1. A **Munkasablon részletei** szakaszban válassza ki az **Új** lehetőséget,ha a rácshoz hozzá szeretne adni egy sort a minőségellenőrzéshez. Figyelje meg, hogy az új sor **Sorszám** mező *3* értékre van állítva.
1. Az új sorban állítsa be a következő értékeket. Az fennmaradó mezőkben hagyja meg az alapértelmezett értékeket.

    - **Munkatípus:** *Minőségellenőrzés*
    - **Munkaosztály azonosítója:** *Beszerzés*
    - **Minőségellenőrzési sablon neve:** *Dokkellenőrzés*

        Válasszon egy egyedi azonosítót a munkaosztályhoz. Ezt az értéket használja a menüelemek beállítására a mobileszközön, és azon munkatípusok beállításához, amelyeket azok a menüelemek fel tudnak dolgozni.

1. A Művelet ablaktáblában válassza a **Mentés** lehetőséget az elvégzett munka mentéséhez.

    Egy tájékoztató üzenet jelenik meg: „Érvénytelen – A minőségellenőrzésnek közvetlenül a kitárolás után kell következnie”. Ennek megfelelően módosítania kell az imént hozzáadott sor **Sorszám** értéket.

1. Az új sor **Sorszám** értékének módosításához kövesse az alábbi lépéseket:

    1. A **Munkasablon részletei** szakaszban válassza ki azt a sort, amelyben a **Munka típusa** mező *Minőségellenőrzés* lehetőségre van állítva.
    2. Válassza a **Feljebb** vagy a **Lentebb** gombra a *Minőségellenőrzés* sor mozgatásához, hogy a *Kitárolás* sor után jöjjön.

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

#### <a name="quality-in-quality-check"></a>Minőség a minőség-ellenőrzésnél

Ezután hozzon létre egy munkasablont a minőségellenőrzéshez.

1. A **Munkasablonok** lap fejlécében módosítsa a **Munkarendelés típusa** mező értékét a *Minőség a minőségellenőrzésben* lehetőségre.
1. A Művelet panelen válassza az **Új** lehetőséget egy sor **Áttekintés** szakaszban lévő rácshoz való hozzáadásához.
1. Az új sorban állítsa be a következő értékeket:

    - **Munkasablon:** *51 Minőségellenőrzés*

        Írja be a sablon nevét.

    - **Munkasablon leírása:** *51 Minőségellenőrzés*

1. A Művelet ablaktáblán a **Mentés** gombra kattintva elérhetővé válik a **Munkasablon részletei** szakasz.
1. Miközben az új sablon még ki van választva az **Áttekintés** szakaszban, válassza az **Új** lehetőséget a **Munkasablon részletei** szakaszban, így hozzáadhat egy sort a sablonban lévő rácshoz.
1. Az új sorban állítsa be a következő értékeket:

    - **Munka típusa:** *Kitárolás*
    - **Munkaosztály azonosítója:** *Minőségellenőrzés*

        Válassza ki a [Munkaosztály](#work-class) nevét, amelyet korábban létrehozott a minőségellenőrzési munkához.

1. A **Munkasablon részletei** szakaszban válassza ki megint az **Új** lehetőséget, ha egy újabb sort szeretne hozzáadni.
1. Az új sorban állítsa be a következő értékeket:

    - **Munka típusa:** *Eltárolás*
    - **Munkaosztály azonosítója:** *Minőségellenőrzés*

        Válassza ki a [Munkaosztály](#work-class) nevét, amelyet korábban létrehozott a minőségellenőrzési munkához.

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

A Munkasablonokkal kapcsolatos további információkat lásd: [A raktári munka ellenőrzése munkasablonok és helyutasítások használatával](control-warehouse-location-directives.md)

### <a name="location-directive--quality-failures"></a>Helyutasítás – Minőségi hibák

A helyutasítások olyan szabályok, amik segítik a kitárolási és betárolási helyek meghatározását, készletmozgatás esetében. Például egy értékesítési rendelés tranzakciójába a helyutasítás azt határozza meg, ahol a cikkek kivétele történik, és ha a kitárolt cikkek kerülnek. Meg kell adnia egy helyutasítást, amely meghatározza, hogy hogyan kezelje a program a sikertelen minőségellenőrzéseket.

1. Ugrás a **Raktárkezelés \> Beállítás \> Helyutasítások** elemre.
1. A bal oldali ablaktáblában a **Munkarendelés típusa** mezőt állítsa *Beszerzési rendelések* értékre, hogy az adott típusú helyutasításokkal együttműködjön.
1. A művelet ablaktáblán válassza az **Új** parancsot a minőségellenőrzéshez használandó új helyutasítás létrehozásához.
1. A fejlécben állítsa be a következő értékeket:

    - **Sorszám:** Fogadja el az alapértelmezett értéket.
    - **Név:** *51 Minőséghez*

1. A **Helyutasítások** gyorslapon állítsa be a következő értékeket. Az fennmaradó mezőkben hagyja meg az alapértelmezett értékeket.

    - **Munka típusa:** *Eltárolás*
    - **Telephely:** *5*
    - **Raktár:** *51*

1. A Műveleti ablaktáblán a **Mentés** gombra kattintva mentheti az utasítást, és elérhetővé válik a **Sorok** gyorslap.
1. A **Sorok** gyorslapon válassza az **Új** parancsot, ha egy sort szeretne hozzáadni a rácshoz.
1. Az új sorban állítsa be a következő értékeket. Az fennmaradó mezőkben hagyja meg az alapértelmezett értékeket.

    - **Kezdő mennyiség:** *1*
    - **Záró mennyiség:** *1000000*

1. A Műveleti ablaktáblán a **Mentés** gombra kattintva mentheti az új sort, és elérhetővé válik a **Helyutasítás műveletei** gyorslap.
1. Ha az új sor továbbra is be ki van választva a **Sorok** gyorslapon, akkor a **Helyutasítás műveletei** gyorslap **Új** elemét kiválasztva egy sort adhat a rácshoz, így beállíthat egy műveletet a sorhoz.
1. Az új sorban állítsa a **Név** mezőt a *Minőség* értékre. Az fennmaradó mezőkben hagyja meg az alapértelmezett értékeket.
1. A Műveleti ablaktáblán a **Mentés** gombra kattintva teheti elérhetővé a **Lekérdezés szerkesztése** gombot a **Helyutasítás műveletei** gyorslapon.
1. Amíg az imént hozzáadott sor továbbra is ki van jelölve a **Helyutasítás műveletei** gyorslapon, válassza a **Lekérdezés szerkesztése** gombot, hogy megnyíljon egy párbeszédpanel, amelyen szerkesztheti a művelet lekérdezését.
1. A **tartomány** lapon válassza a **Hozzáadás** lehetőséget sor hozzáadásához a lekérdezéshez.
1. Az új sorban állítsa be a következő értékeket:

    - **Tábla:** *Helyek*
    - **Származtatott tábla:** *Helyek*
    - **Mező:** *Hely*
    - **Feltételek:** *QMS*

    A *QMS* hely a minőséghez használandó raktári hely.

1. Az **OK** gombbal zárja be a párbeszédpanelt.
1. EKkor módosítania kell a beszerzési rendelés helyutasításokat az *51*-es raktárhoz. Mentse az új *51 Minőséghez* helyutasítást, frissítse a lapot, majd válassza ki a helyutasítást a listából. Ezután a Műveleti ablaktáblán lévő **Feljebb** és **Lejjebb** gombokkal helyezze át a helyutasítást az *51*-es raktárhoz a következő sorrendben. (Mielőtt kiválasztja a **Feljebb** vagy **Lejjebb** gombot, ki kell választania egy helyutasítást a listából.)

    1. 51 Minőséghez
    2. 51 közvetlen beszerzési rendelés
    3. 51 QMS

### <a name="mobile-device-menu-items"></a>Mobileszköz menüpontjai

A menüelemet úgy konfigurálhatja, hogy a mobileszköz végre tudja hajtani a **Minőségellenőrzés** funkciót.

#### <a name="purchase-putaway"></a>Beszerzés betárolása

1. Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz-menüelemek** részre.
1. Válassza ki a listából a **Beszerzés eltárolása** menüelemet.
1. A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.
1. A **Munkaosztályok** szakaszban válassza az **Új** parancsot, ha egy sort szeretne hozzáadni a rácshoz.
1. Az új sorban állítsa be a következő értékeket:

    - **Munkaosztály azonosítója:** *Minőségellenőrzés*

        Adja meg a [Munkaosztály](#work-class) nevét, amelyet korábban létrehozott a minőségellenőrzési munkához.

    - **Munkarendelés típusa:** *Minőség a minőségellenőrzésben*

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

#### <a name="purchase-order-line-receiving"></a>Beszerzésirendelés-sor bevételezése

1. Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz-menüelemek** részre.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. A fejlécben állítsa be a következő értékeket:

    - **Menüelem neve:** *Beszerzési rendelési sor bevételezése*
    - **Cím:** *Beszerzési rendelési sor bevételezése*
    - **Mód:** *Munka*
    - **Meglévő munka használata:** *Nem*

1. Az **Általános** gyorslapon állítsa be a következő értékeket. Az fennmaradó mezőkben hagyja meg az alapértelmezett értékeket.

    - **Munkalétrehozási folyamat:** *Beszerzési rendelési sor bevételezése és eltárolása*
    - **Azonosítótábla létrehozása:** *Igen*
    - **Munkasablon:** *51 Igénylés, beszerzési rendelés*

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

#### <a name="add-the-menu-item-to-a-mobile-device-menu"></a>A menüelem hozzáadása a mobileszköz menühöz

1. Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz menü** elemre.
1. A bal oldali ablaktáblán válassza a **Bejövő** menüt.
1. A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.
1. A **Rendelkezésre álló menük és menüelemek** oszlopban keresse meg és válassza ki az új **Beszerzési rendelési sor bevételezése** menüelemet.
1. Válassza a jobbra mutató nyilat a **Beszerzési rendelési sor bevételezése** áthelyezéséhez a **Menü struktúrája** oszlopba.
1. A **Menü szerkezete** oszlopban válassza ki a **Beszerzési rendelési sor bevételezése** lehetőséget, majd a feljebb vagy lejjebb nyílra kattintva helyezze át a menüelemet a mobileszköz menüjének kívánt pontjára.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

## <a name="example-scenario"></a><a name="example-scenario"></a>Példaforgatókönyv

Miután elvégezte az összes korábban leírt mintaadatok elérhetővé tételét és beállítását, a forgatókönyvön keresztül kipróbálhatja a *Minőségellenőrzés* funkciót. Az ebben a forgatókönyvben látható értékek feltételezik, hogy azokkal a szokásos bemutatóadatokkal dolgozik, amelyeket az **USMF** jogi személyt kiválasztott, és hogy előkészítette a témakör korábbi részében ismertetett mintarekordokat. Ez a forgatókönyv példaként is szolgál, amely megmutatja, hogyan használható a funkció az üzemelési beállításban.

### <a name="create-a-purchase-order"></a>Beszerzési rendelés létrehozása

1. Menjen a **Beszerzés és forrás \> Beszerzési rendelés \> Összes beszerzési rendelés** pontra.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. Az **Beszerzési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:

    - **Szállítói számla:** *104*
    - **Raktár:** *51*

1. Válassza az **OK** gombot a párbeszédpanel bezárásához, és egy új beszerzési rendelés megnyitásához.
1. A **Beszerzési rendelés sorai** gyorslapon a rács egy új, üres sort tartalmaz. Ezen a soron állítsa be a következő értékeket:

    - **Cikkszám:** *M9203*
    - **Mennyiség:** *3*
    - **Egység:** *PL*

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

### <a name="process-quality-check-receiving"></a>Folyamat minőségellenőrzési bevételezése

A beszerzési rendelés létrehozása után a program a **Beszerzési rendelési sor bevételezése** menüelem és a *Minőségellenőrzés* funkció használatával szerezheti be.

#### <a name="receive-pallet-1"></a>1. raklap fogadása

1. Jelentkezzen be az *51*-es raktár felhasználójaként a raktár alkalmazásba. (Írja be a felhasználói azonosítóhoz a *51*-et, a jelszóhoz pedig az *1*-et.)
1. Menjen a **Bejövő \> Beszerzési rendelési sor bevételezése** lehetőségre.
1. A **PONUM** mezőbe adja meg a beszerzési rendelés számát.
1. Erősítse meg újra a beszerzési rendelés számát.
1. A **LINENUM** mezőbe adja meg a bevételezett beszerzési rendelés sorszámát. Mivel a rendelésnek ebben a forgatókönyvben csak egy sora van, ezért a **LINENUM** mezőbe az *1*-es értéket kell beírnia mindegyik bevételezési lépésnél.
1. A sor számának megerősítése.
1. A **Mennyiség** mezőbe írja be a bevételezett mennyiséget. Mivel ebben a forgatókönyvben a beszerzési rendelés három raklapra (*PL*) szól, és három bevételezési lépés van, ezért az *1*-es értéket kell megadnia a **MENNYISÉG** mezőben minden egyes bevételezési lépésnél.
1. Nyugtázza a mennyiséget.

    A megjelenő **Minőségellenőrzés** lap nem tartalmaz bejegyzési mezőket. Csak a megerősítés (pipa) gombot alul, és a Menü gombot (**≡**) felül. (A Menü gombot néha hamburgernek vagy a hamburger gombnak is nevezik.) A minőségellenőrzési folyamat meggyorsításához – amikor a raklap átmegy a minőségellenőrzésen – a felhasználónak csak meg kell erősítenie a **Minőségellenőrzés** lapot.

    ![Minőségellenőrzés lap](media/quality-check.png "Minőségellenőrzés lap")

1. Válassza ki a megerősítés gombot, ha az 1. sorban lévő 1. raklap átment a minőségellenőrzésen.

    A megjelenő **Beszerzési rendelések: Eltárolás** lap az eltárolási munka részleteit jeleníti meg:

    - **LOC:** A rendszer által meghatározott hely

        Ez a hely a beszerzési rendelés bevételezéséhez megadott eltárolási hely.

    - **LP:** A rendszer által létrehozott azonosítótábla azonosítója
    - **Cikk:** *M9203*
    - **Mennyiség:** *1 PL: 100 ea*

    A cíkk leírása is itt látható.

1. Erősítse meg a betárolási munkát.

    A beszerzési rendeléssor **Feladat** lapján a „Munka befejezve” üzenet jelenik meg. A **LINENUM** mező elérhető, úgyhogy fogadhatja a következő raklapot.

#### <a name="receive-pallet-2"></a>2. raklap fogadása

Ennél a forgatókönyvnél a 2. raklapot el fogja utasítani a program.

1. A **LINENUM** mezőbe írja be az *1* értéket , majd erősítse meg a sor számát.
1. A **MENNYISÉG** mező mostantól elérhető. Adja meg az *1* értéket, majd erősítse meg a mennyiséget.

    Megjelenik a **Minőségellenőrzés** oldal. Ezen nyugta esetében a raklapot elutasítja a program a minősége miatt, és a *QMS* minőséghelyre kerül.

1. Válassza ki a lap tetején látható Menü gombot (**≡**), majd válassza az **Elutasítás** lehetőséget a menüben.
1. A megjelenő **Feladat** oldalon adja meg a **QMS** éréket, mint *Betárolási* helyet, hogy a raklapot elküldhesse további ellenőrzésre.

    A megjelenő **Minőség a minőségellenőrzésben: Eltárolás** lap az eltárolási munka részleteit jeleníti meg:

    - **LOC:** *QMS*

        Ez a hely az elutasított minőség bevételezéséhez megadott eltárolási hely.

    - **LP:** A rendszer által létrehozott azonosítótábla azonosítója
    - **Cikk:** *M9203*
    - **Mennyiség:** *1 PL: 100 ea*

    A cíkk leírása is itt látható.

1. Erősítse meg a betárolási munkát.

    A beszerzési rendeléssor **Feladat** lapján a „Munka befejezve” üzenet jelenik meg. A **LINENUM** mező elérhető, úgyhogy fogadhatja a következő raklapot.

Ezennel befejezte a minőségellenőrzést, és létrehozta a minőségi rendelést az elutasított raklaphoz. Ha meg szeretné tekinteni a létrehozott minőségi rendelést, menjen a **Készletkezelés \> Időszakos feladatok \> Minőségkezelés \> Minőségi rendelések** elemre.

A minőségi rendelés tesztelése most már feldolgozható. Ebben a témakörben nem szerepel minőségi tesztelés.

A minőségkezeléssel kapcsolatos további tudnivalókat lásd: [Minőségkezelés áttekintése](../inventory/enable-quality-management.md)

#### <a name="receive-pallet-3"></a>3. raklap fogadása

Ennél a forgatókönyvnél a 3. raklapot el fogja fogadni a program.

1. A **LINENUM** mezőbe írja be az *1* értéket , majd erősítse meg a sor számát.
1. A **MENNYISÉG** mező mostantól elérhető. Adja meg az *1* értéket, majd erősítse meg a mennyiséget.

    Megjelenik a **Minőségellenőrzés** oldal. Ezen nyugta esetében a raklapot el fogja fogadni a program a minősége miatt, és egy ömlesztett eltárolási helyre kerül.

1. Válassza ki a megerősítés gombot, ha átment a minőségellenőrzésen.

    A megjelenő **Beszerzési rendelések: Eltárolás** lap az eltárolási munka részleteit jeleníti meg:

    - **LOC:** A rendszer által meghatározott hely

        Ez a hely a beszerzési rendelés bevételezéséhez megadott eltárolási hely.

    - **LP:** A rendszer által létrehozott azonosítótábla azonosítója
    - **Cikk:** *M9203*
    - **Mennyiség:** *1 PL: 100 ea*

    A cíkk leírása is itt látható.

1. Erősítse meg a betárolási munkát.

    A beszerzési rendeléssor **Feladat** lapján a „Munka befejezve” üzenet jelenik meg. A **LINENUM** mező elérhető, úgyhogy fogadhatja a következő raklapot.

1. Válassza ki a lap tetején látható Menü gombot (**≡**), majd válassza a **Mégsem** lehetőséget a menühöz való visszatéréshez.

Most már bezárhatja a mobilalkalmazást.
