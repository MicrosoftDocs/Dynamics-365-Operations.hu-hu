---
title: Microsoft Office-stílusú felhasználói felület az üzleti dokumentumkezelésben (videót tartalmaz)
description: Ez a témakör elmagyarázza, hogyan lehet használni az új felhasználói felületet az Elektronikus jelentések (ER) keretrendszert az Üzleti dokumentumkezelő funkciójában.
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
ms.openlocfilehash: e33830e2147d92ad5ee53ad11da55a50613b8ef9
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8074741"
---
# <a name="microsoft-office-style-user-interface-in-business-document-management"></a>Microsoft Office stílusú felhasználói felület az Üzleti dokumentumkezelés modulban

[!include [banner](../includes/banner.md)]

Az Üzleti dokumentumkezelés lehetővé teszi az üzleti felhasználók számára, hogy a Microsoft Office 365 szolgáltatás vagy a megfelelő Microsoft Office asztali alkalmazások segítségével szerkesszék az üzleti dokumentumok sablonjait. A szerkesztések lehetnek tervezési változtatások vagy új telepítések, illetve a felhasználók hozzáadhatnak helyőrzőket, hogy a forráskód módosítása nélkül is hozzáadhatók legyenek további adatok. Az üzleti dokumentumkezelés működésével kapcsolatos további tudnivalókat lásd: [Üzleti dokumentumkezelés – áttekintés.](er-business-document-management.md).

Az új felhasználói felület (UI) egyértelműbb és kényelmesebben használható. A **Üzleti dokumentum** terület csak azokat a sablonokat mutatja, amelyek az aktuális tulajdonában vannak [aktív](tasks/er-configuration-provider-mark-it-active-2016-11.md)[szolgáltató](general-electronic-reporting.md#Provider) és a jelenlegi példányban található Dynamics 365 Finance. Az előző felhasználói felületen a **Sablon** lap felsorolja az összes szolgáltatóhoz elérhető sablont. Emellett minden olyan sablont megjelenít, amelyet az azonos szerepkörű felhasználók létrehoztak és megszerkesztettek.

Használhatja a **Új dokumentum** gombot a **Üzleti dokumentumkezelés** munkaterület egy sablon létrehozásához és szerkesztéséhez [Elektronikus jelentéstétel (ER)](general-electronic-reporting.md) formátum [konfigurációt](general-electronic-reporting.md#Configuration) amelyet egy másik szolgáltató biztosít, és az aktuális Finance példányban található, vagy új sablont tölthet fel egy Excel-munkafüzetből. Ezenkívül a 10.0.25 és újabb verziókban használhatja a **Új dokumentum** gombbal létrehozhat és szerkeszthet egy sablont ER formátumú konfigurációban, amely a következőben van tárolva [Globális adattár](general-electronic-reporting.md#Repository).

A témakör példáiban az aktív szolgáltató a Contoso, és ennek segítségével hozhat létre egy olyan sablont, amely a Microsoft által biztosított sablonon alapul. Másik lehetőségként készíthet egy sablont az Excel-formátumban feltöltött saját sablonjából.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWAVQg]

A [Hozzon létre új üzleti dokumentumot az Üzleti dokumentumkezelés segítségével](https://youtu.be/gAIYl-mM_pw) videó (fent látható) szerepel a [Finance and Operations lejátszási lista](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) elérhető YouTube.

## <a name="make-the-new-document-ui-in-business-document-management-available"></a>Az új dokumentum kezelőfelület elérhetővé tétele az üzleti dokumentumkezelés modulban

Ha azt szeretné, hogy a program az új dokumentum kezelőfelületet használja az üzleti dokumentumkezelés modulban, akkor be kell kapcsolni az **Office-szerű UI-élmény az üzleti Dokumentumkezelés számára** funkciót a **Funkciókezelés** munkaterületen.

Kövesse az alábbi lépéseket a funkció bekapcsolásához az összes jogi személynél.

1. A **Funkciókezelés** munkaterületen, az **Összes** lapon válassza ki a listán az **Office-szerű UI-élmény az üzleti Dokumentumkezelés számára** funkciót.
2. Válassza az **Engedélyezés most** lehetőséget a kiválasztott funkció bekapcsolásához.
3. Az új funkció eléréséhez frissítse a lapot.

## <a name="add-or-activate-a-provider"></a>Adjon hozzá vagy aktiváljon szolgáltatót

Az üzleti dokumentumok minden sablonja egy ER formátumú konfigurációban van tárolva, amely egy adott konfigurációs szolgáltató tulajdonaként van megjelölve. Amikor új sablont hoz létre, egy új ER formátum konfiguráció jön létre annak tárolására. Ezért ehhez a konfigurációhoz meg kell határozni a szolgáltatót. Erre a célra az ER keretrendszer aktív szolgáltatóját használják. Ha nincs szolgáltató az ER-ben, létrehozhat egyet. Ha nincs *aktív* szolgáltatót, aktiválhatja a meglévő szolgáltatók egyikét. Amikor szükséges, megnyílik egy párbeszédpanel a szolgáltató hozzáadására vagy aktiválására, miközben elkezdi hozzáadni az új sablont.

### <a name="add-a-new-provider"></a>Új szolgáltató hozzáadása

Új szolgáltató létrehozásához kövesse az alábbi lépéseket a **Konfigurációs szolgáltató** párbeszéd:

1.  A **Válassza ki a konfigurációs szolgáltatót** lapon, a **Név** mezőbe írja be az új szolgáltató nevét.
2.  Ban,-ben **Internet cím** mezőbe írja be az új szolgáltató internetcímét (URL-jét). 
3.  Válassza ki az **OK** lehetőséget.

    ![Új szolgáltató létrehozása az üzleti dokumentumkezelésben.](./media/bdm_create_provider.png)

A hozzáadott szolgáltató automatikusan aktiválódik.

### <a name="activate-a-provider"></a>Aktiváljon egy szolgáltatót

Szolgáltató aktiválásához kövesse az alábbi lépéseket a **Konfigurációs szolgáltató** párbeszéd:

1.  A **Válassza ki a konfigurációs szolgáltatót** lapon, a **Konfigurációs szolgáltató** mezőben válassza ki a szolgáltatót.
2.  Válassza ki az **OK** lehetőséget.

    ![Szolgáltató aktiválása az üzleti dokumentumkezelésben.](./media/bdm_choose_provider.png)

A kiválasztott szolgáltató aktiválódik.

> [!NOTE]
> Minden üzleti dokumentumkezelési sablon egy ER formátumú konfigurációban található, amely a szolgáltatóra, mint konfigurációs szerzőre hivatkozik. Ezért minden sablonhoz aktív szolgáltatóra van szükség.

## <a name="edit-a-template-that-is-owned-by-another-provider"></a>Szerkesszen egy másik szolgáltatóhoz tartozó sablont

Ez a példa bemutatja, hogyan kell használni a **Új dokumentum** gombot a **Üzleti dokumentumkezelés** munkaterület egy sablon létrehozásához és szerkesztéséhez egy másik szolgáltató által biztosított és az aktuális Finance példányban található ER formátumú konfigurációban. Ebben a példában az aktív szolgáltató a Contoso, amely a Microsoft által biztosított ER formátumkonfigurációt használja. Miután kiválasztottad **Új dokumentum**, a **Válassza ki** fülön a **Hozzon létre egy új sablont** oldalon látható az aktuális Finance példány összes olyan sablonja, amely az aktuális szolgáltató és más szolgáltatók tulajdonában van. Válassza ki a sablont a megnyitásához. Ezután létrehozhat egy új szerkeszthető másolatot a sablonról. A szerkesztett sablon egy új ER formátumú konfigurációban kerül tárolásra, amely automatikusan generálódik.

1. Az **Üzleti dokumentumkezelés** munkaterületen válassza az **Új dokumentum** elemet.

    ![Üzletidokumentum-kezelés munkaterület.](./media/BDM_overview_new_template1.png)

2. A **Hozzon létre egy új sablont** oldalon, a **Válassza ki** lapon válassza ki a sablonként használni kívánt dokumentumot, majd válassza ki **Dokumentum létrehozása**.

    ![Üzleti dokumentumok párbeszédpanel.](./media/BDM_overview_new_template2.png)

3. Az új párbeszédpanelen, a **Cím** mezőben, módosítsa a címet szükség szerint. A program az automatikusan létrehozott új ER-formátumkonfiguráció elnevezésére használja a címszöveget. A konfiguráció vázlatverziója (**Customer FTI report (GER) másolata**) tartalmazza a szerkesztett sablont, és az ER-formátum futtatásá lesz használva az aktuális felhasználóhoz. A rendszer alap ER formátumból származó nem módosított eredeti sablon alapján futtatja ezt az ER formátumot bármely más felhasználó számára.
4. A **Név** mezőben módosítsa az automatikusan létrehozandó szerkeszthető sablon első verziójának nevét.
5. A **Megjegyzés** mezőben módosítsa a szerkeszthető sablon automatikusan létrehozott verziójának megjegyzéseit.
6. A szerkesztési folyamat kezdetének jóváhagyásához kattintson az **OK** gombra.

    ![Dokumentum-létrehozás párbeszédpanel.](./media/BDM_overview_new_template3.png)

## <a name="upload-a-template-that-uses-an-existing-excel-workbook"></a>Töltsön fel egy sablont, amely egy meglévő Excel-munkafüzetet használ

Ez a példa bemutatja, hogyan kell használni a **Új dokumentum** gombot a **Üzleti dokumentumkezelés** munkaterület egy sablon létrehozásához és szerkesztéséhez ER formátumú konfigurációban a rendelkezésre álló Excel-munkafüzet alapján. Ebben a példában az aktív szolgáltató a Contoso, és Ön az ER-t használja [adatmodell](er-overview-components.md#data-model-component) és ER [modell leképezés](er-overview-components.md#model-mapping-component) a Microsoft által biztosított konfigurációk. Miután kiválasztottad **Új dokumentum**, válaszd ki a **Feltöltés** fülön a **Hozzon létre egy új sablont** oldalon. Itt megadhatja az Excel-munkafüzet feltöltésének részleteit. Miután feltöltötte az Excel-munkafüzetet, az üzleti dokumentumsablonná alakul, amely megnyílik szerkesztésre. A szerkesztett sablon egy új ER formátumú konfigurációban kerül tárolásra, amely automatikusan generálódik.

A sablon feltöltése előtt kövesse ezeket a lépéseket, és adja meg a szükséges adatokat.

1. Az **Üzleti dokumentumkezelés** munkaterületen válassza az **Új dokumentum** elemet.
2. Az **Új sablon létrehozása** lap **Feltöltés** fül **Sablon** fülén válassza a **Tallózás** lehetőséget, és válassza ki a sablonként használni kívánt Excel-fájlt. A **Sablon** szakasz **Cím** és **Leírás** mezőit a program automatikusan kitölti. Illetve meghatározza az automatikusan létrehozott új ER-formátum konfiguráció nevét és leírását. Igény szerint módosíthatja ezeket a mezőket.
3. A **Dokumentumtípus** szakaszban, a **Név** mezőben adja meg az üzleti dokumentum típusát. Ez az érték lesz használva a helyes adatforrás kereséséhez (azaz ER modellkonfiguráció).

    ![Sablon lap az Új sablon létrehozása oldal Feltöltés lapján.](./media/BDM_overview_new_UI_import_21.jpg)

4. Az **Adatforrás** fül **Szűrő** gyorslapján válassza a **Szűrő alkalmazása** lehetőséget. Az **Adatforrás** szakaszban a rendszer automatikusan kitölti a **Név** mezőt, vagy manuálisan kiválaszthat egy értéket. A szűrő használatával név, leírás, ország/régiókód és üzleti dokumentumtípus szerint keresheti meg a megfelelő adatforrásnevet.

    ![Adatforrás lap az Új sablon létrehozása oldal Feltöltés lapján.](./media/BDM_overview_new_UI_import_31.jpg)

    > [!NOTE]
    > A **Szűrő** gyorslapot a helyes adatforrás kereséséhez használják (azaz ER modellkonfiguráció). Az összes szűrőmező szerkesztésével megkeresheti a feltöltött dokumentumnak leginkább megfelelő adatforrást.
    > 
    > A **Szűrő** gyorslap feltételeit **VAGY** feltételként használják.

5. Válassza a **Hozzárendelés** lap **Automatikus észlelés** elemét. A **Gyökér definíció** mezőt a rendszer automatikusan kitölti, vagy manuálisan kiválaszthat egy értéket. Ezen a fülön a sablon és a modell elemeinek záró leképezése látható.

    ![Leképezés lap az Új sablon létrehozása oldal Feltöltés lapján.](./media/BDM_overview_new_UI_import_41.jpg)

    > [!NOTE]
    > A **Sablonstruktúra** szakasz leképezése az adatforrás címkéinek vagy leírásának teljes egyezését használja a felhasználó nyelvén és a sablon cellanevében.

6. Válassza a **Dokumentum létrehozása** lehetőséget, és erősítse meg, hogy létre szeretne hozni egy sablont, és el szeretné indítani a szerkesztési folyamatot.

További tájékoztatás: [Üzleti dokumentumkezelés – áttekintés](er-business-document-management.md).

## <a name="upload-a-template-from-the-global-repository"></a>Töltsön fel egy sablont a globális adattárból

Ez a példa bemutatja, hogyan kell használni a **Új dokumentum** gombot a **Üzleti dokumentumkezelés** munkaterület egy sablon létrehozásához és szerkesztéséhez a Microsoft által biztosított és a globális lerakatban található ER formátumú konfigurációban. Ebben a példában az aktív szolgáltató a Contoso, amely a Microsoft által biztosított ER formátumkonfigurációt használja. Miután kiválasztottad **Új dokumentum**, a **Importálás a globális adattárból** fülön a **Hozzon létre egy új sablont** oldalon látható az összes üzleti dokumentumsablon, amely a globális lerakatban tárolva van, de hiányzik az aktuális Finance példányból. Miután kiválasztott egy sablont, a rendszer importálja azt a globális tárhelyből az aktuális Finance példányba, hogy új szerkeszthető másolatot hozzon létre. A szerkesztett sablon egy új ER formátumú konfigurációban kerül tárolásra, amely automatikusan generálódik.

1. Az **Üzleti dokumentumkezelés** munkaterületen válassza az **Új dokumentum** elemet.
2. A **Hozzon létre egy új sablont** oldalon, a **Importálás a globális adattárból** lapon válassza ki a sablonként használni kívánt dokumentumot, majd válassza ki **Dokumentum létrehozása**.

    ![Importálás a Globális tárhelyről az Új sablon létrehozása oldalon.](./media/BDM_overview_new_template22.png)

3. Az üzenetmezőben válassza a lehetőséget **Igen** annak megerősítésére, hogy importálni kívánja a kiválasztott dokumentumot a globális tárolóból az aktuális Finance példányba. Ha a rendszer felhatalmazást kér, kövesse a képernyőn megjelenő utasításokat.
4. Az új párbeszédpanelen, a **Cím** mezőben, módosítsa a címet szükség szerint. A program az automatikusan létrehozott új ER-formátumkonfiguráció elnevezésére használja a címszöveget. Ennek a konfigurációnak a vázlatos verziója (**Gyűjteménylevél jegyzet (Excel) Másolat**) tartalmazza a szerkesztett sablont, és az ER formátum futtatására lesz használva az aktuális felhasználó számára. A rendszer alap ER formátumból származó nem módosított eredeti sablon alapján futtatja ezt az ER formátumot bármely más felhasználó számára.
5. A **Név** mezőben módosítsa az automatikusan létrehozandó szerkeszthető sablon első verziójának nevét.
6. A **Megjegyzés** mezőben módosítsa a szerkeszthető sablon automatikusan létrehozott verziójának megjegyzéseit.
7. A szerkesztési folyamat kezdetének jóváhagyásához kattintson az **OK** gombra.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
