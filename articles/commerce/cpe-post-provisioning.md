---
title: Dynamics 365 Commerce értékelési környezet konfigurálása
description: Ez a témakör bemutatja, hogyan lehet konfigurálni egy Microsoft Dynamics 365 Commerce értékelési környezetet a létesítést követően.
author: psimolin
ms.date: 05/12/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: d9738700ca495d54c91ad91aa9c5a3d32c95a5a5
ms.sourcegitcommit: 4a973ac0e7af0176270a8070a96a52293567dfbf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/13/2022
ms.locfileid: "8747637"
---
# <a name="configure-a-dynamics-365-commerce-evaluation-environment"></a>Dynamics 365 Commerce értékelési környezet konfigurálása

[!include [banner](includes/banner.md)]

Ez a témakör bemutatja, hogyan lehet konfigurálni egy Microsoft Dynamics 365 Commerce értékelési környezetet a létesítést követően.

A jelen témakörben ismertetett eljárásokat csak a Commerce értékelési környezet létesítését követően hajtsa végre. A Commerce értékelési környezetének létesítésével kapcsolatos információkért lásd: [Commerce értékelési környezet kiépítése](provisioning-guide.md).

Miután a Commerce értékelési környezet teljes körűen kiépítésre került, további létrehozás utáni konfigurálási lépéseket el kell végezni, mielőtt megkezdheti a környezet értékelését. Ezen lépések elvégzéséhez a Microsoft Dynamics Lifecycle Services (LCS) és Dynamics 365 Commerce alkalmazásokat kell használnia.

## <a name="before-you-start"></a>A program használatának megkezdése előtt

1. Jelentkezzen be az [LCS portálra](https://lcs.dynamics.com).
1. Lépjen a projektjére.
1. Válassza a felső menü **Felhőalapú környezetek** pontját.
1. A listából válassza ki a környezetét.
1. Kattintson a jobb oldalon található környezeti információk **Bejelentkezés a környezetbe** elemére. Megnyílik a Commerce központ modul.
1. Győződjön meg róla , hogy az **USRT** jogi személy van kiválasztva a jobb felső sarokban.
1. Menjen a **Commerce rendszer paramétereihez \> : Konfigurációs paraméterek**, és ellenőrizze, hogy van-e bejegyzés a **ProductSearch.UseAzureSearch** fájlhoz, és hogy az érték igaz értékre van-e **állítva**. Ha hiányzik ez a bejegyzés, hozzáadhatja, az értéket igaz értékre állíthatja, **·** **\>** majd az e-commerce webhelyhez társított Commerce Scale Unit egységre vonatkozó Teljes adatszinkronizálási lehetőséget választhatja.
1. Ugrás a **Retail and Commerce \> Headquarters telepítő \> Commerce ütemezője \>, a Commerce inicializálása ütemezőjére** A Commerce Scheduler **inicializálása** menü **·** **Igen** beállításúra állítsa a Létező konfiguráció törlése parancsot, majd válassza **az OK elemet.**
1. Ha csatornákat szeretne hozzáadni a Commerce Scale Unit egységhez, **válassza a Retail and Commerce \> Headquarters \> beállítás commerce ütemező \> csatorna-adatbázisát**, majd a bal oldali ablakban válassza ki a Commerce Scale Unit beállítást. Adja hozzá a Kiskereskedelmi csatorna **gyorsblokkján** az AW online **áruházat,** az AW Business online **áruházat** és a Gyár bővített online áruházi csatornáit **.** A POS használata esetén kiskereskedelmi áruházakat is hozzáadhat (**például San** **Fransis, San Francisco** **és San Grace**).

A Commerce központ alkalmazásban történő létesítés utáni tevékenységek során győződjön meg arról, hogy a **USRT** jogi személy mindig be van jelölve.

## <a name="configure-the-point-of-sale"></a>A pénztár beállítása

### <a name="associate-a-worker-with-your-identity"></a>Dolgozó társítása az Ön identitásához

Ha a munkavállalót az identitásához szeretné társítani, kövesse az alábbi lépéseket a Commerce központban.

1. A bal oldalon található menü használatával nyissa meg a **Modulok \> Kiskereskedelem és kereskedelem \> Alkalmazottak \> Dolgozók** lehetőséget.
1. Keresse meg és jelölje ki a következő rekordot a listán: **000713 - Andrew Collette**.
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

## <a name="set-up-your-site-in-commerce"></a>Webhely beállítása a Commerce alkalmazásban

Az értékelési webhely beállításának megkezdéséhez a Commerce alkalmazásban, kövesse az alábbi lépéseket.

1. Jelentkezzen be a webhelykészítőbe azzal az URL-címmel, amelyet az e-kereskedelem inicializálásakor a létesítés során megadott (lásd: [E-kereskedelem inicializálása](provisioning-guide.md#initialize-e-commerce)).
1. A hely beállítási mezőjének megnyitásához kattintson a **Fabrikam** helyre.
1. Válassza ki azt a tartományt, amelyet az e-kereskedelem inicializálásakor megadott.
1. Alapértelmezett csatornaként válassza ki a **Fabrikam bővített online áruház** lehetőséget. (Győződjön meg arról, hogy a **kiterjesztett** online áruházat választja.)
1. Alapértelmezett nyelvnek válassza az **en-us** elemet.
1. Hagyja az **Útvonal** mező értékét változatlanul.
1. Válassza ki az **OK** lehetőséget. Megjelenik a webhelyen lévő oldalak listája.
1. Ismételje meg a 2-7 **AdventureWorks**. lépést a webhelyre (**amely az AW online** áruház csatornájára leképezi) **AdventureWorks** és az üzleti webhelyet (**amely az AW üzleti online áruház csatornájára leképezi**). **Ha a Gyár** webhely Elérési útja mező üres, AdventureWorks akkor hozzá kell adni a két hely elérési útvonalát (például "aw" és "awbusiness").

## <a name="enable-jobs"></a>Munkák engedélyezése

A feladatok engedélyezéséhez a Kereskedelemben kövesse az alábbi lépéseket.

1. Jelentkezzen be a környezetbe (HQ).
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

A létesítési és a konfigurálási lépések befejezését követően készen áll arra, hogy elkezdje az értékelési környezet használatát. Használja a Commerce webhelyépítő eszköz URL-címét a szerzői élményhez lépéshez. Használja a Commerce webhelykezelő eszköz URL-címét a kiskereskedelmi ügyfél webhely élményhez lépéshez.

A Commerce értékelési környezete nem kötelező funkcióinak konfigurálásához lásd: [Commerce értékelési környezete nem kötelező funkcióinak konfigurálása](cpe-optional-features.md).

> [!NOTE]
> A kereskedelmi értékelő környezetek egy előre feltöltött Azure Active Directory (Azure AD) üzleti-fogyasztói (B2C) bérlőt tartalmaznak bemutató célokra. A saját Azure AD B2C bérlő konfigurálása nem szükséges az értékelő környezetek esetében. Ha azonban az értékelő környezetet úgy konfigurálja, hogy a saját Azure AD B2C bérlőjét használja, kérjük, győződjön meg róla, hogy az Azure Portálon keresztül hozzáadja a ``https://login.commerce.dynamics.com/_msdyn365/authresp`` címet válasz URL-ként a Azure AD B2C alkalmazásban.

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

A központnál győződjön meg arról, hogy az online **áruház** **csatornája a B2B vevőtípushoz van beállítva**. Ha a **Vevő típusa** **B2C**, új csatornát kell létrehozni, mert a meglévő csatorna nem szerkeszthető. 

A Commerce 10.0.26-os **és korábbi verziójában szállított bemutatóadatoknál egy hiba történt, ahol az AW Business online áruház** csatornája hibás volt. A megoldás megoldás egy új csatorna létrehozása ugyanazokkal a **beállításokkal** és konfigurációval, kivéve a Vevőtípust, amelyet **B2B-re kell beállítani**.

## <a name="additional-resources"></a>További erőforrások

[Dynamics 365 Commerce értékelési környezet áttekintése](cpe-overview.md)

[Dynamics 365 Commerce értékelési környezet kiépítése](provisioning-guide.md)

[Dynamics 365 Commerce értékelési környezet választható funkcióinak konfigurálása](cpe-optional-features.md)

[BOPIS konfigurálása Dynamics 365 Commerce értékelési környezetben](cpe-bopis.md)

[Dynamics 365 Commerce értékelési környezet GYIK](cpe-faq.md)

[Microsoft Lifecycle Services (LCS)](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Retail Cloud Scale Unit (RCSU)](/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Microsoft Azure-portál](https://azure.microsoft.com/features/azure-portal)

[Dynamics 365 Commerce-webhely](https://aka.ms/Dynamics365CommerceWebsite)

[B2C-bérlő beállítása a Commerce alkalmazásban](set-up-B2C-tenant.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
