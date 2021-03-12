---
title: Online funkcióprofil létrehozása
description: Ez a témakör azt mutatja be, hogyan lehet egy online funkcióprofilt létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 1b0afeabfecb60672156692f3cd809445624020c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969976"
---
# <a name="create-an-online-functionality-profile"></a>Online funkcióprofil létrehozása


[!include [banner](includes/banner.md)]

Ez a témakör áttekintést nyújt a Microsoft Dynamics 365 Commerce online funkcióprofiljainak beállításáról.

## <a name="overview"></a>Áttekintés

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
  
![Példa az online funkcióprofilra](media/online-functionality-profile.png)

## <a name="functions"></a>Függvények

- **Összesített termékek**: Ha engedélyezve van, ez a funkció lehetővé teszi a kosár számára, hogy frissítse a mennyiséget, ha ugyanazt a tételt többször hozáadták.
- **Fizetés nélküli pénztár engedélyezése**: Ha be van jelölve, ez a funkció kezeli a helyzetet, amikor a kosárba felvett cikkek ára 0,00 USD.
- **Vevő létrehozása aszinkron módban**: Ez egy örökölt beállítás, amely harmadik fél e-Commerce csatornákra vonatkozik, és nem alkalmazható a Dynamics 365 e-Commerce webhelyre.

## <a name="additional-resources"></a>További erőforrások

[Csatornák áttekintése](channels-overview.md)

[Csatornák beállításának előfeltételei](channels-prerequisites.md)

[Online csatorna beállítása](channel-setup-online.md)

[Kiskereskedelmi csatorna beállítása](channel-setup-retail.md)

[Hívásközpont csatorna beállítása](channel-setup-callcenter.md)
