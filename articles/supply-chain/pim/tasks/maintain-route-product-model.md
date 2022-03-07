---
title: Termékmodell útvonalának karbantartása
description: Ezen eljárás futtatásához szükség van egy már létező termékkonfigurációs modellre.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCRouteOperationDetails, WrkCtrCapabilityLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 45c6b1e6e75645bb17ce4defa0bca0e6d2131b6e
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921265"
---
# <a name="maintain-route-for-a-product-model"></a>Termékmodell útvonalának karbantartása

[!include [banner](../../includes/banner.md)]

Ezen eljárás futtatásához szükség van egy már létező termékkonfigurációs modellre. Ez az eljárás az USMF bemutatócég felső kategóriás hangszóró modelljét használva vezeti Önt végig a folyamaton.

## <a name="add-a-route-operation"></a>Útvonalművelet hozzáadása

1. Lépjen a **Termékinformáció-kezelés \> Termékek \> Termékkonfigurációs modellek** elemre.
1. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Válassza ki a Felső kategóriás modellt ehhez a gyakorlathoz.  
1. A listában válassza ki a kiválasztott sorból a hivatkozást.
1. Bontsa ki az **Útvonalműveletek** szakaszt.
1. Válassza a **Hozzáadás** lehetőséget.
1. Írjon be egy értéket a **Név** mezőbe.
1. Írjon egy értéket a **Leírás** mezőbe.
1. Válassza a **Mentés** lehetőséget.

## <a name="enter-route-operation-details"></a>Útvonalművelet részleteinek megadása

1. **Útvonalművelet részleteinek** kiválasztása.
1. A **Műveletek** mezőben adjon meg vagy válasszon ki egy értéket.
1. A **Műveletszám** mezőben adjon meg egy számot.
    * A műveleti számok határozzák meg az útvonalsorrendet.  
    * Egy útvonalművelet egyes tulajdonságainak lehet statikus értékük, vagy hozzá lehet rendelni őket egy attribútumhoz. Az attribútumhoz rendelés következtében az érték a konfiguráció része lesz.  
1. Az **Útvonalcsoport** mezőben adjon meg, vagy válasszon ki egy értéket.
    * Az útvonalcsoport határozza meg az alapvető viselkedést a költségszámítási, a felhasználás és beállítás esetében.  
1. Válassza ki a **Beállítás** fület.
1. Válassza ki az **Időpontok** fület.
1. A **Folyamat menny.** mezőben adjon meg egy számot.
    * Határozza meg, hogy mennyi lesz feldolgozva egy művelet során.  
1. Az **Órák/idő** mezőben adjon meg egy számot.
    * Adja meg az időarányt.  
1. Jelölje be a **Beállít** jelölőnégyzetet.
1. Adjon meg egy számot a **Futási idő** mezőben.
    * Határozza meg a feldolgozási időt a megadott mennyiséghez.  
1. Válassza ki az **Erőforrás-követelmények** fület.
1. Válassza a **Hozzáadás** lehetőséget.
1. A listában jelölje meg a kiválasztott sort.
1. A **Követelmény típusa** mezőben válasszon ki egy lehetőséget.
    * Döntse el, hogy akar-e megadni konkrét erőforrásokat vagy adottságokat, amelyeket fel kell dolgozniuk.  
1. A **Követelmény** mezőben adjon meg vagy válasszon ki egy értéket.
1. Válassza ki az **OK** lehetőséget.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]