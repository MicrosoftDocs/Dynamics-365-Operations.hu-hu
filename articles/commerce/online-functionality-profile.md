---
title: Online funkcióprofil létrehozása
description: Ez a témakör azt ismerteti, hogyan lehet online funkcióprofilt létrehozni a következőben:Microsoft Dynamics 365 Commerce
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 5ce81900cd0648132748167d03906afc64e97f25
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276801"
---
# <a name="create-an-online-functionality-profile"></a>Online funkcióprofil létrehozása

[!include [banner](includes/banner.md)]

Ez a témakör áttekintést nyújt a következő online funkcióprofilok beállításávalról:Microsoft Dynamics 365 Commerce

Az online funkcióprofil különböző beállításokat biztosít az online csatornákhoz. Minden online csatornának meg kell adnia egy online funkcióprofilt.

## <a name="create-an-online-functionality-profile"></a>Online funkcióprofil létrehozása

A következő eljárás bemutatja, hogyan lehet online funkcióprofilt létrehozni a Commerce Headquarters alkalmazásból.

1. A navigációs ablaktáblán ugorjon a **Modulok \> Csatorna beállítás \> Online áruház beállítása \> Funkcióprofilok** elemre.
1. A műveleti ablaktáblán kattintson az **Új** elemre.
1. A **Profil** mezőbe írja be a profil azonosítóját.
1. A **Leírás** mezőbe írjon be egy értéket (a lenti példában szereplő képen: „Kalandorbolt-profil”).
1. A **Funkciók** részben szükség szerint módosítsa a **KOSÁR**, **KISKERESKEDELMI VEVŐK** vagy **PÉNZTÁR** beállításokat.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

A következő kép egy példát mutat az online funkcióprofilra.
  
![Példa az online funkcióprofilra.](media/online-functionality-profile.png)

## <a name="functions"></a>Funkciók

- **Összesített termékek**: Ha engedélyezve van, ez a funkció lehetővé teszi a kosár számára, hogy frissítse a mennyiséget, ha ugyanazt a tételt többször hozáadták.
- **Fizetés nélküli pénztár engedélyezése**: Ha be van jelölve, ez a funkció kezeli a helyzetet, amikor a kosárba felvett cikkek ára 0,00 USD.
- **Vevő létrehozása aszinkron módban**: Ez egy örökölt beállítás, amely harmadik fél e-Commerce csatornákra vonatkozik, és nem alkalmazható a Dynamics 365 e-Commerce webhelyre.

## <a name="additional-resources"></a>További erőforrások

[Csatornák áttekintése](channels-overview.md)

[Csatornák beállításának előfeltételei](channels-prerequisites.md)

[Online csatorna beállítása](channel-setup-online.md)

[Kiskereskedelmi csatorna beállítása](channel-setup-retail.md)

[Hívásközpont csatorna beállítása](channel-setup-callcenter.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
