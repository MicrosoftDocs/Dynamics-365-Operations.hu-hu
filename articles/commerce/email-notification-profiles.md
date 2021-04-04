---
title: E-mail-értesítési profil beállítása
description: Ez a témakör azt mutatja be, hogyan lehet egy e-mailes értesítést létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.
author: bicyclingfool
manager: annbe
ms.date: 03/01/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: d82a1abe68ff6e162acb75c6fdc1e207af11c279
ms.sourcegitcommit: 88babb2fffe97e93bbde543633fc492120f2a4fc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/06/2021
ms.locfileid: "5555307"
---
# <a name="set-up-an-email-notification-profile"></a>E-mail-értesítési profil beállítása

[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet egy e-mailes értesítést létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.

Amikor csatornákat hoz létre, létrehozhat egy e-mail-értesítési profilt. Ily módon e-maileket küldhet a vevőknek különböző tranzakciós eseményekről, például a rendelés létrehozásáról, a rendelés szállítási állapotáról és a sikertelen kifizetésről.

Az e-mail konfigurálásával kapcsolatos további tudnivalókat lásd: [E-mail konfigurálása és küldése](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).

## <a name="create-an-email-notification-profile"></a>E-mail-értesítési profil létrehozása

E-mail értesítési profil létrehozásához hajtsa végre az alábbi lépéseket.

1. A navigációs ablaktáblán lépjen a **Modulok \> Kiskereskedelem és kereskedelem \> Központ beállítás \> Kereskedelmi e-mail értesítési profil** részhez.
1. A műveleti panelen kattintson az **Új** elemre.
1. Az **E-mail értesítési profilja** mezőbe írjon be egy nevet a profil meghatározásához.
1. Adjon meg egy releváns leírást a **Leírás** mezőben.
1. Az **Aktív** kapcsolót állítsa **Igen** értékre.

### <a name="create-an-email-template"></a>E-mail sablon létrehozása

Az e-mail-értesítés típusának engedélyezése előtt szervezeti e-mail sablont kell létrehoznia a Commerce központi felületén. Ez a sablon meghatározza az e-mail tárgyát, a feladót, az alapértelmezett nyelvet és az e-mail törzsét minden használni kívánt nyelvhez.

E-mail-sablon létrehozásához kövesse az alábbi lépéseket.

1. A navigációs ablaktáblán lépjen a **Modulok \> Kiskereskedelem és kereskedelem \> Központ beállítás \> Paraméterek \> Szervezeti e-mail-sablonok** részhez.
1. A műveleti ablaktáblán kattintson az **Új** elemre.
1. Az **E-mail azonosító** mezőbe írjon be egy azonosítót, amely segít a sablon azonosításában.
1. A **Küldő név** mezőben adja meg a küldő nevét.
1. Adjon meg egy releváns leírást az **E-mail leírása** mezőben.
1. A **Feladó e-mail címe** mezőbe írja be a feladók e-mail címét.
1. Az **Általános** szakaszban válassza ki az e-mail-sablon alapértelmezett nyelvét. A rendszer az alapértelmezett nyelvet használja, ha a megadott nyelven nem létezik honosított sablon.
1. Bontsa ki az **E-mail üzenet tartalma** szakaszt, és válassza az **Új** parancsot a sablon tartalmának létrehozásához. Minden tartalmi elemhez válassza ki a nyelvet, és adja meg az e-mail tárgysorát. Ha az e-mail törzset fog tartalmazni, győződjön meg arról, hogy be van jelölve a **Törzs létezik** jelölőnégyzet.
1. A műveleti ablaktáblán válassza ki az **E-mail üzenet** elemet az e-mail szövegtörzssablon megadásához.

A következő képen látható néhány példa az e-mail-sablon beállításaira.

![E-mail-sablon beállításai](media/email-template.png)

### <a name="create-an-email-event"></a>E-mail esemény létrehozása

E-mail-esemény létrehozásához kövesse az alábbi lépéseket.

1. A navigációs ablaktáblán lépjen a **Modulok \> Kiskereskedelem és kereskedelem \> Központ beállítás \> Kereskedelmi e-mail értesítési profil** részhez.
1. Keresse meg és jelölje ki a kívánt rekordot a listán. 
1. Válassza ki az e-mail sablont az **E-mail azonosítója** legördülő listából.
1. Válassza ki a megfelelő **E-mail-értesítés típusa** kiválasztást a legördülő listából.
1. Jelölje be az **Aktív** jelölőnégyzetet.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

A következő képen látható néhány példa az eseményértesítés beállításaira.

![Esemény értesítési beállításai](media/email-notification-profile.png)

### <a name="next-steps"></a>További lépések

E-mailek küldése előtt konfigurálnia kell a kimenő levelek szolgáltatását, és be kell állítania egy kötegelt feladatot. További információ: [E-mailek konfigurálása és küldése](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).


## <a name="additional-resources"></a>További erőforrások

[E-mail konfigurálása és küldése](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json)

[Csatornák áttekintése](channels-overview.md)

[Csatornák beállításának előfeltételei](channels-prerequisites.md)

[Szervezetek és szervezeti hierarchiák áttekintése](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
