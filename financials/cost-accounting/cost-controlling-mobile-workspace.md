---
title: "Költségkontroll mobil munkaterület a Microsoft Dynamics 365 for Operations alkalmazás számára"
description: "A Költségkontroll mobil munkaterülettel a költséghelyek vezetői bármikor és bárhol megtekinthetik a költséghely teljesítményét."
author: YuyuScheller
manager: AnnBe
ms.date: 2017-01-12 16 - 53 - 04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 267114
ms.assetid: 84740472-494f-444c-9b74-f83b7342fd25
ms.search.region: global
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: c8c96dc9705688308dd4a5c720700ddc17657d75
ms.openlocfilehash: 8136efb1d2669c39fcc0f80b60e80ecae983d5d8
ms.lasthandoff: 03/31/2017


---

# <a name="cost-controlling-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>Költségkontroll mobil munkaterület a Microsoft Dynamics 365 for Operations alkalmazás számára

A Költségkontroll mobil munkaterülettel a költséghelyek vezetői bármikor és bárhol megtekinthetik a költséghely teljesítményét. 

<a name="prerequisites"></a>Előfeltételek
-------------

| Előfeltételek                                                         | Leírás                                                                                                                                                                   |
|----------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Tudnivalók a Microsoft Dynamics 365 for Operations mobilplatformról | [Dynamics 365 for Operations mobilplatform](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform)                                                              |
| Dynamics 365 for Operations                                          | Győződjön meg arról, hogy olyan környezetet használ, amely rendelkezik a Microsoft Dynamics 365 for Operations 1611-es verziójával és a Microsoft Dynamics for Operations 3-as platformfrissítésével (2016. november). |
| Gyorsavítás – Tudásbázis, 3215650                                                    | Telepítse a gyorsjavítást a Microsoft Dynamics 365 for Operationsben biztosított munkaterületek engedélyezéséhez.                                                                       |
| Mobileszköz, amelyre telepítve van Dynamics 365 for Operations alkalmazás | Töltse le Dynamics 365 for Operations mobilalkalmazást a mobiljához tartozó alkalmazásáruházból.                                                                                                      |

## <a name="introduction"></a>Bevezetés
A Költségkontroll mobil munkaterületen azonnal megtekinthető a költséghelyek aktuális teljesítménye, és a tényleges költségek összevethetők a tervezett költségekkel. Az egyes költségtényezők állapotáig leáshat.

### <a name="example"></a>Példa

Egy alkalmazott meghívást kap egy nemzetközi konferenciára. Az utazási költségeket a szervezetnek kell fedeznie. Az alkalmazott megkérdezi a vezetőjét, hogy ő is részt vesz-e a konferencián. A vezető gyorsan megnyitja a Költségkontroll mobil munkaterületet a mobiltelefonján, és megnézi, hogy van-e költségvetése ahhoz, hogy az alkalmazott részt vehessen a konferencián.

### <a name="data-security"></a>Adatbiztonság

A Költségkontroll mobil munkaterület adatait felhasználói hitelesítő adatok védik. A költséghely vezetője csak a saját költséghelye adatait láthatja. A hozzáférési szint biztonságának kezelése a Költségkönyvelési modulon belül történik. A Költségkontroll mobil munkaterület konfigurációját a költségkönyvelők határozzák meg a Költségkönyvelés modulban. A munkaterület a Microsoft Dynamics 365 for Operations alkalmazásban való közzététele után elérhetővé válik a Dynamics 365 for Operations mobilalkalmazásban. Ez biztosítja, hogy a szervezet összes költséghelyének vezetője ugyanabban a formátumban lássa az adatokat.

### <a name="actions-views-and-links"></a>Műveletek, nézetek és hivatkozások

A Dynamics 365 for Operations alkalmazás Költségkontroll mobil munkaterülete a következő műveleteket, nézeteket és hivatkozásokat biztosítja:

-   Műveletek 
    -   Válassza a **Konfigurációk** elemet elrendezés kiválasztásához.
    -   Válassza a **Költségobjektumok** elemet a költséghelyek kiválasztásához, amelyek adatait szűrni szeretné. **Megjegyzés:** a lista a Költségkönyvelés modulban megadott hozzáférésnek megfelelően jelenik meg.

<!-- -->

-   Annak alapján, hogy mi van kiválasztva a **Műveletek** részben, és mi a van konfigurálva a Költségkönyvelési modulban, a következő információkat tekintheti meg a kártyákon. Fontos megjegyezni, hogy az összeg ugyanabban a formában jelenik meg: Tényleges, Költségvetés, Eltérés és Eltérési %. 
    -   Tényleges és Költségvetés (aktuális időszak)
    -   Tényleges és Módosított költségvetés (aktuális időszak)
    -   Tényleges és Költségvetés (előző időszak)
    -   Tényleges és Módosított költségvetés (előző időszak)
    -   Tényleges és Költségvetés (folyó év mai dátumig)
    -   Tényleges és Módosított költségvetés (folyó év mai dátumig)

<!-- -->

-   Hivatkozások
    -   Aktuális időszak részletei.
    -   Előző időszak részletei.
    -   Folyó év mai dátumig részletei.

Ha a hivatkozások egyikét választja, költségtényezőnként megjelenik egy kártya. Az kártyákon szereplő összeg a következő formátumban jelenik meg: Aktuális, Költségvetés, Költségvetés eltérése, Költségvetési eltérés %, Módosított költségvetés, Módosított költségvetés eltérése és Módosított költségvetési eltérés %.  [![cost-controlling](./media/cost-controlling.png)](./media/cost-controlling.png)

## <a name="get-started"></a>Első lépések
Kövesse az alábbi lépéseket, és kezdjen hozzá a költségkontroll-mobilalkalmazás használatához a mobileszközén.

1.  A mobiljához tartozó alkalmazásáruházból töltse le és telepítse a Microsoft Dynamics 365 for Operations alkalmazást.
2.  Indítsa el az alkalmazást a készülékén.
3.  Adja meg a Dynamics 365 URL-címét.
4.  Adja meg a vállalatot a bejelentkezéshez. Például írja be azt, hogy **USMF**.
5.  Az első bejelentkezéskor a rendszer kéri a felhasználónevet és jelszót a Microsoft Dynamics 365 for Operations-fiókjához. Adja meg a hitelesítési adatait. A bejelentkezést követően megjelennek a vállalata rendelkezésre álló munkaterületek.

A munkaterületek a mobilalkalmazásban történő megtekintéséhez először a kívánt munkaterületeket közzé kell tenni Dynamics 365 for Operations alkalmazásban.

1.  Indítsa el a Dynamics 365 for Operationst.
2.  Lépjen a **Rendszerfelügyelet** &gt; **Beállítás** &gt; **Rendszerparaméterek** elemre.
3.  Válassza a **Mobilalkalmazás kezelése** lehetőséget.
4.  Válassza a **Költségkontroll** munkaterületet a mobilplatformon való közzétételre.
5.  Válassza a **Munkaterület közzététele** lehetőséget.
6.  Frissítse az eszközt a közzétett munkaterületek ellenőrzéséhez.

## <a name="view-the-performance-of-your-cost-center"></a>A költséghely teljesítményének megtekintése
1.  A mobileszközön válassza a **Költségkontroll** munkaterület.
2.  Válassza a **Költségobjektum-kontroll** elemet.
3.  Kattintson a **Műveletek** elemre.
4.  Kattintson a **Konfiguráció kiválasztása** elemre és válasszon költségkontroll-elrendezést.
5.  Kattintson a **Kész** gombra.
6.  Kattintson a **Műveletek** elemre.
7.  Kattintson a **Költség objektum kiválasztása** elemre, és válassza ki a költséghelyeket, amelyekhez hozzáfér.
8.  Kattintson a **Kész** gombra.
9.  Tekintse meg a költséghely összteljesítményét.
10. Kattintson az **Aktuális időszak részletei** elemre.
11. Tekintse meg az egyedi költségelemek teljesítményét.
12. Konkrét költségelemekre is kereshet.



