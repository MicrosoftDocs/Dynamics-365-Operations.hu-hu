---
title: Dynamics 365 Commerce tesztkörnyezet konfigurálása
description: Ez a cikk bemutatja, hogyan kell konfigurálni az Microsoft Dynamics 365 Commerce üzenetkészlet-környezetet a beállítás után.
author: josaw1
ms.date: 06/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: ae6a8c63721ac32f525e1846a10c0b2caeb08f9f
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9270372"
---
# <a name="configure-a-dynamics-365-commerce-sandbox-environment"></a>Dynamics 365 Commerce tesztkörnyezet konfigurálása

[!include [banner](includes/banner.md)]

Ez a cikk bemutatja, hogyan kell konfigurálni az Microsoft Dynamics 365 Commerce üzenetkészlet-környezetet a beállítás után.

Az ebben a cikkben olvasható eljárásokat csak akkor kell végrehajtani, ha a Commerce üzenetkészlet-környezet már létesítve van. A Commerce üzenetkészlet környezetének létesítével kapcsolatos tudnivalókat [lásd: Provision a Commerce üzenetbox környezet](provisioning-guide.md).

Miután a Commerce üzenetkészlet környezete elkészült, a környezet használata előtt további, az utólagos létesítés konfigurációs lépéseit kell végrehajtani. Ezen lépések elvégzéséhez a Microsoft Dynamics Lifecycle Services (LCS) és Dynamics 365 Commerce alkalmazásokat kell használnia.

## <a name="before-you-start"></a>A program használatának megkezdése előtt

1. Jelentkezzen be az [LCS portálra](https://lcs.dynamics.com).
1. Lépjen a projektjére.
1. A listából válassza ki a környezetét.
1. Kattintson a jobb oldalon található környezeti információk **Bejelentkezés a környezetbe** elemére. Megnyílik a Commerce központ modul.
1. Győződjön meg róla , hogy az **USRT** jogi személy van kiválasztva a jobb felső sarokban. Ez a jogi személy előre konfigurálva van a bemutató adataiban.
1. Menjen a **Commerce rendszer paramétereihez \> : Konfigurációs paraméterek**, és ellenőrizze, hogy van-e bejegyzés a **ProductSearch.UseAzureSearch** fájlhoz, és hogy az érték igaz értékre van-e **állítva**. Ha hiányzik ez a bejegyzés, adja hozzá, és állítsa igaz értékre **az értéket**.
1. Ugrás a **Retail and Commerce \> Headquarters telepítő \> Commerce ütemezője \>, a Commerce inicializálása ütemezőjére** A Commerce Scheduler **inicializálása** menü **·** **Igen** beállításúra állítsa a Létező konfiguráció törlése parancsot, majd válassza **az OK elemet.**
1. Ahhoz, hogy az üzlet- és az e-commerce csatornák megfelelően működjön, hozzá kell adni őket a Commerce Scale Unit egységhez. Menjen a **Retail and Commerce \> Headquarters beállításához \> a Commerce ütemező \> csatorna-adatbázisához**, majd a bal oldali ablakban válassza ki a Commerce Scale Unit beállítást. **A Retail csatorna** gyorséta panelen **adja hozzá az AW online** áruházat, **az AW Business online** **áruházat és a Gyár bővített online** áruházi csatornáit, ha ezeket az e-commerce csatornákat tervezi használni. Arra is lehetőség van, hogy kiskereskedelmi áruházakat is hozzáad a pénztárhoz (POS) (**például Washington**, **San Francisco** és/vagy **San Ba).**
1. Annak érdekében, hogy minden módosítás szinkronizálva legyen a csatorna-adatbázissal, jelölje **\> be a Csatorna-adatbázis teljes** adatszinkronizálását a Commerce Scale Unit számára.

A Commerce központ alkalmazásban történő létesítés utáni tevékenységek során győződjön meg arról, hogy a **USRT** jogi személy mindig be van jelölve.

## <a name="configure-the-point-of-sale"></a>A pénztár beállítása

### <a name="associate-a-worker-with-your-identity"></a>Dolgozó társítása az Ön identitásához

Ha a munkavállalót az identitásához szeretné társítani, kövesse az alábbi lépéseket a Commerce központban.

1. A bal oldalon található menü használatával nyissa meg a **Modulok \> Kiskereskedelem és kereskedelem \> Alkalmazottak \> Dolgozók** lehetőséget.
1. Keresse meg és jelölje ki a következő rekordot a listán: **000713 - Andrew Collette**. Ebben a példában a felhasználó társítva van a Következő szakaszban használt San Fransis üzlethez.
1. A Műveleti ablaktáblán válassza ki a **Commerce** lehetőséget.
1. Válassza a **Létező identitás társítása** lehetőséget.
1. Írja be az e-mail címét az **E-mail** mezőbe a **Keresés e-mailt használatával** lehetőségtől jobbra.
1. Válassza a **Keresés** lehetőséget.
1. Válassza ki a rekordot a saját nevével.
1. Válassza ki az **OK** lehetőséget.
1. Válassza a **Mentés** lehetőséget.

### <a name="activate-cloud-pos"></a>Felhőalapú pénztár aktiválása

A Felhőalapú pénztár aktiválásához hajtsa végre az alábbi lépéseket az LCS-ben.

1. Válassza a felső menü **Felhőalapú környezetek** pontját.
1. A listából válassza ki a környezetét.
1. Kattintson a jobb oldalon található környezeti információk **Bejelentkezés a felhőalapú pénztárba** elemére.
1. Kattintson a **Következő** gombra az **Indítás előtt** párbeszédpanel megnyitásához.
1. Hagyja a **Kiszolgáló URL-címe** mező értékét változatlanul. Válassza ki **Következő** lehetőséget.
1. Jelentkezzen be a Microsoft Azure Active Directory (Azure AD) fiókja segítségével.
1. Az **Üzlet neve** területen válassza a **San Francisco** lehetőséget, majd a **Következő** elemet.
1. A **Pénztár és eszköz** területen válassza a **SANFRAN-1** lehetőséget.
1. Válassza az **Aktiválás** lehetõséget. Kijelentkezett, és a pénztár bejelentkezési oldalára került.
1. Most bejelentkezhet a Felhőalapú pénztár élménybe, a **000713** kezelői azonosítóval és az **123** jelszóval.

## <a name="set-up-your-e-commerce-sites"></a>E-kereskedelmi webhelyek beállítása

Három e-commerce bemutatóhely érhetők el: a Gyár, a Kalandor munka és a Kalandor munka. Az alábbi lépések szerint konfigurálhatja az egyes bemutatówebhelyeket.

1. Jelentkezzen be a webhelykészítőbe azzal az URL-címmel, amelyet az e-kereskedelem inicializálásakor a létesítés során megadott (lásd: [E-kereskedelem inicializálása](provisioning-guide.md#initialize-e-commerce)).
1. Válassza ki a telephelyet (Gyár, Kalandoror **vagy** Kalandoror **üzlet), és nyissa meg a webhely beállítási párbeszédpanelét.** **·**
1. Válassza ki a Commerce inicializálása során megadott tartományt.
1. A központban válassza ki az alapértelmezett csatornának megfelelő előre beállított online áruház-csatornát (Gyár kiterjesztett online áruház, **AW** online **áruház vagy AW Business online áruház**).**·**
1. Alapértelmezett nyelvnek válassza az **en-us** elemet.
1. Az elérési út mezőinek konfigurálása. Ezt üresen is lehet hagyni egyetlen hely esetén, de konfigurálni kell, ha több hely ugyanazt a tartománynevet használja. `https://www.constoso.com` Ha például a tartománynév az, akkor üres elérési utat használhat a Gyár számára,`https://contoso.com` majd az "aw" nevet a Kalandorüzlet () és az "awbusiness"`https://contoso.com/aw` nevet a Kalandorüzlet üzleti webhely számára`https://contoso.com/awbusiness`.
1. Válassza ki az **OK** lehetőséget. Megjelenik a webhelyen lévő oldalak listája.
1. Ha szükséges, ismételje meg a 2–7. lépést a többi bemutatóhely beállításának érdekében.

## <a name="enable-jobs"></a>Munkák engedélyezése

A feladatok engedélyezéséhez a Kereskedelemben kövesse az alábbi lépéseket.

1. Jelentkezzen be a központ környezetbe.
1. A bal oldali menü használatával nyissa meg a **Kiskereskedelem és kereskedelem \> Lekérdezések és jelentések \> Kötegelt feladatok** lehetőséget.

    Az eljárás további lépéseit az alábbi feladatok mindegyikére el kell végezni:

    * Kiskereskedelmi rendelés e-mail értesítésének feldolgozása
    * Termék elérhetősége
    * P-0001
    * Rendelésfeladatok szinkronizálása

1. A Gyorsszűrő használatával kereshet a feladatra név szerint.
1. Ha a feladat állapota **Végrehajtás**, hajtsa végre a következő lépéseket:

    1. Válassza ki a rekordot.
    1. A Művelet panel **Kötegelt feladat** lapján válassza az **Állapot módosítása** lehetőséget.
    1. Válassza a **Megszakítás**, majd az **OK** elemet.

1. Ha a feladat állapota **Visszatartva**, hajtsa végre a következő lépéseket:

    1. Válassza ki a rekordot.
    1. A Művelet panel **Kötegelt feladat** lapján válassza az **Állapot módosítása** lehetőséget.
    1. Válassza a **Várakozás** parancsot, majd válassza az **OK** elemet.

Lehetőség van arra is, hogy a következő feladatokhoz egy (1) percet is be lehessen állítani az ismétlődési intervallumhoz:

* Kiskereskedelmi rendelés e-mail értesítésének feldolgozása feladat
* P-0001 feladat
* Rendelésfeladatok szinkronizálása

### <a name="run-full-data-synchronization"></a>Teljes adatszinkronizálás futtatása

Ha teljes adatszinkronizálást szeretne futtatni a Kereskedelemben, kövesse az alábbi lépéseket a Kereskedelmi központban.

1. A bal oldali menü használatával nyissa meg a **Modulok \> Kiskereskedelem és kereskedelem \> Központ beállítása \> Kereskedelmi ütemezés \> Csatorna-adatbázis** lehetőséget.
1. Válassza ki a másik csatornát, az **scXXXXXXXXX** nevűt.
1. A műveleti ablakban válassza ki a **Teljes adatszinkronizálás** elemet.
1. Adja meg **9999** értéket az elosztási ütemezéshez.
1. Válassza ki az **OK** lehetőséget.
1. Válassza ki az **OK** lehetőséget.

### <a name="test-credit-card-information-to-do-test-purchases"></a>A hitelkártyaadatok tesztelése tesztvásárlások végrehajtásához

Teszttranzakciók végrehajtásához a weboldalon használhatja a következő teszt hitelkártyaadatokat:

- **Kártyaszám:** 4111-1111-1111-1111
- **Lejárat dátuma:** 10/30
- **Kártyaellenőrző kód (CVV):** 737

> [!IMPORTANT]
> Semmilyen körülmények között ne próbáljon ki tényleges hitelkártya-adatokat a tesztoldalon.

## <a name="next-steps"></a>Következő lépések

A létesítés és a konfigurálás lépésének befejezése után elkezdheti használni abox környezetét. Használja a Commerce webhelyépítő eszköz URL-címét a szerzői élményhez lépéshez. Használja a Commerce webhelykezelő eszköz URL-címét a kiskereskedelmi ügyfél webhely élményhez lépéshez.

A Commerce üzenetdoboz környezet választható funkcióinak konfigurálása a [Commerce üzenetbox környezet választható funkcióinak konfigurálása.](cpe-optional-features.md)

Ahhoz, hogy az e-commerce felhasználók bejelentkeztek volna az e-commerce webhelyre, Azure Active Directory további konfigurálás szükséges a vállalati felhasználókon (B2C) keresztüli hitelesítés engedélyezéséhez. További tudnivalók: [B2C bérlő beállítása a Commerce rendszerből](set-up-b2c-tenant.md).

## <a name="troubleshooting"></a>Hibaelhárítás

### <a name="site-builder-channel-list-is-empty-when-configuring-site"></a>Üres a helyszerkesztő csatornalistja a hely konfigurálásakor.

Ha a webhelyszerkesztő nem mutat online áruházi csatornákat, a központ gondoskodik arról, hogy a csatornákat hozzáadják a Commerce Scale Unit [egységhez](#before-you-start) a fenti Kezdés előtt szakaszban leírtak szerint. Futtassa a Commerce **Scheduler** inicializálását is Úgy, hogy **a Létező konfigurációs érték** törlése beállítás Igen értékre van **állítva**.  A lépések befejezése **után** a Csatorna-adatbázis oldalon (**Retail and Commerce Headquarters \> beállítás Commerce \> scheduler \> Channel database**) **futtassa a 9999-es** feladatot a Commerce Scale Unit osztályon.

### <a name="color-swatches-are-not-rendering-on-the-category-page-but-are-rendering-on-the-product-details-page-pdp-page"></a>A színadatok nem a kategóriaoldalon, hanem a termék részletei (PDP) oldalon adatokat tartalmaznak.

A következő lépések segítségével biztosíthatja, hogy a szín- és méretméretek finomíthatók legyen.

1. A központ beállítási csatornakategóriáihoz **és \> termékattribútumainak a beállításához menjen a Retail és a Commerce \> Channel beállításához**.
1. A bal oldali ablakban jelölje ki az online áruház csatornáját, majd válassza az Attribútum metaadatainak **beállítása lehetőséget**.
1. Állítsa Igen **beállításra** **az Attribútum megjelenítése a csatornán beállítást, állítsa** **·** **Igen** beállításra a Lehet finomhangítható beállítást, majd válassza **a Mentés lehetőséget.** 
1. Térjen vissza az online áruház csatornaoldalára, és válassza a Csatornafrissítések közzététele **lehetőséget**.
1. Menjen a **Retail and Commerce \> Headquarters beállításához \> a Commerce scheduler \> Channel adatbázishoz** **, és futtassa a 9999-es** feladatot a Commerce Scale Unit osztályon.

### <a name="business-features-dont-appear-to-be-turned-on-for-the-adventureworks-business-site"></a>Úgy látszik, hogy az üzleti funkciók nincsenek bekapcsolva az üzleti webhelyen AdventureWorks.

A központnál győződjön meg arról, hogy az online **áruház** **csatornája a B2B vevőtípushoz van beállítva.** Ha a **Vevő típusa** **B2C**, új csatornát kell létrehozni, mert a meglévő csatorna nem szerkeszthető. 

A Commerce 10.0.26-os **és korábbi verziójában szállított bemutatóadatoknál egy hiba történt, ahol az AW Business online áruház** csatornája hibás volt. A megoldás megoldás egy új csatorna létrehozása ugyanazokkal a **beállításokkal** és konfigurációval, kivéve a Vevőtípust, amelyet **B2B-re kell beállítani**.

## <a name="additional-resources"></a>További erőforrások

[Üzenetkészlet Dynamics 365 Commerce környezetének létesítása](provisioning-guide.md)

[Az üzenetdoboz-környezet választható funkcióinak Dynamics 365 Commerce konfigurálása](cpe-optional-features.md)

[BoPIS konfigurálásabox Dynamics 365 Commerce környezetben](cpe-bopis.md)

[Microsoft Lifecycle Services (LCS)](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Retail Cloud Scale Unit (RCSU)](/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Microsoft Azure-portál](https://azure.microsoft.com/features/azure-portal)

[Dynamics 365 Commerce-webhely](https://aka.ms/Dynamics365CommerceWebsite)

[B2C-bérlő beállítása a Commerce alkalmazásban](set-up-B2C-tenant.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
