---
title: Vevői bejelentkezéssel kapcsolatos értesítések engedélyezése a pénztárnál (POS)
description: Ez a témakör azt ismerteti, hogyan lehet engedélyezni a Microsoft Dynamics 365 Commerce pénztár (POS) szolgáltatásban engedélyezni a vevői bejelentkezéssel kapcsolatos értesítéseket.
author: bicyclingfool
ms.date: 12/03/2021
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
ms.openlocfilehash: 320e9d73ca98bf4ed22ac9bdff2fc34ae83223ec
ms.sourcegitcommit: 5f5a8b1790076904f5fda567925089472868cc5a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/03/2021
ms.locfileid: "7891412"
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

A **Csomagolás befejezve** értesítési típushoz lekérdezett sablonhoz kapcsolható hivatkozás vagy gomb, valamint a határidős rendelés teljesítéséhez használt szállítási mód hozzáadása. A sablonban hozzon létre egy HTML-hivatkozást vagy -gombot, amely a létrehozott bejelentkezést megerősítő lap URL-címére mutat, és amely tartalmazza a paraméterneveket és -értékeket, amint azt az alábbi példa mutatja.

`<a href="https://[YOUR_SITE_DOMAIN]/[CHECK-IN_CONFIRMATION_PAGE]?channelReferenceId=%confirmationid%&channelId=%channelid%&packingSlipId=%packingslipid%" target="_blank">I am here!</a>`

Az e-mail-sablonok konfigurálási módjával kapcsolatos további információért lásd: [Tranzakciós e-mailek testreszabása kézbesítési mód szerint](customize-email-delivery-mode.md). 

## <a name="a-check-in-confirmation-task-is-created-in-pos"></a>A pénztárban létrejön egy bejelentkezést megerősítő feladat

Miután a vevő értesíti az üzletet, hogy a felvételre jelen vannak, a bejelentkezéshez megjelenő oldalon egy visszaigazoló üzenet és egy opcionális QR-kód látható, amely tartalmazza a vevő rendelés-visszaigazolási azonosítóját. Ezzel egyidőben egy feladat jön létre a POS-ban található feladatlistán ahhoz az üzlethez, ahol a vevő felveszi a rendelést. Ez a feladat tartalmazza a rendelés teljesítéséhez szükséges összes vevő- és rendelési információt. A feladathoz az utasítás mezőben a kiegészítő adatképernyőn keresztül a vevőtől gyűjtött információk is megjelenik.

## <a name="end-to-end-testing"></a>Tesztelés vége

A vevői bejelentkezéshez meghatározott paramétereket és értékeket kell átadottnak lennie a be- és bejelentkezés API-jának. Ennek megfelelően a legegyszerűbb módszer a szolgáltatás tesztelése olyan környezetben, ahol tesztrendelést lehet létrehozni és csomagolni. Ily módon létre lehet hozva egy "felvételre kész rendelés" e-mailt, amely a szükséges paraméterneveket és értékeket tartalmazó URL-címet tartalmaz.

A vevői bejelentkezés funkció tesztelése érdekében kövesse az alábbi lépéseket.

1. A vevői bejelentkezés oldal létrehozása, majd a vevői bejelentkezés modul hozzáadása és konfigurálása. A további tudnivalókat lásd [a Be- és felvétel modulban](check-in-pickup-module.md). 
1. Ellenőrizze az oldalon, de ne tegye közzé.
1. Adja hozzá a következő hivatkozást egy e-mail sablonhoz, amelyet egy felvételes szállítási mód csomagolásának teljes értesítési típusa hív meg. További tájékoztatás: [Tranzakciós események e-mail sablonjainak létrehozása](email-templates-transactions.md).

    - **Termelés előtti (UAT) környezetek esetén: Adja hozzá a kódrészletet a témakör korábbi, Tranzakciós e-mail sablonjának**[konfigurálása](#configure-the-transactional-email-template) szakaszból.
    - **Éles környezetben: Adja meg a következő megjegyzést, hogy a meglévő vevőket ne befolyásolja** a probléma.

        `<!-- https://[DOMAIN]/[CHECK_IN_PAGE]?channelReferenceId=%confirmationid%&channelId=%pickupchannelid%&packingSlipId=%packingslipid%&preview=inprogress -->`

1. Rendelés létrehozása, amelyben meg van adva a válogatásos szállítás módja.
1. Amikor meg megkapja a csomagolási teljes értesítési típus által kiváltott e-mailt, a korábban megadott URL-címet kapó beküldési lap megnyitásával tesztelje a be- és bejelentkezést. Mivel az URL-cím tartalmazza a jelzőt, a rendszer a lap megtekintése előtt kéri a `&preview=inprogress` hitelesítést.
1. Adja meg a modul konfigurálásához szükséges további információkat.
1. Ellenőrizze, hogy a bejelentkezés visszaigazolási nézete megfelelően látható-e.
1. A rendelés felvételét lehetővé tárolják az üzlet POS-terminálját.
1. Válassza ki a csempe felvenni kívánt rendeléseit, és ellenőrizze, hogy **megjelenik**-e a rendelés.
1. Győződjön meg róla, hogy a részleteket tartalmazó ablakban megjelennek a betekintő modulban konfigurált további információk.

Miután ellenőrizte, hogy a vevői bejelentkezés funkció a végtől a végéig működik, kövesse ezeket a lépéseket.

1. A be check-in oldal közzététele
1. Ha éles környezetben tesztel, akkor az URL-cím meghagyása a "rendelés felvételre kész" e-mail sablonban, hogy az **I am here link vagy button** megjelenik. Ezután töltse be újra a sablont.

## <a name="additional-resources"></a>További erőforrások

[Bejelentkezés az átvételi modulba](check-in-pickup-module.md)

[Tranzakciós e-mailek testreszabása szállítási mód szerint](customize-email-delivery-mode.md)

[E-mail-sablonok létrehozása tranzakciós eseményekhez](email-templates-transactions.md)
