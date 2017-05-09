---
title: "Aktuális készlet mobil munkaterület a Microsoft Dynamics 365 for Operations alkalmazás számára"
description: "Az Aktuális készlet mobil munkaterület segítségével bármikor és bárhol, mobilon tájékozódhat a fenntartott és a rendelkezésre álló készletről."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 267094
ms.assetid: 85058f55-e566-40e2-9234-42d3e4fe5ff6
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 7a0a2af2094e3e5be757d3dd82255769677b96ea
ms.openlocfilehash: 2ad48765528e1d1c6e7c90417b54a248ec79f546
ms.lasthandoff: 03/31/2017


---

# <a name="inventory-on-hand-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>Aktuális készlet mobil munkaterület a Microsoft Dynamics 365 for Operations alkalmazás számára

Az Aktuális készlet mobil munkaterület segítségével bármikor és bárhol, mobilon tájékozódhat a fenntartott és a rendelkezésre álló készletről. 

<a name="prerequisites"></a>Előfeltételek
-------------

| Előfeltételek                                                         | Leírás                                                                                                                                        |
|----------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| Tudnivalók a Microsoft Dynamics 365 for Operations mobilplatformról | [Dynamics 365 for Operations mobilplatform](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform)                                   |
| Dynamics 365 for Operations                                          | Olyan környezet, amely rendelkezik a Microsoft Dynamics 365 for Operations 1611-es verziójával és a Microsoft Dynamics for Operations 3-as platformfrissítésével (2016. november). |
| Gyorsavítás – Tudásbázis, 3215650                                                    | Telepítse a gyorsjavítást a Microsoft Dynamics 365 for Operationsben biztosított munkaterületek engedélyezéséhez.                                       |
| Mobileszköz, amelyre telepítve van Dynamics 365 for Operations alkalmazás | Töltse le Dynamics 365 for Operations mobilalkalmazást a mobiljához tartozó alkalmazásáruházból.                                                                           |

## <a name="introduction"></a>Bevezetés
Általában a cégek készleténél több szállításra és bevételezésre kerül sor mindennap. Ezek a mozgások folyamatosan módosítják az aktuális készlet állapotát. Az Aktuális készlet mobil munkaterület segítségével átláthatja a több vállalatot érintő aktuális készlet állapotát, így tetszés szerinti a mobileszközön a legfrissebb adatok alapján tájékozódhat a készletadatokról. Függetlenül attól, hogy a raktárban, beszerzésnél, értékesítésben, gyártásban vagy a vezetőségben dolgozik-e, vagy más szerepkörrel rendelkezik, az aktuális készletadatokat bárhol és bármikor elérheti. A mobil munkaterületen azonnal megtekinthető az aktuális, különböző létesítményeket felölelő állapot, és megtekinthető a különböző létesítményeket felölelő aktuális készlet, aktuális anyagfoglalások és le nem foglalt aktuális készlet. Ezenkívül az aktuális készlet cikkszámok megadásával lekérdezhető , és az aktuális termékekre vagy változatokra szűrt keresés végezhető. A mobil munkaterület konkrétan az alábbi szolgáltatásokat nyújtja:

-   Kereshet terméktípus és termék neve alapján termékeket, és megtekintheti a rájuk vonatkozó aktuális készletállapotot.
-   A kijelölt termékeknél a következő információkat tekintheti meg:
    -   Aktuális készlet telephely szerint
    -   Aktuális készlet raktár szerint
    -   Aktuális készlet hely szerint
    -   Aktuális készlet köteg szerint (kötegvezérelt termékeknél)
    -   Aktuális készlet készlet állapota szerint

<!-- -->

-   Az aktuális termékkészlet az alábbi módon jelenik meg:
    -   Fizikai készlet alapján (Ez a nézet a teljes mennyiséget jelöli.)
    -   Fizikai fenntartott alapján (Ez a nézet a fenntartott mennyiséget jelöli.)
    -   Elérhető fizikai alapján (Ez a nézet a rendelkezésre álló, nem fenntartott mennyiséget jelöli.)

## <a name="get-started"></a>Első lépések
A használat megkezdése a mobileszközön:

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

## <a name="view-the-onhand-inventory-for-a-product"></a>Termék aktuális készletének megtekintése
1.  A mobileszközön válassza az **Aktuális készlet** munkaterület.
2.  Válassza az **Aktuális ellenőrzése egy cikkhez** lehetőséget. Megjelenik a kapcsolat nélküli használatra az alkalmazásba betöltött termékek listája. Alapértelmezés szerint 50 elem töltődik be, de módosíthatja ezt a számot. A további tudnivalókat lásd az előre olvasási kézikönyvben.
3.  Ha a cikk nem szerepel a listán, válassza a **Továbbiak keresése** elemet a Dynamics 365 for Operationsben végzett online keresés érdekében. Keressen termékszám alapján, vagy térjen át terméknévalapú keresésre.
4.  Válasszon ki egy terméket. Ha a cikkhez tartozik kép, a kép megjelenik.
5.  A készlet aktuális állapotának megjelenítéséhez a következő lehetőségek közül választhat:
    -   Aktuális megjelenítése telephely szerint
    -   Aktuális megjelenítése raktár szerint
    -   Aktuális megjelenítése hely szerint
    -   Aktuális megjelenítése köteg szerint (kötegvezérelt termékeknél)
    -   Aktuális megjelenítése készletállapot szerint

    Az aktuális termékkészlet az alábbi módon jelenik meg:
    -   Fizikai készlet alapján (Ez a nézet a teljes mennyiséget jelöli.)
    -   Fizikai fenntartott alapján (Ez a nézet a fenntartott mennyiséget jelöli.)
    -   Elérhető fizikai alapján (Ez a nézet a rendelkezésre álló, nem fenntartott mennyiséget jelöli.)




