---
title: Microsoft Office stílusú felhasználói felület az Üzleti dokumentumkezelés modulban
description: Ez a témakör elmagyarázza, hogyan lehet használni az új felhasználói felületet az Elektronikus jelentések (ER) keretrendszert az Üzleti dokumentumkezelő funkciójában.
author: v-anamir
ms.date: 04/12/2021
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
ms.openlocfilehash: e6c5081f71a18dfac83b7aea950395436b42f50e
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881036"
---
# <a name="microsoft-office-style-user-interface-in-business-document-management"></a>Microsoft Office stílusú felhasználói felület az Üzleti dokumentumkezelés modulban

[!include [banner](../includes/banner.md)]

Az Üzleti dokumentumkezelés lehetővé teszi az üzleti felhasználók számára, hogy a Microsoft 365 szolgáltatás vagy a megfelelő Microsoft Office asztali alkalmazások segítségével szerkesszék az üzleti dokumentumok sablonjait. A szerkesztések lehetnek tervezési változtatások vagy új telepítések, illetve a felhasználók hozzáadhatnak helyőrzőket, hogy a forráskód módosítása nélkül is hozzáadhatók legyenek további adatok. Az üzleti dokumentumkezelés működésével kapcsolatos további tudnivalókat lásd: [Üzleti dokumentumkezelés – áttekintés.](er-business-document-management.md).

Az új felhasználói felület (UI) egyértelműbb és kényelmesebben használható. Az **Üzleti dokumentum** terület csak az aktuális szolgáltatóhoz rendelkezésre álló sablonokat jeleníti meg. Az előző felhasználói felületen a **Sablon** fül felsorolja az összes szolgáltató számára elérhető sablonokat. Emellett minden olyan sablont megjelenít, amelyet az azonos szerepkörű felhasználók létrehoztak és megszerkesztettek.

Az **Új dokumentum** gomb használatával egy másik szolgáltató által biztosított elektronikus jelentési (ER) formátum konfigurációban létrehozhat és szerkeszthet egy sablont. Az ebben a témakörben szereplő példában a szolgáltató a Microsoft. Másik lehetőségként készíthet egy sablont az Excel-formátumban feltöltött saját sablonjából.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWAVQg]

Az [Új üzleti dokumentum létrehozása az Üzleti dokumentumkezelés](https://youtu.be/gAIYl-mM_pw) videó (lásd fent) megtalálható a [Finance and Operations lejátszási listán](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW): YouTube.

## <a name="make-the-new-document-ui-in-business-document-management-available"></a>Az új dokumentum kezelőfelület elérhetővé tétele az üzleti dokumentumkezelés modulban

Ha azt szeretné, hogy a program az új dokumentum kezelőfelületet használja az üzleti dokumentumkezelés modulban, akkor be kell kapcsolni az **Office-szerű UI-élmény az üzleti Dokumentumkezelés számára** funkciót a **Funkciókezelés** munkaterületen.

Kövesse az alábbi lépéseket a funkció bekapcsolásához az összes jogi személynél.

1. A **Funkciókezelés** munkaterületen, az **Összes** lapon válassza ki a listán az **Office-szerű UI-élmény az üzleti Dokumentumkezelés számára** funkciót.
2. Válassza az **Engedélyezés most** lehetőséget a kiválasztott funkció bekapcsolásához.
3. Az új funkció eléréséhez frissítse a lapot.

## <a name="edit-templates-that-are-owned-by-other-providers"></a>Más szolgáltatók tulajdonában lévő sablonok szerkesztése

1. Az **Üzleti dokumentumkezelés** munkaterületen válassza az **Új dokumentum** elemet.

    ![Üzletidokumentum-kezelés munkaterület](./media/BDM_overview_new_template1.png)

2. A **Kiválasztás** fülön válassza ki a sablonként használni kívánt dokumentumot, majd válassza a **Dokumentum létrehozása** elemet.

    ![Üzleti dokumentumok párbeszédpanel](./media/BDM_overview_new_template2.png)

3. Az új párbeszédpanelen, a **Cím** mezőben, módosítsa a címet szükség szerint. A program az automatikusan létrehozott új ER-formátumkonfiguráció elnevezésére használja a címszöveget. A konfiguráció vázlatverziója (**Customer FTI report (GER) másolata**) tartalmazza a szerkesztett sablont, és az ER-formátum futtatásá lesz használva az aktuális felhasználóhoz. A rendszer alap ER formátumból származó nem módosított eredeti sablon alapján futtatja ezt az ER formátumot bármely más felhasználó számára.
4. A **Név** mezőben módosítsa az automatikusan létrehozandó szerkeszthető sablon első verziójának nevét.
5. A **Megjegyzés** mezőben módosítsa a szerkeszthető sablon automatikusan létrehozott verziójának megjegyzéseit.
6. A szerkesztési folyamat kezdetének jóváhagyásához kattintson az **OK** gombra.

    ![Dokumentum-létrehozás párbeszédpanel](./media/BDM_overview_new_template3.png)

Az **Új dokumentum** gomb lehetővé teszi, hogy egy másik szolgáltató által biztosított elektronikus jelentési (ER) formátum konfigurációban hozzunk létre és szerkesszünk egy sablont. Ebben a példában a szolgáltató a Microsoft. Az **Új dokumentum** elem kiválasztásakor az aktuális és más szolgáltatók által birtokolt összes sablon látható. Miután kiválasztja a sablont, szerkesztésre megnyílik. Ezt követően a szerkesztett sablon egy új, automatikusan létrejövő ER formátumkonfigurációban lesz tárolva.

## <a name="upload-a-template-that-uses-an-existing-excel-format"></a>Meglévő Excel-formátumot használó sablon feltöltése
A sablon feltöltése előtt kövesse ezeket a lépéseket, és adja meg a szükséges adatokat.

1. Az **Üzleti dokumentumkezelés** munkaterületen válassza az **Új dokumentum** elemet.

    ![Üzletidokumentum-kezelés munkaterület](./media/BDM_overview_new_template1.png)
    
2. Az **Új sablon létrehozása** lap **Feltöltés** fül **Sablon** fülén válassza a **Tallózás** lehetőséget, és válassza ki a sablonként használni kívánt Excel-fájlt. A **Sablon** szakasz **Cím** és **Leírás** mezőit a program automatikusan kitölti. Illetve meghatározza az automatikusan létrehozott új ER-formátum konfiguráció nevét és leírását. Igény szerint módosíthatja ezeket a mezőket.
3. A **Dokumentumtípus** szakaszban, a **Név** mezőben adja meg az üzleti dokumentum típusát. Ez az érték lesz használva a helyes adatforrás kereséséhez (azaz ER modellkonfiguráció).

    ![Sablon fül](./media/BDM_overview_new_UI_import_21.jpg)

4. Az **Adatforrás** fül **Szűrő** gyorslapján válassza a **Szűrő alkalmazása** lehetőséget. Az **Adatforrás** szakaszban a rendszer automatikusan kitölti a **Név** mezőt, vagy manuálisan kiválaszthat egy értéket. A szűrő használatával név, leírás, ország/régiókód és üzleti dokumentumtípus szerint keresheti meg a megfelelő adatforrásnevet.

    ![Adatforrás fül](./media/BDM_overview_new_UI_import_31.jpg)
    
    > [!NOTE]
    > A **Szűrő** gyorslapot a helyes adatforrás kereséséhez használják (azaz ER modellkonfiguráció). Az összes szűrőmező szerkesztésével megkeresheti a feltöltött dokumentumnak leginkább megfelelő adatforrást.
    > 
    > A **Szűrő** gyorslap feltételeit **VAGY** feltételként használják.
    
5. Válassza a **Hozzárendelés** lap **Automatikus észlelés** elemét. A **Gyökér definíció** mezőt a rendszer automatikusan kitölti, vagy manuálisan kiválaszthat egy értéket. Ezen a fülön a sablon és a modell elemeinek záró leképezése látható.

    ![Leképezési fül](./media/BDM_overview_new_UI_import_41.jpg)
    
   > [!NOTE]
   > A **Sablonstruktúra** szakasz leképezése az adatforrás címkéinek vagy leírásának teljes egyezését használja a felhasználó nyelvén és a sablon cellanevében.

6. Válassza a **Dokumentum létrehozása** lehetőséget, és erősítse meg, hogy létre szeretne hozni egy sablont, és el szeretné indítani a szerkesztési folyamatot.

További tájékoztatás: [Üzleti dokumentumkezelés – áttekintés](er-business-document-management.md).

Ha nincs szolgáltató az Elektronikus jelentéskészítésben, létrehozhat egyet. Ha nincs aktív szolgáltató, kiválaszthat és aktiválhat egyet.

- Szolgáltató létrehozásához módosítsa a szolgáltató nevét a **Név** mezőben, frissítse az új szolgáltató internetcímét az **Internetcím** mezőben, majd a megerősítéshez kattintson az **OK** gombra.

    ![Új szolgáltató létrehozása a BDM-ben](./media/bdm_create_provider.png)
    
- A meglévő szolgáltató aktiválásához válassza ki a szolgáltató nevét a **Konfigurációszolgáltató** mezőben, és válassza az **OK** gombot, a szolgáltató aktiválásához.

    ![Szolgáltató aktiválása a BDM-ben](./media/bdm_choose_provider.png)

> [!NOTE]
> Minden egyes BDM-sablon a konfiguráció szerzőjeként hivatkozik a szolgáltatóra. Ezért van szükség egy aktív szolgáltatóra a sablonhoz.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
