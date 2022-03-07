---
title: Modulok használata
description: Ez a témakör azt mutatja be, hogyan és mikor lehet a modulokat a Microsoft Dynamics 365 Commerce rendszerben használni.
author: phinneyridge
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: ce16aa98a37cd5dec60bcdbf86f59f74810da9755a6d3514bdd3e38a21afb748
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6728264"
---
# <a name="work-with-modules"></a>Modulok használata

[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan és mikor lehet a modulokat a Microsoft Dynamics 365 Commerce rendszerben használni.

A modulok olyan logikai építőelemek, amelyek megalkotják a lap struktúráját, és különböző céljaik és hatóköreik vannak. Egyes modulok magas szintű tárolók, és egyetlen céljuk a többi modul (származtatott modulok) megtartása és rendszerezése. A többi modul – például egy egyszerű képelhelyezési modul – kifejezetten konkrét célt szolgál. Más modulok, például a körhinta-modul, valahová a két kategória közé esnek.

Alapértelmezés szerint a Dynamics 365 Commerce webhely tartalmaz egy modulkönyvtárat, amely lehetővé teszi a legalapvetőbb e-kereskedelmi forgatókönyvek megvalósítását. Kizárólag ezen modulok használatával is létrehozhat egy teljes körű e-kereskedelmi weboldalt. Előfordulhat azonban, hogy testre szeretné szabni ezeket a modulokat, vagy új egyéni modulokat szeretne létrehozni adott igényekhez. Egyéni modulok készítéséhez egy modultervező szoftverfejlesztői készlet (SDK) érhető el, amely segítséget nyújt az egyéni modulkönyvtár létrehozásában.

## <a name="container-modules-and-slots"></a>Tárolómodulok és helyek

Ahogy korábban már említettük, néhány modul a származtatott modulok tárolásához van kialakítva. Ezek a modulok *konténerként* ismertek, és lehetővé teszik a beágyazott modulok hierarchiájának létrehozását. Tárolómodulok *helyeket* tartalmaznak. A helyek a származtatott modulok elrendezésének és céljának kezelésére szolgálnak a tárolóban. Egy példa egy egyszerű laptároló modul (bármely lap felső szintű modulja), amely több fontos helyet határoz meg:

- Fejléc hely
- Alfejléc hely
- Fő hely
- Egy lábléc hely
- Allábléc hely

A modul fejlesztői ezeket a helyeket definiálják, és meghatározzák, hogy mely származtatott modulokat és hány származtatott modult lehet közvetlenül benne elhelyezni. Például a fejléc hely csak a **Fejlécmodul** típusú modult támogat, míg a törzs helyek korlátlan számú modult támogatnak (kivéve más oldaltároló modulokat).

A szerkesztőeszközökben a lap szerzőjének nem kell előzetesen tudnia, hogy mely modulok helyezhetők el és nem helyezhetők el az egyes helyekre. Amikor az oldalszerzők egy helyet kijelölnek majd megpróbálnak kiválasztani egy modult, akkor az adott helyhez tartozó modulok szűrt listáját látják.

## <a name="content-modules"></a>Tartalommodulok

A tartalmi modulok tartalmazzák a tartalmakat és a multimédiás elemeket, például a szöveget (például a fejléceket, a bekezdéseket és a hivatkozásokat) vagy az eszközhivatkozásokat (például képek, videók és PDF-állományok). A jellemző tartalmi modultípusok közé tartozik a tartalomblokk, a szövegterület és a promó bannermodulok. Ezeknek a három típusnak a moduljai tartalmazhatnak szöveget vagy médiát, és nem igényelnek származtatott modulokat ahhoz, hogy láthatóvá tegyenek valamit egy oldalon.

Az általános, gyakran használt oldal- és tartalomszerkesztési tevékenységek többsége tartalmi modulokat tartalmaz elsősorban, mivel ezek a modulok határozzák meg a szülő tároló moduljukban megjelenített tényleges tartalmat. Számos tartalmi modul érhető el, és ezek a modulok általában az utolsó darabok, amelyeket hozzáad az oldal beágyazott modulokból álló hierarchiájához.

A következő ábra bemutatja, hogyan vannak a modulok a szülő tároló helyeire beágyazva.

![Modulok beágyazása.](../commerce/media/basic-module-nesting.png)

## <a name="add-or-remove-modules"></a>Modulok hozzáadása vagy eltávolítása

A következő eljárások leírják a modulok hozzáadását és eltávolítását.

### <a name="add-a-module"></a>Modul hozzáadása

A következő lépésekkel lehet hozzáadni egy modult egy helyhez vagy tárolóhoz egy lapon.

1. A bal oldali vázlat ablaktáblán vagy közvetlenül a fő vásznon, válassza ki azt a tárolót vagy helyet, amelyhez hozzá szeretné adni az alárendelt modult.

    > [!NOTE]
    > A modultervező meghatározza azoknak a moduloknak a listáját, amelyek hozzáadhatók egy adott modulbővítőhelyhez. A sablon szerzője ezt követően finomíthatja az engedélyezett modul beállításait, így garantálva a következetes keresőmotor-optimalizálást (SEO) és szerkesztés hatékonyságát az összes olyan oldalhoz, amelyeket egy adott sablonból építettek fel. Amikor hozzáad egy modult egy helyhez, a **Modul hozzáadása** párbeszédpanelt a program automatikusan szűri, így csak a kiválasztott tárolóban vagy bővítőhelyen támogatott modulokat jeleníti meg. Az engedélyezett modulok listáját a lap sablonja vagy a tárolómodul definíciója határozza meg.

1. Ha a körvonal ablaktáblát használja, válassza ki a modul neve melletti három pontot (**...**), majd válassza a **Modul hozzáadása** elemet. Ha közvetlenül a vásznon belül használja a vezérlőket, válassza ki a plusz jelet (**+**) egy üres helyen vagy a kiválasztott modul szomszédos helyen, majd válassza ki a **Modul hozzáadása** elemet.

    > [!NOTE]
    > Ha egy tároló vagy egy bővítőhely nem támogatja az új származtatott modulokat, akkor a **Modul hozzáadása** lehetőség nem érhető el.

1. A **Modul hozzáadása** párbeszédpanelen válasszon ki egy modult, hogy hozzáadja az oldalhoz.

    > [!TIP]
    > A **Tartalomblokk** kezdőknek való modultípus.

1. Az **OK** gombra kattintva adja hozzá a kijelölt modult a kiválasztott tárolóhoz vagy helyhez a lapon.

### <a name="remove-a-module"></a>Modul eltávolítása

A következő lépésekkel lehet eltávolítani egy modult egy helyről vagy tárolóból az oldalon.

1. A bal oldali vázlat ablaktáblán válassza az eltávolítani kívánt modul neve melletti három pontot (**...**), majd válassza a kuka gombját. Másik lehetőségként a fő vászonban is kijelölheti a kiválasztott modul eszköztárán lévő kuka szimbólumot.
1. Amikor a program megkérdezi, hogy szeretné-e eltávolítani a modult, válassza az **OK** lehetőséget.

## <a name="move-a-module-to-a-new-position"></a>Modul áthelyezése egy új pozícióba

Ha egy modult át szeretne helyezni egy új pozícióba a lapon belül, akkor használja az alábbi módszerek valamelyikét.

### <a name="move-a-module-using-the-outline-pane"></a>Modul áthelyezése a körvonal ablaktábla használatával

Ha egy modult a körvonal ablaktáblával szeretne áthelyezni, kövesse az alábbi lépéseket.

1. Jelölje ki és tartsa lenyomva az áthelyezni kívánt modult a körvonal ablaktáblán, majd húzza át a modult a körvonalban szereplő új pozícióra. A körvonalon és a vásznon lévő kék sor jelzi, hogy hova helyezheti a modult.
1. A modul kiadása, hogy át lehessen dobni az új pozícióba.

### <a name="move-a-module-directly-within-the-canvas"></a>Modul áthelyezése közvetlenül a vásznon belül

Ha egy modult közvetlenül a vásznon belül szeretne áthelyezni, kövesse az alábbi lépéseket.

1. Válassza ki azt a modult, amelyet át szeretne helyezni a vásznon belül. 
1. Válassza ki a modul eszköztárában a felfelé vagy lefelé mutató nyilat, majd húzza a nyilat a lap új helyére. A vászonban és a körvonalban lévő kék sor jelzi, hogy hova helyezheti a modult. Ha egy modult nem lehet felfelé vagy lefelé mozgatni, akkor a nyíl gomb szürkén jelenik meg. 
1. A modul kiadása, hogy át lehessen dobni az új pozícióba.

### <a name="move-a-module-using-the-ellipsis-menu"></a>Modul áthelyezése a három pont menü használatával

Ha egy modult a három pont menüvel szeretne áthelyezni, kövesse az alábbi lépéseket.

1. Válasszon ki egy modult a körvonalban vagy a vásznon.
1. Válassza ki a modul neve mellett lévő a három pontot (**...**) a körvonal ablaktáblán vagy a modul eszköztárában található vásznon.
1. Ha a modult a tárolóban vagy a helyen belül fel-le mozgathatja, akkor a **Mozgatás felfelé** vagy **Mozgatás lefelé** beállítások láthatók. Válassza ki a kívánt áthelyezési beállítást a modult származtatottjaihoz képest felfelé vagy lefelé mozgatásához.

## <a name="configure-modules"></a>Modulok konfigurálása

A következő eljárások leírják a tartalom- és tárolómodulok konfigurálását.

### <a name="configure-a-content-module"></a>Tartalommodul konfigurálása

Egy tartalommodulnak egy lapon történő konfigurálásához kövesse az alábbi lépéseket.

1. A bal oldali vázlat ablaktáblán bontsa ki a fastruktúrát, és válasszon ki egy bármilyen tartalommodult (például **Tartalomblokk**). Másik lehetőségként válassza ki azt a modult, amelyet át szeretne helyezni a fő vásznon belül.
1. A jobb oldali modul tulajdonságai ablaktáblán írja be a kívánt modulvezérlők tulajdonságait.
1. A parancssávon válassza a **Mentés** elemet. Ennek hatására az előnézeti vászon is frissül.

### <a name="edit-module-text-properties"></a>Modul szövegtulajdonságainak szerkesztése

A nem írásvédett modul szövegtulajdonságait közvetlenül a vásznon belül tudja szerkeszteni.

A modul szövegtulajdonságainak szerkesztéséhez kövesse az alábbi lépéseket.

1. Válassza ki a vásznon a szövegvezérlőt, majd helyezze a mutatót oda, ahol szerkeszteni szeretné a szöveget.
1. Adja meg a szöveges tartalmat.
1. Ha folytatni szeretné az egyéb tartalmak szerkesztését, bökjön a szövegtartalmon kívül bárhová.

### <a name="inline-image-selection"></a>Szövegközi kép kiválasztása

A nem írásvédett modul képeit közvetlenül a vászonból módosíthatja.

Egy új kép tartalommodulhoz való kiválasztásához kövesse az alábbi lépéseket.

1. A vásznon kattintson duplán a képre. Ekkor megjelenik a médiaválasztó ablaka.
1. Keresse meg és válassza ki a használni kívánt új képet, majd kattintson az **OK** gombra. Az új kép ezennel renderelve lett a vászonba.

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



[!INCLUDE[footer-include](../includes/footer-banner.md)]
