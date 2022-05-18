---
title: Üzleti partner felhasználóinak kezelése a B2B e-commerce webhelyeken a Dynamics 365 Értékesítések segítségével
description: Ez a témakör azt ismerteti, hogyan Microsoft Dynamics lehet a 365 Értékesítés segítségével kezelni az üzleti partner jóváhagyásait a Dynamics 365 Commerce vállalathoz –vállalaton keresztül (B2B) webhelyeken.
author: shajain
ms.date: 2/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: shajain
ms.search.validFrom: 2022-01-31
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 540e8f26d7f2a08060a3839f9e4f97bf8ddcafac
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/04/2022
ms.locfileid: "8692563"
---
# <a name="manage-business-partner-users-on-b2b-e-commerce-websites-using-dynamics-365-sales"></a>Üzleti partner felhasználóinak kezelése a B2B e-commerce webhelyeken a Dynamics 365 Értékesítések segítségével

[!include [banner](../../includes/banner.md)]

Ez a témakör azt ismerteti, hogyan Microsoft Dynamics lehet a 365 Értékesítés segítségével kezelni az üzleti partner jóváhagyásait a Dynamics 365 Commerce vállalathoz –vállalaton keresztül (B2B) webhelyeken. Azok a szervezetek, amelyek már beleesnek a Dynamics 365 értékesítési megoldásba, a B2B e-commerce üzleti partner jóváhagyási folyamatában használhatók az érdeklődő- és lehetőségkoncepciók.

A B2B [üzleti partner jóváhagyási folyamatával kapcsolatos háttér-információkért lásd az üzleti partner felhasználóinak kezelése a B2B e-commerce webhelyeken](manage-b2b-users.md).

A potenciális üzleti partnerek úgy kezdeményezhetik a berakodási folyamatot egy B2B e-commerce webhelyre, hogy egy, a B2B webhelyen található hivatkozáson keresztül benyújtására vonatkozó kérést küldjenek el. A rendszer a kérés elküldését követően, és a kapcsolódó feladatokat (**például A P-0001** **és** a Rendelések és csatornaigénylések szinkronizálása) futtatja a Commerce Headquartersban, **a** rendszer menti a berakodó kérést a Commerce Headquarters Minden potenciális vevő lapján. Ezt követően az üzleti partner potenciális vevőinek jóváhagyási folyamata az Értékesítés folyamatban 2005 200 200 200 000 lehet.

Az Értékesítés és Commerce közötti integráció engedélyezése után az üzleti partner potenciális vevő létrehozása a Commerce rendszerében egy érdeklődő létrehozását okozza az *Értékesítésben*.

A következő ábra egy példát mutat be egy értékesítési partner potenciális vevőinek érdeklődő-létrehozási oldalára.

![Érdeklődő-létrehozási lap a Dynamics 365 értékesítésben](../media/LeadInSales.png)

Az ábra a Kapcsolattartó **területen** látható a berakodó személy, **a** Vállalat szakasz pedig a szervezetet. Az Idősor szakasz **egyik megjegyzése** azt jelzi, hogy az érdeklődőt két írásos infrastruktúra generálta. Mivel ezt a kettős írású infrastruktúra hozta létre, **ez az érdeklődő nem fog megjelenni a Saját nyitott érdeklődők** legördülő listában. Ehelyett egy Minden Commerce B2B érdeklődő **nevű új nézetben jelenik meg**.

Az Értékesítés folyamat általános érdeklődő-minősítési folyamata szerint, ha egy felhasználó "minősíti" az érdeklődőt, *lehetőségrekordot*, kapcsolattartó-rekordot *és* számlarekordot *hoz* létre. A kettős írású infrastruktúra segítségével lehet a kapcsolattartót és a számlarekordokat a Commerce rendszernek megírni. A kapcsolattartó személy típusú *vevőként* jön létre, és a vállalat a szervezet típusának vevőjeként *jön* létre. Ha egy felhasználó a lehetőséghez **a Bezárás wonként** lehetőséget választja, a potenciális vevőt jóváhagyják a Commerce rendszer. Egy potenciális vevő jóváhagyásának hatására létrejön egy vevőhierarchia.

Minden fennmaradó üzleti folyamat a Commerce rendszerből történik. Ezek közé tartozik az üzleti partnernek küldött e-mail üzenet, a felhasználók hitelkeret-kezelése, valamint további felhasználók hozzáadása a B2B webhelyhez. Ha azonban egy felhasználó nem minősíti megfelelőnek az érdeklődőt, vagy az érdeklődő minősítése helyett elvesztettként jelöli meg a lehetőséget, a Commerce rendszer a "elutasított" jelzést jelzi, és a rendszer a felkérésnek egy elutasító e-mailt küld.

## <a name="enable-integration-between-sales-and-commerce"></a>Az Értékesítés és Commerce közötti integráció engedélyezése

Az Értékesítés és Commerce integráció a kettős írású infrastruktúrán alapul. Ennek megfelelően engedélyezni és dolgozni kell a kettős írást, hogy az egyik rendszerben létrehozott vevőket beíratják a másik rendszerbe. A két írásos infrastruktúrával kapcsolatos további tudnivalókat lásd [a Kettős írású infrastruktúra témakörben](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-overview).

Miután a kettős írású beállítást befejezte, [Microsoft AppSource](https://appsource.microsoft.com/)[a bevezetési partner keresheti a Dual-write Commerce Solutions nevű megoldást](https://partner.microsoft.com/dashboard/commercial-marketplace/offers/7ca1d8c9-dc79-4cb7-a82e-8dc96a25acca/overview). Telepítse a csomagot a szokásos telepítési varázslóval, majd tesztelje úgy, hogy létrehoz egy potenciális vevőt egy B2B webhelyen. Miután létrejött a potenciális vevő, ellenőrizze, **hogy** a Minden potenciális vevő megjelenik-e a Commerce rendszerében, majd ellenőrizze, hogy a potenciális vevő érdeklődőként jelenik-e meg az Értékesítésben.

## <a name="additional-resources"></a>További erőforrások

[Üzleti partner típusú felhasználók kezelése a B2B e-kereskedelmi webhelyeken](manage-b2b-users.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
