---
title: Ingyenes termékvásárlás konfigurálása
description: Ez a témakör azt ismerteti, hogyan kell konfigurálni egy terméket úgy, hogy ingyenes termékként megvásárolható legyen a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
ms.date: 10/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 760b97a895758073c8ffd1209be4a5f7df0f13a8
ms.sourcegitcommit: 9c2bc045eafc05b39ed1a6b601ccef48bd62ec55
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/14/2021
ms.locfileid: "7919450"
---
# <a name="configure-a-product-to-be-purchased-for-free"></a>Ingyenes termékvásárlás konfigurálása

[!include [banner](includes/banner.md)]


Ez a témakör azt ismerteti, hogyan kell konfigurálni egy terméket úgy, hogy ingyenes termékként megvásárolható legyen a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="configure-the-product"></a>A termék konfigurálása

Ha ingyen szeretne értékesíteni egy terméket a Dynamics 365 Commerce alkalmazásban, nullára (0) kell állítania az árát. Ezenkívül konfigurálni kell a termék **Nullás ár érvényes** beállítását is.

A Commerce központ **Nullás ár érvényes** beállításának konfigurálását a következő lépések szerint lehet elvégezni.

1. Nyissa meg a következőt: **Kiskereskedelem és kereskedelem \> Termékek és kategóriák \> Kiadott termékek kategóriák szerint**.
1. Ugorjon arra a termékre, amelyet ingyenesen szeretne értékesíteni. 
1. A termékoldal **Commerce** szakaszában állítsa a **Nullás ár érvényes** lehetőséget **Igen** beállításra.

A következő ábra egy olyan termék példáját mutatja be, ahol a **Nullás ár érvényes** beállítás beállítása **Igen**.

![Példa olyan termékre, ahol a Nullás ár érvényes beállítás beállítása Igen.](./media/Zero-price.png)

## <a name="configure-the-online-stores-functionality-profile"></a>Az online áruház funkcióprofiljának konfigurálása

Az ingyenes tranzakciók feldolgozása előtt konfigurálnia kell a **Fizetés nélküli pénztár engedélyezése** beállítást az áruház funkcióprofiljában, hogy a fizetés nélküli tranzakciók engedélyezve legyenek. További tájékoztatás a funkcióprofilok létrehozásáról: [Online funkcióprofil létrehozása](online-functionality-profile.md).

A Commerce központ **Fizetés nélküli pénztár engedélyezése** beállításának konfigurálását a következő lépések szerint lehet elvégezni.

1. Ugorjon a következő elemre: **Kiskereskedelem és kereskedelem \> Csatorna beállítása \> Online üzlet beállítása**.
1. Az üzlet funkcióprofilját tároló lapon, a **Fizetés** alatt állítsa a **Fizetés nélküli pénztár engedélyezése** beállítást **Igen** értékre.

A következő ábra egy olyan online áruház profilját mutatja be, ahol a **Fizetés nélküli pénztár engedélyezése** beállítása **Igen**.

![Példa egy olyan online áruházi profilra, ahol a Fizetés nélküli pénztár engedélyezése beállítása Igen.](./media/Zero-price-profile.png)

## <a name="additional-resources"></a>További erőforrások

[Kiskereskedelmi értékesítési ár kezelése](price-management.md)

[Online funkcióprofil létrehozása](online-functionality-profile.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
