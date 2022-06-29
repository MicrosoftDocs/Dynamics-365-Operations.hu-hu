---
title: SEO-metaadatok kezelése
description: Ez a témakör azt ismerteti, hogyan kell kezelni a keresőprogram optimalizálási metaadatait a Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 04/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 99c28c2bff7b683f3e92dea4ba24d8bead556443
ms.sourcegitcommit: 6616b969afd6beb11a79d8e740560bf00016ea7f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/17/2022
ms.locfileid: "9027309"
---
# <a name="manage-seo-metadata"></a>SEO-metaadatok kezelése

[!include [banner](includes/banner.md)]

Ez a témakör azt ismerteti, hogyan kell kezelni a keresőprogram optimalizálási metaadatait a Microsoft Dynamics 365 Commerce.

A webhely SEO metaadatait a webhelytérképek és az oldalak metaadatai használatával lehet kezelni.
    
## <a name="site-maps"></a>Oldaltérképek

A Oldaltérkép egy géppel olvasható lista, amely XML-formátumban, a webhely oldalain található. A keresőmotorok számára készült, hogy a webhelyhez jobb keresési eredményeket jelenítsenek meg. Az oldaltérképeket manuálisan át lehet adni a keresőmotorok számára, vagy közzétehetők egy robots.txt fájlban.

A Dynamics 365 Commerce támohtaj au oldaltérképek automatikus generálását. A program automatikusan frissíti az oldaltérképeket a lapok közzétételekor és közzétételük megszűntetésekor.

### <a name="turn-on-site-map-generation"></a>A Oldaltérkép-generálás bekapcsolása

1. Jelentkezzen be a szerkesztőeszközbe.
1. A **Webhelyek** alatt válassza a **Fabrikam** (vagy a webhelye neve) lehetőséget.
1. A bal oldali navigációs ablakban válassza ki a **Webhelykezelés** lehetőséget.
1. Győződjön meg arról, hogy az **Oldaltérképek engedélyezve** beállítás be van kapcsolva.

## <a name="page-metadata"></a>Oldal metaadatai

Dynamics 365 Commerce a SEO-metaadatok kezelését lehetővé teszi az egyes oldalakhoz. Ezt az információt a lap egy tárolójának **SEO-tulajdonságok** szakaszában tekintheti meg és módosíthatja. Jelenleg a következő SEO-metaadat-tulajdonságok támogatottak:

- Beosztás
- Leírás
- SEO-kulcsszavak
- Aria-címkék
- noindex
- nofollow
- noarchive
- nocache
- noOpenDirectoryProject
- nosnippet
- noImageIndex
- unavailableAfter

### <a name="modify-page-metadata"></a>Oldal metaadatainak módosítása

Az oldal metaadatainak módosításához kövesse az alábbi lépéseket.
1. A **Webhelyek** alatt válassza a **Gyár** (vagy a webhelye neve) lehetőséget.
1. A bal oldali navigációs ablakban válassza ki a **Oldalak** lehetőséget.
1. Válassza ki a kezdőlapot a megnyitáshoz a lapszerkesztőben.
1. Válassza a parancssáv **Szerkesztés** elemét.
1. Az oldalszerkesztő **bal felső tagolási vezérlőjében válassza a Szerkezeti mód** lehetőséget (fogaskerekek szimbóluma), majd válassza a Speciális **szerkezeti nézetet**.
1. A szerkezeti nézetben bontsa ki a favezérlőket **a HTML-feji rés tartalmának megjelenítése** érdekében.
1. A HTML-feji résben válassza ki a kívánt HTML-modult (**például** oldalösszegzés, **termékoldal** összegzése, **kategóriaoldal összegzése** **vagy metatagok).** **·**
1. A jobb oldalon található tulajdonságok ablakában szerkessze a kiválasztott KÜLDŐ modul kívánt ADATOKAT (**például** Cím, **·** **Leírás vagy Megosztási kép**).
1. Válassza a **Mentés** parancsot, majd válassza a **Szerkesztés befejezése** elemet.
1. A Megjegyzések **mezőben** adja meg **a Frissített ITT adatokat**, majd válassza az **OK gombra.**
1. A oldal előnézetének megjelenítéséhez válassza az **Előnézet** lehetőséget. Ha befejezte, zárja be az előnézeti lapot, és térjen vissza a szerkesztési eszközhöz.
1. Válassza a **Közzététel** lehetőséget.

> [!TIP]
> A vázlatok az oldalszerkesztő **bal** oldali tagolási vezérlőjének tetején található Szerkezeti mód beállítással (**fogaskerekek) beállítással válthatnak az Alap szerkezeti nézet** **és a Speciális szerkezeti nézet között**. **Az alapszintű szerkezeti nézet** az alapértelmezett **beállítás**, amely úgy szűri a szerkezetet, hogy csak a lap Törzs HTML-résének moduljait jeleníti meg. **A speciális szerkezeti nézet** a teljes oldalmodult mutatja, **beleértve a HTML-fejet**, **a Törzskezdetet** **és a Törzsvégi időszakokat**. Ez a nézet olyankor hasznos, amikor egy lapra vonatkozó KONKRÉT ÉS VAGY parancsfájlmodul-beállításokat kell szerkeszteni.

## <a name="additional-resources"></a>További erőforrások

[Meglévő webhelyoldal módosítása](modify-existing-page.md)

[Új webhelyoldal hozzáadása](add-new-page.md)

[Oldalelrendezések kiválasztása](select-page-layouts.md)

[Oldal mentése, megtekintése és közzététele](save-preview-publish-page.md)

[A termékoldal bővítése](enrich-product-page.md)

[Kategória céloldalának bővítése](enrich-category-page.md)

[Oldaltartalom hozzáférhetőségének ellenőrzése](verify-accessibility.md)

[Dinamikus e-kereskedelmi oldalak létrehozása URL-paraméterek alapján](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
