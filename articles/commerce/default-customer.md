---
title: Alapértelmezett vevő létrehozása
description: Ez a témakör azt mutatja be, hogyan lehet a Microsoft Dynamics 365 Commerce megoldásban egy csatorna létrehozásakor használandó alapértelmezett vevőt létrehozni.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: ecdf4e5618d3397527bf83977857fbe3f8dbb265
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799179"
---
# <a name="create-a-default-customer"></a>Alapértelmezett vevő létrehozása

[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet a Microsoft Dynamics 365 Commerce megoldásban egy csatorna létrehozásakor használandó alapértelmezett vevőt létrehozni.

Csatorna létrehozásakor meg kell adni egy alapértelmezett vevőt. Az alapértelmezett vevő egyszerűen létrehozható a vevőcsoport és a vevői címjegyzék létrehozása után.

## <a name="create-a-customer-group"></a>Vevőcsoport létrehozása

Ha még nem léteznek vevőcsoportok, létrehozhat egyet. A példák lehetnek a különböző vevőcsoportok, például nagykereskedelem, kiskereskedelem, internet, alkalmazottak.

Ügyfélcsoport létrehozásához tegye a következőket.

1. A navigációs ablaktáblán lépjen a **Modulok \> Kiskereskedelem és kereskedelem \> Ügyfelek \> Ügyfélcsoportok** részhez.
1. A műveleti ablaktáblán kattintson az **Új** elemre.
1. Az **Ügyfélcsoport** mezőbe írja be az ügyfélcsoport azonosítóját.
1. Ha szükséges, akkor adjon meg egy leírást a **Leírás** mezőben.
1. Ha szükséges, akkor adjon meg egy értéket a **Fizetési feltételek** mezőben.
1. **A számla esedékességének dátuma és a fizetési dátum közötti idő** mezőben adja meg a megfelelő értéket.
1. Ha szükséges, az **Alapértelmezett adócsoport** mezőben adjon meg egy adócsoportot.
1. Szükség szerint jelölje be **Az árak tartalmazzák az áfát** jelölőnégyzetet.
1. Ha szükséges, írja be a megfelelő értéket az **Alapértelmezett leírási indok** mezőbe.

A következő kép több konfigurált vevői csoportot mutat be.

![Vevőcsoportok](media/customer-groups.png)

## <a name="create-a-customer-address-book"></a>Új ügyfélcímjegyzék létrehozása

A vevőnek címjegyzékhez kell tartoznia. Ha még nincs létrehozva, akkor létre kell hozni egyet.

Ügyfélcímjegyzék létrehozásához kövesse az alábbi lépéseket.

1. A navigációs ablaktáblán lépjen a **Modulok \> Kiskereskedelem és kereskedelem \> Csatornák beállítása \> Címjegyzékek** részhez.
1. A műveleti ablaktáblán kattintson az **Új** elemre.
1. A **Név** mezőben adjon meg egy nevet.
1. Adjon meg egy leírást a **Leírás** mezőben.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

A következő kép egy példát mutat a címjegyzékre.

![Címjegyzék](media/address-book.png)

## <a name="create-a-default-customer&quot;></a>Alapértelmezett vevő létrehozása

Alapértelmezett ügyfél létrehozásához tegye a következőket.

1. A navigációs ablaktáblán lépjen a **Modulok \> Kiskereskedelem és kereskedelem \> Minden ügyfél \> Ügyfélcsoportok** részhez.
1. A műveleti ablaktáblán kattintson az **Új** elemre.
1. A **Típus** legördülő listán válassza a Személy elemet.
1. A **Vevőfiók** legördülő listából válassza ki vagy adja meg a számlaszámot (például &quot;100001").
1. Az **Utónév** legördülő listából válassza ki vagy írja be a nevet (például "Alapértelmezett").
1. A **Középső név** legördülő listából válassza ki vagy írja be a nevet (például "Kiskereskedelmi").
1. A **Vezetéknév** legördülő listából válassza ki vagy írja be a nevet (például "Ügyfél").
1. A **Pénznem** legördülő listából válassza ki vagy írja be a pénznem nevét (például "USD").
1. A **Pénznem** legördülő listában válassza ki a korábban létrehozott ügyfélcsoportot.
1. A **Címjegyzékek** legördülő listából válasszon ki egy meglévő vevői címjegyzéket.
1. A mentéshez válassza a **Mentés** parancsot, majd térjen vissza a vevő adatainak képernyőjére az új vevő számára.

> [!NOTE]
> Nem szükséges hozzáadni egy alapértelmezett vevő címét.

A következő kép egy példát mutat az ügyféllétrehozásra.

![Alapértelmezett vevő létrehozása](media/default-customer-creation.png)

A következő kép egy alapértelmezett vevői konfigurációt mutat be.

![Vevői mintakonfiguráció](media/default-customer-configuration1.png)

A vevő részletek képernyőjén található alapértelmezett értékek többsége maradhat, de a két értéket módosítani kell.

1. A vevő részletes adatai képernyő bontsa ki a **Értékesítési rendelés alapértelmezései** elemet.
1. A **Webhely** legördülő listából válassza ki vagy adja meg az előre konfigurált webhelyet.
1. A **Raktár** legördülő listából válassza ki vagy adja meg az előre konfigurált raktárat.

A következő kép egy példát mutat az ügyfélkonfigurációra.

![Példa ügyfélkonfiguráció](media/default-customer-configuration2.png)

## <a name="additional-resources"></a>További erőforrások

[Csatornák áttekintése](channels-overview.md)

[Csatornák beállításának előfeltételei](channels-prerequisites.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
