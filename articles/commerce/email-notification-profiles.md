---
title: E-mail-értesítési profil beállítása
description: Ez a témakör azt ismerteti, hogyan lehet létrehozni egy e-mail értesítési profilt a Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: db6c46d471e3b54982132df3e4819236833cf4a8
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9292135"
---
# <a name="set-up-an-email-notification-profile"></a>E-mail-értesítési profil beállítása

[!include [banner](includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet létrehozni egy e-mail értesítési profilt a Microsoft Dynamics 365 Commerce.

Amikor csatornákat hoz létre, létrehozhat egy e-mail-értesítési profilt. Az e-mail értesítési profil határozza meg az értékesítési tranzakció eseményeit (például a rendelés létrejöttét, a rendelésre csomagolt és a rendelés számlázott eseményeit), amelyekről értesítéseket fog küldeni a vevőknek. 

Az e-mail konfigurálásával kapcsolatos további tudnivalókat lásd: [E-mail konfigurálása és küldése](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).



## <a name="create-an-email-template"></a>E-mail sablon létrehozása

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

## <a name="create-an-email-notification-profile"></a>E-mail-értesítési profil létrehozása

E-mail értesítési profilnak a központi létrehozásához kövesse ezeket a lépéseket.

1. A navigációs ablaktáblán lépjen a **Modulok \> Kiskereskedelem és kereskedelem \> Központ beállítás \> Kereskedelmi e-mail értesítési profil** részhez.
1. A műveleti ablaktáblán kattintson az **Új** elemre.
1. Az **E-mail értesítési profilja** mezőbe írjon be egy nevet a profil meghatározásához.
1. Adjon meg egy releváns leírást a **Leírás** mezőben.
1. Az **Aktív** kapcsolót állítsa **Igen** értékre.

## <a name="add-a-notification-type"></a>Értesítéstípus hozzáadása

E-mail-esemény létrehozásához kövesse az alábbi lépéseket.

1. A navigációs ablaktáblán lépjen a **Modulok \> Kiskereskedelem és kereskedelem \> Központ beállítás \> Kereskedelmi e-mail értesítési profil** részhez.
1. A **Retail e-mail értesítési beállításai csoportban válassza** az Új **lehetőséget**.
1. Válassza ki a megfelelő **E-mail-értesítés típusa** kiválasztást a legördülő listából.
1. Válassza ki a fent létrehozott e-mail sablont az **e-mail azonosító** legördülő listából.
1. Jelölje be az **Aktív** jelölőnégyzetet.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

A következő képen látható néhány példa az eseményértesítés beállításaira.

![Esemény értesítési beállításai.](media/email-notification-profile.png)


## <a name="schedule-a-recurring-email-notification-process-job"></a>Ismétlődő e-mail értesítési folyamat feladatának ütemezése

Az e-mail értesítések elküldését úgy küldheti el, **hogy fut a Kiskereskedelmi rendelés feldolgozása e-mail értesítési** feladat.

A következő lépésekkel beállíthatja a központi kötegelt feladatot a tranzakciós e-mailek küldésére.

1. Menjen a **Retail and Commerce \> Retail and Commerce IT \> e-mail címére és az értesítésküldési értesítésbe \>**.
1. A Kiskereskedelmi rendelés **feldolgozása e-mail értesítési** párbeszédpanelen válassza az Ismétlődés **lehetőséget**.
1. Az Ismétlődés **definiálása** párbeszédpanelen válassza a Nincs **záró dátum lehetőséget**.
1. Az Ismétlődési **szabály területen válassza** a Percek **lehetőséget**, majd **állítsa** **a Számlálás mezőt 1-re.** Ezek a beállítások biztosítják, hogy az e-mail értesítések feldolgozása a lehető leggyorsabb legyen.
1. Az **OK gombra** való visszatéréshez térjen **vissza a Kiskereskedelmi rendelés feldolgozása e-mail értesítési párbeszédpanelre**.
1. A **feladat beállításának befejezéséhez kattintson az OK** gombra.

## <a name="next-steps"></a>További lépések

E-mail küldése előtt be kell állítania a kimenő levelezési szolgáltatást. További információ: [E-mailek konfigurálása és küldése](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).

## <a name="additional-resources"></a>További erőforrások

[E-mail konfigurálása és küldése](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json)

[Csatornák áttekintése](channels-overview.md)

[Csatornák beállításának előfeltételei](channels-prerequisites.md)

[Szervezetek és szervezeti hierarchiák áttekintése](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
