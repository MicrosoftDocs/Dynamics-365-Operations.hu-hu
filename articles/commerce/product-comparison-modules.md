---
title: Termék-összehasonlítási modulok
description: Ez a témakör leírja a termék-összehasonlítási Microsoft Dynamics 365 Commerce modulokat, és bemutatja, hogyan lehet azokat megvalósítani, hogy a vevők termék-összehasonlításokat tudjanak végrehajtani az e-commerce webhelyeken.
author: ashishmsft
ms.date: 10/03/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2022-02-28
ms.openlocfilehash: 9ff45f3fbcc86b21f336d580582adef586417de4
ms.sourcegitcommit: 66b954827826706ea2ba00c2afd5d694ad92148d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/03/2022
ms.locfileid: "9618385"
---
# <a name="product-comparison-modules"></a>Termék-összehasonlítási modulok

[!include [banner](../includes/banner.md)]

Ez a témakör leírja a termék-összehasonlítási Microsoft Dynamics 365 Commerce modulokat, és bemutatja, hogyan lehet azokat megvalósítani, hogy a vevők termék-összehasonlításokat tudjanak végrehajtani az e-commerce webhelyeken.

> [!NOTE]
> A termék-összehasonlítási Dynamics 365 Commerce és termék-összehasonlítási gombmodulok a 10.0.29-es verzióban érhetők el. Mind a vállalkozások, mind a vállalkozások között (B2B) webhelyekhez használhatók.

A termék-összehasonlítási funkció segítségével a vásárlók a termék-összehasonlítási oldalon összehasonlítják a termék részleteit, így jobb beszerzési döntéshozásokat hozhatnak. Ezt a funkciót a Commerce Webhelyszerkesztő termék-összehasonlítási modulja konfigurálja. A terméklistaoldalakon (PLP), például a kategóriaeredmények, a keresési eredmények és a termékgyűjtemények lapjain beállíthatja a termék-összehasonlításhoz tartozó gombot, hogy a vásárlók termékeket vegyenek fel az összehasonlítási tálcába. Ezt a funkciót a Webhelyszerkesztő a termék-összehasonlítási gombmodul segítségével konfigurálja, [amely a Gyorsnézet modulhoz hasonló módon működik](quick-view-module.md).

Amikor a webhely felhasználói a terméktermék-beállítások kiválasztásával hozzáadják az összehasonlításhoz a termékeket, a lap alján megjelenik egy összehasonlítási tálca. Az összehasonlítási tálca az éppen összehasonlított termékeket, valamint a termékek rövid előnézetét jeleníti meg. A hely felhasználói a termék részletező oldalaiból is felvehetnek termékeket, valamint konkrét termékváltozatokat is hozzáadhatnak az alaptermékekkel való összehasonlításhoz.

Miután a vevők néhány terméket hozzáadtak az összehasonlítási tálcához, **a** összehasonlítási lapra való átirányításhoz az Összehasonlítás lehetőséget választják. A termék-összehasonlítási lap megjeleníti az egyes kiválasztott termékek részletes adatait, így a vevők összehasonlíthatják a képeket, az árakat, a termékdimenziókat (méret, stílus és szín), az összesített minősítési adatokat és más termékattribútumokat.

A következő ábra példákat mutat be a termék összehasonlítására, az összehasonlítási gombból való eltávolításra, az összehasonlítási tálcára és a termék összehasonlítási lapjára.

![A termék összehasonlítására vonatkozó gombot, az összehasonlításból való eltávolítást, az összehasonlítási tálca panelt és a termék összehasonlítási lapját megjelenítő termék-összehasonlítási áttekintés.](./media/Product-Comparison-Overview.png)

> [!NOTE]
> - A termék-összehasonlítási lap összehasonlítja egy alapértelmezett terméktulajdonság-készletet és minden olyan attribútumot, amely megtekinthető egy adott termék pdp-ján.
> - A termék-összehasonlítási oldalon nem nézettek meg olyan tulajdonságok, mint a szállítási mód, az aktuális készlet és a mértékegység.
> - A vevők különböző kategóriákból származó termékeket adhatnak hozzá az összehasonlítási tálcához, feltéve, hogy a termékek ugyanabban a katalógusban vannak.
> - A termék-összehasonlítási funkciók jelenleg csak az egyes katalógusok termékeinek összehasonlítására korlátozódnak. A webhely felhasználói nem hasonlíthat össze katalógusközi összehasonlításokat.
> - Gondoskodnia kell arról, **hogy** minden termék-összehasonlítási modul esetében törlődik a Megjelenítés modul ügyféloldali tulajdonsága.
> - Gondoskodnia kell arról, hogy az oldal szintű gyorsítótárazás minden olyan lapon le legyen tiltva, ahol a termék-összehasonlítási modult használja. Ezek közé tartoznak a PDP-k, a PLP-k és a termék-összehasonlítási oldalak. További információ az oldal-gyorsítótárazás [konfigurálása oldalon található](e-commerce-extensibility/page-caching.md).

Az alábbi ábra a termék-összehasonlítási lap egy példáját mutatja be.

![Termék-összehasonlítási oldal.](./media/Product-Comparison-Page.png)

## <a name="add-the-product-comparison-module-to-a-new-product-comparison-page"></a>A termék-összehasonlítási modul hozzáadása új termék-összehasonlítási laphoz

Ha egy lap törzséhez egy termék-összehasonlítási modult ad hozzá, létrehozhat külön termék-összehasonlítási lapot. Az egyes termékek termék-összehasonlítási modulja úgy is konfigurálható, hogy a vevők a termékek összehasonlítását követően gyorsan befejezze a beszerzést. A termék-összehasonlítási modul egy **Üres** összehasonlítási helyet is tartalmaz, ahol az üres állapotot leíró tartalomblokkmodult adhat meg (például "A termék-összehasonlítás üres").

A következő lépésekkel lehet termék-összehasonlítási modult hozzáadni egy új termék-összehasonlítási laphoz.

1. Lépjen az **Oldalak** pontra, majd válassza az **Új** lehetőséget új oldal létrehozásához.
1. Az Új lap létrehozása párbeszédpanel **Lap neve csoportban** **írja be a megfelelő lap nevét (** **például termék összehasonlítását), majd válassza** a Tovább gombra.**·**
1. A **Sablon kiválasztása csoportban** válassza ki a megfelelő sablont (például az alapértelmezett kategóriaoldal által használt sablont), majd válassza **a Tovább gombra**.
1. Az **Elrendezés kiválasztása oldalon válasszon** egy lapelrendezést (például **rugalmas** elrendezés), majd válassza **a Tovább lehetőséget**.
1. Az Ellenőrzés **és befejezés lapon** ellenőrizze a lap konfigurációját. Ha szerkesztenie kell a lap adatait, válassza a Vissza **lehetőséget**. Ha a lap adatai helyesek, válassza a Létrehozás **lapot**.
1. A fő **pontnál válassza** ki a három pontból (**...**), majd válassza a **Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **a** Tároló modult, majd válassza az **OK gombra.**
1. A tárolóhelyen **válassza** ki a három pontból (**...**), majd válassza a **Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **a Termék-összehasonlítási** modult, majd válassza az **OK gombra.**
1. A Gyorsnézet **gombműveletben** válassza ki a három pontból (**...**), majd válassza a **Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki a Termék **gyorsnézet** modulját, majd kattintson az **OK gombra**.
1. A jobb oldali tulajdonságablakban állítsa be a Termék **gyorsnézet** modultulajdonságokat.
1. Az Üres összehasonlítási **pontnál** válassza ki a három pontból (**...**), majd válassza a **Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki a **Tartalomblokk** modult, majd válassza az **OK gombra.**
1. A jobb oldali tulajdonságablakban állítsa be a Tartalomblokk **modul** tulajdonságait. 
1. Válassza a **Mentés** lehetőséget, majd az oldal előnézetének megtekintéséhez az **Előnézet** elemet.
1. Válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

A következő ábra egy üres összehasonlítási oldalt mutat be a webhelyszerkesztőben.

![Termék-összehasonlítási modul](./media/Product-comparison-module.png)

## <a name="add-a-product-comparison-button-to-product-tiles-on-search-and-category-results-pages"></a>Termék-összehasonlítási gomb hozzáadása a termékoldalak keresési és kategória-eredményoldalakon való eredményoldalához

A termék-összehasonlítási gomb segítségével a felhasználók gyorsan hozzá tudják adni a termékeket az összehasonlítási tálcához, amikor a listaoldalon tallózással böngésznek a termékek között. Egy listaoldalról egy vagy több terméket is hozzá lehet adni az összehasonlítási tálcához anélkül, hogy egy PDP-re kellene átmenni.

A termék-összehasonlítási gombot a termékgyűjtemény, a keresési eredmények és a PDP vásárláshoz használható dobozmodulok támogatják.

Ha a keresési és kategória eredményoldalakon termék-összehasonlítási gombot szeretne hozzáadni a termékhoz, kövesse ezeket a lépéseket.

1. A webhelyszerkesztőben nyissa **meg a Pages lapokat**, és nyissa meg azt a kategóriaoldalt, amelybe termék-összehasonlítási gombot szeretne hozzáadni.
1. A fő **pontnál válassza** ki a három pontból (**...**), majd válassza a **Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **a Keresési** eredmények modult, majd válassza az **OK gombra.**
1. Válassza ki a **Keresési eredmények modul** **Termék**-összehasonlítás gomb rését, válassza ki a három pontból (**...**), **majd válassza a Modul hozzáadása lehetőséget.**
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki a Termék-összehasonlítás **gomb** modult, majd válassza az **OK gombra.**
1. A jobb oldali tulajdonságablakban állítsa be a Termék-összehasonlítás **gomb** modul tulajdonságait.
1. Válassza a **Mentés** lehetőséget, majd az oldal előnézetének megtekintéséhez az **Előnézet** elemet.
1. Válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

## <a name="add-a-product-comparison-preview-panel-module-to-pages-on-your-website"></a>Termék-összehasonlítási előnézeti panelmodul hozzáadása a webhely lapjaihoz

A termék-összehasonlítás előnézeti panelmodulja lehetőséget nyújt a vevőknek arra, hogy áttekintsék azokat a termékeket, amelyekhez hozzáadják az összehasonlítást, illetve eltávolítják az összehasonlításból. Az előnézeti panel lehetőséget nyújt arra is, hogy közvetlenül az összehasonlítási oldalra lépjen, vagy törölje a termékek teljes listáját. 

Javasoljuk, hogy minden olyan oldalon engedélyezze az előnézeti panelt, **amelyeken engedélyezve van a Termék-összehasonlítás gomb**. A modult **hozzá** lehet adni a Termék-összehasonlítás gombhoz mint slot, vagy használható különálló modulként, amely bármelyik oldalon konfigurálható, még akkor is, ha nincs olyan funkció, amely az összehasonlítható termékek hozzáadására vagy eltávolítására használható. 

Manuálisan kell hozzáadnia a termék-összehasonlítás előnézeti panelmodulját egy laphoz. Egy laphoz csak egy előnézeti panelmodult adjon hozzá. Ha a modulból több példányt ad hozzá egy laphoz, akkor a rendszer az első modult fogja látni, a többit figyelmen kívül hagyja.

![Termék-összehasonlítás előnézeti panelje](./media/product-comparison-preview-panel-2.png)

Ha megadja a termék-összehasonlítási korlátozást, akkor az előnézeti panelen engedélyezheti a helyőrzőket, amelyek azt jelzik, hogy hány további terméket lehet hozzáadni az összehasonlításhoz. A helyőrzők helyére az összehasonlításban hozzáadott termékek kerülnek. Ha konfigurálni szeretné a termék-összehasonlítási korlátot, és engedélyezni szeretné a helyőrzőket a Webhelyszerkesztőben, **kattintson a > beállításokra**, **és tegye meg a változtatásokat a Termék-összehasonlítások szakaszban**. A rendszer a konfigurációt az összes lap minden előnézeti előképére alkalmazza. 


## <a name="specify-the-maximum-number-of-products-to-show-in-the-comparison-tray"></a>Adja meg az összehasonlítási tálcában található termékek maximális számát.

A Webhely-beállítási **\>** bővítmények segítségével megadhatja az összehasonlítási tálcában maximálisan kívánt termékek számát. Az asztali és a mobil/táblagép nézethez külön maximumot lehet beállítani. Alapértelmezés szerint semmilyen korlátozás nem lesz érvényben, ha nincs megadva maximális korlátozás.

> [!NOTE]
> **Az optimális böngészési élmény érdekében ajánlott a maximálisan használható termékeket az összehasonlítási tálcában 2-re** állítani a mobil nézetportnál, **4-et** az asztali nézetportnál, hogy csökkentse a szükséges vízszintes görgetés mennyiségét.

A következő lépések szerint adja meg az összehasonlítási tálcában található termékek maximális számát.

1. A Webhelyszerkesztőben használja a Webhelybeállítás-bővítményeket **\>**.
1. Az asztali **eszközök** tulajdonságában az összehasonlítási korlátban található termékeknél adja meg, hogy legfeljebb hány termék megjelenik az asztali nézetablakok összehasonlítási tálcájában.
1. Az összehasonlítási **korlátban található termékek – mobil és táblagépes** eszközök tulajdonsága esetén adja meg, hogy legfeljebb hány terméknek kell láthatónak lennie a mobil és a táblagépes nézetportok összehasonlítási tálcájában.
1. Válassza a mentés és a közzététel lehetőséget a **parancssorban**.

![Helybeállítások az összehasonlítási tálcában található termékek korlátozásához.](./media/Site-settings-to-limit-products-in-comparison-tray.png)
