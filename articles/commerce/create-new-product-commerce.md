---
title: Új termék létrehozása Commerce-ben
description: Ez a témakör azt mutatja be, hogyan lehet új terméket létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: eb2dd36c6149f2aa40305cd57eac060b232b09e5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412820"
---
# <a name="create-a-new-product-in-commerce"></a>Új termék létrehozása Commerce-ben


[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet új terméket létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A terméket elsősorban a termékszáma, a neve és a leírása határozza meg. Azonban más adatokra is szükség van egy termék vagy egy szolgáltatás leírásához:

## <a name="create-a-new-product"></a>Új termék létrehozása

1. A Navigációs ablaktáblán lépjen ide: **Modulok \> Kiskereskedelmi és kereskedelem \> Termékek és kategóriák \> Termékek kategóriák szerint**.
1. A műveleti ablaktáblán kattintson az **Új** elemre.
1. A **Termék típusa** legördülő listában válassza a **Cikk** vagy a **Szolgáltatás** elemet.
1. A **Termék altípusa** legördülő listában válassza a **Termék** (ha a termék nem tartalmaz változatokat) vagy az **Alaptermék** (ha a terméknek vannak változatai) lehetőséget.
1. A **Termékszám** mezőbe írjon be egy termékszámot ha még nincs előzetesen kitöltve.
1. A **Termék neve** mezőbe írjon be egy terméknevet.
1. A **Keresési név** mezőbe írjon be egy keresési nevet.
1. A **Kiskereskedelmi kategória** legördülő listából válassza ki a megfelelő kategóriát.
1. Ha a termék egy készlet , válassza az **Igen** lehetőséget a **Termékkészlet** alatt.
1. Ha a termék altípusa alaptermék, akkor a **Termék dimenzióját** állítsa be, hogy tartalmazza a támogatott változatokat. A lehetőségek többek között a **Szín**, **Méret**, **Stílus** és **Konfiguráció**. Szükség esetén előfordulhat, hogy további cikkdimenzió-csoportokat kell létrehoznia.
1. A **Konfigurációkategória** legördülő listából válassza ki a megfelelő beállítást.
1. Válassza ki az **OK** lehetőséget.

A következő képen egy példaként hozzáadott termék jelenik meg.

![Termék létrehozása](media/create-new-product.png)

A termék hozzáadását követően további adatok is megadhatók, például a **Termék leírása**, **Változatcsoportok**, **Dimenziócsoportok**, **Termékattribútumok** és **Kapcsolódó termékek**.

A következő kép egy termék további részleteit jeleníti meg.

![Termék részletei](media/create-new-product-2.png)

### <a name="create-product-variants"></a>Termékváltozatok létrehozása

Ha a termék altípusa **Alaptermék**, akkor konkrét változatokat kell létrehozni. 

Termékváltozatok létrehozásához kövesse az alábbi lépéseket.

1. A művelet ablaktáblán válassza ki a **Termékváltozatok** elemet.
1. Ha a műveleti ablaktáblában változatcsoportok lettek kiválasztva, válassza a **Változatjavaslatok* elemet.
1. Válassza ki a termékhez támogatandó változatokat.
1. Válassza a **Létrehozása** lehetőséget.

## <a name="release-a-product"></a>Egy termék kiadása

A termék értékesítéséhez először egy jogi személynek ki kell adni azt.

1. A termék lapon válassza ki a **Termékek kiadása** lehetőséget.

    ![Termék kiadása](media/create-new-product-3.png)

1. Válassza ki a kiadni kívánt terméket, majd kattintsona **Tovább** gombra.

    ![Válasszon egy terméket kiadásra](media/create-new-product-4.png)

1. Válassza ki a kiadni kívánt termékváltozatok készletét, majd kattintson a **Tovább** gombra.

    ![Változatok kiválasztása kiadásra](media/create-new-product-5.png)

1. Válassza ki a jogi személyt, majd kattintsona **Tovább** gombra.

    ![Jogi személy kiválasztása](media/create-new-product-6.png)

1. Válassza a **Befejezés** lehetőséget.

    ![Termékkiadás befejezése](media/create-new-product-7.png)

## <a name="configure-a-released-product"></a>Egy kiadott termék konfigurálása

Egy termék kiadása után a rendszer további konfigurációt igényel, amely tartalmazza az ár hozzáadását a termékhez.

1. A navigációs ablaktáblán lépjen ide: **Modulok \> Kiskereskedelmi és kereskedelem \> Termékek és kategóriák \> Kiadott termékek kategóriák szerint**.
1. Válassza ki a termék kategóriájának csomópontját a kiadott termékhez, majd válassza ki a terméket a listából.
1. A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.
1. A **Beszerzés** szakaszban konfigurálja a szükséges tulajdonságokat, többek között az **Egységet**, az **Árat** és a **Mennyiséget**.
1. A műveleti panelen jelölje be az **Ellenőrzés** jelölőnégyzetet, hogy a hiányzó mezők esetében ne jelentsen a rendszer hibát.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

A következő kép egy példát mutat egy kiadott termék beállítási konfigurációjáról.

![Kiadott termék konfigurálása](media/create-new-product-8.png)

## <a name="additional-resources"></a>További erőforrások

[Jogi személyek létrehozása](channels-legal-entities.md)

[Változatcsoport létrehozása](create-variant-group.md) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]