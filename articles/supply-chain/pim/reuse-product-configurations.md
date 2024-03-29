---
title: Termékkonfigurációk újrahasználása
description: Megadhatja, hogy szeretne-e automatikusan újrahasználni egy meglévő konfigurációt egy termékhez. Miután a felhasználó befejezte a konfigurációs munkamenetet, a rendszer ellenőrzi, hogy létezik-e már a felhasználói beállításokkal megegyező konfiguráció. Ha a rendszer talál megfelelő konfigurációt, újból felhasználásra kerül a Konfigurációazonosító, a megfelelő anyagjegyzék (AJ) és az útvonal.
author: t-benebo
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: 201813
ms.assetid: 4985e308-7824-41fc-83fd-fd0bdae888e3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0898bd1832fa7007fc3aa265beee2e930f157a39
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7577408"
---
# <a name="reuse-product-configurations"></a>Termékkonfigurációk újrahasználása

[!include [banner](../includes/banner.md)]

Megadhatja, hogy szeretne-e automatikusan újrahasználni egy meglévő konfigurációt egy termékhez. Miután a felhasználó befejezte a konfigurációs munkamenetet, a rendszer ellenőrzi, hogy létezik-e már a felhasználói beállításokkal megegyező konfiguráció. Ha a rendszer talál megfelelő konfigurációt, újból felhasználásra kerül a Konfigurációazonosító, a megfelelő anyagjegyzék (AJ) és az útvonal.

## <a name="requirements-for-reusing-configurations"></a>Konfigurációk újbóli használatának feltételei

A konfigurációk újbóli felhasználásához meg kell adnia az összetevőkre és az attribútumokra vonatkozó következő adatokat a **Termékkonfigurálási modell részletei** lapon:

-   **Összetevők és alösszetevők** – az **Általános** gyorslapon a **Konfigurációk újbóli használata** mezőben válassza az **Igen** lehetőséget.
-   **Attribútumok** – az **Attribútumok** gyorslapon jelölje be a **Felvétel az újrahasználhatók közé** lehetőséget. Ez a lehetőség csak akkor jelenik meg, ha a kapcsolódó összetevő újbóli felhasználása engedélyezve van. Amennyiben nem választ ki újból felhasználandó attribútumokat, a konfigurációt mindig újból felhasználja a rendszer, függetlenül a konfigurációs munkamenet során végzett felhasználói beállításoktól. A meglévő konfiguráció termékattribútum-értékeinek meg kell egyeznie a felhasználói beállításokkal. Ha például egy felhasználó a konfigurációs munkamenet során a **Kék** színt választja ki, a rendszer ellenőrzi, hogy az összetevő meglévő konfigurációjában jelen van-e a kék szín.

## <a name="resetting-configuration-reuse"></a>Konfigurációk újbóli használatának alaphelyzetbe állítása
Amikor a konfigurációk újbóli használatát alaphelyzetbe állítja, a korábban létrehozott konfigurációk nem számítanak használhatónak. Érdemes a konfigurációk újbóli használatának alaphelyzetbe állítása, ha az Anyagjegyzék vagy útvonal módosult, de a kapcsolódó attribútumok nem módosultak. A konfigurációk újbóli használatának alaphelyzetbe állítását az összetevő **Általános** gyorslapján végezheti el.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]