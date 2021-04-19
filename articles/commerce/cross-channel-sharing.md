---
title: Csatornaközi megosztás engedélyezése és használata
description: Ez a témakör azt mutatja be, hogyan lehet engedélyezni és használni a Microsoft Dynamics 365 Commerce webhelykészítő csatornaközi megosztás funkcióját.
author: psimolin
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: de317c2fae4607f5b8b887dd5e866d812043dcd3
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799517"
---
# <a name="enable-and-use-cross-channel-sharing"></a>Csatornaközi megosztás engedélyezése és használata

[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet engedélyezni és használni a Microsoft Dynamics 365 Commerce webhelykészítő csatornaközi megosztás funkcióját.

A csatornaközi megosztással a kiskereskedők újra felhasználhatják és megoszthatják a tartalmat a webhely több csatornája között. Ez a lehetőség akkor hasznos, ha a webhelycsatornák kompatibilis alapnyelvet használnak, vagy ha sok közös tartalmi elemük van.

A csatornaközi megosztás úgy működik, hogy lehetővé teszi egy alapértelmezett csatorna keresését a rendelkezésre álló tartalomhoz, ha a kért tartalomhoz nem található csatornaspecifikus változat. A csatornák között megosztani kívánt tartalmat az alapértelmezett csatorna hozza létre. Ez a tartalom lokalizálható bármilyen webhelycsatornán használt helyszínre.

## <a name="when-to-use-cross-channel-sharing"></a>Mikor használunk csatornaközi megosztást

A csatornák közötti megosztás hasznos, mert egyetlen webhelyen több csatorna is megoszthat tartalmat. Például egy olyan kiskereskedő, akinek több márkaneve és üzlete van, amelyet egyetlen weboldal fog össze, megoszthatja a tartalmat néhány vagy az összes üzlet között. Ez a megosztott tartalom tartalmazhatja az értékesítési és a fizetési feltételeket, a szállítási módokat, valamint a gyakran feltett kérdéseket (GYIK).

A csatornaközi megosztás a töredékeket is támogatja. Emiatt a csatornaspecifikus töredékeket tartalmazó tartalomoldal csatornaközi tartalomként is létrehozható. Ebben az esetben, bár a tartalom legnagyobb része megosztásra kerül a csatornák között, a csatorna-specifikus töredékek csak akkor lesznek megjelenítve a csatornaközi oldalon, ha a megfelelő üzlet csatornáján érkezik a kérés.

A több csatornás weboldalakon, ahol nem lehet tartalmat megosztani, és a csak egy csatornával rendelkező webhelyeken nem működik a csatornaközi megosztás.

## <a name="enable-cross-channel-sharing"></a>Csatornaközi megosztás engedélyezése

A csatornaközi megosztás webhelyszinten van engedélyezve. Ez a művelet egyirányú. Azaz, ha a csatornaközi megosztás engedélyezve lett, később már nem lehet letiltani.

A következő lépésekkel engedélyezheti a csatornaközi megosztást a Commerce webhelyszerkesztőben.

1. Lépjen a **Webhelybeállítások \> Funkciók** elemre.
1. Állítsa a **Csatornaközi** funkciót **Be** értékre.

    ![„Be” értékre állított Csatornaközi opció a Commerce webhelyszerkesztőben](./media/enabling-cross-channel-sharing.png)

Miután engedélyezte a csatornaközi megosztást, a csatornaközi adatok megjelennek a **Csatornák** szakaszban a **Webhelybeállítások \> Funkciók** alatt, ahogy az alábbi ábrán látható.

![A csatornák megjelenített adatai a csatornaközi megosztás engedélyezése után](./media/channels-cross-channel.png)

A csatornaközi megosztás engedélyezését követően a Commerce webhelyszerkesztő jobb felső sarkában a **Csatorna** mezőben megjelenik egy **Csatornaközi online áruház** opció, amely a csatornaközi tartalom kezelésére használható, amint azt a következő ábra mutatja.

![A Csatornaközi online áruház opció a Csatornák mezőben, a csatornaközi megosztás engedélyezése után](./media/cross-channel-dropdown.png)

## <a name="create-and-use-cross-channel-content"></a>Csatornaközi tartalom létrehozása és használata

Csatornaközi tartalom többféleképpen is létrehozható és használható. Létrehozhat például csatornaközi töredékeket, létrehozhat olyan csatornaközi oldalakat, amelyek csatornaközi és csatornaspecifikus tartalmat alkalmaznak, és felülírhat csatornaközi töredékeket a töredékek csatornaspecifikus verzióival.

### <a name="create-a-cross-channel-fragment"></a>Csatornaközi töredék létrehozása

A következő lépésekkel hozhat létre csatornaközi töredéket a Commerce webhelyszerkesztőben.

1. Lépjen a **Töredékek** pontra, és válassza az **Új** lehetőséget új töredék létrehozásához.
1. Az **Új töredék** párbeszédpanelen válassza ki a **Promóciós szalagcím** modult, majd a **Töredék neve** alatt adjon meg egy nevet (például **Csatornaközi szalagcím**). Majd kattintson az **OK** lehetőségre.
1. A **Promóciós szalagcím** modul tulajdonságlapján válassza az **Üzenet hozzáadása** lehetőséget, majd válassza az **Üzenet** elemet.
1. Az **Üzenet** párbeszédpanelben a **Szöveg** alatt írja be, hogy **Csatornaközi**, majd kattintson az **OK** gombra. 
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

Ez a csatornaközi töredék bármely webhelycsatornán létrehozott csatornaközi és csatornaspecifikus oldalon használható.

### <a name="create-a-cross-channel-page-that-uses-cross-channel-content"></a>Csatornaközi tartalmat használó csatornaközi oldal létrehozása

Csatornaközi oldalak a webhely bármely csatornáján használhatók. Ebből következően ha egyszer létrehoz egy megosztott tartalmú oldalt, az esetleges későbbi frissítéseket egyetlen helyen elvégezheti. Például egy csatornaközi **Feltételek** oldal, amelyen az URL-cím `/toc`, megosztható a webhely összes csatornája között. Ha a webhelycsatornák alap URL-címei a `www.fabrikam.com/brand1` és a `www.fabrikam.com/brand2`, a közös csatornaközi megosztott **Feltételek** oldal a webhelycsatorna mindkét URL-címéről elérhető lesz, a `www.fabrikam.com/brand1/toc` és a `www.fabrikam.com/brand2/toc` alatt is. Ha később frissíteni kell a **Feltételek** oldalt, akkor csak az egyetlen megosztott lapot kell frissítenie.

Ha a Commerce webhelykészítőben csatornaközi tartalmat használó csatornaközi oldalt szeretne létrehozni, hajtsa végre az alábbi lépéseket.

1. Lépjen az **Oldalak** pontra, majd válassza az **Új** lehetőséget új oldal létrehozásához.
1. A **Sablon kiválasztása** párbeszédpanelen válassza ki a sablont, pl. a **Marketing** sablont.
1. Az **Oldal neve** alatt adjon nevet az oldalnak (pl. **Csatornaközi oldal**).
1. Az **Oldal URL-címe** alatt adja meg az oldal URL-címét (pl. **mintaoldal**), majd kattintson az **OK** gombra.
1. Az új oldal **Fő** helyén válassza ki a három pont (**…**) gombot, majd válassza a **Töredék hozzáadása** elemet.
1. A **Töredék hozzáadása** párbeszédpanelen válassza ki a korábban létrehozott, promóciós szalagcímet tartalmazó csatornaközi töredéket, majd kattintson az **OK** gombra.
1. Válassza a **Mentés** lehetőséget, majd az oldal előnézetének megtekintéséhez az **Előnézet** elemet. Megjelenik a „Csatornaközi” promóciós szalagcím.
1. Válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

### <a name="create-a-channel-specific-page-that-uses-cross-channel-content"></a>Csatornaközi tartalmat használó csatornaspecifikus oldal létrehozása

A csatornaspecifikus oldalakon csatornaközi tartalmat használva egyszer kell csak létrehoznia megosztott tartalmi töredéket; utána már használhatja a csatornaspecifikus oldalakon. Ez az „egyetlen forrás” olyan megosztott tartalmak esetében hasznos, mint például az általános és a fizetési feltételek vagy a kapcsolattartási adatok.

Ha a Commerce webhelykészítőben csatornaspecifikus tartalmat használó csatornaközi oldalt szeretne létrehozni, hajtsa végre az alábbi lépéseket.

1. Egy adott csatornából, például a **Fabrikam bővített online áruházból**, lépjen az **Oldalak** elemre, majd válassza az **Új** lehetőséget az új oldal létrehozásához.
1. A **Sablon kiválasztása** párbeszédpanelen válassza ki a sablont, pl. a **Marketing** sablont.
1. Az **Oldal neve** alatt adjon nevet az oldalnak (pl. **Csatornaspecifikus oldal**).
1. Az **Oldal URL-címe** alatt adja meg az oldal URL-címét (pl. **csatornaspecifikusoldal**), majd kattintson az **OK** gombra.
1. Az új oldal **Fő** helyén válassza ki a három pont (**…**) gombot, majd válassza a **Töredék hozzáadása** elemet.
1. A **Töredék hozzáadása** párbeszédpanelen a **Csatorna** alatt válassza a **Csatornaközi online áruház** elemet. A korábban létrehozott csatornaközi töredéknek meg kell jelennie a listán. Válassza ki, majd kattintson az **OK** gombra.
1. Válassza a **Mentés** lehetőséget, majd az oldal előnézetének megtekintéséhez az **Előnézet** elemet. Megjelenik a „Csatornaközi” promóciós szalagcím.
1. Válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

### <a name="create-a-channel-specific-version-of-a-cross-channel-page"></a>Csatornaközi oldal csatornaspecifikus verziójának létrehozása

A csatornaközi megosztás támogatja a csatornaközi tartalom felülírását. Ha például egy kivételével az összes webhelycsatornája ugyanazt a tartalmat osztja meg. Az az egy webhelycsatorna más tartalmat igényel. Az eltérő tartalom megvalósításához felül kell írnia a csatornaközi tartalmat csatornaspecifikus tartalommal, a csatornaközi oldal csatornaspecifikus változatának létrehozásával.

Ha a Commerce webhelykészítőben létre szeretné hozni a csatornaközi oldal csatornaspecifikus verzióját, hajtsa végre az alábbi lépéseket.

1. A jobb oldalon felül található **Csatorna** mezőben válassza a **Csatornaközi online áruház** elemet.
1. Nyissa meg a korábban létrehozott csatornaközi oldalt.
1. A jobb oldalon felül található **Csatorna** mezőben válassza ki azt a csatornát, amelyhez más tartalmat szeretne. Az oldalszerkesztő üzenetet jelenít meg, amely arra kéri, hogy hozzon létre új oldalváltozatot.
1. Válassza az **Oldalváltozat létrehozása** lehetőséget.
1. Az oldalváltozat **Fő** helyén válassza ki a három pont (**…**) gombot, majd válassza a **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza a **Promóciós szalagcím** modult, majd kattintson az **OK** gombra.
1. A **Promóciós szalagcím** modul tulajdonságlapján válassza az **Üzenet hozzáadása** lehetőséget, majd válassza az **Üzenet** elemet.
1. Az **Üzenet** párbeszédpanelben a **Szöveg** alatt írja be, hogy **Csatornaspecifikus**, majd kattintson az **OK** gombra.
1. Válassza a **Mentés** lehetőséget, majd az oldal előnézetének megtekintéséhez az **Előnézet** elemet. Megjelenik a „Csatornaspecifikus” promóciós szalagcím.
1. Válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

Most, ha a csatorna alap URL-címét használja, és felkeresi az adott webhelyen a csatornaközi oldal URL-címét, akkor a csatornaközi tartalom helyett a csatornaspecifikus tartalom jelenik meg.

## <a name="additional-resources"></a>További erőforrások

[A tartalom hozzáadásának módjai](add-manage-content.md)

[Oldal modellszószedete](page-elements-overview.md)

[Állapotok és életciklus-dokumentálás](document-states-overview.md)

[A közzétételi csoportokkal végzett munka](publish-groups.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
