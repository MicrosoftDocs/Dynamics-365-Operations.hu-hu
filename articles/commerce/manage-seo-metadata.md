---
title: SEO-metaadatok kezelése
description: Ez a témakör azt mutatja be, hogyan lehet kezelni a keresőmotor-optimalizálási (SEO) metaadatokat a Microsoft Dynamics 365 Commerce megoldásban.
author: psimolin
ms.date: 04/14/2020
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
ms.openlocfilehash: 1e03ef346df92a94b0a403f241d0f7d1f64fd210
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5794211"
---
# <a name="manage-seo-metadata"></a>SEO-metaadatok kezelése

[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet kezelni a keresőmotor-optimalizálási (SEO) metaadatokat a Microsoft Dynamics 365 Commerce megoldásban.

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
1. A jobb oldali tulajdonságok ablaktáblán bontsa ki az **Alapértelmezett metacímkék** lehetőséget.
1. Új metacímke hozzáadásához kattintson a **Hozzáadás** gombra, majd írja be a címkét a mezőbe. Ha törölni szeretne egy létező metacímkét, válassza a mellette, jobbra található kuka szimbólumot.
1. Válassza a **Mentés** parancsot, majd válassza a **Szerkesztés befejezése** elemet.
1. A **Megjegyzések** mezőbe írja be a **Frissített metacímkék** szöveget, majd kattintson az **OK** gombra.
1. A oldal előnézetének megjelenítéséhez válassza az **Előnézet** lehetőséget. Ha befejezte, zárja be az előnézeti lapot, és térjen vissza a szerkesztési eszközhöz.
1. Válassza a **Közzététel** lehetőséget.

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
