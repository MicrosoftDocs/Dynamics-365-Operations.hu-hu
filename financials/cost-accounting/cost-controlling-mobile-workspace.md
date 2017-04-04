---
title: "Microsoft Dynamics 365 ellenőrző mobil munkaterület költsége műveletek app"
description: "A költséget vezérlése hordozható munkaterület, költség, erőforrás-menedzserek tekintheti meg a költség központ teljesítmény bármikor és bárhol."
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

# <a name="cost-controlling-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>Microsoft Dynamics 365 ellenőrző mobil munkaterület költsége műveletek app

A költséget vezérlése hordozható munkaterület, költség, erőforrás-menedzserek tekintheti meg a költség központ teljesítmény bármikor és bárhol. 

<a name="prerequisites"></a>Előfeltételek
-------------

| Előfeltételek                                                         | Leírás                                                                                                                                                                   |
|----------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Olvassa el a Microsoft Dynamics 365 műveletek mobil platform | [365 Dynamics műveletek mobil platform](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform)                                                              |
| 365 Dynamics műveletek                                          | Győződjön meg arról, hogy olyan környezetben, amely rendelkezik a Microsoft Dynamics 365 műveletek verzió 1611 használ, és a Microsoft Dynamics műveletek platform frissítése (November 2016) 3. |
| A gyorsjavítás KB 3215650                                                    | A gyorsjavítást a Microsoft Dynamics 365 műveletekhez biztosított munkaterületek engedélyezése.                                                                       |
| Mobil eszköz, amely a Dynamics 365 a műveletek alkalmazás telepítve van | Töltse le a mobil app store app műveletek esetében a Dynamics 365.                                                                                                      |

## <a name="introduction"></a>Bevezetés
A vezérlése hordozható munkaterület költség költséghelyek aktuális teljesítmény azonnali információkra tényleges költségek ellen tervezett költségeinek összevetésével biztosít. Az egyes költségtényezők állapotok leáshat.

### <a name="example"></a>Példa

Az alkalmazott nemzetközi konferencia meghívást kap. Utazási költségek fedezésére a szervezet lesz. Az alkalmazott saját kezelő kéri, ha ő is részt vesz a konferencián. A kezelő gyorsan megnyitja, hogy ő tartozik a konferencián részt venni az alkalmazott költségvetési szabályozása a mobiltelefonon mobil munkaterület költség.

### <a name="data-security"></a>Adatbiztonság

Az adatok ellenőrzése a munkaterület költsége védi-e felhasználói hitelesítő adatokat. Költség központ vezető csak engedélyezett saját erőforrás adatainak megtekintéséhez. Biztonság a hozzáférést a költségkönyvelési modulon belül kezeli. Költség könyvelők határozza meg a költség, a költségkönyvelési modul mobil munkaterület konfigurációjának ellenőrzése. A munkaterület a Microsoft Dynamics 365 a műveletek app van közzétéve, miután érhető el a Dynamics 365 műveletek mobile alkalmazás számára. Ez biztosítja, hogy a szervezet összes költség központ vezetők meg adatokat ugyanabban a formátumban.

### <a name="actions-views-and-links"></a>Műveletek, nézetek és hivatkozások

Mobil munkaterület szabályozása 365 Dynamics műveletek app a költség a következő műveletek, nézetek és hivatkozásokat biztosít:

-   Műveletek 
    -   Válassza ki **konfigurációk** elrendezés kiválasztása.
    -   Válassza ki **objektumok költség** alapjául szolgáló adatok szűrése a költséghelyek kiválasztásához. **Megjegyzés:** a hozzáférést a Költségkönyvelés modul nyújtott megfelelően jelennek meg a listában.

<!-- -->

-   A kijelölt alapján **műveletek**, és mi a költségkönyvelési modul van konfigurálva, a következő információkat is megtekinthetik a kártyák. Fontos megjegyezni, hogy az összeg ugyanabban a formában jelenik meg: aktuális, költségvetés, az eltérés és eltérés %. 
    -   Tényleges vagy költségvetési (aktuális időszak)
    -   Tényleges és módosított költségvetési (aktuális időszak)
    -   Tényleges vagy költségvetési (az előző időszak)
    -   Tényleges és módosított költségvetési (az előző időszak)
    -   Tényleges vagy költségvetési (dátum év)
    -   Tényleges és módosított költségvetési (dátum év)

<!-- -->

-   Hivatkozások
    -   Aktuális időszak adatait.
    -   Előző időszak adatait.
    -   Év elejétől részleteit.

Ha a hivatkozások egyikét választja, egy kártyát egy költségtényező jelenik meg. Az összeg a kártyák a következő formátumban jelenik meg: aktuális, költségvetés, költségvetés eltérése, költségvetési eltérés %, módosított költségvetési, módosított költségvetés eltérése és módosított költségvetési eltérés %.  [![Költség szabályozás](./media/cost-controlling.png)](./media/cost-controlling.png)

## <a name="get-started"></a>Első lépések
Kövesse az alábbi lépéseket a kezdéshez a költség vezérlő mobile alkalmazás segítségével a mobileszközön.

1.  A mobil app-tárolóban töltse le és telepítse a Microsoft Dynamics 365 app műveletek esetében.
2.  Az alkalmazás indításához az eszközön.
3.  A Dynamics 365 URL-CÍMÉT adja meg.
4.  Adja meg a vállalat a bejelentkezéshez. Például, adja meg az **USMF**.
5.  Az első bejelentkezéskor kéri a felhasználónevet és jelszót a Microsoft Dynamics 365 költségszámla esetében. Adja meg hitelesítő adatait. A bejelentkezést követően a vállalat jelennek meg a rendelkezésre álló munkaterületek.

A mobil app munkaterületek megtekintéséhez először a kívánt munkaterületet kell közzétenni a vonatkozó műveletek app a Dynamics 365.

1.  Indítsa el a Dynamics 365 műveletekhez.
2.  Ugrás a **rendszer felügyeleti**&gt;**a telepítő**&gt;**Rendszerparaméterek**.
3.  Válassza ki **mobile alkalmazás kezelése**.
4.  Jelölje be a munkaterület ** költség szabályozás ** közzététele a mobil platform.
5.  Válassza ki **közzététele a munkaterület**.
6.  Frissítse az eszközt, és ellenőrizze a közzétett munkaterületek.

## <a name="view-the-performance-of-your-cost-center"></a>A költséghely teljesítményének megtekintése
1.  A mobileszközön válassza ki a **szabályozása költség** munkaterület.
2.  Válassza a **objektum szabályozása költség**.
3.  Kattintson a **műveletek**.
4.  Kattintson a **Select configuration** jelölje be az elrendezés szabályozása költséget.
5.  Click **Done**.
6.  Kattintson a **műveletek**.
7.  Kattintson a **válassza ki a költség objektum** jelölje ki a költséghelyek által biztosított hozzáférést.
8.  Click **Done**.
9.  A költséghely teljesítménye megtekintése.
10. Kattintson a **az aktuális időszakra részletek**.
11. Az egyes költségtényezők teljesítményét megtekinteni.
12. Egyes költségtényezők is kereshet.



