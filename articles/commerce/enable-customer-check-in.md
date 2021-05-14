---
title: Vevői bejelentkezéssel kapcsolatos értesítések engedélyezése a pénztárnál (POS)
description: Ez a témakör azt ismerteti, hogyan lehet engedélyezni a Microsoft Dynamics 365 Commerce pénztár (POS) szolgáltatásban engedélyezni a vevői bejelentkezéssel kapcsolatos értesítéseket.
author: bicyclingfool
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ROBOTS: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: e4defc15d9ef198a361934d51e31016747dbb5ab
ms.sourcegitcommit: 593438a145672c55ff6a910eabce2939300b40ad
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/23/2021
ms.locfileid: "5937588"
---
# <a name="enable-customer-check-in-notifications-in-point-of-sale-pos"></a>Vevői bejelentkezéssel kapcsolatos értesítések engedélyezése a pénztárnál (POS)

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Ez a témakör azt ismerteti, hogyan lehet engedélyezni a Microsoft Dynamics 365 Commerce pénztár (POS) szolgáltatásban engedélyezni a vevői bejelentkezéssel kapcsolatos értesítéseket.

A szervezet a „rendelés készen áll a felvételre” e-mailjeiben egy hivatkozást vagy gombot biztosít, hogy a vevők értesítsék az üzletet arról, hogy a létesítményben vannak, és arra várnak, hogy kihozzák hozzájuk a csomagjukat. A vevők ezt követően megerősítést kapnak a bejelentkezésükről, és az üzlet értesítést kap a pénztár alkalmazásában. Ez a feladat arra kéri az értékesítési munkatársat, hogy a rendelést kivigye a vevő járművéhez. A vevőnek tehát nem kell bemennie az üzletbe.

A vevői bejelentkezés munkafolyamata a vevőkkel kapcsolatos további adatok gyűjtésére is beállítható – például a parkolási hely száma, a jármű márkája, modellje, színe, illetve a szállítási utasítások. A kiskereskedelmi üzlet munkatársa ezt az információt a rendelés teljesítésének megkönnyítése érdekében felhasználhatja.

## <a name="enable-customer-check-in"></a>Vevői bejelentkezés engedélyezése

Ha be van kapcsolva a vevői bejelentkezés funkció, a Commerce létrehoz egy rendelésvisszaigazolási azonosítót (más néven csatornahivatkozási azonosítót). Rendelés-visszaigazolási azonosítókat is létrehoz a pénztári (POS) csatornákon vagy hívásközponti csatornákon keresztül létrehozott rendelésekhez. 

A vevői bejelentkezés funkciónak a Commerce központi felületén történő bekapcsolásához kövesse az alábbi lépéseket.

1. Menjen a **Munkaterületek \> Funkciókezelés** lehetőségre.
2. Keresse meg a **Konzisztens csatornahivatkozási azonosító formátum létrehozása a csatornák között** funkciót. 
3. Válassza ki a funkciót, majd a tulajdonsások ablaktáblán válassza az **Engedélyezés most** lehetőséget. 

## <a name="create-a-check-in-confirmation-page"></a>Bejelentkezést megerősítő oldal létrehozása

Az e-kereskedelmi webhelyen létre kell hoznia egy új oldalt, amely a bejelentkezés megerősítésére szolgál. A további konfigurációkon keresztül a lap egy olyan képernyőt is tartalmazhat, amely további adatokat gyűjt a vevőktől, hogy megkönnyítse a rendelés teljesítését. Az oldal és a modul beállításával kapcsolatos további információért lásd: [Vevői bejelentkezés modul](check-in-pickup-module.md).

## <a name="configure-the-transactional-email-template"></a>A tranzakciós e-mail-sablon konfigurálása

Ahhoz a tranzakciós e-mail-sablonhoz, amit a vevők akkor kapnak, amikor a rendelésük készen áll a felvételre, egy **Itt vagyok** hivatkozást vagy gombot kell hozzáadnia. A vevők ezzel a hivatkozással vagy gombbal értesítik az üzletet, hogy megérkeztek, és felveszik a rendelésüket. 

A **Csomagolás befejezve** értesítési típushoz lekérdezett sablonhoz kapcsolható hivatkozás vagy gomb, valamint a határidős rendelés teljesítéséhez használt szállítási mód hozzáadása. A sablonban hozzon létre egy HTML-hivatkozást vagy gombot, amely a létrehozott bejelentkezést megerősítő lap URL-címére mutat. Íme, egy példa.

```
<a href="https://[YOUR_SITE_DOMAIN]/[CHECK-IN_CONFIRMATION_PAGE]?channelReferenceId=%channelreferenceid%&channelId=%channelid%&packingSlipId=%packingslipid%" target="_blank">I am here!</a>
```
Az e-mail-sablonok konfigurálási módjával kapcsolatos további információért lásd: [Tranzakciós e-mailek testreszabása kézbesítési mód szerint](customize-email-delivery-mode.md). 

## <a name="a-check-in-confirmation-task-is-created-in-pos"></a>A pénztárban létrejön egy bejelentkezést megerősítő feladat

Miután a vevő értesíti az üzletet, hogy megérkezett a rendelésfelvételre, megerősítést kap a bejelentkezésről, és a pénztárfeladatok listájában létrejön egy feladat azon üzlet számára, ahol a vevő felveszi a rendelést. A feladat a rendelés teljesítéséhez szükséges összes vevő- és rendelésinformációt tartalmazza. A feladatban az utasítás mezőben látható minden olyan információ, amely a vevőtől a kiegészítő információs űrlapon keresztül lett összegyűjtve. 

## <a name="additional-resources"></a>További erőforrások

[Bejelentkezés az átvételi modulba](check-in-pickup-module.md)
