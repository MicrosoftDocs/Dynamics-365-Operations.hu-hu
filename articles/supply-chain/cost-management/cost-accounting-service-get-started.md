---
title: Első lépések a költségkönyvelési szolgáltatásban
description: Ez a témakör bemutatja a költségkönyvelési szolgáltatás licencelési adatait és telepítési útmutatását.
author: AndersGirke
manager: tfehr
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-17
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: cbbce7eaac264973bf0b95ad5175bf70ed2b4ae9
ms.sourcegitcommit: e06da171b9cba8163893e30244c52a9ce0901146
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/21/2020
ms.locfileid: "3276924"
---
# <a name="get-started-with-the-cost-accounting-service"></a>Első lépések a költségkönyvelési szolgáltatásban

[!INCLUDE [banner](../includes/banner.md)]

> [!IMPORTANT]
> A témakörben leírt funkciók privát előzetes kiadás részeként állnak rendelkezésre. Ennek a témakörnek a tartalma és az ebben ismertetett funkciók változhatnak. Az előzetes kiadásokkal kapcsolatban további információkat az [Egyverziós szolgáltatásfrissítések GYIK](../../fin-ops-core/fin-ops/get-started/one-version.md) oldalon találhat.

A Költségkönyvelés szolgáltatás segítségével több készlet könyvelését végezheti el a beállított költségkönyvelési főkönyvben. Minden költségkönyvelési főkönyvhöz egy *szabályt* társít. Egy szabály a következő típusú könyvelési irányelvek gyűjteményét jelenti:

- Költségobjektum
- Bemeneti mérték alapja
- Költségforgalom-feltételezés
- Költségösszetevő

> [!NOTE]
> Még a költségkönyvelési szolgáltatás bekapcsolása után is elvégezheti szokás szerint a készletkönyvelést a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban.

A Költségkönyvelés szolgáltatás egy bővítmény. Ahhoz, hogy hozzáférhetővé váljanak a funkciók, telepítenie kell a Microsoft Dynamics Lifecycle Services (LCS) felületéről. Ennek megfelelően kiválaszthatja, hogy a termelési környezetekben való bekapcsolás előtt szeretné-e értékelni tesztkörnyezetben.

A Költségkönyvelés szolgáltatás jelenleg nem támogatja a Dynamics 365 Supply Chain Management szolgáltatásba beépített összes költségkönyvelési funkciót. Ezért fontos, hogy meggyőződjön, hogy a jelenleg elérhető funkciókészlet kielégíti-e a követelményeket.

## <a name="licensing"></a>Licenckezelés

A Költségkönyvelés szolgáltatás egy licencben szerepel az Supply Chain Management szolgáltatásban elérhető készletkönyvelési standard funkciókkal. Nem kell további licencet vásárolnia a Költségkönyvelés szolgáltatás használatához.

## <a name="install-the-add-in"></a>Telepítse a bővítményt

> [!IMPORTANT]
> A költségkönyvelési szolgáltatás használatához rendelkeznie kell LCS-kompatibilis magas elérhetőségű környezettel (nem OneBox.környezettel), és a Dynamics 365 Supply Chain Management 10.0.11-es vagy újabb verzióját kell futtatnia.

A Költségkönyvelés szolgáltatás használatához a következő eljárás szerint telepítse a Supply Chain Management költségszámítási szolgáltatásának beépülő modulját.

1. Bejelentkezés az LCS alkalmazásba.

1. Lépjen a **Előzetes funkció kezelése** lehetőségre.

1. Válassza ki a plusz jelet (**+**).

1. A **kód** mezőbe írja be a költségkönyvelési szolgáltatáshoz tartozó bővítmény bétakulcsát. (E-mailben meg kellett volna kapnia a kulcsot.)

1. Válassza a **Blokkolás feloldása** lehetőséget.

1. Nyissa meg azt a LCS-környezetet, amelyhez hozzá szeretné adni a szolgáltatást.

1. Lépjen a **Teljes részletek** elemre.

1. Görgessen le a **Környezeti bővítmények** gyorslapra.

1. Válassza az **Új bővítmény telepítése** lehetőséget.

1. Válassza a **Költségkönyvelési szolgáltatás** elemet.

1. Kövesse a telepítési útmutatót, és fogadja el a feltételeit és kikötéseit.

1. Válassza a **Telepítés** parancsot.

1. A **környezeti bővítmények** gyorslapon látható, hogy a Költségkönyvelés szolgáltatás telepítése folyamatban van. Néhány perc múlva az állapotot változik **Telepítés folyamatban** állapotról **Telepítve** értékre. (Elképzelhető, hogy frissíteni kell a lapot a változás megtekintéséhez.) Ezen a ponton a Költségkönyvelés szolgáltatás készen áll a használatra.

## <a name="set-up-the-integration"></a>Integráció beállítása

A Költségkönyvelés szolgáltatás és Dynamics 365 Supply Chain Management közötti integráció beállításához:

1. Lépjen a **Rendszerfelügyelet > Funkciókezelés** elemre.

1. Válassza a **Frissítések keresése** elemet.

1. Nyissa meg az **összes** fület, és keresse meg a *Költségkönyvelési szolgáltatás* nevű funkciót.

1. Válassza az **Engedélyezés most** lehetőséget.

1. Lépjen a **Költségkezelés > Költségkönyvelési szolgáltatás > Beállítás > Költségkönyvelési szolgáltatás paraméterei > Integráció paraméterei** elemre.

1. Írja be a következő kódot az **Alkalmazás azonosítója** mezőbe:<br> 08231eb2-a501-4edb-b3c5-aede5e5e0c3f

1. Az **Adatszolgáltatási végpont** mezőbe írja be a következő URL-címet:<br>https://operationsdataservice.operations365.dynamics.com/

1. Az **Költségkönyvelési szolgáltatási végpont** mezőbe írja be a következő URL-címet:<br>https://costaccountingservice.operations365.dynamics.com/

1. A Költségkönyvelés szolgáltatás készen áll a használatra.

## <a name="related-resources"></a>Kapcsolódó erőforrások

[Költségkönyvelési szolgáltatás kezdőlap](cost-accounting-service-home.md)