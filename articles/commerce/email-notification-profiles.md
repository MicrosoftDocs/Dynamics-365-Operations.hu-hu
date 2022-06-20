---
title: E-mail-értesítési profil beállítása
description: Ez a témakör azt ismerteti, hogyan lehet létrehozni egy e-mail értesítési profilt a Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 109adcc4e8b49c665bd14ecab2b7cc56cebd2291
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8878486"
---
# <a name="set-up-an-email-notification-profile"></a>E-mail-értesítési profil beállítása

[!include [banner](includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet létrehozni egy e-mail értesítési profilt a Microsoft Dynamics 365 Commerce.

Amikor csatornákat hoz létre, létrehozhat egy e-mail-értesítési profilt. Az e-mail értesítési profil határozza meg az értékesítési tranzakció eseményeit (például a rendelés létrejöttét, a rendelésre csomagolt és a rendelés számlázott eseményeit), amelyekről értesítéseket fog küldeni a vevőknek. 

Az e-mail konfigurálásával kapcsolatos további tudnivalókat lásd: [E-mail konfigurálása és küldése](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).

## <a name="create-an-email-notification-profile"></a>E-mail-értesítési profil létrehozása

E-mail értesítési profil létrehozásához hajtsa végre az alábbi lépéseket.

1. A navigációs ablaktáblán lépjen a **Modulok \> Kiskereskedelem és kereskedelem \> Központ beállítás \> Kereskedelmi e-mail értesítési profil** részhez.
1. A műveleti panelen kattintson az **Új** elemre.
1. Az **E-mail értesítési profilja** mezőbe írjon be egy nevet a profil meghatározásához.
1. Adjon meg egy releváns leírást a **Leírás** mezőben.
1. Az **Aktív** kapcsolót állítsa **Igen** értékre.

### <a name="create-an-email-template"></a>E-mail sablon létrehozása

Az e-mail értesítési típus engedélyezése előtt létre kell hoznia egy szervezeti e-mail sablont a Commerce Headquarters minden olyan értesítéstípusához, amely támogatott. Ez a sablon minden támogatott nyelvhez meghatározza az e-mail tárgyát, a feladót, az alapértelmezett nyelvet és az e-mail szöveg törzsét.

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

![E-mail-sablon beállításai.](media/email-template.png)

Az e-mail sablonok létrehozásával kapcsolatos további tudnivalókat [lásd: E-mail sablonok létrehozása a tranzakciós eseményekhez](email-templates-transactions.md). 

### <a name="create-an-email-event"></a>E-mail esemény létrehozása

E-mail-esemény létrehozásához kövesse az alábbi lépéseket.

1. A navigációs ablaktáblán lépjen a **Modulok \> Kiskereskedelem és kereskedelem \> Központ beállítás \> Kereskedelmi e-mail értesítési profil** részhez.
1. Keresse meg és jelölje ki a kívánt rekordot a listán. 
1. Válassza ki az e-mail sablont az **E-mail azonosítója** legördülő listából.
1. Válassza ki a megfelelő **E-mail-értesítés típusa** kiválasztást a legördülő listából.
1. Jelölje be az **Aktív** jelölőnégyzetet.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

A következő képen látható néhány példa az eseményértesítés beállításaira.

![Esemény értesítési beállításai.](media/email-notification-profile.png)

> [!NOTE]
> Az ügyfél által létrehozott értesítési típushoz testre kell szabni az e-mailben küldött értesítéseket.

### <a name="schedule-a-recurring-email-notification-process-job"></a>Ismétlődő e-mail értesítési folyamat feladatának ütemezése

Az e-mail értesítések elküldését úgy küldheti el, **hogy fut a Kiskereskedelmi rendelés feldolgozása e-mail értesítési** feladat.

Ha még **nem** tette meg, állítsa be a Kiskereskedelmi rendelés feldolgozása e-mail értesítési feladatot a Commerce Headquarters szolgáltatásban.

1. Menjen a **Retail and Commerce \> Retail and Commerce IT \> e-mail címére és az értesítésküldési értesítésbe \>**.
1. A Kiskereskedelmi rendelés **feldolgozása e-mail értesítési** párbeszédpanelen válassza az Ismétlődés **lehetőséget**.
1. Az Ismétlődés **definiálása** párbeszédpanelen válassza a Nincs **záró dátum lehetőséget**.
1. Az Ismétlődési **szabály területen válassza** a Percek **lehetőséget**, majd **állítsa** **a Számlálás mezőt 1-re.** Ezek a beállítások biztosítják, hogy az e-mail értesítések feldolgozása a lehető leggyorsabb legyen.
1. Az **OK gombra** való visszatéréshez térjen **vissza a Kiskereskedelmi rendelés feldolgozása e-mail értesítési párbeszédpanelre**.
1. A **feladat beállításának befejezéséhez kattintson az OK** gombra.

### <a name="next-steps"></a>További lépések

E-mailek küldése előtt konfigurálnia kell a kimenő levelek szolgáltatását, és be kell állítania egy kötegelt feladatot. További információ: [E-mailek konfigurálása és küldése](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).

## <a name="additional-resources"></a>További erőforrások

[E-mail konfigurálása és küldése](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json)

[Csatornák áttekintése](channels-overview.md)

[Csatornák beállításának előfeltételei](channels-prerequisites.md)

[Szervezetek és szervezeti hierarchiák áttekintése](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
