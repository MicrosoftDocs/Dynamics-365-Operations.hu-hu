---
title: Interaktívfunkció-modul
description: Ez a témakör az interaktívfunkció-modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
ms.date: 07/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: a01fb446a1b7dd07e0429b96ff949b88a591f800
ms.sourcegitcommit: 7e976059118938b0089e40bef948029a8c088b38
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/09/2021
ms.locfileid: "6479472"
---
# <a name="interactive-feature-module"></a>Interaktívfunkció-modul

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Ez a témakör az interaktívfunkció-modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Microsoft Dynamics 365 Commerce alkalmazásban.

Az interaktívfunkció-modulok olyan mozaikszerű modulok, amelyek több termékkategória vagy termékmárka különböző kép- és szövegkombinációk használatával történő marketingéhez használhatók. Egy kiskereskedő például egy interaktívfunkció-modult felvehet egy e-commerce webhely kezdőlapjára, hogy elősegítse a legfelső eladási kategóriákat. Az interaktívfunkció-modul hasonlít a csempelista modulra, de más az elrendezése és az interakciós funkciói.

Minden interaktívfunkció-modul interaktív funkcióelem-modulok gyűjteménye. Minden funkcióelem-modul működése a tartalomkezelő rendszer (CMS) adatain alapul. Ez nem függ a Commerce központ más moduljaitól és adataitól. Az interaktívfunkció-modul minden olyan webhelylapon elhelyezhető, ahol egy kiskereskedő értékesíteni vagy népszerűsíteni szeretne valamit (például termékeket, kategóriákat vagy márkákat).

> [!IMPORTANT]
> - Az interaktívfunkció-modul a Dynamics 365 Commerce 10.0.20-es verziójának kiadásaként érhető el.
> - Az interaktívfunkció-modult az Adventure Works téma mutatja be.

Az alábbi ábra egy interaktívfunkció-modul példáját mutatja be egy Adventure Works webhely kezdőoldalán.

![Egy interaktívfunkció-modul példája egy Adventure Works webhely kezdőoldalán](./media/Feature.PNG)

## <a name="interactive-feature-module-and-themes"></a>Interaktívfunkció-modul és témák

Az interaktívfunkció-modul különböző elrendezéseket és stílusokat támogathat egy téma alapján. Például az Adventure Works téma interaktívfunkció-modulja kétoszlopos elrendezést tartalmaz, amely az egyes elemek fölé vive az egérmutatót animációs hatásokat jeleníti meg a webhely felhasználója számára. Az interaktívfunkció-modul páros számú képre van optimalizálva, amelyek kétoszlopos elrendezésben vannak.

## <a name="interactive-feature-module-properties"></a>Interaktívfunkció-modul tulajdonságai

| Tulajdonság neve | Értékek | Leírás |
|---------------|--------|-------------|
| Fejléc       | Fejléc szövege és fejléc címkéje (**H1**, **H2**, **H3**, **H4**, **H5** vagy **H6**) | Az interaktívfunkció-modul szöveges fejléce. |

## <a name="interactive-feature-item-module-properties"></a>Interaktívfunkcióelem-modul tulajdonságai

| Tulajdonság neve | Értékek | Leírás |
|---------------|--------|-------------|
| Kép         | Képfájl | Egy terméket vagy kategóriát képviselő kép. A kép feltölthető a Commerce webhelykészítő médiatárába, de meglévő kép is használható. |
| Fejléc       | Fejléc szövege és fejléc címkéje (**H1**, **H2**, **H3**, **H4**, **H5** vagy **H6**) | Alapértelmezés szerint a **H2** fejléccímke használatos a fejlécekhez, de a címke az akadálymentességi követelményeknek megfelelően módosítható. |
| Bekezdés     | Bekezdés szövege | A modul támogatja a rich text formátumú bekezdésszöveget. A rendszer támogat néhány alapvető rich text képességet támogat, például a hiperhivatkozásokat, valamint a félkövér, az aláhúzott és a dőlt szövegformázást. Ezeket a képességeket a modulra alkalmazott laptéma felülbírálhatja. |
| Hivatkozás          | Hivatkozás szövege, hivatkozás URL-címe, akadálymentes dinamikus webes alkalmazások (ARIA) címke és **Hivatkozás megnyitása új lapon** választó | A modul egy vagy több „cselekvésre való felhívás” hivatkozást támogat. Hivatkozás hozzáadásakor hivatkozásszöveg, URL és ARIA címke szükséges. Az ARIA-címkéknek az akadálymentességi követelmények kielégítése érdekében leíró jellegűnek kell lenniük. A hivatkozások beállíthatók úgy, hogy új lapon legyenek megnyitva. |

## <a name="add-an-interactive-feature-module-to-a-new-page"></a>Interaktívfunkció-modul felvétele egy új lapra

Egy interaktívfunkció-modul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához a Commerce webhelyépítőben, hajtsa végre az alábbi lépéseket.

1. Nyissa meg a **Sablonok** lapot, és nyissa meg a webhely kezdőlapjának marketingsablonját (vagy hozzon létre új marketingsablont).
1. Az Alapértelmezett lap **Fő** helyén válassza ki a három pont (**…**) gombot, majd válassza a **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki az **Interaktív funkció** modult, majd kattintson az **OK** gombra.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.
1. Nyissa meg az **Oldalak** területet, majd a webhely kezdőlapját (vagy hozzon létre egy új kezdőlapot a marketingsablon használatával).
1. Az alapértelmezett lap **Fő** helyén válassza ki a három pont (**…**) gombot, majd válassza a **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen a **Modulok kiválasztása** alatt válasszon ki egy **Interaktív funkció** modult, majd kattintson az **OK** gombra.
1. Az interaktívfunkció-modul tulajdonságlapján adjon hozzá egy fejlécet.
1. Az **Interaktív funkció** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki az **Interaktív funkció elem** modult, majd kattintson az **OK** gombra.
1. Az interaktívfunkcióelem-modul tulajdonságablakában adjon hozzá egy képet, egy fejlécszöveget, egy bekezdésszöveget és egy URL-címet.
1. Szükség szerint adja hozzá és konfigurálja a további interaktívfunkció-modulokat.
1. Válassza a **Mentés** lehetőséget, majd az oldal előnézetének megtekintéséhez az **Előnézet** elemet.
1. Válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

## <a name="additional-resources"></a>További erőforrások

[Modultár áttekintése](starter-kit-overview.md)

[Adventure Works téma](adventure-works-theme.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
