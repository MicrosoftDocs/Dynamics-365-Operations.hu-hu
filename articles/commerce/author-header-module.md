---
title: Fejlécmodul
description: Ez a témakör a fejlécmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet oldalfejléceket létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
ms.date: 07/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 21bf454e57c62a2542ed055bb0913c48ab70e235
ms.sourcegitcommit: 7e976059118938b0089e40bef948029a8c088b38
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/09/2021
ms.locfileid: "6479256"
---
# <a name="header-module"></a>Fejlécmodul

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Ez a témakör a fejlécmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet oldalfejléceket létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.

A Dynamics 365 Commerce alkalmazásban egy oldalfejléc oldaltöredékként van konfigurálva, amely tartalmazza a fejléc, promóciós banner és cookie-hozzájárulás modulokat. 

A fejlécmodul tartalmaz egy webhelyemblémát, a navigációs hierarchiára mutató hivatkozásokat, a webhely egyéb oldalaira mutató hivatkozásokat, egy kosárikon modult, egy kívánságlista szimbólumot, bejelentkezési beállításokat és a keresési sávot. A program automatikusan optimalizálja a fejlécmodult arra az eszközre, amelyről a webhelyet megtekintik (azaz egy asztali eszközre vagy egy mobileszközre). Egy mobileszköz esetében például a navigációs sáv össze van csukva egy **Menü** gombba (amelyet néha *hamburger menünek* neveznek).

A következő kép egy kezdőoldalon használt címsormodul egy példáját jeleníti meg.

![Példa egy címsormodulra.](./media/ecommerce-header.png)

## <a name="properties-of-a-header-module"></a>Fejlécmodul tulajdonságai

A fejlécmodul az **Emblémakép**, **Embléma hivatkozása** és **Saját fiókhivatkozások** tulajdonságokat támogatja. 

Az **Emblémakép** és az **Emblémahivatkozás** tulajdonságokkal adható meg az embléma az oldalon. További tudnivalók: [Embléma hozzáadása](add-logo.md). 

A **Saját fiókhivatkozások** tulajdonsággal megadhatók olyan fiókoldalak, amelyekre mutató hivatkozásokat a webhelytulajdonos meg akar jeleníteni a fejlécben.

## <a name="modules-that-are-available-within-a-header-module"></a>A fejlécmodulban elérhető modulok

A következő modulban használható a fejlécmodulban:

- **Navigációs menü** – A navigációs menü a csatorna navigációs hierarchiáját és más statikus navigációs hivatkozásokat jelenít meg. További információ: [Navigációs menü modul](nav-menu-module.md).

- **Keresősáv** – A keresőmodul lehetővé teszi a felhasználók számára, hogy keresési kifejezéseket írjanak be, amelyekkel termékeket kereshetnek. Az alapértelmezett keresési lap URL-jét és a keresési lekérdezések paramétereit a **Webhelybeállítások \> Bővítmények** részben kell megadni. A keresési modulnak van olyan tulajdonsága, amely lehetővé teszi a keresési gomb vagy címke elrejtését szükség esetén. A keresési modul olyan automatikus javaslati beállításokat is támogat, mint a termék, a kulcsszó és a kategória keresési eredményei.

- **Kosár ikon** - A kosár ikon modul a kosárikont jeleníti meg, amely a kosárban lévő cikkek számát mutatja bármely időpontban. A további tudnivalókat lásd a [kosár ikon modul](cart-icon-module.md) részben.

- **Telephely-választó** – a telephely-választó modul lehetővé teszi a felhasználók számára, hogy a piaci, a régiós és a területi beállítások alapján különböző előre meghatározott telephelyeket böngésszenek. További információ: [Telephely-választó modul](site-selector.md).

- **Üzletválasztó** – az üzletválasztó modul szerepelhet a fejléc modul üzletválasztó helyén. Lehetővé teszi, hogy a felhasználók böngésszenek és megtalálják a közeli üzleteket. A felhasználók megadhatnak egy preferált üzletet is. Ez az üzlet a fejlécben jelenik meg. Amikor az üzletválasztó modul szerepel a fejléc modulban, a **mód** tulajdonsága beállítása legyen **üzletek keresése**. További információ: [Üzletválasztó modul](store-selector.md).

> [!NOTE]
> - A kosárikon modul használatának támogatása a fejlécmodulban a Dynamics 365 Commerce 10.0.11-es verziójában érhető el.
> - A webhelyválasztó modul használatának támogatása a fejlécmodulban a Dynamics 365 Commerce 10.0.14-es verziójában érhető el.
> - Az üzletválasztó modul használatának támogatása a fejlécmodulban a Dynamics 365 Commerce 10.0.15-ös verziójában érhető el.

## <a name="header-module-in-the-adventure-works-theme"></a>A fejlécmodul a Adventure Works témában

Az Adventure Works témában a fejlécmodul támogatja a **Mobileembléma** tulajdonságot. Ez a tulajdonság lehetővé teszi egy embléma megadását a mobil nézetablakok számára. A **Mobilembléma** tulajdonság moduldefiníciós bővítményként áll rendelkezésre.

> [!IMPORTANT]
> Az Adventure Works téma a Dynamics 365 Commerce 10.0.20-as kiadásában érhető el.

## <a name="create-a-header-fragment-for-a-page"></a>Fejléctöredék létrehozása egy oldalhoz

Fejléctöredék létrehozásához kövesse az alábbi lépéseket.

1. Lépjen a **Töredékek** pontra, és válassza az **Új** lehetőséget új töredék létrehozásához.
1. Az **Új töredék** párbeszédpanelen válassza ki a **Tároló** modult, adja meg a töredék nevét, majd kattintson az **OK** gombra.
1. Válassza ki az **Alapértelmezett tároló** helyet, majd a jobb oldali tulajdonságok ablaktáblán állítsa be a **Szélesség** tulajdonságot **Képernyő kitöltése** értékre.
1. Az **Alapértelmezett tároló** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza a **Cookie hozzájárulás** **Fejléc** és **Promóciós banner** modulokat majd kattintson az **OK** gombra.
1. A **Promóciós banner** modul tulajdonságok ablaktábláján válassza az **Üzenet hozzáadása** lehetőséget, majd válassza az **Üzenet** elemet.
1. Az **Üzenet** párbeszédpanelen adja meg a szöveget és a promóciós tartalomhoz tartozó hivatkozásokat, majd kattintson az **OK** gombra.
1. A **Cookie-hozzájárulás** modul tulajdonságok ablaktáblájában adja meg a szöveget és a webhelye adatvédelmi oldalára mutató hivatkozást.
1. Válassza ki a három pont (**...**) elemet a címsor modul **Navigációs menü** helyén, amely tartalmazza a váráslásmező modult, majd válassza a **Modul hozzáadása** lehetőséget.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki a **Navigációs menü** modult, majd kattintson az **OK** gombra.
1. A navigációs menü modul tulajdonság lapján, a **Navigációs menü forrása** alatt válassza a **Retail Server** elemet.
1. A navigációs menü modul tulajdonságlapján, a **Statikus menüelemek** területen válassza a **Menüelem hozzáadása** lehetőséget. majd válassza a **Menüelem** lehetőséget. 
1. A **Menüelem** párbeszédpanelén, a **Menüelem szövege** mezőbe írja be: „Kapcsolat”.
1. A **Menüelem** párbeszédpanelen a **Menüelem-hivatkozás célja** alatt válassz a **Hivatkozás hozzáadása** lehetőséget.
1. A **Hivatkozás hozzáadása** párbeszédpanelen jelölje ki a „Kapcsolat” lap URL-címét, majd kattintson az **OK** gombra.  
1. A **Menüelem** párbeszédpanelen válassza az **OK** lehetőséget.
1. Válassza ki a három pont (**...**) elemet a címsor modul **Keresés** helyén, amely tartalmazza a váráslásmező modult, majd válassza a **Modul hozzáadása** lehetőséget.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki a **Keresés** modult, majd kattintson az **OK** gombra.
1. A keresés modul tulajdonságlapján konfigurálja a tulajdonságokat igény szerint.
1. Válassza ki a három pont (**...**) elemet a címsor modul **Kosárikon** helyén, amely tartalmazza a váráslásmező modult, majd válassza a **Modul hozzáadása** lehetőséget.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki az **Kosárikon** modult, majd kattintson az **OK** gombra.
1. A kosárikon modul tulajdonságlapján konfigurálja a tulajdonságokat igény szerint. Ha azt szeretné, hogy a kosárikon megjelenítsen egy kosárösszegzést (más néven mini kosarat), amikor a felhasználó fölé viszi az egérmutatót, akkor válassza ki a **Mini kosár megjelenítése** lehetőséget.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a töredék ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

Ha azt szeretné, hogy minden lapon megjelenjen a fejléc, hajtsa végre az alábbi lépéseket a webhelyhez létrehozott összes oldalsablon esetében.

1. Az **Alapértelmezett** lap **Címsor** helyén a láblécmodulban adja meg a létrehozott lábléctöredéket.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

## <a name="additional-resources"></a>További erőforrások

[Modulkönyvtár – áttekintés](starter-kit-overview.md)

[Tárolómodul](add-container-module.md)

[Kosárikon modul](cart-icon-module.md)

[Promóciós szalagcím modul](add-alert.md)

[Navigációs menü modulja](nav-menu-module.md) 

[Cookie-kkal kapcsolatos hozzájárulás](cookie-consent-module.md)

[Láblécmodul](author-footer-module.md)

[Telephelyválasztó modul](site-selector.md)

[Üzletválasztó modul](store-selector.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
