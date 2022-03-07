---
title: Dynamics 365 Commerce értékelési környezet konfigurálása
description: Ez a témakör bemutatja, hogyan lehet konfigurálni egy Microsoft Dynamics 365 Commerce értékelési környezetet a létesítést követően.
author: psimolin
ms.date: 12/10/2021
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
ms.openlocfilehash: 5883a6e68628d706fa19d7d23b68f17007c32890
ms.sourcegitcommit: eef5d9935ccd1e20e69a1d5b773956aeba4a46bc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/11/2021
ms.locfileid: "7913727"
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
2. Menjen a Commerce >, és ellenőrizze, hogy van-e **a** **ProductSearch.UseAzureSearch paraméter igaz beállítású** **bejegyzése**. Ha hiányzik ez a bejegyzés, hozzáadhatja ezt a bejegyzést, és teljes szinkronizálást futtathat **> az eCommerce webhelyhez társított** Commerce Scale egység számára.

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

1. Ha a feladat állapota **Visszatartva, hajtsa végre a következő** lépéseket:

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
