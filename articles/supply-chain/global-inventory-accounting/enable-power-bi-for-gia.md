---
title: Válassza a Globális Inventory Accounting Power BI-t
description: Ez a témakör azt ismerteti, hogyan lehet engedélyezni a Microsoft Power BI globális készletkönyvelést.
author: JennySong-SH
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: b1edfa314d2810bff4cf02762aeb66bee801858d
ms.sourcegitcommit: 6b209919de39c15e0ebe4abc9cbcd30618f2af0b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/11/2022
ms.locfileid: "9135425"
---
# <a name="enable-power-bi-for-global-inventory-accounting"></a>Válassza a Globális Inventory Accounting Power BI-t

[!include [banner](../includes/banner.md)]

Csempéket, irányítópultokat és jelentéseket rögzíthet [a PowerBI.com](https://powerbi.com/) fiókjából a Microsoft Dynamics 365 alkalmazás munkaterületére.

## <a name="prerequisites"></a>Előfeltételek

A Power BI jelentés engedélyezéséhez a következő előfeltételeknek kell lenniük:

- Rendszergazdaként kell részt vennie a Dynamics 365 alkalmazásban.
- Rendelkeznie kell [egy PowerBI.com](https://powerbi.com/) számlával.
- Legalább egy irányítópultnak és egy jelentésnek kell lennie a Power BI fiókjában.
- Rendszergazdaként kell rendelkeznie a Azure Active Directory (Azure AD) fiókjához.
- A Azure AD tartománynak ugyanazzal a tartománysal kell rendelkeznie, amelyet a [PowerBI.com](https://powerbi.com/) fiókjához használt.

## <a name="setup"></a>Beállítás

A Power BI integráció beállításához hajtsa végre az alábbi lépéseket.

1. Jelentkezzen be a [Microsoft Dynamics LifeCycle Services (LCS)](https://lcs.dynamics.com/Logon/Index) szolgáltatásba.
1. Lépjen a **Megosztott eszközkönyvtárba**, válassza ki a **Power BI jelentésmodellt** eszköztípusként, és töltse le a **Global Inventory Accounting** csomagot. 
1. Jelentkezzen be [a PowerBI.com](https://app.powerbi.com/), és töltse fel a **Global Inventory Accounting** számviteli jelentés Power BI fájlját az alábbi lépésekben:

    1. Válassza az **Új** lehetőséget.
    1. Válassza a **Fájl feltöltése** lehetőséget.
    1. Válassza ki a **Global Inventory Accounting** Power BI jelentésfájlt.

1. Konfigurálja a **Global Inventory Accounting** Power BI jelentést az alábbi lépésekkel:

    1. Lépjen a **Saját** munkaterületre, keresse meg a Global Inventory Accounting adatkészletét, majd a **Beállítások** menü **Beállítások** parancsát válassza.
    1. A **Globális készletkönyvelés beállításai** csoportban bővítse a **Paramétereket**, és szükség szerint frissítse az összes paramétert. Különösen a következő beállításokat kell ellenőrizni:
        1. Írja felül az **Dataverse alapértelmezett URL-címeket** az **LCS**(a Power Platform integrációja szakasz) Power Platform **környezetének adataiban** található értékek használatával.
        1. A környezetazonosítók alapértelmezett **értékeinek** felülírása **az** LCS környezet részleteiben (**a Környezet kezelése** szakaszban) található értékek használatával.
        1. Válassza a **Hitelesítő adatok szerkesztése** hivatkozást az **Adatforrás hitelesítő adatainak szakasz CDS-címkéje** **mellett**. Ezután jelentkezzen be a Dataverse-fiókjába az **OAuth2** hitelesítési módszerrel.
    1. Győződjön meg róla, hogy a **Saját munkaterület \> Jelentések \> Globális készletkönyvelés** helyen található Power BI-jelentések megfelelően működnek, és megjelenítenek tartalmat a rendszerből.

1. Regisztrálja az alkalmazást a [Konfigurálás PowerBI.com](../../fin-ops-core/dev-itpro/analytics/configure-power-bi-integration.md#registration-process) szerint.
1. Integrálja a **Global Inventory Accounting** Power BI jelentésfájlt a Dynamics 365 Supply Chain Management szolgáltatásra az alábbi lépésekkel:

    1. Lépjen a **Rendszerfelügyelet \> Beállítás \> PowerBI.com konfiguráció** elemre.
    1. Válassza ki a **Szerkesztés** opciót.
    1. Válassza a **PowerBI.Com integráció** lehetőséget.
    1. Írja be az alkalmazásazonosítót az **Alkalmazás azonosítója** mezőbe.
    1. Írja be az alkalmazáskulcs az **Alkalmazás kulcsa** mezőbe.
    1. Válassza a **Mentés** lehetőséget.

1. Frissítse az oldalt úgy, hogy a Power BI bejelentkezési párbeszédpanel is megjelenik.
1. A **Beállítások** lapon válassza a **Jelentéskatalógus megnyitása** lehetőséget, majd válassza a korábban feltöltött **Global Inventory Accounting** Power BI jelentésfájlt.
1. Frissítse a lapot.. Látnia kell, hogy a jelentés hozzá van adva.
1. Válassza ki a **Global Inventory Accounting** linket a **Power BI jelentések** alatt.

További tudnivalókért lásd: [PowerBI.com-integráció konfigurálása](../../fin-ops-core/dev-itpro/analytics/configure-power-bi-integration.md).
