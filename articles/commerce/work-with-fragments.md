---
title: Töredékek használata
description: Ez a témakör ismerteti, hogy miért, mikor és hogyan lehet a cikkrészleteket használni Microsoft Dynamics 365 Commerce.
author: phinneyridge
ms.date: 02/03/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.search.industry: retail
ms.search.form: ''
ms.openlocfilehash: 785e6f847fd1645557060356926f2dda8da22ac1
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268205"
---
# <a name="work-with-fragments"></a>Töredékek használata 

[!include [banner](includes/banner.md)]

Ez a témakör ismerteti, hogy miért, mikor és hogyan lehet a cikkrészleteket használni Microsoft Dynamics 365 Commerce.

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

Ha egy korábban konfigurált modult újra felhasználható töredékké szeretne átalakítani a Commerce webhelykészítőben, hajtsa végre az alábbi lépéseket.

1. Nyisson meg egy olyan lapot vagy sablont, amely a töredékké alakítandó modult tartalmazza.
1. A bal oldali vázlat ablaktáblán vagy közvetlenül a vizuális oldalkészítőben, válassza ki az előzőleg konfigurált modult.
1. Válassza ki a modul neve mellett lévő azt a három pont (**...**) a vázlat ablaktáblán vagy a kiválasztott modul eszköztárában, a vizuális oldalkészítőben. 
1. Válassza ki a **Megosztást töredékként** lehetőséget. 
1. A **Mentés töredékként** párbeszédpanelen adjon nevet a töredéknek.
1. Az **OK** gombra kattintva mentheti a modulkonfigurációt olyan töredékként, amely más lapokhoz is hozzáadható.
<!-- The following image shows how to save a module configuration as a fragment.-->
<!--![A screen capture of how to save a module configuration as a fragment.](./media/save-as-fragment.png)-->

### <a name="create-a-new-fragment"></a>Új töredék létrehozása

A következő lépésekkel hozhat létre új töredéket a Commerce webhelykészítőben.

1. A bal oldali navigációs ablakban válassza ki a **Töredékek** lehetőséget.
1. Válassza az **Új** lehetőséget. Megjelenik az **Új töredék** párbeszédpanel, amelyen az összes elérhető modultípus látható. A korábban említetteknek megfelelően a töredékek bármilyen típusú modulból létrehozhatók.
1. A modul típusának kiválasztása a töredékhez.

<!-- The following image shows where to create a new fragment.-->
<!-- ![A screen capture of where to create a new fragment.](./media/fragment-nav-menu.png)-->
> [!TIP]
> Egy általános tárolómodul-típus kiválasztásával a legrugalmasabban frissítheti és konfigurálhatja a töredéket később.

## <a name="add-remove-or-edit-fragments-on-a-page"></a>Töredékek hozzáadása, eltávolítása vagy szerkesztése egy lapon

A következő eljárások leírják a töredékek hozzáadását, eltávolítását és szerkesztését.

### <a name="add-a-fragment"></a>Töredék hozzáadása

A következő lépésekkel adhat hozzá új töredéket egy oldalhoz a Commerce webhelykészítőben.

1. A bal oldali vázlat ablaktáblán vagy közvetlenül a vizuális oldalkészítőben, válassza ki azt a tárolót vagy helyet, amelyhez hozzá szeretné adni a származtatott modulokat.
1. Válassza ki a tároló vagy a hely neve melletti három pontot (**...**).  Másik lehetőségként, ha a vizuális oldalkészítőt használja, válassza ki a pluszjelet (**+**).  
1. Válassza a **Töredék hozzáadása** lehetőséget.
    <!-- ![A screen capture of how to add an existing fragment to a slot or container.](./media/add-fragment.png)-->
 
    > [!NOTE]
    > Ha a tároló vagy a bővítőhely nem támogatja az új származtatott modulokat, akkor a **Töredék hozzáadása** lehetőség nem érhető el.
    
1. A **Töredék kiválasztása** párbeszédpanelen keressen meg és válasszon ki egy töredéket a hozzáadáshoz. Ha nincs elérhető töredék a listán, először létre kell hozni egy töredéket egy olyan modultípusból, amelyet a kiválasztott tároló vagy bővítőhely támogat.
1. Válassza ki és adja hozzá a kívánt töredéket a tárolóhoz vagy helyhez a lapon.
<!--    ![A screen capture of the fragment picker modal window.](./media/fragment-picker.png)-->

> [!NOTE]
> A tárolókban vagy bővítőhelyekben engedélyezett modulokat a lapsablonja vagy a modulok saját definíciói határozzák meg.

### <a name="remove-a-fragment"></a>Töredék eltávolítása

A Commerce webhelykészítő egy lapján lévő bővítőhelyen vagy tárolóban levő töredék eltávolításához kövesse az alábbi lépéseket.

1. A bal oldali vázlat ablaktáblán válassza az eltávolítani kívánt töredék neve melletti három pontot (**...**), majd válassza a kuka gombját.  Másik lehetőségként kiválaszthatja a töredéket a vizuális oldalkészítőben, és kiválaszthatja a kuka lehetőséget a töredék eszköztárában.
1. Amikor a program megkérdezi, hogy szeretné-e eltávolítani a töredéket, válassza az **OK** lehetőséget.

> [!NOTE]
> Ha eltávolít egy töredéket egy lapról, akkor csak az adott oldalról távolítja el a hivatkozást. **Nem** törli a töredéket az oldalról. Ha törölni szeretne egy töredékeket a webhelyről, akkor a töredékvizsgáló felhasználói felülteét kell használnia. A webhely töredékeit csak akkor törölheti, ha a lapok, sablonok vagy más töredékek jelenleg nem hivatkoznak rájuk.

### <a name="edit-a-fragment"></a>Töredék szerkesztése

A töredékek szerkesztéséhez a töredék-szerkesztő felhasználói felületét kell használnia. Ez korlátozás szándékos. Ez segít szavatolni, hogy a szerzők nem tévesztik össze a modulok szerkesztési folyamatát a több lapon megosztott töredékek szerkesztési folyamatával.

A következő lépésekkel szerkeszthet új töredéket a Commerce webhelykészítőben.

1. A bal oldali navigációs ablakban válassza ki a **Töredékek** lehetőséget.
1. A **Töredékek** alatt válassza ki a szerkeszteni kívánt töredéket.
1. Igény szerint szerkesztheti a töredék moduljának jellemzőit és szerkezetét. A folyamat hasonló a modulok szerkesztési folyamataihoz a lap szerkesztőnézetében.

A töredékeket úgy is szerkesztheti, hogy kijelöli azt egy lapon, egy sablonban vagy egy szülő töredékben, majd a jobb oldali Tulajdonságok ablaktáblában kiválasztja a **Töredék szerkesztése** elemet.

### <a name="rename-a-fragment"></a>Részlet átnevezése

A webhelyszerkesztő egy meglévő részletének átnevezéséhez hajtsa végre a következő lépéseket.

1. A bal oldali navigációs ablakban válassza a Részletek **lehetőséget**.
1. Válassza ki az átnevezni kívánt részlet nevét.
1. A szerkesztés **kiválasztásával** elkezdheti szerkeszteni a részletet. Ne feledje, hogy ha valaki más már szerkeszti a részletet, akkor a részlet nem szerkeszthető.
1. A részlettulajdonságok ablaktáblán válassza ki a részletnév melletti tollszimbólumot.
1. Szükség szerint szerkessze a részletnevet.
1. A névváltozás megerősítéséhez jelölje be ezt a jelölőnégyzetet.
1. Válassza a **Szerkesztés befejezése** lehetőséget.

Létrehozás után átnevezhet egy részletet, ha szerkeszti, majd a tulajdonságablakban kiválasztja a részlet neve melletti toll szimbólumot.

## <a name="additional-resources"></a>További erőforrások

[Sablonok és elrendezések áttekintése](templates-layouts-overview.md)

[Sablonok használata](work-with-templates.md)

[Előre beállított elrendezések használata](work-with-layouts.md)

[A közzétételi csoportokkal végzett munka](publish-groups.md)

[Verzióelőzmények megtekintése az oldalak és részletek visszaállításhoz](version-history-revert.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
