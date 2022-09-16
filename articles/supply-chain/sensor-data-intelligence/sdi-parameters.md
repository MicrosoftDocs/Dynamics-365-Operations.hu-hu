---
title: Sensor Data Intelligence paraméterei
description: Ez a cikk a Konfigurációs beállításokról nyújt tájékoztatást, amelyek a Konfigurációs adatok paraméterei oldalon érhetők el.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: IoTIntCoreServiceParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 4a6665cc078e54da4ebb7920ec8826352ab7a816
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/08/2022
ms.locfileid: "9428980"
---
# <a name="sensor-data-intelligence-parameters"></a>Sensor Data Intelligence paraméterei

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Az **Adatinteraméterek** lapon néhány beállítást is meg lehet jelenni, amelyek a funkció beállítására használhatók. Ezek közé tartoznak az Azure-kapcsolati paraméterek és a felhasználóknak a mértékegységre válaszként küldött figyelmeztető üzenetek élettartamának paramétere.

## <a name="read-and-change-connection-details-for-your-azure-iot-solution"></a>Az Azure Azure-megoldás kapcsolati részleteinek olvasása és módosítása

Az Azure Dynamics 365 Supply Chain Management Azure Azure-megoldást jellemzően az Azure-erőforrások telepítése és csatlakoztatása a Microsofthoz **lapról** lehet beállítani, amely mindkét eljárásban végigvezeti a folyamaton. (További tájékoztatás: [Az Azure platformra telepített Ionét-megoldás](sdi-deploy-iot-solution-on-azure.md).) Az ellátásilánc-kezelésben a csatlakozási részletek bármikor megtekinthetők és szerkeszthetők a következő lépések segítségével.

1. Ugrás a rendszerfelügyelet **beállításához \>\> – Az adatintelligencia \>- és adatintelligencia-paraméterek.**
1. **·** **Adja meg az Idősorozatok lap Redis metrikus üzlet kapcsolati karakterláncának** **mezőjében annak az Azure-IÓT-megoldásnak az elsődleges kapcsolati karakterláncát (StackExchange.Redis),** amelybe csatlakozni szeretne. Az érték megkeresével kapcsolatos további [tudnivalókat lásd Az Azure-alapú Ionyen alapú megoldás telepítése.](sdi-deploy-iot-solution-on-azure.md)
1. Az Integrációk **lap** **Azure AD** alkalmazás-ügyfélazonosító mezőjében adja meg annak az Azure-IÓ-megoldásnak az ügyfélazonosítóját, **amelybe** csatlakozni kíván. Az érték megkeresével kapcsolatos további [tudnivalókat lásd Az Azure-alapú Ionyen alapú megoldás telepítése.](sdi-deploy-iot-solution-on-azure.md)

## <a name="set-the-lifetime-of-alert-messages"></a>A figyelmeztető üzenetek élettartamának beállítása

Minden alkalommal, amikor az adatintelligencia képes észlelni egy olyan helyzetet, amely felhasználói beavatkozást igényel, értesítést küld az érintett felhasználónak. Ha meg szeretné akadályozni, hogy ezek az értesítések feledődni tudjanak a rendszerben, néhány nap múlva be kell állítania az értesítések lejáratát.

1. Ugrás a rendszerfelügyelet **beállításához \>\> – Az adatintelligencia \>- és adatintelligencia-paraméterek.**
1. Az Értesítések **lap** **Értesítés** napjai az élő mezőben adja meg, hogy hány napig kell az értesítést megtartani. A megadott időmennyiséget követően a rendszer törli az értesítést.
