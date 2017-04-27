---
title: "Értékesítési rendelések mobil munkaterülete a Microsoft Dynamics 365 for Operations alkalmazásban"
description: "Az értékesítési rendelések mobil munkaterületének segítségével bármikor és bárhol is legyen, naprakész maradhat az értékesítési rendeléseivel kapcsolatban."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 267134
ms.assetid: dbc6dc39-b535-42d3-9fbd-4724597388ad
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 7a0a2af2094e3e5be757d3dd82255769677b96ea
ms.openlocfilehash: 851c53e1c53fb37488ed86e25e3ede83ca0541db
ms.lasthandoff: 03/31/2017


---

# <a name="sales-orders-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>Értékesítési rendelések mobil munkaterülete a Microsoft Dynamics 365 for Operations alkalmazásban

Az értékesítési rendelések mobil munkaterületének segítségével bármikor és bárhol is legyen, naprakész maradhat az értékesítési rendeléseivel kapcsolatban. 

<a name="prerequisites"></a>Előfeltételek
-------------

| Előfeltételek                                                         | Leírás                                                                                                                                                                   |
|----------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Tudnivalók a Microsoft Dynamics 365 for Operations mobilplatformról | [Dynamics 365 for Operations mobilplatform](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform)                                                              |
| Dynamics 365 for Operations                                          | Győződjön meg arról, hogy olyan környezetet használ, amely rendelkezik a Microsoft Dynamics 365 for Operations 1611-es verziójával és a Microsoft Dynamics for Operations 3-as platformfrissítésével (2016. november). |
| Gyorsjavítás – Tudásbázis, 3215650                                                    | Telepítse a gyorsjavítást a Microsoft Dynamics 365 for Operationsben biztosított munkaterületek engedélyezéséhez.                                                                       |
| Mobileszköz, amelyre telepítve van Dynamics 365 for Operations alkalmazás | Töltse le Dynamics 365 for Operations mobilalkalmazást a mobiljához tartozó alkalmazásáruházból.                                                                                                      |

## <a name="overview"></a>Áttekintés
Ez a mobil munkaterület hozzáférést biztosít a Dynamics 365 for Operations alkalmazáshoz, és segítségével megtekintheti az egyes értékesítési rendelésekkel kapcsolatos részletes információkat, például a rendelés állapotát, a vevő kapcsolattartási adatait és a megrendelő kapcsolattartási adatait. A mobil munkaterület azonnali rálátást biztosít az értékesítési rendelésekre. Megtekintheti az értékesítési rendeléseket ügyfelek szerint, vagy megtekintheti egy adott értékesítési rendelés információit. A mobil munkaterület két nézetet kínál, ahol részletesen elemezheti az értékesítési rendeléseket.

### <a name="view-all-sales-orders"></a>Összes értékesítési rendelés megtekintése

Ez a nézet az összes értékesítési rendelést megjeleníti.

-   A következő szűrők egyikének segítségével kiválaszthatja a megtekinteni kívánt értékesítési rendeléseket.
    -   Keresés értékesítési rendelés szerint
    -   Keresés vevői számla alapján
    -   Keresés vevő neve szerint
    -   Keresés állapot szerint
    -   Keresés kiadási állapot szerint
    -   Keresés a létrehozás dátuma és ideje alapján

<!-- -->

-   A értékesítési rendelések kiválasztását követően megtekintheti az adott rendelések részleteit. Pontosabban a következőket tekintheti meg:
    -   Ügyfél neve és címadatai
    -   Különböző értékesítésirendelés-dátumok, például a kért szállítási dátum és a visszaigazolt szállítási dátum
    -   Megrendelő kapcsolattartási adatai
    -   Vevői kapcsolattartási adatok
    -   Rendeléssorok
    -   Szállítmányok, amelyek megmutatják, hogyan és mikor szállították ki az értékesítési rendelést

### <a name="view-orders-for-a-customer-"></a>Vevő rendeléseinek megtekintése** **

Ez a nézet értékesítési rendeléseket jelenít meg vevőnként.

-   A következő szűrők segítségével tekintheti meg egy vevő rendeléseit.
    -   Keresés név szerint
    -   Keresés számla alapján

<!-- -->

-   Egy vevő kiválasztását követően a következőket tekintheti meg:
    -   Vevő neve és csoportja
    -   Vevői kapcsolattartási adatok
    -   Vevői értékesítési rendelések és az értékesítési rendelések részletei:
        -   Ügyfél neve és címadatai
        -   Különböző értékesítésirendelés-dátumok
        -   Megrendelő kapcsolattartási adatai
        -   Vevői kapcsolattartási adatok
        -   Rendeléssorok
        -   Szállítmányok, amelyek megmutatják, hogyan és mikor szállították ki az értékesítési rendeléseket

## <a name="get-started"></a>Első lépések
Kövesse az alábbi lépéseket, és kezdjen hozzá az értékesítési rendelések mobil munkaterületének használatához a mobileszközén.

1.  A mobiljához tartozó alkalmazásáruházból töltse le és telepítse a Microsoft Dynamics 365 for Operations alkalmazást.
2.  Indítsa el az alkalmazást a készülékén.
3.  Adja meg a Dynamics 365 URL-címét.
4.  Adja meg a vállalatot a bejelentkezéshez. Például írja be azt, hogy **USMF**.
5.  Az első bejelentkezéskor a rendszer kéri a felhasználónevet és jelszót a Microsoft Dynamics 365 for Operations-fiókjához. Adja meg a hitelesítési adatait. A bejelentkezést követően megjelennek a vállalata rendelkezésre álló munkaterületek.

A munkaterületek a mobilalkalmazásban történő megtekintéséhez először a kívánt munkaterületeket közzé kell tenni Dynamics 365 for Operations alkalmazásban.

1.  Indítsa el a Dynamics 365 for Operationst.
2.  Lépjen a **Rendszerfelügyelet** &gt; **Beállítás** &gt; **Rendszerparaméterek** elemre.
3.  Válassza a **Mobilalkalmazás kezelése** lehetőséget.
4.  Válassza ki a munkaterületet a mobilplatformon való közzétételre.
5.  Válassza a **Munkaterület közzététele** lehetőséget.
6.  Frissítse az eszközt a közzétett munkaterületek ellenőrzéséhez.

## <a name="view-information-about-sales-orders-for-a-customer"></a>Vevőhöz tartozó értékesítési rendelésekkel kapcsolatos információk megjelenítése
1.  A mobileszközön válassza az **Értékesítési rendelések** munkaterület.
2.  Válassza ki a **Vevő rendeléseinek megtekintése** lehetőséget.
3.  Keresse ki a kívánt ügyfél adatait a **Számla **vagy a **Vevő neve **információknál.
4.  Válassza ki az ügyfelet.
5.  Válassza ki a **Kapcsolattartó adatai** vagy az **Értékesítési rendelések** lehetőséget.
6.  Az **Értékesítési rendelések** kiválasztása esetén megjelenik egy lista a vevő számára az értékesítési rendelésekről.
7.  Válassza ki az **Értékesítési rendelés** lehetőséget.
8.  Itt tekintheti meg az értékesítési rendelések sorairól, a szállítmányokról, a vevői kapcsolattartási adatokról és a megrendelő elérhetőségéről szóló információkat.




