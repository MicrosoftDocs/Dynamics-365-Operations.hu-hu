---
title: Töredékek használata
description: Ez a témakör azt mutatja be, miért, hogyan és mikor lehet a töredékeket a Microsoft Dynamics 365 Commerce rendszerben használni.
author: phinneyridge
manager: annbe
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: retail
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 671caf1feeb7ac9e7d5a166c5de12540ab9b9792
ms.sourcegitcommit: 97ceb24f191161ca601e0889a539df665834ac3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/16/2020
ms.locfileid: "3818350"
---
# <a name="work-with-fragments"></a>Töredékek használata 

[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, miért, hogyan és mikor lehet a töredékeket a Microsoft Dynamics 365 Commerce rendszerben használni.

## <a name="overview"></a>Áttekintés

A töredékek lehetővé teszik a modul-konfigurációk központosított szerkesztési élményének létrehozásár, amelyet a webhely minden területén újra fel lehet használni. Például a fejléceket, élőlábakat és szalagcímeket gyakran töredékként konfigurálják, mivel több oldal megosztva használja azokat. A töredékeket úgy képzelje el, mint kicsiny weboldalakat, amelyek a webhely egyéb oldalaiba illeszthetők be. A töredékek saját életciklussal rendelkeznek. Más szóval a létrehozásuk, hivatkozásuk, frissítése és törlése független entitásként történik a szerkesztőeszközökben.

A töredékek konfigurálását követően azok használhatók, ahol modulok használhatók a weboldal struktúrájában. A töredékekre a lapokon, az elrendezésekben, a sablonokban és más töredékekben is hivatkozni lehet.

> [!NOTE]
> A töredékek a többi töredéken belül legfeljebb hét szint mélyen ágyazhatók be.

Például, ha szeretné népszerűsíteni egy szezonális eseményt több oldalon a honlapon, akkor egy töredéket is használhat. Az új töredékek létrehozási folyamatának első lépése a kiinduló modul típusának kiválasztása. Ebben a példában egy hős modulból hozhat létre egy töredéket.

> [!NOTE]
> A töredékeket bármilyen típusú modulból fel lehet építeni.

Ezt követően a hős töredéket konfigurálhatja az adott promóciós tartalommal. Igény szerint lokalizálhatja is azt. Ezt követően az új, önálló hős töredéket egy előre konfigurált modulként lehet használni a webhelyen. Egyszerűen hozzáadhatja azt sablonokhoz meghatározott oldalakhoz illetve a hero modulokat tartalmazó más töredékekhez.

Minden olyan hely, ahová a töredéket hozzáadták, a létrehozott központi hős-töredékre hivatkozik. Ha a töredékekhez módosításokat tesz közzé, akkor ezek a módosítások azonnal megjelennek az összes olyan helyen, ahol a töredékre hivatkoznak a webhelyen. Ennek megfelelően a töredékek hatékony módszert biztosítanak a webhely modul-konfigurációinak újrahasznosításához és központi kezeléséhez. A hatékony használat révén jelentősen növelheti az agilitást, és csökkentheti a webhely tartalomkezelésének költségeit.

A következő ábra bemutatja, hogy hogyan használhatók a töredékek a megosztott modul-konfigurációk létrehozásához egy e-kereskedelmi webhely szintjén.

![Egy ábra bemutatja, hogy hogyan használhatók a töredékek a megosztott modul-konfigurációk létrehozásához egy e-kereskedelmi webhely szintjén.](./media/fragment-figure1.png)

## <a name="create-a-fragment"></a>Töredék létrehozása

Létrehozhat új töredéket hozhat, illetve egy meglévő modul konfigurációját mentheti töredékként.

### <a name="save-an-existing-module-configuration-as-a-fragment"></a>Meglévő modulkonfiguráció mentése töredékként

Ha egy korábban konfigurált modult újra felhasználható töredékké szeretne átalakítani, hajtsa végre az alábbi lépéseket.

1. Nyisson meg egy olyan lapot vagy sablont, amely a töredékké alakítandó modult tartalmazza.
1. A bal oldali vázlat ablaktáblán vagy közvetlenül a fő vásznon, válassza ki az előzőleg konfigurált modult.
1. Válassza ki a modul neve mellett lévő azt a három pont (**...**) a vázlat ablaktáblán vagy a kiválasztott modul eszköztárában található vásznon. 
1. Válassza ki a **Megosztás oldaltöredékként** lehetőséget. 
1. A **Mentés oldaltöredékként** párbeszédpanelen adjon nevet a töredéknek.
1. Az **OK** gombra kattintva mentheti a modulkonfigurációt olyan töredékként, amely más lapokhoz is hozzáadható.

A következő kép azt ábrázolja, hogyan kell menteni a modulok konfigurációját töredékként.

![A modulok konfigurációjának töredékként való mentésének képernyőfelvétele](./media/save-as-fragment.png)

### <a name="create-a-new-fragment"></a>Új töredék létrehozása

Új töredék létrehozásához kövesse az alábbi lépéseket.

1. A bal oldali navigációs ablakban válassza ki a **Töredékek** lehetőséget.
1. Válassza az **Új oldaltöredék** lehetőséget. Megjelenik egy párbeszédpanel, amelyen az összes elérhető modultípus látható. A korábban említetteknek megfelelően a töredékek bármilyen típusú modulból létrehozhatók.
1. A modul típusának kiválasztása a töredékhez.

A következő kép bemutatja, hogy hol hozzon létre új töredéket.

![Új töredék létrehozási helyének képernyőfelvétele](./media/fragment-nav-menu.png)

> [!TIP]
> Egy általános tárolómodul-típus kiválasztásával a legrugalmasabban frissítheti és konfigurálhatja a töredéket később.

## <a name="add-remove-or-edit-fragments-on-a-page"></a>Töredékek hozzáadása, eltávolítása vagy szerkesztése egy lapon

A következő eljárások leírják a töredékek hozzáadását, eltávolítását és szerkesztését.

### <a name="add-a-fragment"></a>Töredék hozzáadása

Töredék hozzáadásához a oldalhoz tegye a következőket:

1. A bal oldali vázlat ablaktáblán vagy közvetlenül a fő vásznon, válassza ki azt a tárolót vagy helyet, amelyhez hozzá szeretné adni a származtatott modulokat.
1. Az online ablaktáblán válassza ki a tároló vagy a hely neve melletti három pontot (**...**).  Másik lehetőségként, ha a fő vásznat használja, válassza ki a plusz jelet (**+**).  
1. Válassza a **Töredék hozzáadása** lehetőséget.

    ![A meglévő töredékek bővítőhelyhez vagy konténerhez történő hozzáadásának képernyőfelvétele](./media/add-fragment.png)
 
    > [!NOTE]
    > Ha a tároló vagy a bővítőhely nem támogatja az új származtatott modulokat, akkor a **Töredék hozzáadása** lehetőség nem érhető el.
    
1. A **Töredék hozzáadása** párbeszédpanelen keressen meg és válasszon ki egy töredéket, hogy hozzáadja. Ha nincs elérhető töredék a listán, először létre kell hozni egy töredéket egy olyan modultípusból, amelyet a kiválasztott tároló vagy bővítőhely támogat.
1. Válassza ki és adja hozzá a kívánt töredéket a tárolóhoz vagy helyhez a lapon.

    ![A töredékkiválasztó modális ablak képernyőfelvétele](./media/fragment-picker.png)

> [!NOTE]
> A tárolókban vagy bővítőhelyekben engedélyezett modulokat a lapsablonja vagy a modulok saját definíciói határozzák meg.

### <a name="remove-a-fragment"></a>Töredék eltávolítása

A következő lépésekkel lehet eltávolítani egy töredéket egy helyről vagy tárolóból az oldalon.

1. A bal oldali vázlat ablaktáblán válassza az eltávolítani kívánt töredék neve melletti három pontot (**...**), majd válassza a kuka gombját.  Másik lehetőségként kiválaszthatja a töredéket a vásznon, és kiválaszthatja a kuka lehetőséget a töredék eszköztárában.
1. Amikor a program megkérdezi, hogy szeretné-e eltávolítani a töredéket, válassza az **OK** lehetőséget.

> [!NOTE]
> Ha eltávolít egy töredéket egy lapról, akkor csak az adott oldalról távolítja el a hivatkozást. **Nem** törli a töredéket az oldalról. Ha törölni szeretne egy töredékeket a webhelyről, akkor a töredékvizsgáló felhasználói felülteét kell használnia. A webhely töredékeit csak akkor törölheti, ha a lapok, sablonok vagy más töredékek jelenleg nem hivatkoznak rájuk.

### <a name="edit-a-fragment"></a>Töredék szerkesztése

A töredékek szerkesztéséhez a töredék-szerkesztő felhasználói felületét kell használnia. Ez korlátozás szándékos. Ez segít szavatolni, hogy a szerzők nem tévesztik össze a modulok szerkesztési folyamatát a több lapon megosztott töredékek szerkesztési folyamatával.

Egy töredék szerkesztéséhez kövesse az alábbi lépéseket.

1. A bal oldali navigációs ablakban válassza ki a **Töredékek** lehetőséget.
1. A **Töredékek** alatt válassza ki a szerkeszteni kívánt töredéket.
1. Igény szerint szerkesztheti a töredék moduljának jellemzőit és szerkezetét. A folyamat hasonló a modulok szerkesztési folyamataihoz a lap szerkesztőnézetében.

A töredékeket úgy is szerkesztheti, hogy kijelöli azt egy lapon, egy sablonban vagy egy szülő töredékben, majd a jobb oldali Tulajdonságok ablaktáblában kiválasztja a **Töredék szerkesztése** elemet.

## <a name="additional-resources"></a>További erőforrások

[Sablonok és elrendezések áttekintése](templates-layouts-overview.md)

[Sablonok használata](work-with-templates.md)

[Előre beállított elrendezések használata](work-with-layouts.md)

[A közzétételi csoportokkal végzett munka](publish-groups.md)
