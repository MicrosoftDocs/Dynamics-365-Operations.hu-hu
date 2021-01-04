---
title: Új dokumentum felhasználói felület az üzleti dokumentumkezelés modulban
description: Ez a témakör azt mutatja be, hogyan lehet használni az új dokumentum felhasználói felületet (UI) az elektronikus jelentési (ER) keretrendszer üzleti dokumentumkezelő funkciójában.
author: v-anamir
manager: AnnBe
ms.date: 05/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: 2cb6e0da4af07b9b8486bf1e5bda29523cbd08e9
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4681352"
---
# <a name="new-document-user-interface-in-business-document-management"></a>Új dokumentum felhasználói felület az üzleti dokumentumkezelés modulban

[!include [banner](../includes/banner.md)]

Az Üzleti dokumentumkezelés lehetővé teszi az üzleti felhasználók számára, hogy a Microsoft 365 szolgáltatás vagy a megfelelő Microsoft Office asztali alkalmazások segítségével szerkesszék az üzleti dokumentumok sablonjait. A szerkesztések lehetnek tervezési változtatások vagy új telepítések, illetve a felhasználók hozzáadhatnak helyőrzőket, hogy a forráskód módosítása nélkül is hozzáadhatók legyenek további adatok. Az üzleti dokumentumkezelés működésével kapcsolatos további tudnivalókat lásd: [Üzleti dokumentumkezelés – áttekintés.](er-business-document-management.md).

Az új dokumentum felhasználói felület (UI) egyértelműbb és kényelmesebben használható. Az **Üzleti dokumentum** terület csak az aktuális szolgáltatóhoz rendelkezésre álló sablonokat jeleníti meg.

Az **Új dokumentum** gomb lehetővé teszi a felhasználók számára, hogy egy másik szolgáltató által biztosított elektronikus jelentési (ER) formátum konfigurációban hozzanak létre és szerkesszenek egy sablont. Az ebben a témakörben szereplő példában a szolgáltató a Microsoft.

## <a name="make-the-new-document-ui-in-business-document-management-available"></a>Az új dokumentum kezelőfelület elérhetővé tétele az üzleti dokumentumkezelés modulban

Ha azt szeretné, hogy a program az új dokumentum kezelőfelületet használja az üzleti dokumentumkezelés modulban, akkor be kell kapcsolni az **Office-szerű UI-élmény az üzleti Dokumentumkezelés számára** funkciót a **Funkciókezelés** munkaterületen.

Kövesse az alábbi lépéseket a funkció bekapcsolásához az összes jogi személynél.

1. A **Funkciókezelés** munkaterületen, az **Új** lapon válassza ki a listán az **Office-szerű UI-élmény az üzleti Dokumentumkezelés számára** funkciót.
2. Válassza az **Engedélyezés most** lehetőséget a kiválasztott funkció bekapcsolásához.
3. Az új funkció eléréséhez frissítse a lapot.

### <a name="edit-templates-that-are-owned-by-other-providers"></a>Más szolgáltatók tulajdonában lévő sablonok szerkesztése

1. Az **Üzleti dokumentumkezelés** munkaterületen válassza az **Új dokumentum** elemet.

    ![Üzletidokumentum-kezelés munkaterület](./media/BDM_overview_new_template1.png)

2. A párbeszédpanelen válassza ki a sablonként használni kívánt dokumentumot, majd válassza a **Dokumentum létrehozása** elemet.

    ![Üzleti dokumentumok párbeszédpanel](./media/BDM_overview_new_template2.png)

3. Az új párbeszédpanelen, a **Cím** mezőben, módosítsa a címet szükség szerint. A program az automatikusan létrehozott új ER-formátumkonfiguráció elnevezésére használja a címszöveget. A konfiguráció vázlatverziója (**Customer FTI report (GER) másolata**) tartalmazza a szerkesztett sablont, és az ER-formátum futtatásá lesz használva az aktuális felhasználóhoz. A rendszer alap ER formátumból származó nem módosított eredeti sablon alapján futtatja ezt az ER formátumot bármely más felhasználó számára.
4. A **Név** mezőben módosítsa az automatikusan létrehozandó szerkeszthető sablon első verziójának nevét.
5. A **Megjegyzés** mezőben módosítsa a szerkeszthető sablon automatikusan létrehozott verziójának megjegyzéseit.
6. A szerkesztési folyamat kezdetének jóváhagyásához kattintson az **OK** gombra.

    ![Dokumentum-létrehozás párbeszédpanel](./media/BDM_overview_new_template3.png)

Az **Új dokumentum** gomb lehetővé teszi, hogy egy másik szolgáltató által biztosított elektronikus jelentési (ER) formátum konfigurációban hozzunk létre és szerkesszünk egy sablont. Ebben a példában a szolgáltató a Microsoft. Az **Új dokumentum** elem kiválasztásakor az aktuális és más szolgáltatók által birtokolt összes sablon látható. Miután kiválasztja a sablont, szerkesztésre megnyílik. Ezt követően a szerkesztett sablon egy új, automatikusan létrejövő ER formátumkonfigurációban lesz tárolva.

További tájékoztatás: [Üzleti dokumentumkezelés – áttekintés](er-business-document-management.md).
