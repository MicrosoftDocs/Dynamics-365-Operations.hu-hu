---
title: Első lépések a Global Inventory Accounting szolgáltatással
description: Ez a témakör azt ismerteti, hogyan lehet elkezdeni a globális készletkönyvelést.
author: JennySong-SH
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 463a66002ec7a6536c9ff829f9ea2c3734138eae
ms.sourcegitcommit: 6221a25f81aa83ab335de7cb6b6c3014dbec0116
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/19/2022
ms.locfileid: "9177148"
---
# <a name="get-started-with-global-inventory-accounting"></a>Első lépések a Global Inventory Accounting szolgáltatással

[!include [banner](../includes/banner.md)]

A Global Inventory Accounting szolgáltatás segítségével több készlet könyveléseit végezheti el a beállított Global Inventory Accounting főkönyvben. Minden Global Inventory Accounting főkönyvhöz egy *szabályt* társít. Egy szabály a következő típusú könyvelési irányelvek gyűjteményét jelenti:

- Költségobjektum
- Bemeneti mérték alapja
- Költségforgalom-feltételezés
- Költségösszetevő

> [!NOTE]
> Még a Global Inventory Accounting bekapcsolása után is elvégezheti szokás szerint a készletkönyvelést a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban.

A Global Inventory Accounting szolgáltatás egy bővítmény. Ahhoz, hogy hozzáférhetővé váljanak a funkciók, telepítenie kell a Microsoft Dynamics Lifecycle Services (LCS) felületéről. Kiválaszthatja, hogy a termelési környezetekben való bekapcsolás előtt szeretné-e értékelni tesztkörnyezetben.

A Global Inventory Accounting jelenleg nem támogatja a Supply Chain Management eszközbe beépített költségkezelési funkciókat. Ezért fontos, hogy meggyőződjön, hogy a jelenleg elérhető funkciókészlet kielégíti-e a követelményeket.

## <a name="how-to-get-the-global-inventory-accounting-add-in"></a><a name="sign-up"></a> A Globális készletkönyvelés bővítmény bejezése

> [!IMPORTANT]
> A Global Inventory Accounting csak akkor használható, ha engedélyezve van az LCS-szolgáltatásban engedélyezett, nagy rendelkezésre állású környezet (nem OneBox környezet). Ezenkívül a Supply Chain Management 10.0.19-es vagy újabb verziójának is futnia kell.

### <a name="supply-chain-management-version-10019-to-10026"></a>Az Ellátásilánc-kezelés 10.0.19-es verziója 10.0.26-ra

Ha telepíteni szeretne egy globális készletkönyvelést az Ellátásilánc-kezelés 10.0.19-es verziójához a 10.0.26-os verzióhoz, telepítse [a bővítményt](#install). Ezután küldje el az LCS-környezetazonosítót és vállalatnevet e-mailben a globális [készletkönyvelési csoportnak](mailto:GlobalInvAccount@microsoft.com). A csoport egy követési e-mailt küld, amely a globális készletkönyvelési szolgáltatási végpontokat tartalmazza.

### <a name="supply-chain-management-version-10027-and-later"></a>Ellátásilánc-kezelés – 10.0.27-es és újabb verzió

Ha telepíteni szeretne egy globális készletkönyvelést az Ellátásilánc-kezelés 10.0.27-es és újabb verziójához, akkor telepítse a [bővítményt](#install). Az Ellátásilánc-kezelés ezen verzióihoz automatikusan be lesznek állítva a globális készletkönyvelési szolgáltatási végpontok, így ezeket nem kell manuálisan megtalálni. Ha a bővítmény beállítása során bármilyen problémát tapasztal, forduljon a [globális készletkönyvelési csapathoz](mailto:GlobalInvAccount@microsoft.com).

## <a name="licensing"></a>Licenckezelés

A Global Inventory Accounting szolgáltatás egy licencben szerepel az Supply Chain Management szolgáltatásban elérhető készletkönyvelési standard funkciókkal. Nem kell további licencet vásárolnia a Global Inventory Accounting szolgáltatás használatához.

## <a name="prerequisites"></a>Előfeltételek

### <a name="set-up-microsoft-power-platform-integration"></a>Microsoft Power Platform-integráció beállítása

A bővítmények funkcióit a következő lépések segítségével kell Microsoft Power Platform platformmal integrálni.

1. Nyissa meg azt a LCS-környezetet, amelyhez hozzá szeretné adni a szolgáltatást.
1. Lépjen a **Teljes részletek** elemre.
1. Válassza a **Beállítás**  lehetőséget a **Power Platform-integráció** szakaszban.
1. A **Power Platform környezetének** beállítása párbeszédpanelen jelölje be a jelölőnégyzetet, majd válassza a **Beállítás** lehetőséget. A beállítás általában 60 és 90 perc közötti időt vesz igénybe.
1. A Microsoft Power Platform környezet beállítása után az oldal megjeleníti a környezet nevét. Ezenkívül az **Power Platform Integráció** szakasz a "Power Platform környezet beállítása kész" utasítást is megjeleníti. A Global Inventory Accountinghoz nem szükséges kétírásos alkalmazás.

További információkért lásd: [Engedélyezés a környezet üzemelő példánya után](../../fin-ops-core/dev-itpro/power-platform/enable-power-platform-integration.md#enable-after-deploy).

## <a name="install-or-update-the-add-in-and-solution"></a><a name="install"></a> A bővítmény és a megoldás telepítése vagy frissítése

A következő eljárás szerint telepítheti vagy frissítheti a Globális készletkönyvelés bővítményét és megoldását. Az eljárásnak az a része, amelyet végre kell követnie, attól függ, hogy első alkalommal telepíti a rendszert, vagy csak egy meglévő telepítés megoldását kell frissítenie.

- Ha még soha nem telepítette a bővítményt, a teljes eljárást kövesse a bővítmény és a megoldás telepítéséhez is.
- Ha már globális készletkönyvelést [Power Platform használ, de frissítenie kell a megoldást a rendszergazdai](https://admin.powerplatform.microsoft.com) központban, csak a 6. lépést tegye meg, és hagyja ki az összes többi lépést.

A bővítmény és a megoldás telepítése vagy frissítése:

1. Bejelentkezés az [LCS](https://lcs.dynamics.com/Logon/Index) alkalmazásba.
1. Nyissa meg azt a LCS-környezetet, amelyhez hozzá szeretné adni a szolgáltatást.
1. Lépjen a **Teljes részletek** elemre.
1. Menjen az Integráció **Power Platform gombra,** és válassza a **Telepítőt**.
1. A **Power Platform környezetének** beállítása párbeszédpanelen jelölje be a jelölőnégyzetet, majd válassza a **Beállítás** lehetőséget. A beállítás általában 60 és 90 perc közötti időt vesz igénybe.
1. A környezet Microsoft Power Platform beállítása után jelentkezzen be a rendszergazdai központba, [Power Platform](https://admin.powerplatform.microsoft.com) majd a következő lépések segítségével telepítse vagy frissítse a globális készletkönyvelési megoldást:
   1. Válassza ki azt a környezetet, ahová telepíteni vagy frissíteni szeretné a megoldást.
   1. Válassza ki a **Dynamics 365-alkalmazásokat**.
   1. Válassza a **Telepítési alkalmazást**.
   1. Válassza a **Dynamics 365 globális készletkönyvelést**.
   1. A telepítéshez **válassza a Tovább** gombra.
1. A megoldás teljes telepítése után menjen vissza az LCS-környezethez. A **Környezetbővítmények** gyorslapon válassza az **Új bővítmény telepítése** lehetőséget.
1. Válassza a **Globális Inventory Accounting** eseményt.
1. Kövesse a telepítési útmutatót, és fogadja el a feltételeit és kikötéseit.
1. Válassza a **Telepítés** parancsot.
1. A **Környezeti bővítmények** gyorslapon látható, hogy a Global Inventory Accounting szolgáltatás telepítése folyamatban van. Néhány perc múlva az állapotot változik *Telepítés folyamatban* állapotról *Telepítve* értékre. (Elképzelhető, hogy frissíteni kell a lapot a változás megtekintéséhez.) Ezen a ponton a Global Inventory Accounting szolgáltatás készen áll a használatra.

Ha a telepítés alapértelmezett Dataverse nyelve nem angol, kövesse az alábbi lépéseket:

1. Ugrás ide: **Speciális beállítások \> Adminisztráció \> Nyelvek**.
1. Válassza az *Angol* (*LanguageCode=1033*), és majd az **Alkalmaz** lehetőséget.

## <a name="set-up-the-integration"></a>Integráció beállítása

A következő lépések szerint állíthatja be a Global Inventory Accounting és a Supply Chain Management közötti integrációt.

1. Jelentkezzen be a Supply Chain Management alkalmazásba.
1. Lépjen a **Rendszerfelügyelet \> Funkciókezelés** elemre.
1. Válassza a **Frissítések keresése** elemet.
1. A Mind **lapon** keresse meg a globális készletkönyvelés nevű *(Előnézet) funkciót*.
1. Válassza az **Engedélyezés most** lehetőséget.
1. Ugrás a **Globális készletkönyvelés \> Beállítása \> Global Inventory Accounting paraméterei \> Integrációs paraméterek**.
1. A futtatott Ellátásilánc-kezelés melyik verziójától függően tegye a következő lépéseket:
    - **Ellátásilánc-kezelés - 10.0.19-10.0.26- 10.0.26**: **·** **Az** Adatszolgáltatás végpontja és a Globális készletkönyvelés végpont mezőiben adja meg a globális készletkönyvelési csoporttól e-mailben Önnek küldött URL-címeket [(](#sign-up) lásd még a Globális készletkönyvelés bővítmény beolvassa).
    - **Ellátásilánc-kezelés – 10.0.27-es** verzió és újabb: Nem kell megadnia a végpontokat, ezért kihagyhatja ezt a lépést.

A Global Inventory Accounting készen áll a használatra.
