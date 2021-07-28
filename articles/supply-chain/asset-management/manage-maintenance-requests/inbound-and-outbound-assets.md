---
title: Bejövő és kimenő eszközök
description: Ez a cikk a bejövő és kimenő eszközök Eszközök kezelése szolgáltatásban való regisztrálását ismerteti.
author: johanhoffmann
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetOutboundObjectsListPage, EntAssetOutboundObjectsDeliver, EntAssetInboundObjectsListPage, EntAssetInboundObjectsRecieve
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 86d85d280b32834c36691535a019ef6d5141bf93
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2021
ms.locfileid: "6356021"
---
# <a name="inbound-and-outbound-assets"></a>Bejövő és kimenő eszközök

[!include [banner](../../includes/banner.md)]

 

Ha a cég más helyekről vagy ügyfelektől kapott eszközök javítási vagy karbantartási feladataival (is) foglalkozik, akkor az Eszközök kezelése szolgáltatással nyomon követhetők mind a cég felé küldött eszközök, mind a visszakerülő kimenő eszközök.

> [!NOTE]
> Ha bejövő és kimenő életciklus-állapotokkal szeretné kezelni a bejövő és a visszakerülő eszközöket, akkor az ilyen műveletek támogatásához életciklus-állapotokat és életciklusmodelleket kell beállítania a karbantartási kérésekhez. További információ: [Karbantartási kérések](../setup-for-maintenance-requests/requests.md).

Az Eszközök kezelése beállítása határozza meg, hogy használhatók-e bejövő és kimenő eszközök.

## <a name="register-assets-as-inbound"></a>Eszközök regisztrálása bejövőként

1. Válassza az **Eszközök kezelése** \> **Közös** \> **Karbantartási kérések** \> **Aktív karbantartási kérések** elemet.
2. Válassza ki a karbantartási kérést.
3. Válassza a **Karbantartási kérés állapotának frissítése** lehetőséget.
4. Válassza a **Bejövő** (vagy a bejövő eszközökhöz létrehozott másik életciklus-állapotot), majd az **OK** lehetőséget.

![Eszközök regisztrálása bejövőként.](media/07-manage-maintenance-requests.png)

## <a name="register-inbound-assets-as-received"></a>Bejövő eszközök regisztrálása fogadottként

1. Válassza az **Eszközök kezelése** \> **Közös** \> **Bejövő / kimenő** \> **Bejövő eszközök** lehetőséget.
2. Válassza ki az eszközt vagy a karbantartási kérést.
3. Válassza ki a **Tárgyi eszközök fogadása** lehetőséget.
4. A **Fogadott** mezőben adja meg a dátumot és az időpontot. Majd kattintson az **OK** lehetőségre. A rekord eltűnik a **Bejövő eszközök** listaoldalról.

![Bejövő eszközök regisztrálása fogadottként.](media/08-manage-maintenance-requests.png)

## <a name="register-assets-as-outbound"></a>Eszközök regisztrálása kimenőként

A karbantartási vagy javítási feladat befejezése után regisztrálhatja az eszközt visszaküldöttként.

1. Válassza az **Eszközök kezelése** \> **Közös** \> **Karbantartási kérések** \> **Aktív karbantartási kérések** elemet.
2. Válassza ki a karbantartási kérést.
3. Válassza a **Karbantartási kérés állapotának frissítése** lehetőséget.
4. Válassza a **Kimenő** (vagy a kimenő eszközökhöz létrehozott másik életciklus-állapotot), majd az **OK** lehetőséget.

## <a name="register-outbound-assets-as-delivered"></a>Kimenő eszközök regisztrálása átadottként

1. Válassza az **Eszközök kezelése** \> **Közös** \> **Bejövő / kimenő** \> **Kimenő eszközök** lehetőséget.
2. Válassza ki az eszközt vagy a karbantartási kérést.
3. Válassza ki az **Eszközök kézbesítése** lehetőséget.
4. A **Kézbesítve** mezőben adja meg a dátumot és az időpontot. Majd kattintson az **OK** lehetőségre. A rekord eltűnik a **Kimenő eszközök** listaoldalról.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]