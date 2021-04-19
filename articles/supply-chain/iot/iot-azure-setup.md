---
title: A IoT Intelligencia Azure-erőforrásainak beállítása
description: Ez a témakör azt mutatja be, hogyan lehet létrehozni és konfigurálni a Microsoft Azure-erőforrásokat, amelyekre az IoT Intelligencia alkalmazáshoz szükség van.
author: robinarh
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: ''
ms.custom: ''
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 722904aa75a9d95b99c83f39a1d79b9c796714b3
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5821105"
---
# <a name="set-up-azure-resources-for-iot-intelligence"></a>A IoT Intelligencia Azure-erőforrásainak beállítása

[!include [banner](../../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet létrehozni és konfigurálni a Microsoft Azure-erőforrásokat, amelyekre az IoT Intelligencia alkalmazáshoz szükség van.

## <a name="create-azure-resources"></a>Azure-erőforrások létrehozása

Hajtsa végre az alábbi lépéseket egy IoT-központ, egy Redis-gyorsítótár és egy a Microsoft Dynamics 365 Supply Chain Management által elérhető kulcstároló létrehozásához.

### <a name="verify-that-the-microsoft-dynamics-erp-microservices-first-party-app-id-is-in-your-tenant"></a>Győződjön meg róla, hogy a Microsoft Dynamics ERP Microservices belső alkalmazás azonosítója a bérlőben található.

Ha ellenőrizni szeretné, hogy a Microsoft Dynamics ERP Microservices -szolgáltatások belső alkalmazás azonosítója a bérlőben található, kövesse az alábbi lépéseket.

1. Jelentkezzen be az Azure portálon: <https://portal.azure.com>.
2. Ugorjon ide: **Azure Active Directory**.
3. Nyissa meg a **Vállalati alkalmazásokat**.
4. Az **Alkalmazás típusa** mezőben válassza ki a **Microsoft-alkalmazások** lehetőséget.
5. A keresőmezőbe írja be a **Microsoft Dynamics ERP Microservices** kifejezést.
6. Ellenőrizze, hogy a **Microsoft Dynamics ERP Microservices** szerepel-e a listán. Más alkalmazások neve hasonló lehet. Ezért győződjön meg arról, hogy megtalálta a megfelelő alkalmazást. Az alkalmazás azonosítója: **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.

    Ha az alkalmazás nem szerepel a listában, akkor azt fel kell venni a bérlőhöz:

    1. Az Azure portál eszköztárán válassza ki a gombot az Azure Cloud Shell megnyitásához.
    2. Futtassa az **Install-Module AzureAD** parancsot. Adja meg az **Y** értéket a modul telepítéséhez.
    3. Futtassa a **Get-InstalledModule -Name "AzureAD"** parancsot annak ellenőrzéséhez, hogy a modul telepítve van.
    4. Futtassa a **Connect-AzureAD -Confirm** parancsot a hitelesítés futtatásához.
    5. Futtassa a **New-AzureADServicePrincipal -AppId 0cdb527f-a8d1-4bf8-9436-b352c68682b2** parancsot.

    Most ismételje meg az 1–6. lépést, és győződjön meg róla, hogy az alkalmazás azonosítója a bérlőben található.

### <a name="create-a-key-vault-resource"></a>Kulcstároló erőforrás létrehozása

Kulcstároló erőforrás létrehozásához az alábbi lépéseket hajtsa végre.

1. Az Azure portálon hozzon létre vagy nyisson meg egy erőforráscsoportot.
2. Válassza a **Hozzáadás** lehetőséget.
3. Az **Új** oldalon, a keresés mezőben írja be a **Kulcstároló** értéket. Ezután válassza a **Létrehozása** lehetőséget.
4. A **Kulcstároló létrehozása** oldalon, a **Kulcstároló neve** mezőben adjon meg egy nevet.
5. Tekintse át az alapértelmezett értékeket, majd válassza az **Ellenőrzés és létrehozás** elemet.
6. Válassza a **Létrehozása** lehetőséget.

A kulcstároló a háttérben jön létre.

### <a name="create-an-iot-hub-resource"></a>IoT-központ erőforrásának létrehozása

Egy IoT-központ erőforrás létrehozásához az alábbi lépéseket hajtsa végre.

1. Hozzon létre vagy nyisson meg egy erőforráscsoportot.
2. Válassza a **Hozzáadás** lehetőséget.
3. Az **Új** oldalon, a keresés mezőben írja be az **IoT-központ** értéket. Ezután válassza a **Létrehozása** lehetőséget.
4. Az **IoT-központ neve** mezőben adjon meg egy nevet.
5. Tekintse át az alapértelmezett értékeket, majd válassza az **Ellenőrzés és létrehozás** elemet.
6. Válassza a **Létrehozása** lehetőséget.

Az IoT-központ a háttérben jön létre.

> [!NOTE]
> Azt ajánljuk, hogy az egyes környezetekben csak egy IoT-központ erőforrást hozzon létre.

### <a name="create-a-redis-cache-resource"></a>Redis-gyorsítótár erőforrásának létrehozása

Redis-gyorsítótár erőforrás létrehozásához az alábbi lépéseket hajtsa végre.

1. Hozzon létre vagy nyisson meg egy erőforráscsoportot.
2. Válassza a **Hozzáadás** lehetőséget.
3. Az **Új** oldalon, a keresés mezőben írja be az **Azure gyorsítótár Redig számára** értéket. Ezután válassza a **Létrehozása** lehetőséget.
4. A **DNS-név** mezőben adjon meg egy nevet.
5. Tekintse át az alapértelmezett értékeket, majd válassza a **Létrehozás** elemet.

A Redis-gyorsítótár a háttérben jön létre.

> [!NOTE]
> Azt ajánljuk, hogy az egyes környezetekben csak egy Redis-gyorsítótárat hozzon létre.

Az összes erőforrás létrehozásra került.

## <a name="configure-the-azure-resources"></a>Az Azure-erőforrások konfigurálása

### <a name="configure-the-iot-hub"></a>Az IoT-központ konfigurálása

Az IoT-központ konfigurálásához tegye a következőket.

1. Válassza ki az IoT-központ erőforrását az erőforrások között.
2. A bal oldali navigációs ablakban válassza a **Beépített végpontok** elemet.
3. A **Fogyasztói csoportok** területen illessze be a következő fogyasztói csoportokat. Ezek a fogyasztói csoportok megfelelnek a nem beépített eseteknek.

    + microsoft.dynamics.iotintelligence-1
    + microsoft.dynamics.iotintelligence-2
    + microsoft.dynamics.iotintelligence-3

### <a name="configure-the-key-vault"></a>A kulcstároló konfigurálása

A kulcstároló konfigurálásához tegye a következőket.

1. Válassza ki a kulcstároló erőforrását az erőforrások között.
2. A bal oldali navigációs ablakban válassza ki a **Hozzáférési irányelvek** lehetőséget.
3. Válassza a **Hozzáférési irányelv hozzáadása** lehetőséget.
4. A **Hozzáférési irányelv hozzáadása** oldalon, a **Titkos engedélyek** mezőben válassza a **Beolvasás** és a **Lista** elemet.
5. Kattintson a **Főszolgáltató kiválasztása** lehetőségre.
6. A **Főszolgáltató** párbeszédpanelen keresse meg és válassza ki a **Microsoft Dynamics ERP Microservices** lehetőséget. Ezután válassza a **Kiválasztás** lehetőséget.
7. Válassza a **Hozzáadás** lehetőséget.
8. Válassza a **Mentés** lehetőséget.

Az alkalmazásnak most már van hozzáférése a kulcstároló titkos kódjaihoz.

### <a name="save-the-iot-hub-connection-string-secret"></a>Mentse az IoT-központ titkos kapcsolati karakterláncát

Az IoT-központ kapcsolati karakterláncához tartozó titkos kód mentéséhez kövesse az alábbi lépéseket.

1. Válassza ki az IoT-központ erőforrását az erőforrások között.
2. A bal oldali navigációs ablakban válassza a **Beépített végpontok** elemet.
3. Másolja az értéket az **Eseményközpont-kompatibilis végpont** mezőbe.
4. Ugrás a kulcstároló-erőforrásra.
5. A bal oldali navigációs ablakban válassza ki a **Titkos kódok** lehetőséget.
6. Válassza a **Generálás/Importálás** lehetőséget.
7. A **Név** mezőben adjon meg egy nevet.
8. Az **Érték** mezőbe illessze be a korábban másolt végpontértéket.
9. Válassza a **Létrehozása** lehetőséget.

### <a name="save-the-redis-cache-connection-string-secret"></a>A Redis-gyorsítótár titkos kapcsolati karakterláncának mentése

A Redis-gyorsítótár kapcsolati karakterláncához tartozó titkos kód mentéséhez kövesse az alábbi lépéseket.

1. Válassza ki a Redis-gyorsítótár erőforrását az erőforrások között.
2. Válassza a **Hozzáférési kulcsok** lehetőséget.
3. Másolja az **Elsődleges kapcsolati karakterlánc** mező értékét.
4. Ugrás a kulcstároló-erőforrásra.
5. A bal oldali navigációs ablakban válassza ki a **Titkos kódok** lehetőséget.
6. Válassza a **Generálás/Importálás** lehetőséget.
7. A **Név** mezőben adjon meg egy nevet.
8. Az **Érték** mezőbe illessze be a korábban másolt kapcsolati karakterláncot.
9. Válassza a **Létrehozása** lehetőséget.

> [!NOTE]
> Minden alkalommal, amikor frissít egy kapcsolati karakterláncot, frissítenie kell a titkos értékeket is.

Most befejezte a szükséges Azure-erőforrások létesítését. A következő lépés az [IoT Intelligencia beépülő modul telepítése a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban](iot-lcs-setup.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]