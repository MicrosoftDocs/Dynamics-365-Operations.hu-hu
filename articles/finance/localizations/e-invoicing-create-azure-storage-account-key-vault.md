---
title: Hozzon létre Azure tárfiókot és egy kulcstartót
description: Ez a témakör bemutatja, hogyan lehet Azure-tárolási fiókokat és kulcsokat létrehozni.
author: gionoder
ms.date: 08/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: ae2f21e959e35690ca3d8bd09059cfbf679ab842
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8907761"
---
# <a name="create-an-azure-storage-account-and-a-key-vault"></a>Hozzon létre Azure tárfiókot és egy kulcstartót

[!include [banner](../includes/banner.md)]

## <a name="prerequisites"></a>Előfeltételek

A cikk lépéseit csak akkor lehet végrehajtani, ha előtte befejezte a következő feladatokat:

- Kulcstartó-erőforrás létrehozása az Azure szolgáltatásban. További információkért lásd [Az Azure Key Vaulról](/azure/key-vault/general/overview) lehetőséget.
- Hozzon létre egy Azure tárfiókot (Blob-tároló). További információkért lásd a [Azure tárfiók karbantartása](/azure/storage/blobs/) lehetőséget.

## <a name="overview"></a>Áttekintés

Ebben a cikkben két lépést kell végrehajtania:

- Az Azure tárfiók beállítása a tárfiók URI-azonosítójának megszerzéséhez.
- A kulcstartó beállítása a tárfiók URI-azonosítójának tárolásához.

## <a name="set-up-the-azure-storage-account-to-get-the-storage-account-uri"></a>Az Azure tárfiók beállítása a tárfiók URI-azonosítójának megszerzéséhez

1. Nyissa meg az elektronikus számlázással használni kívánt tárfiókot.
2. Nyissa meg az **Adattárolás** > **Tárolók** lehetőséget, és hozzon létre egy új tárolót.
3. Adjon egy nevet a tárolónak, majd állítsa a **Nyilvános hozzáférési szint** mezőt **Privát (névtelen hozzáférés nem lehetséges)** értékre.
4. Nyissa ki a tárolót, és menjen a **Beállítások** > **Hozzáférési szabályzat** lehetőségre.
5. Válassza ki a **Szabályzat hozzáadása** lehetőséget a tárolt hozzáférési szabályok hozzáadásához.
6. Megfelelő módon adja állítsa be az **Azonosító** és az **Engedélyek** mezőt. Az **Engedélyek** mezőben válassza ki az összes engedélyt.

    ![Blob-tárterület-engedély megadása.](media/e-Invoicing-services-create-azure-resources-grant-blob-permissions.png)

7. Adja meg a kezdő és lejárati dátumokat. A lejárati dátumnak jövőbeli dátumnak kell lennie.
8. Válassza az **OK** gombot a szabályzat mentéséhez, majd mentse a módosításokat a tárolóba.
9. Ugorjon a **Beállítások** > **Megosztott hozzáférési jogkivonatok** beállításokhoz, és állítsa be a mezőértékeket. 
10. Adja meg a kezdő és záró dátumokat. A záró dátumnak jövőbeli dátumnak kell lennie.
11. Az **Engedélyek** mezőben válassza a következő engedélyeket: **Olvasás**, **Hozzáadás**, **Létrehozás**, **Írás**, **Törlés** és **Lista**. 
12. Válassza a **SAS-jogkivonat és URL létrehozása** lehetőséget.
13. Másolja és tárolja az értéket a **Blob SAS URL-cím** mezőjében. Ezt az értéket használja a rendszer a következő eljárásban, és *Közös hozzáférésű jogosultságkód URI* néven fog rá hivatkozni.

## <a name="set-up-the-key-vault-to-store-the-storage-account-uri"></a>A kulcstartó beállítása a tárfiók URI-azonosítójának tárolásához

1. Nyissa meg az elektronikus számlázással használni kívánt kulcstartót.
2. Menjen a **Beállítások** \> **Titkok** lehetőségre, majd válassza a **Létrehozás/importálás** elemet az új titok létrehozásához.
3. A **Titok létrehozása** oldal **Feltöltési beállítások** mezőjében válassza a **Manuális** lehetőséget.
4. Adja meg a titok nevét. Ezt a nevet fogják használni a szolgáltatás Regulatory Configuration Service (RCS) szolgáltatásban történő beállításakor, illetve *kulcstartó titok* néven fognak rá hivatkozni.
5. Az **Érték** mezőben adja meg az előző műveletben átmásolt közös hozzáférésű jogosultságkód URI-ját, majd válassza a **Létrehozás** lehetőséget.
6. Állítsa be a hozzáférési szabályzatot, hogy az Elektronikus számlázás megfelelő biztonsági hozzáférési szintet tudjon engedélyezni a létrehozott titoknak. Menjen a **Beállítások \> Hozzáférési szabályzat** lehetőségre, és válassza a **Hozzáférési szabályzat hozzáadása** elemet.
7. Állítsa be a **Megszerzés** és a **Lista** műveleteihez tartozó titkos engedélyeket.

    ![Szolgáltatáshozzáférés megadása.](media/e-Invoicing-services-create-azure-resources-grant-service-access.png)

8. Állítsa be a **Megszerzés** és a **Lista** műveleteihez tartozó tanúsítványengedélyeket.

    ![Tanúsítványengedély megadása.](media/e-Invoicing-services-create-azure-resources-grant-certificate-permission.png)

9. A **Rendszerbiztonsági tag kiválasztása** mezőben válassza a **Nincs kiválasztva** lehetőséget.
10. A **Rendszerbiztonsági tag** párbeszédpanelen válassza ki a rendszerbiztonsági tagot az **e-számlázási szolgáltatás** hozzáadásával.
11. Válassza a **Hozzáadás** parancsot, majd válassza a **Mentés** elemet.
12. Az **Áttekintés** oldalról másolja át a **DNS név** lehetőséghez tartozó kulcstartó értékét. Ezt az értéket fogják használni a szolgáltatás RCS-ben történő beállításakor, illetve *kulcstartó URI* néven fognak rá hivatkozni.

> [!NOTE]
> A tárfiók további biztonságának érdekében konfigurálja az Azure Defender for Storage szolgáltatást.
> 
> További információért lásd: [Bevezetés az Azure Defender for Storage szolgáltatásba](/azure/security-center/defender-for-storage-introduction).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
