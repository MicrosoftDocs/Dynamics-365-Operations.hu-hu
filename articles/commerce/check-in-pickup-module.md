---
title: Bejelentkezés átvételre modul
description: Ez a témakör ismerteti az átvételre való bejelentkezés modult, és bemutatja, hogyan konfigurálhatjuk a Microsoft Dynamics 365 Commerce alkalmazásban.
author: bicyclingfool
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ROBOTS: ''
audience: Application user
ms.reviewer: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: f6359f41f3b97325db4fda083dc32d39839811297a96a1f2d99a93990c00afae
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6747465"
---
# <a name="check-in-for-pickup-module"></a>Bejelentkezés átvételre modul

[!include [banner](includes/banner.md)]

Ez a témakör ismerteti az átvételre való bejelentkezés modult, és bemutatja, hogyan konfigurálhatjuk a Microsoft Dynamics 365 Commerce alkalmazásban.

Az átvételre való bejelentkezés modul megerősítő oldalt biztosít olyan ügyfeleknek, akik a Dynamics 365 Commerce ügyfélbejelentkezési lehetőségeinek használatával értesítik az üzletet az érkezésükről. Az átvételre való bejelentkezés modullal egy olyan űrlap is konfigurálható, amely további adatokat gyűjt az ügyfelektől a kiszállítás leegyszerűsítése érdekében. Az adatok között szerepel a vevő parkolóhelyének száma, valamint járművének évjárata és modellje. 

## <a name="module-properties"></a>Modul tulajdonságai

| Tulajdonság neve | Értékek | Leírás |
|---------------|--------|-------------|
| Visszaigazolás szövege | Szöveges sztring | A bejelentkezést megerősítő oldalon megjelenő fejléc tartalma. |
| QR-kód megjelenítése | **Igaz** vagy **Hamis** | Ha a tulajdonság **Igaz** értékre van állítva, a bejelentkezést megerősítő oldalon a rendelés visszaigazolási azonosítóját képviselő QR-kód jelenik meg. |
| További információk címsor | Szöveges sztring | A fejléc tartalma, amely akkor jelenik meg, ha további információs mezőket konfiguráltak. |
| További információs kulcsok | Erőforrás-azonosító/erőforrás értékpárja | Minden egyes kulcs egy űrlapmezőt és egy társított címkét hoz létre, amellyel további információk gyűjthetők a vevőktől. |
| További információs kulcsok \> Erőforrás-azonosító | Szöveges sztring | Minden egyes információs kulcs egy űrlapmezőt és egy társított címkét hoz létre, amellyel további információk gyűjthetők a vevőktől. Ez a tulajdonság azonosítja a további információk kulcsát. A pénztárban (POS) létrehozott feladatban ennek a tulajdonságnak az értéke jelenik meg címkeként az utasítások mezőjében. |
| További információs kulcsok \> Erőforrásérték | Szöveges sztring | A feladat szövegmezőjétnekcímkéje a pénztárban. |
| További információs kulcsok \> Kötelező | **Igaz** vagy **Hamis** | Ez a tulajdonság megadja, hogy a vevőknek ki kell-e tölteniük az űrlapmezőt, mielőtt továbbhaladnak. Ha ez a tulajdonság **Igaz** értékre van állítva, az űrlap címkéje mellett egy csillag jelenik meg, és egy nullérték-ellenőrzés történik, amely megakadályozza a vevők továbbhaladását, ha nem adnak meg értéket. |

## <a name="add-the-check-in-for-pickup-module-to-a-page"></a>Az átvételre való bejelentkezés modul hozzáadása egy oldalhoz

Az átvételre való bejelentkezés modult egy új oldalhoz kell hozzáadni, amelyet a bejelentkezés megerősítéséhez hoz létre. Ez a lap a bejelentkezés megerősítési felületeként szolgál az olyan vevők számára, akik az e-mailben az **Itt vagyok** hivatkozást vagy gombot választják. 

## <a name="configure-the-additional-information-form"></a>További információ űrlap konfigurálása

Ha nincsenek konfigurálva további információs kulcsok, alapértelmezés szerint a modul megjeleníti a vevők számára a bejelentkezést megerősítő oldalt. Amint a bejelentkezés megerősítése megjelenik, egy feladat jön létre a pénztárbanban ahhoz az üzlethez, ahol a rendelést átveszik.

Ha egy vagy több további információs kulcs be van állítva, akkor a program először felszólítja a vevőket, hogy adjanak meg adatokat. A **Küldés** lehetőséget választva megjelenik a bejelentkezés visszaigazolása, és létrejön egy feladat a pénztárban. 

## <a name="additional-resources"></a>További erőforrások

[Vevői bejelentkezéssel kapcsolatos értesítések engedélyezése a pénztárnál (POS)](enable-customer-check-in.md)
