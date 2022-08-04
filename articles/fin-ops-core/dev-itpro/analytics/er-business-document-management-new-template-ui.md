---
title: Microsoft Office-style felhasználói felület az üzleti dokumentumkezelésben (video)
description: Ez a cikk bemutatja az elektronikus jelentéskészítési (ER) keretrendszer üzleti dokumentumkezelési funkció új felhasználói felületének használatát.
author: v-anamir
ms.date: 01/05/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: v-anamir
ms.search.validFrom: 2019-08-01
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 208cfc91f11d4893785538ce4874e85a5725e993
ms.sourcegitcommit: 3289478a05040910f356baf1995ce0523d347368
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2022
ms.locfileid: "9109260"
---
# <a name="microsoft-office-style-user-interface-in-business-document-management"></a>Microsoft Office stílusú felhasználói felület az Üzleti dokumentumkezelés modulban

[!include [banner](../includes/banner.md)]

Az Üzleti dokumentumkezelés lehetővé teszi az üzleti felhasználók számára, hogy a Microsoft Office 365 szolgáltatás vagy a megfelelő Microsoft Office asztali alkalmazások segítségével szerkesszék az üzleti dokumentumok sablonjait. A szerkesztések lehetnek tervezési változtatások vagy új telepítések, illetve a felhasználók hozzáadhatnak helyőrzőket, hogy a forráskód módosítása nélkül is hozzáadhatók legyenek további adatok. Az üzleti dokumentumkezelés működésével kapcsolatos további tudnivalókat lásd: [Üzleti dokumentumkezelés – áttekintés.](er-business-document-management.md).

Az új felhasználói felület (UI) egyértelműbb és kényelmesebben használható. Az **Üzleti dokumentumok** terület [csak](tasks/er-configuration-provider-mark-it-active-2016-11.md)[azokat](general-electronic-reporting.md#Provider) a sablonokat jeleníti meg, amelyek az aktuális aktív szolgáltató tulajdonában állnak, és amelyek a Dynamics 365 Pénzügy aktuális példányában találhatók. Az előző felhasználói felületen a Sablon lap felsorolja az összes olyan sablont, **amely** bármelyik szolgáltató számára elérhető volt. Emellett minden olyan sablont megjelenít, amelyet az azonos szerepkörű felhasználók létrehoztak és megszerkesztettek.

**·** **·**[...](general-electronic-reporting.md)[Az](general-electronic-reporting.md#Configuration) Üzleti dokumentumkezelési munkaterület Új dokumentum gombjával létrehozhat és szerkeszthet egy sablont egy másik szolgáltató által biztosított, az aktuális Pénzügyi példányban található elektronikusjelentés-formátum konfigurációjában, vagy feltölthet egy új sablont egy Excel-munkafüzetből. Ezenkívül a 10.0.25-ös **és** újabb verziókban az Új dokumentum gomb használatával a globális tárházban tárolt ER-formátumkonfigurációban [sablonokat lehet létrehozni és szerkeszteni](general-electronic-reporting.md#Repository).

A példában ebben a példában az aktív szolgáltató a Contoso, és a felhasználó a Microsoft által biztosított sablonon alapuló sablon létrehozására használja. Másik lehetőségként készíthet egy sablont az Excel-formátumban feltöltött saját sablonjából.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWAVQg]

Az [Új üzleti dokumentum létrehozása az Üzleti](https://youtu.be/gAIYl-mM_pw) dokumentumkezelés segítségével – amely fent látható – [része](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) a pénzügyi és műveleti lehetőségeknek YouTube.

## <a name="make-the-new-document-ui-in-business-document-management-available"></a>Az új dokumentum kezelőfelület elérhetővé tétele az üzleti dokumentumkezelés modulban

Ha azt szeretné, hogy a program az új dokumentum kezelőfelületet használja az üzleti dokumentumkezelés modulban, akkor be kell kapcsolni az **Office-szerű UI-élmény az üzleti Dokumentumkezelés számára** funkciót a **Funkciókezelés** munkaterületen.

Kövesse az alábbi lépéseket a funkció bekapcsolásához az összes jogi személynél.

1. A **Funkciókezelés** munkaterületen, az **Összes** lapon válassza ki a listán az **Office-szerű UI-élmény az üzleti Dokumentumkezelés számára** funkciót.
2. Válassza az **Engedélyezés most** lehetőséget a kiválasztott funkció bekapcsolásához.
3. Az új funkció eléréséhez frissítse a lapot.

## <a name="add-or-activate-a-provider"></a>Szolgáltató hozzáadása vagy aktiválása

Az üzleti dokumentumok minden sablonja egy ER-formátum konfigurációban van tárolva, amely egy adott konfigurációszolgáltató tulajdonában van. Új sablon létrehozásakor új ER-formátumkonfiguráció jön létre, amely a sablont fogja tartalmazni. Ebből következően meg kell határozni egy szolgáltatót az adott konfigurációhoz. Erre a célra az Er-keretrendszer aktív szolgáltatója szolgál. Ha nincs szolgáltató az erszdőben, létrehozhat egyet. Ha nincs aktív *szolgáltató*, aktiválhatja a meglévő szolgáltatókat. A szolgáltató hozzáadására és aktiválásra szolgáló párbeszédpanelt a rendszer szükség esetén megnyitja, ugyanakkor elindítja az új sablonok hozzáadását.

### <a name="add-a-new-provider"></a>Új szolgáltató hozzáadása

Új szolgáltató létrehozásához kövesse az alábbi lépéseket a Konfigurációszolgáltató **párbeszédpanelen**:

1.  Adja meg **az új szolgáltató nevét a Konfigurációszolgáltató** **kiválasztása** lapon a Név mezőben.
2.  Adja meg **az** új szolgáltató internetcímét (URL-címét) az Internetcím mezőben. 
3.  Válassza ki az **OK** lehetőséget.

    ![Új szolgáltató létrehozása az Üzleti dokumentumkezelésben](./media/bdm_create_provider.png)

A hozzáadott szolgáltató automatikusan aktiválódik.

### <a name="activate-a-provider"></a>Szolgáltató aktiválása

Szolgáltató aktiválásához kövesse az alábbi lépéseket a Konfigurációszolgáltató **párbeszédpanelen**:

1.  A Konfigurációszolgáltató **kiválasztása** lapon, **a Konfigurációszolgáltató** mezőben válassza ki a szolgáltatót.
2.  Válassza ki az **OK** lehetőséget.

    ![Szolgáltató aktiválása az Üzleti dokumentumkezelésben](./media/bdm_choose_provider.png)

A kijelölt szolgáltató aktiválódik.

> [!NOTE]
> Az üzleti dokumentumok kezelési sablonja egy ER formátumkonfigurációban található, amely a szolgáltatóra hivatkozik, mint konfiguráció szerzője. Emiatt minden sablonhoz szükség van egy aktív szolgáltatóra.

## <a name="edit-a-template-that-is-owned-by-another-provider"></a>Másik szolgáltató tulajdonában álló sablon szerkesztése

A példa bemutatja, **·** **hogy** hogyan használható az Üzleti dokumentumkezelési munkaterület Új dokumentum gombja egy sablon létrehozásához és szerkesztéséhez olyan ER formátumkonfigurációban, amelyet egy másik szolgáltató biztosít, és amely az aktuális Pénzügyi példányban található. Ebben a példában az aktív szolgáltató a Contoso, amely a Microsoft ER-formátumkonfigurációját használja. Az Új dokumentum **kiválasztása** után az Új sablon létrehozása lap Kijelölés lapján az aktuális pénzügyi példány összes olyan sablonja látható, **·** **amely** az aktuális szolgáltató és más szolgáltatók tulajdonában van. Válassza ki a megnyitni kívánt sablont. Ezt követően létrehozhatja a sablon új szerkeszthető példányát. A szerkesztett sablont a rendszer automatikusan generált új ER-formátumkonfigurációban tárolja.

1. Az **Üzleti dokumentumkezelés** munkaterületen válassza az **Új dokumentum** elemet.

    ![Üzletidokumentum-kezelés munkaterület.](./media/BDM_overview_new_template1.png)

2. Az Új sablon **létrehozása lapon,** **a Kijelölés lapon jelölje ki a sablonként használni kívánt dokumentumot,** majd válassza a Dokumentum létrehozása **lehetőséget**.

    ![Üzleti dokumentumok párbeszédpanel.](./media/BDM_overview_new_template2.png)

3. Az új párbeszédpanelen, a **Cím** mezőben, módosítsa a címet szükség szerint. A program az automatikusan létrehozott új ER-formátumkonfiguráció elnevezésére használja a címszöveget. A konfiguráció vázlatverziója (**Customer FTI report (GER) másolata**) tartalmazza a szerkesztett sablont, és az ER-formátum futtatásá lesz használva az aktuális felhasználóhoz. A rendszer alap ER formátumból származó nem módosított eredeti sablon alapján futtatja ezt az ER formátumot bármely más felhasználó számára.
4. A **Név** mezőben módosítsa az automatikusan létrehozandó szerkeszthető sablon első verziójának nevét.
5. A **Megjegyzés** mezőben módosítsa a szerkeszthető sablon automatikusan létrehozott verziójának megjegyzéseit.
6. A szerkesztési folyamat kezdetének jóváhagyásához kattintson az **OK** gombra.

    ![Dokumentum-létrehozás párbeszédpanel.](./media/BDM_overview_new_template3.png)

## <a name="upload-a-template-that-uses-an-existing-excel-workbook"></a>Meglévő Excel-munkafüzetet használó sablon feltöltése

A példa bemutatja, **·** **hogyan** használható az Üzleti dokumentumkezelési munkaterület Új dokumentum gombja egy ER formátumú sablon létrehozásához és szerkesztéséhez az elérhető Excel-munkafüzet alapján. Ebben a példában az aktív szolgáltató a Contoso, [és](er-overview-components.md#data-model-component) a Microsoft er adatmodell- és ER-modellleképezési [konfigurációit](er-overview-components.md#model-mapping-component) használja. Az Új dokumentum kiválasztása **után válassza** az **Új** sablon létrehozása lap **Feltöltés lapját**. Itt megadhatja egy Excel-munkafüzet feltöltésének adatait. Az Excel-munkafüzet feltöltése után egy szerkesztésre megnyitott üzletidokumentum-sablonvá alakul át. A szerkesztett sablon egy új ER-formátumkonfigurációban lesz tárolva, amely automatikusan létrejön.

A sablon feltöltése előtt kövesse ezeket a lépéseket, és adja meg a szükséges adatokat.

1. Az **Üzleti dokumentumkezelés** munkaterületen válassza az **Új dokumentum** elemet.
2. Az **Új sablon létrehozása** lap **Feltöltés** fül **Sablon** fülén válassza a **Tallózás** lehetőséget, és válassza ki a sablonként használni kívánt Excel-fájlt. A **Sablon** szakasz **Cím** és **Leírás** mezőit a program automatikusan kitölti. Illetve meghatározza az automatikusan létrehozott új ER-formátum konfiguráció nevét és leírását. Igény szerint módosíthatja ezeket a mezőket.
3. A **Dokumentumtípus** szakaszban, a **Név** mezőben adja meg az üzleti dokumentum típusát. Ez az érték lesz használva a helyes adatforrás kereséséhez (azaz ER modellkonfiguráció).

    ![Sablon lap az Új sablon létrehozása lap Feltöltés lapján.](./media/BDM_overview_new_UI_import_21.jpg)

4. Az **Adatforrás** fül **Szűrő** gyorslapján válassza a **Szűrő alkalmazása** lehetőséget. Az **Adatforrás** szakaszban a rendszer automatikusan kitölti a **Név** mezőt, vagy manuálisan kiválaszthat egy értéket. A szűrő használatával név, leírás, ország/régiókód és üzleti dokumentumtípus szerint keresheti meg a megfelelő adatforrásnevet.

    ![Adatforrás lap az Új sablon létrehozása lap Feltöltés lapján.](./media/BDM_overview_new_UI_import_31.jpg)

    > [!NOTE]
    > A **Szűrő** gyorslapot a helyes adatforrás kereséséhez használják (azaz ER modellkonfiguráció). Az összes szűrőmező szerkesztésével megkeresheti a feltöltött dokumentumnak leginkább megfelelő adatforrást.
    > 
    > A **Szűrő** gyorslap feltételeit **VAGY** feltételként használják.

5. Válassza a **Hozzárendelés** lap **Automatikus észlelés** elemét. A **Gyökér definíció** mezőt a rendszer automatikusan kitölti, vagy manuálisan kiválaszthat egy értéket. Ezen a fülön a sablon és a modell elemeinek záró leképezése látható.

    ![Hozzárendelés lap az Új sablon létrehozása lap Feltöltés lapján.](./media/BDM_overview_new_UI_import_41.jpg)

    > [!NOTE]
    > A **Sablonstruktúra** szakasz leképezése az adatforrás címkéinek vagy leírásának teljes egyezését használja a felhasználó nyelvén és a sablon cellanevében.

6. Válassza a **Dokumentum létrehozása** lehetőséget, és erősítse meg, hogy létre szeretne hozni egy sablont, és el szeretné indítani a szerkesztési folyamatot.

További tájékoztatás: [Üzleti dokumentumkezelés – áttekintés](er-business-document-management.md).

## <a name="upload-a-template-from-the-global-repository"></a>Sablon feltöltése a globális tárházból

A példa bemutatja, **·** **hogy** hogyan használható az Üzleti dokumentumkezelési munkaterület Új dokumentum gombjának használatával a Microsoft által biztosított ÉS a globális tárházban található ER formátumkonfigurációban létrehozott és szerkesztett sablon. Ebben a példában az aktív szolgáltató a Contoso, amely a Microsoft ER-formátumkonfigurációját használja. **Az** Új dokumentum kiválasztása után az Új sablon létrehozása lap Globális tárházból lapja megjeleníti azokat az üzleti dokumentumsablonokat, amelyek a globális tárházban vannak tárolva, **·** **de** az aktuális Pénzügyi példányból hiányoznak. Miután kiválasztotta a sablont, a rendszer a globális tárházból importálja az aktuális pénzügyi példányba, és létrehoz egy új szerkeszthető másolatot. A szerkesztett sablont a rendszer automatikusan generált új ER-formátumkonfigurációban tárolja.

1. Az **Üzleti dokumentumkezelés** munkaterületen válassza az **Új dokumentum** elemet.
2. Válassza ki **sablonként használni kívánt dokumentumot az Új sablonoldal importálása a Globális tárházból lapon,** és válassza ki **a** **Dokumentum létrehozása lehetőséget.**

    ![Importálás az Új sablonlap Globális tárház lapról](./media/BDM_overview_new_template22.png)

3. Az Üzenet mezőBen válassza az Igen **lehetőséget, és győződjön meg arról,** hogy a kijelölt dokumentumot importálni szeretné a globális tárházból az aktuális Pénzügyi példányba. Ha kéri az engedélyezést, kövesse a képernyőn látható utasításokat.
4. Az új párbeszédpanelen, a **Cím** mezőben, módosítsa a címet szükség szerint. A program az automatikusan létrehozott új ER-formátumkonfiguráció elnevezésére használja a címszöveget. A konfiguráció vázlatverziója (Fizetési megjegyzés (**Excel)** másolata) a módosított sablont fogja tartalmazni, és ezt az ER-formátumot fogja használni az aktuális felhasználóra. A rendszer alap ER formátumból származó nem módosított eredeti sablon alapján futtatja ezt az ER formátumot bármely más felhasználó számára.
5. A **Név** mezőben módosítsa az automatikusan létrehozandó szerkeszthető sablon első verziójának nevét.
6. A **Megjegyzés** mezőben módosítsa a szerkeszthető sablon automatikusan létrehozott verziójának megjegyzéseit.
7. A szerkesztési folyamat kezdetének jóváhagyásához kattintson az **OK** gombra.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

