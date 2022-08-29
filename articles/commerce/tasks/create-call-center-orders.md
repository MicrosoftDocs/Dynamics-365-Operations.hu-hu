---
title: Hívásközponti rendelések létrehozása
description: Ez a cikk végigvezet egy példa eljárást, amelyben a hívásközponti felhasználó megkeresi a vevőt, létrehoz egy új rendelést, megkeres egy terméket, és beszedi a kifizetést a vevőtől a következőben:Microsoft Dynamics 365 Commerce
author: josaw1
ms.date: 08/05/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: MCRCustomerService, SalesTable, MCRSourceIdTargetLookup, MCRSalesQuickQuote, MCRSalesOrderRecap, MCRCustPaymDialog, MCRCustPaymLookup
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 16d483896ce131e9a7bc60ab5ea7b8fa01a3bea8
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/06/2022
ms.locfileid: "9228510"
---
# <a name="create-call-center-orders"></a>Hívásközponti rendelések létrehozása

[!include [banner](../includes/banner.md)]

Ez a cikk végigvezet egy példa eljárást, amelyben a hívásközponti felhasználó megkeresi a vevőt, létrehoz egy új rendelést, megkeres egy terméket, és beszedi a kifizetést a vevőtől a következőben:Microsoft Dynamics 365 Commerce Az eljárás az USRT bemutatóadat-vállalatot használja, és az értékesítési rendelés adminisztrátorai számára való. 

## <a name="prerequisites"></a>Előfeltételek

Az eljárást végrehajtani képes felhasználót hívásközponti felhasználóként kell beállítani. Ha szükséges, a Gyár féléves katalógusa közzé is tehető legalább egy forráskódgal.

### <a name="add-yourself-as-a-call-center-user"></a>Saját maga hozzáadása hívásközponti felhasználóként

A következő lépések szerint add hozzá saját magát hívásközponti felhasználóként.

1. A Commerce Headquarters rendszer a **Retail és Commerce \> Channels \> Hívásközpontok mind hívásközpontját \> elérhető**.
1. A Felhasználók **mezőben** válassza ki a Csatorna **felhasználóit**.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. Adja meg **felhasználói** azonosítóját a Felhasználó azonosítója mezőben.
1. A Név **mezőben** adja meg a felhasználó nevét. A felhasználónév ugyanaz lehet, mint a felhasználói azonosító.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
1. Vissza a Kiskereskedelmi és **Kereskedelmi csatornák hívásközpontokhoz \>\> minden hívásközponthoz \>**.
1. A hívásközpont kiskereskedelmi csatornaazonosítójának kiválasztása.
1. Győződjön meg arról, hogy **a Rendelés befejezésének** engedélyezése beállítás Igen beállításra **van állítva**. Ha a beállítás nem látható, kihagyhatja ezt a lépést.

## <a name="complete-the-example-call-center-procedure"></a>A példa hívásközponti eljárásának befejezése

A példa hívásközponti eljárásának hajtsa végre a következő lépéseket.

1. Nyissa meg a következőt: **Kiskereskedelem és kereskedelem \> Ügyfelek \> Ügyfélszolgálat**.
1. A Vevőkeresés **lapon** adja meg a vevő keresésére vonatkozó keresési feltételeket. Ebben a példában adja meg **Katanéot**.
1. Válassza a **Keresés** lehetőséget. **Megjelenik a Vevőkereső** párbeszédpanel, amely felsorolja a keresési eredményeket.
1. Válassza ki a 2001-es vevői számlaszámú Kataliáns **vevőrekordot**, **majd válassza a Kijelölés lehetőséget**.**·**
1. A munkaablakban válassza az Új értékesítési **rendelés lehetőséget**.
1. A jobb oldalon válassza a Fejléc **lapot**.
1. Válassza a **99**-es **szabványt** **a Szállítási mód mező Szállítás gyorstétmezőben**.

    ![Szállítási mód kiválasztása.](../media/Select_Mode_of_Delivery.png)

1. A jobb oldalon válassza a Sorok **lapot**.
1. Az Értékesítésirendelés-sorok **szakaszban** az új értékesítési sor új sorában a Cikkszám **mezőbe** írja be a keresni kívánt cikkszámot. Ebben a példában adja **meg a 81327-es** listára, majd válassza ki a terméket a legördülő listából, és adja hozzá az értékesítési rendeléshez.
1. A Mennyiség **mezőbe** írja be az értékesítési mennyiséget.
1. A Forráskód **mezőben** válassza ki a katalógus forráskódját. Ha nincsenek aktív forráskódok, kihagyhatja ezt a lépést.
1. A munkaablakBan a Kész gombra kattintva **rögzítheti** a vevői kifizetést. Ez a művelet megnyitja az **Értékesítési rendelés összegzése** párbeszédpanelt, amelyen az esedékes összeg látható. A művelet az esetleges költségek ( például a szállítás és kezelés) kiszámítását is elindítja, **és megjeleníti azokat az Értékesítési** rendeléseket összegző párbeszédpanelen.

    ![Kész gomb](../media/Complete_button.png)

1. A Kifizetések **gyorspanel** **Értékesítési** rendeléseket összegző párbeszédpanelén válassza a Hozzáadás gombra a **fizetések** rögzítéséhez.

    ![Az értékesítési rendeléseket összegző párbeszédpanel.](../media/order_summary.png)

1. Válassza ki **a fizetési módot a Vevői** **kifizetések adatai párbeszédpanel Fizetési mód** mezőjében. Ebben a példában válassza a Készpénz **lehetőséget**.
1. A Kifizetés **összege mezőben** adja meg a kifizetés összegét. Ebben a példában **adja meg a 120,00-t**, **ami egyenlő az Értékesítési rendelés összegző párbeszédpanelen látható rendelési egyenleggel**. Az összeg megadásával a rendelést teljesen kifizetettként is ki lehet fizetni.
1. Válassza ki az **OK** lehetőséget.
1. Válassza a **Beküldés** lehetőséget.

## <a name="additional-resources"></a>További erőforrások

[Tranzakciós e-mailek testreszabása szállítási mód szerint](../customize-email-delivery-mode.md)

[Szállítási mód módosítása a pénztárban](../pos-change-delivery-mode.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
