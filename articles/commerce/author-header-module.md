---
title: Fejlécmodul
description: Ez a témakör a fejlécmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet oldalfejléceket létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar
manager: annbe
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar-ms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: e7dde3ba1ad375b309ae66cc6d31ccad85615e45
ms.sourcegitcommit: 81f162f2d50557d7afe292c8d326618ba0bc3259
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/11/2020
ms.locfileid: "3686622"
---
# <a name="header-module"></a>Fejlécmodul

[!include [banner](includes/banner.md)]

Ez a témakör a fejlécmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet oldalfejléceket létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A Dynamics 365 Commerce szolgáltatásban egy oldalfejléc több modulból áll, például a fejlécből, a navigációs menüből, a keresésből, a promóciós szalagcímből és a cookie-hozzájárulás moduljaiból. 

A fejlécmodul tartalmaz egy webhelyemblémát, a navigációs hierarchiára mutató hivatkozásokat, a webhely egyéb oldalaira mutató hivatkozásokat, egy kosár-szimbólumot, egy kívánságlista szimbólumot, bejelentkezési beállításokat és a keresési sávot. A program automatikusan optimalizálja a fejlécmodult arra az eszközre, amelyről a webhelyet megtekintik (azaz egy asztali eszközre vagy egy mobileszközre). Egy mobileszköz esetében például a navigációs sáv össze van csukva egy **Menü** gombba (amelyet néha *hamburger menünek* neveznek).

A következő kép egy kezdőoldalon használt címsormodul egy példáját jeleníti meg.

![Példa egy címsor modulra](./media/ecommerce-header.png)

## <a name="properties-of-a-header-module"></a>Fejlécmodul tulajdonságai

A fejlécmodul az **Emblémakép**, **Embléma hivatkozása** és **Saját fiókhivatkozások** tulajdonságokat támogatja. 

Az **Emblémakép** és az **Emblémahivatkozás** tulajdonságokkal adható meg az embléma az oldalon. További tudnivalók: [Embléma hozzáadása](add-logo.md). 

A **Saját fiókhivatkozások** tulajdonsággal megadhatók olyan fiókoldalak, amelyekre mutató hivatkozásokat a webhelytulajdonos meg akar jeleníteni a fejlécben.

## <a name="modules-that-are-available-in-a-header-module"></a>A fejlécmodulban elérhető modulok

A következő modulban használható a fejlécmodulban:

- **Navigációs menü** – A navigációs menü a csatorna navigációs hierarchiáját és más statikus navigációs hivatkozásokat jelenít meg. A csatorna navigációs hierarchiája a Dynamics 365 Commerce alkalmazásban állítható be. A navigációs menü egy **navigációs forrás** tulajdonsággal rendelkezik, amellyel megadhatók a Retail Server navigációs menüelemei és a statikus menüelemek forrásként. Ha a statikus menüelemek forrásként vannak megadva, akkor a webhely más lapjaihoz kapcsolódó relatív hivatkozásokat is meg lehet adni. A konfigurált elemek ezután fejlécnavigációként jelennek meg. 

- **Keresősáv** – A keresőmodul lehetővé teszi a felhasználók számára, hogy keresési kifejezéseket írjanak be, amelyekkel termékeket kereshetnek. Az alapértelmezett keresési lap URL-jét és a keresési lekérdezések paramétereit a **Webhelybeállítások \> Bővítmények** részben kell megadni. A keresési modulnak van olyan tulajdonsága, amely lehetővé teszi a keresési gomb vagy címke elrejtését szükség esetén. A keresési modul olyan automatikus javaslati beállításokat is támogat, mint a termék, a kulcsszó és a kategória keresési eredményei.

- **Kosár ikon** - A kosár ikon modul a kosárikont jeleníti meg, amely a kosárban lévő cikkek számát mutatja bármely időpontban. A további tudnivalókat lásd a [kosár ikon modul](cart-icon-module.md) részben.

## <a name="create-a-header-module-for-a-page"></a>Fejlécmodul létrehozása egy oldalhoz

Fejlécmodul létrehozásához kövesse az alábbi lépéseket.

1. Lépjen a **Töredékek** pontra, és válassza az **Új** lehetőséget új töredék létrehozásához.
1. Az **Új oldaltöredék** párbeszédpanelen válassza ki a **Tároló** modult, adja meg az oldaltöredék nevét, majd kattintson az **OK** gombra.
1. Válassza ki az **Alapértelmezett tároló** helyet, majd a jobb oldali tulajdonságok ablaktáblán állítsa be a **Szélesség** tulajdonságot **Tároló kitöltése** értékre.
1. Az **Alapértelmezett tároló** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza a **Promóciós banner** és a **Süti beleegyezés** modulokat majd kattintson az **OK** gombra.
1. Az **Alapértelmezett tároló** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki az **Tároló** modult, majd kattintson az **OK** gombra.
1. Válassza ki az **Tároló** helyet, majd a jobb oldali tulajdonságok ablaktáblán állítsa be a **Szélesség** tulajdonságot **Tároló kitöltése** értékre.
1. Az **Tároló** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki a **Címsor** modult, majd kattintson az **OK** gombra.
1. Válassza ki a három pont (**...**) elemet a címsor modul **Navigációs menü** helyén, amely tartalmazza a váráslásmező modult, majd válassza a **Modul hozzáadása** lehetőséget.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki a **Navigációs menü** modult, majd kattintson az **OK** gombra.
1. A navigációs menü modul tulajdonságlapján konfigurálja a tulajdonságokat igény szerint.
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

[Kezdőcsomag áttekintése](starter-kit-overview.md)

[Tárolómodul](add-container-module.md)

[Vásárlásmező-modul](add-buy-box.md)

[Kosármodul](add-cart-module.md)

[Kosárikon modul](cart-icon-module.md)

[Fizetésmodul](add-checkout-module.md)

[Rendelésmegerősítési modul](order-confirmation-module.md)

[Fejlécmodul](author-header-module.md)

[Láblécmodul](author-footer-module.md)
