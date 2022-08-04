---
title: Katalógusválasztó modul
description: Ez a témakör a katalógusválasztó Microsoft Dynamics 365 Commerce modulokat ismerteti, és bemutatja, hogyan lehet hozzáadni őket a vállalathoz – B2B – e-commerce webhelyekhez.
author: ashishmsft
ms.date: 07/11/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2022-04-21
ms.openlocfilehash: 642319eea7e40415fd32898f6ec07bfc86f3b1b1
ms.sourcegitcommit: d1491362421bf2fcf72a81dc2dc2d13d3b98122b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/11/2022
ms.locfileid: "9136928"
---
# <a name="catalog-picker-module"></a>Katalógusválasztó modul

[!include [banner](includes/banner.md)]

Ez a témakör a katalógusválasztó Microsoft Dynamics 365 Commerce modulokat ismerteti, és bemutatja, hogyan lehet hozzáadni őket a vállalathoz – B2B – e-commerce webhelyekhez.

A katalógusválasztó modul egy speciális tároló, amely a B2B webhely felhasználói számára elérhető összes termékkatalógus listázására használható vásárlásra. Jelenleg csak a B2B webhelyeken támogatott több katalógus.

Az alábbi ábra egy példaként illusztrálja a katalógusválasztó modult.

![Példa egy katalógusválasztó modulra, amely három termékkatalógust listázza.](./media/Catalog-picker-sample.png)

## <a name="add-a-catalog-picker-module-to-your-site"></a>Katalógusválasztó modul hozzáadása a webhelyhez

Ha katalógusválasztó modult szeretne hozzáadni webhelyéhez a Commerce webhelyszerkesztőben, kövesse ezeket a lépéseket.

### <a name="create-a-catalog-picker-page"></a>Katalógusválasztó oldal létrehozása

Először hozzon létre egy katalógusválasztó oldalt.

1. Lépjen az **Oldalak** pontra, majd válassza az **Új** lehetőséget új oldal létrehozásához.
1. Az Új oldal **létrehozása párbeszédpanel** **Lap neve** csoportban adja meg **a katalógusválasztót**.
1. Adja meg **az oldal URL-címét** a lap URL-címében, majd válassza a Tovább **gombra**.

    ![Új lap párbeszédpanel létrehozása.](./media/Create-catalog-picker-page.png)

1. A **Sablon kiválasztása mezőben válassza** az Általános **tartalmat**, majd válassza a Tovább **lehetőséget**.
1. Válasszon **egy elrendezést**, válassza a Rugalmas **elrendezés**, majd a Tovább **lehetőséget**.
1. Az Ellenőrzés **és befejezés lapon** ellenőrizze a lap konfigurációját. Ha szerkesztenie kell a lap adatait, válassza a Vissza **lehetőséget**. Ha a lap adatai helyesek, válassza a Létrehozás **lapot**.
1. A **Katalógusválasztó részen válassza** ki **a** Fő ponthelyet, válassza ki a három pontból (**...**), **majd válassza a Modul hozzáadása lehetőséget**.

    ![Modul hozzáadása a fő ponthoz a katalógusválasztó alatt](./media/Author-web-page-catalog-picker-1.png)

1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **a** Tároló modult, majd válassza az **OK gombra.**
1. Válassza ki a **tárolóbehelyet**, válassza ki a három pontból (**...**), majd válassza a **Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **a Katalógusválasztó** modult, majd válassza az **OK gombra.**
1. A Katalógusválasztó **tulajdonságai** ablak Fejléc **lapján** **válassza** ki a Katalógusokat, majd adjon meg egy fejlécet a katalógusválasztó laphoz.
1. A **Fejléc szintje alatt** válasszon egy fejlécszintet, majd válassza az **OK gombra.**
1. A **Rich Text** mezőben adja meg a katalógusválasztó oldal tetején megjelenő szöveget.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

### <a name="add-a-link-on-your-account-page"></a>Hivatkozás hozzáadása a számlaoldalhoz

Ezután adjon hozzá egy hivatkozást **a saját számlaoldalon a katalógusválasztó oldalára**.

1. Menjen az **Oldalak lapra**, keresse meg és válassza ki a webhely **Saját** számla lapját, majd válassza a **Szerkesztés lehetőséget**.
1. Az oldal **fő** bejedő részen válassza ki a **Fiók általános csempebejáratot**. 
1. A Számla általános csempetulajdonságok ablaktáblán **, a** Hivatkozások **csoportban** válassza a Művelet hozzáadása hivatkozást **, majd válassza a Művelet hivatkozását** **.**
1. A Művelet **hivatkozás párbeszédpanel** hivatkozásszövegének **lapján** adja meg a katalógusválasztó oldalára mutató hivatkozás szövegét.
1. A **Hivatkozás célcsoportban** válassza a Hivatkozás **hozzáadása lehetőséget**.
1. A Hivatkozás **hozzáadása párbeszédpanelen** válassza **az** Egyéni lapot, majd a Tovább **gombra**.
1. A Név mezőben válassza ki a katalógusválasztó lapját, válassza az **Alkalmaz**, majd az **OK gombra való lehetőséget**.**·**
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

A következő ábra egy olyan számlaoldalt mutat be, amely a katalógusoldalra hivatkozik.

![Saját számlák lap katalógusra mutató hivatkozással](./media/my-accounts.png)

### <a name="add-a-link-from-the-header"></a>Hivatkozás hozzáadása a fejlécből

Végül adjon hozzá egy hivatkozást a webhely fejlécében a katalógusok számára.

1. Menjen a Részletrészletek **lapra**, keresse meg és válassza ki a webhely fejlécének részletét, majd válassza a Szerkesztés **lehetőséget**.
1. Válassza ki **Fejléc** helyet. 
1. A Fejléc tulajdonságai **ablak Saját számla hivatkozásai csoportban** **válassza** a Művelet hozzáadása **hivatkozást, majd válassza a Művelet hivatkozását**.**·**
1. A Művelet **hivatkozás párbeszédpanel** hivatkozásszövegének **lapján** adja meg a katalógusválasztó oldalára mutató hivatkozás szövegét.
1. A **Hivatkozás célcsoportban** válassza a Hivatkozás **hozzáadása lehetőséget**.
1. A Hivatkozás **hozzáadása párbeszédpanelen** válassza **az** Egyéni lapot, majd a Tovább **gombra**.
1. A Név mezőben válassza ki a katalógusválasztó lapját, válassza az **Alkalmaz**, majd az **OK gombra való lehetőséget**.**·**
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a fejléctöredék ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

A következő ábra egy olyan példa bemutatja az ecommerce webhely fejlécét, amely hivatkozást mutat a B2B katalógusra.

![Ecommerce webhely fejléce a katalógusra mutató legördülő hivatkozással](./media/catalog-in-header.png)


## <a name="additional-resources"></a>További erőforrások 

[Commerce-katalógusok létrehozása B2B webhelyekhez](catalogs-b2b-sites.md)

[Commerce-katalógusok B2B-testreszabásokra vonatkozó bővíthetőségi hatása](catalogs-b2b-sites-dev.md)

[Commerce-katalógusok B2B-hez – GYIK](catalogs-b2b-sites-FAQ.md)

[Számlakezelési oldalak és modulok](account-management.md)

[Fejlécmodul](author-header-module.md)
