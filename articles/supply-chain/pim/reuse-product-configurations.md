---
title: "Termékkonfigurációk újrahasználása"
description: "Megadhatja, hogy szeretne-e automatikusan újrahasználni egy meglévő konfigurációt egy termékhez. Miután a felhasználó befejezte a konfigurációs munkamenetet, a rendszer ellenőrzi, hogy létezik-e már a felhasználói beállításokkal megegyező konfiguráció. Ha a rendszer talál megfelelő konfigurációt, újból felhasználásra kerül a Konfigurációazonosító, a megfelelő anyagjegyzék (AJ) és az útvonal."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 201813
ms.assetid: 4985e308-7824-41fc-83fd-fd0bdae888e3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: c447440c33c1f80c6056974086b90d3b43e8499e
ms.contentlocale: hu-hu
ms.lasthandoff: 02/07/2018

---

# <a name="reuse-product-configurations"></a>Termékkonfigurációk újrahasználása

[!INCLUDE [banner](../includes/banner.md)]

Megadhatja, hogy szeretne-e automatikusan újrahasználni egy meglévő konfigurációt egy termékhez. Miután a felhasználó befejezte a konfigurációs munkamenetet, a rendszer ellenőrzi, hogy létezik-e már a felhasználói beállításokkal megegyező konfiguráció. Ha a rendszer talál megfelelő konfigurációt, újból felhasználásra kerül a Konfigurációazonosító, a megfelelő anyagjegyzék (AJ) és az útvonal.

<a name="requirements-for-reusing-configurations"></a>Konfigurációk újbóli használatának feltételei
---------------------------------------

A konfigurációk újbóli felhasználásához meg kell adnia az összetevőkre és az attribútumokra vonatkozó következő adatokat a **Termékkonfigurálási modell részletei**lapon:

-   **Összetevők és alösszetevők** – az **Általános** gyorslapon a **Konfigurációk újbóli használata** mezőben válassza az **Igen** lehetőséget.
-   **Attribútumok** – az **Attribútumok** gyorslapon jelölje be a **Felvétel az újrahasználhatók közé** lehetőséget. Ez a lehetőség csak akkor jelenik meg, ha a kapcsolódó összetevő újbóli felhasználása engedélyezve van. Amennyiben nem választ ki újból felhasználandó attribútumokat, a konfigurációt mindig újból felhasználja a rendszer, függetlenül a konfigurációs munkamenet során végzett felhasználói beállításoktól. A meglévő konfiguráció termékattribútum-értékeinek meg kell egyeznie a felhasználói beállításokkal. Ha például egy felhasználó a konfigurációs munkamenet során a **Kék** színt választja ki, a rendszer ellenőrzi, hogy az összetevő meglévő konfigurációjában jelen van-e a kék szín.

## <a name="resetting-configuration-reuse"></a>Konfigurációk újbóli használatának alaphelyzetbe állítása
Amikor a konfigurációk újbóli használatát alaphelyzetbe állítja, a korábban létrehozott konfigurációk nem számítanak használhatónak. Érdemes a konfigurációk újbóli használatának alaphelyzetbe állítása, ha az Anyagjegyzék vagy útvonal módosult, de a kapcsolódó attribútumok nem módosultak. A konfigurációk újbóli használatának alaphelyzetbe állítását az összetevő **Általános** gyorslapján végezheti el.




