---
title: Modulok használata
description: Ez a témakör azt mutatja be, hogyan és mikor lehet a modulokat a Microsoft Dynamics 365 Commerce rendszerben használni.
author: v-chgri
manager: annbe
ms.date: 01/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: phinneyridge
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 769d6754fa944830b989d657e0dad9cc42212932
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025879"
---
# <a name="work-with-modules"></a>Modulok használata

Ez a témakör azt mutatja be, hogyan és mikor lehet a modulokat a Microsoft Dynamics 365 Commerce rendszerben használni.


[!include [banner](includes/banner.md)]

## <a name="overview"></a>Áttekintés

A modulok olyan logikai építőelemek, amelyek megalkotják a lap struktúráját, és különböző céljaik és hatóköreik vannak. Egyes modulok magas szintű tárolók, és egyetlen céljuk a többi modul (származtatott modulok) megtartása és rendszerezése. A többi modul – például egy egyszerű képelhelyezési modul – kifejezetten konkrét célt szolgál. Más modulok, például a körhinta-modul, valahová a két kategória közé esnek.

Alapértelmezés szerint a Dynamics 365 Commerce webhely tartalmaz egy kezdőszett modul könyvtárat, amely lehetővé teszi a legalapvetőbb e-kereskedelmi forgatókönyvek megvalósítását. Kizárólag ezen modulok használatával is létrehozhat egy teljes körű e-kereskedelmi weboldalt. Előfordulhat azonban, hogy testre szeretné szabni ezeket a modulokat, vagy új egyéni modulokat szeretne létrehozni adott igényekhez. Egyéni modulok készítéséhez egy modultervező szoftverfejlesztői készlet (SDK) érhető el, amely segítséget nyújt az egyéni modulkönyvtár létrehozásában.

## <a name="container-modules-and-slots"></a>Tárolómodulok és helyek

Ahogy korábban már említettük, néhány modul a származtatott modulok tárolásához van kialakítva. Ezek a modulok *konténerként*ismertek, és lehetővé teszik a beágyazott modulok hierarchiájának létrehozását. Tárolómodulok *helyeket* tartalmaznak. A helyek a származtatott modulok elrendezésének és céljának kezelésére szolgálnak a tárolóban. Egy példa egy egyszerű laptároló modul (bármely lap felső szintű modulja), amely több fontos helyet határoz meg:

- Fejléc hely
- Egy törzsszöveg hely
- Egy lábléc hely

A modul fejlesztői ezeket a helyeket definiálják, és meghatározzák, hogy mely származtatott modulokat és hány származtatott modult lehet közvetlenül benne elhelyezni. Például a fejléc hely csak a **Fejlécmodul** típusú modult támogat, míg a törzs helyek korlátlan számú modult támogatnak (kivéve más oldaltároló modulokat).

A szerkesztőeszközökben a lap szerzőjének nem kell előzetesen tudnia, hogy mely modulok helyezhetők el és nem helyezhetők el az egyes helyekre. Amikor az oldalszerzők egy helyet kijelölnek majd megpróbálnak kiválasztani egy modult, akkor az adott helyhez tartozó modulok szűrt listáját látják.

## <a name="content-modules"></a>Tartalommodulok

A tartalmi modulok tartalmazzák a tartalmakat és a multimédiás elemeket, például a szöveget (például a fejléceket, a bekezdéseket és a hivatkozásokat) vagy az eszközhivatkozásokat (például képek, videók és PDF-állományok). A tipikus tartalmi modul típusokra példa a **Hős** ,a **Szolgáltatás** és **Szalagcím**. Ezeknek a három típusnak a moduljai tartalmazhatnak szöveget vagy médiát, és nem igényelnek származtatott modulokat ahhoz, hogy láthatóvá tegyenek valamit egy oldalon.

Az általános, gyakran használt oldal- és tartalomszerkesztési tevékenységek többsége tartalmi modulokat tartalmaz elsősorban, mivel ezek a modulok határozzák meg a szülő tároló moduljukban megjelenített tényleges tartalmat. Számos tartalmi modul érhető el, és ezek a modulok általában az utolsó darabok, amelyeket hozzáad az oldal beágyazott modulokból álló hierarchiájához.

A következő ábra bemutatja, hogyan vannak a modulok a szülő tároló helyeire beágyazva.

![Modulok beágyazása](../commerce/media/basic-module-nesting.png)

## <a name="add-or-remove-modules"></a>Modulok hozzáadása vagy eltávolítása

A következő eljárások leírják a modulok hozzáadását és eltávolítását.

### <a name="add-a-module"></a>Modul hozzáadása

A következő lépésekkel lehet hozzáadni egy modult egy helyhez vagy tárolóhoz egy lapon.

1. A bal oldali vázlat ablaktáblán válassza ki azt a tárolóhelyet vagy bővítőhelyet, amelyhez hozzá szeretné adni a származtatott modult.

    > [!NOTE]
    > A modultervező meghatározza azoknak a moduloknak a listáját, amelyek hozzáadhatók egy adott modulbővítőhelyhez. A sablon szerzője ezt követően finomíthatja az engedélyezett modul beállításait, így garantálva a következetes keresőmotor-optimalizálást (SEO) és szerkesztés hatékonyságát az összes olyan oldalhoz, amelyeket egy adott sablonból építettek fel.

1. Válassza ki a modulhoz tartozó három pont gombot (**…**), majd válassza a **Modul hozzáadása** elemet. Megjelenik a **Modul hozzáadása** párbeszédpanel. Ezt a párbeszédpanelt a program automatikusan szűri, így csak a kiválasztott tárolóban vagy bővítőhelyen támogatott modulokat jeleníti meg. A modulok listáját a lap sablonja vagy a tárolómodul definíciója határozza meg.

    > [!NOTE]
    > Ha egy tároló vagy egy bővítőhely nem támogatja az új származtatott modulokat, akkor a **Modul hozzáadása** lehetőség nem érhető el.

1. A párbeszédpanelen keressen meg. és válasszon ki egy modult, hogy hozzáadja az oldalhoz.

    > [!TIP]
    > A **Szolgáltatás** és a **Hős** jó modulok kezdők számára.

1. Az **OK** gombra kattintva adja hozzá a kijelölt modult a kiválasztott tárolóhoz vagy helyhez a lapon.

### <a name="remove-a-module"></a>Modul eltávolítása

A következő lépésekkel lehet eltávolítani egy modult egy helyről vagy tárolóból az oldalon.

1. A bal oldali vázlat ablaktáblán válassza az eltávolítani kívánt modul neve melletti három pont gombot, majd válassza a kuka gombját.
1. Amikor a program megkérdezi, hogy szeretné-e eltávolítani a modult, válassza az **OK** lehetőséget.

## <a name="configure-modules"></a>Modulok konfigurálása

A következő eljárások leírják a tartalom- és tárolómodulok konfigurálását.

### <a name="configure-a-content-module"></a>Tartalommodul konfigurálása

Egy tartalommodulnak egy lapon történő konfigurálásához kövesse az alábbi lépéseket.

1. A bal oldali vázlat ablaktáblán bontsa ki a fastruktúrát, és válasszon ki egy bármilyen tartalommodult (például **Funkció**, **Hős** vagy **Szalagcím**).
1. A jobb oldali Tulajdonságok ablaktáblában keresse meg a modul tartalmi és beállítási vezérlőit.
1. Adja meg a kívánt modul-vezérlőelemek tulajdonságait.
1. A parancssávon válassza a **Mentés** elemet. Ennek hatására az előnézeti vászon is frissül.

### <a name="configure-a-container-module"></a>Tárolómodul konfigurálása

Egy tárolómodulnak egy lapon történő konfigurálásához kövesse az alábbi lépéseket.

1. Válasszon ki egy konténermodult az oldalon (például körhinta vagy folyékony tárolómodult).
1. A jobb oldali tulajdonságok ablaktáblán bontsa ki a beágyazott vezérlőket a fejlécek kiválasztásával, és adja meg a szükséges vezérlő értékeket.
1. A bal oldali vázlat ablaktáblán válassza az eltávolítani tároló vagy a tároló bármelyik helye neve melletti három pont gombot, majd válassza ki a **Modul hozzáadása** lehetőséget. Ezután adja hozzá a származtatott modulokat a kiválasztott tárolóhoz. A további tudnivalókat lásd: [Modulok használata](#add-a-module) rész a témakör korábbi részében.
1. Ha több származtatott modul van egy szülő tárolóban, akkor a szülő tárolóban módosítható a megjelenítési sorrendjük. Jelölje ki az egyik modulhoz tartozó három pont gombot, majd a fel és a le nyílbillentyűket.

## <a name="additional-resources"></a>További erőforrások

[Sablonok és elrendezések áttekintése](templates-layouts-overview.md)

[Sablonok használata](work-with-templates.md)

[Előre beállított elrendezések használata](work-with-layouts.md)

[Töredékek használata](work-with-fragments.md)

[Tárolómodul hozzáadása egy oldalhoz](add-container-module.md)

[A közzétételi csoportokkal végzett munka](publish-groups.md)

