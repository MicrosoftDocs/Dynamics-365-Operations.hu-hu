---
title: Vevő által birtokolt eszközök karbantartási számlája
description: Ez a témakör bemutatja, hogy hogyan lehet létrehozni, feldolgozni és számlázni a vevők eszközeivel kapcsolatos karbantartási munkát.
author: johanhoffmann
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProjProjectContractsListPage, ProjInvoiceTable, ProjProjectsListPage, ProjTable, EntAssetWorkOrderType, EntAssetWorkOrderProjectSetup, EntAssetObjectTable, EntAssetWorkOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-01-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: a48e681da1801ef3c0d1c9c03cebaa5eecd37d76349a7b1c3cfe53e892fae489
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6774945"
---
# <a name="bill-for-maintenance-on-customer-owned-assets"></a>Vevő által birtokolt eszközök karbantartási számlája

[!include [banner](../../includes/banner.md)]

A *munkarendelések számlázása* funkcióval a vevők tulajdonában levő tárgyi eszközök karbantartására vonatkozó munka hozható létre, dolgozható fel és számlázható. A funkciók segítségével az alábbi műveleteket végezeti el:

- Vevők összekapcsolása a tulajdonukban levő eszközökkel.
- Válasszon ki egy vevőt, és tekintse meg azokat az eszközöket, amelyek a vevő tulajdonában vannak, a munkarendelés létrehozásakor.
- Állítson be egy szülőprojektet minden vevő számára.
- Órák, cikkek, költségek és díjak regisztrálása a munkarendelésre, majd később számlajavaslat létrehozása a vevő számára.

Ezenkívül a funkció a következő funkciókat biztosítja:

- A program automatikusan átmásolja a vevő szülőprojektből származó projektszerződést a megfelelő munkarendelési projektbe.
- Az eszközkezelés a *díj* projekt tranzakciótípust most már mind a munkarendelési előrejelzésekben, mind a munkarendelési naplókban használhatja.

## <a name="turn-on-the-customer-billing-feature"></a>Kapcsolja be az ügyfél fizetési elemzés funkciót

A funkció használata előtt be kell azt kapcsolnia saját rendszerében. A rendszergazdák használhatják a [funkciókezelési](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és bekapcsolásához. A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:

- **Modul:** *Projektvezetés és könyvelés*
- **Funkció neve:** *Munkarendelés számlázása*

## <a name="example-scenario"></a>Példaforgatókönyv

A funkció működését a következő példaesetben lehet megismerni.

Ha ezt a forgatókönyvet az itt megadott mintaadatok és értékek alapján kívánja elvégezni, akkor egy olyan rendszert kell használnia amelynél a szokásos [demóadatok](../../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) telepítve vannak. Az **USMF** jogi személyt ki kell választani a kezdés előtt.

A forgatókönyvet a gyártási rendszerben végzett munka során a funkció használatához útmutatásként is használhatja. Ebben az esetben azonban a saját értékeit kell helyettesítenie, és előfordulhat, hogy bizonyos típusú kötelező rekordok hiányoznak, amelyeket a szabvány demóadatok biztosítanak.

### <a name="step-1-create-a-new-project-contract-for-the-customer"></a>1. lépés: Új projektszerződés létrehozása a vevő számára

1. Lépjen a **Projektvezetés és könyvelés \> Projektek \> Projektszerződések** menüpontba.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. Az **Új projektszerződés** párbeszédpanelen a következő értékeket állíthatja be:

    - **Név:** *Pelikán Nagykereskedelem*
    - **Finanszírozás típusa:** *Vevő*
    - **Finanszírozási forrás:** *US-013* (*Pelikán Nagykereskedelem*)

1. Válassza ki az **OK** lehetőséget.

### <a name="step-2-create-a-new-parent-project-for-the-customer"></a>2. lépés: Új szülőprojekt létrehozása a vevő számára

Az itt létrehozott szülőprojektet használja a program a vevői munkarendelések létrehozásakor.

1. Ugorjon a **Projektvezetés és könyvelés \> Projektek \> Minden projekt** pontra.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. Az **Új projekt** párbeszédpanelen adja meg a következő értékeket:

    - **Projekt típusa:** *Idő és anyag*
    - **Projekt neve:** *Pelikán Nagykereskedelem munkarendelések*
    - **Projektcsoport:** *TM*
    - **Projektszerződés azonosítója:** *Pelikán Nagykereskedelem* (a korábban létrehozott szerződés)
    - **Kezdő dátum:** válassza ki a mai napot.

1. Válassza a **Projekt létrehozása** elemet.
1. Az új projekt megnyílik. Jegyezze fel a **Projektazonosító** értékét. Ezt később kell megadnia.

### <a name="step-3-create-a-new-work-order-type-in-asset-management"></a>3. lépés: Új munkarendelés-típus létrehozása az Eszközkezelésben

1. Válassza ki az **Eszközkezelés \> Beállítás \> Munkarendelések \> Munkarendelés-típusai** elemet.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. A program új rekordot ad hozzá a listához. A következő értékeket állítsa be hozzá:

    - **Munkarendelés típusa:** *Szolgáltatás*
    - **Név:** *Szolgáltatási munkarendelés*
    - **Munkarendelés életciklus-állapot:** *Standard*

### <a name="step-4-link-the-customer-account-to-the-parent-project"></a>4. lépés: A vevőszámla csatolása a szülőprojekthez

A vevői számlát most az Eszközkezelés projektbeállításában kell a szülőprojekthez csatolni.

1. Válassza ki az **Eszközkezelés \> Beállítás \> Munkarendelések \> Projektbeállítás** elemet.
1. A **Szülőprojekt** lapon válassza a **Hozzáadás** lehetőséget új sor hozzáadásához.
1. Az új sorban állítsa be a következő értékeket:

    - **Vevői számla:** *US-013* (*Pelikán Nagykereskedelem*)
    - **Projektazonosító:** Adja meg annak a projektnek az azonosítóját, amelyről korábban megjegyzést készített.

### <a name="step-5-link-the-project-group-and-type-to-the-work-order-project"></a>5. lépés: A projektcsoport és a típus összekapcsolása és munkarendelési projekttel

Továbbra is a **Projekt beállítása** lapon kell lennie (**Eszközkezelés \> Beállítás \> Munkarendelések \> Projekt beállítása**).

1. A **Projektcsoport** lapon válassza a **Hozzáadás** lehetőséget új sor hozzáadásához.
1. Az új sorban állítsa be a következő értékeket:

    - **Munkarendelés típusa:** *Szolgáltatás* (a korábban létrehozott munkarendelés-típus)
    - **Projektcsoport:** *TM*

> [!NOTE]
> A munkarendelési projekt projektszerződése mindig a szülőprojekttől öröklődik.

### <a name="step-6-link-an-asset-to-the-customer-id"></a>6. lépés: Eszköz csatolása a vevőazonosítóhoz

1. Lépjen az **Eszközkezelés \> Eszközök \> Aktív eszközök** lehetőségre.
1. A **Szűrő** mezőben adja meg a *VE-102* értékét, és válassza az **Eszköz** szerinti szűrést.
1. Válassza ki az eszközt a beállításai megnyitásához.
1. A **Vevő** gyorslapon adja meg a **Vevőfiók** mezőt az *US-013* (*Pelikán Nagykereskedelem*) értékhez.

    A **Név** mező automatikusan frissítve lesz a *Pelikán Nagykereskedelem* névre.

### <a name="step-7-create-a-new-work-order-on-the-asset"></a>7. lépés: Új munkarendelés létrehozása az eszközhöz

1. Válassza ki az **Eszközkezelés \> Munkarendelések \> Aktív munkarendelések** elemet.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. A **Munkarendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:

    - **Munkarendelés típusa:** *Szolgáltatás*
    - **Leírás:** *Teherautó javítása*
    - **Vevői számla:** *US-013* (*Pelikán Nagykereskedelem*)
    - **Eszköz:** *VE-102*

        > [!NOTE]
        > A keresés csak azokat az eszközöket jeleníti meg, amelyek a kiválasztott vevői számlához vannak kapcsolva.

    - **Karbantartási feladat típusa:** *Javítás*
    - **Szakma:** *Autószerelő*
    - **Szolgáltatásszint:** *4*

1. Válassza ki az **OK** lehetőséget.

### <a name="step-8-review-the-work-order-and-start-to-work-on-it"></a>8. lépés: Tekintse át a munkarendelést, és indítsa el a munkát

Ebben a szakaszban az előző szakaszban létrehozott munkarendelésen fog dolgozni.

1. A következő lépések szerint ellenőrizze, hogy a szülőprojekt a *Pelikán Nagykereskedelem* projekt-e:

    1. Válasszon ki egy sort a **Munkarendelés karbantartási feladatai** szakaszban.
    1. A **Sor részletei** gyorslapon vizsgálja meg a **Projektazonosító** értékét. Kötőjelezett számnak kell lennie a következő formátumban: *\<Parent-Project-ID\>-\<Project-ID\>*. Ez az érték egy hivatkozás.
    1. Válassza ki a projektazonosító hivatkozását egy olyan lap megnyitásához, ahol megtekinthetők a szülőprojektek és a projektnevek.

1. A Művelet ablaktábla **Munkarendelés** lapjának **Életciklus-állapot** csoportjában válassza a **Munkarendelés állapotának frissítése** elemet.
1. A **Munkarendelés állapotának frissítése** párbeszédpanel **Kijelölés** oszlopában jelölje be annak a sornak a jelölőnégyzetét, ahol az **Életciklus-állapot** mező beállítása a *Folyamatban*.
1. Válassza ki az **OK** lehetőséget.
1. Az **Életciklus-állapot: Folyamatban** párbeszédpanelen válassza az **OK** gombot.

### <a name="step-9-post-the-hours-that-were-spent-on-the-work-order-and-create-a-new-invoice-proposal"></a>9. lépés: A munkarendelésre fordított órák feladása, és új számlajavaslat létrehozása

Ebben a szakaszban az előző szakaszban létrehozott munkarendelésen fogja folytatni a munkát.

1. A Műveleti ablaktáblán, a **Munkarendelés** lapon a **Projekt** csoportban kattintson a **Naplók** elemre.

    Megjelenik a **Munkarendelési naplók** lap. Itt regisztrálhatja a munkarendelésre fordított időt.

1. Az **Órák** gyorslapon válassza a **Sor hozzáadása** lehetőséget.
1. Az új sorban állítsa **Órák** mezőt a *4* értékre.
1. A Művelet ablaktáblán válassza ki a **Naplók feladása** elemet.
1. A munkarendelésre való visszatéréshez zárja be a **Munkarendelési naplók** lapot.
1. A Művelet panel **Számlázás** lapján válassza az **Új számlajavaslat** menüpontot.
1. A **Számlajavaslat létrehozása** párbeszédpanel **Projekttranzakciók** szakaszában minden számlázni kívánt sor esetében jelölje be a **Kijelölés** jelölőnégyzetet.
1. Válassza az **OK** gombot a párbeszédpanel bezárásához és az új számlajavaslat megtekintéséhez.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]