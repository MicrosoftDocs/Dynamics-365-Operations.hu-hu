---
title: Hozzon létre Azure tárfiókot és egy kulcstartót
description: Ez a témakör azt mutatja be, hogyan lehet egy Azure tárfiókot és egy kulcstartót létrehozni.
author: gionoder
manager: AnnBe
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: b8e39539f767cc2944a9a7fdda09121921c64763
ms.sourcegitcommit: 025561f6a21fe8705493daa290f3f6bfb9f1b962
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/23/2020
ms.locfileid: "3835970"
---
# <a name="create-an-azure-storage-account-and-a-key-vault"></a>Hozzon létre Azure tárfiókot és egy kulcstartót

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]


Az Elektronikus számlázásbővítmény szolgáltatás a felelős a vállalat tulajdonában lévő Microsoft Azure-erőforrásokban lévő összes üzleti adatának tárolásáért. Ha biztosítani szeretné, hogy a szolgáltatás megfelelően működjön, és hogy az elektronikus számlázásbővítményhez szükséges, illetve az általa létrehozott összes üzleti adat csak a bővítmény számára legyen érhető el, akkor két fő Azure-erőforrást kell létrehoznia:

- Az elektronikus számlák tárolásához szükséges Azure tárfiókot (Blob-tároló)
- Egy Azure-kulcstartót a tanúsítványok és a tárolási fiók Uniform Resource Identifier (URI) tárolásához

> [!NOTE]
> A dedikált kulcstartó-erőforrást és a vevői Blob-tárolót kifejezetten az Elektronikus számlázásbővítménnyel történő használatra kell felosztani.

## <a name="prerequisites"></a>Előfeltételek

Mielőtt teljesítené az ebben a témakörben ismertetett lépéseket, bizonyosodjon meg arról, hogy a következő feladatok el lettek végezve:

- Kulcstartó-erőforrás létrehozása az Azure szolgáltatásban. További információkért lásd [Az Azure Key Vaulról](https://docs.microsoft.com/azure/key-vault/general/overview) lehetőséget.
- Hozzon létre egy Azure tárfiókot (Blob-tároló). További információkért lásd a [Azure tárfiók karbantartása](https://docs.microsoft.com/azure/storage/blobs/) lehetőséget.

## <a name="overview"></a>Áttekintés

Ebben a témakörben két fő lépést kell végrehajtania:

- Az Azure tárfiók beállítása a tárfiók URI-azonosítójának megszerzéséhez.
- A kulcstartó beállítása a tárfiók URI-azonosítójának tárolásához.

## <a name="set-up-the-azure-storage-account-to-get-the-storage-account-uri"></a>Az Azure tárfiók beállítása a tárfiók URI-azonosítójának megszerzéséhez

1. Nyissa meg az elektronikus számlázásbővítménnyel használni kívánt tárfiókot.
2. Nyissa meg a **Blob-szolgáltatás** \> **Tárolók** lehetőséget, és hozzon létre egy új tárolót.
3. Adjon egy nevet a tárolónak, majd állítsa a **Nyilvános hozzáférési szint** mezőt **Privát (névtelen hozzáférés nem lehetséges)** értékre.
4. Nyissa ki a tárolót, és menjen a **Beállítások \> Hozzáférési szabályzat** lehetőségre.
5. Válassza ki a **Szabályzat hozzáadása** lehetőséget a tárolt hozzáférési szabályok hozzáadásához.
6. Megfelelő módon adja állítsa be az **Azonosító** és az **Engedélyek** mezőt. Az **Engedélyek** mezőben válassza ki az összes engedélyt.

    ![Blob-tárterület-engedély megadása](media/e-Invoicing-services-create-azure-resources-grant-blob-permissions.png)

7. Adja meg a kezdő és lejárati dátumokat. A lejárati dátumnak jövőbeli dátumnak kell lennie.
8. Válassza az **OK** gombot a szabályzat mentéséhez, majd mentse a módosításokat a tárolóba.
9. Térjen vissza a tárfiókhoz, és nyissa meg a **Storage Explorer (előzetes verzió)** lehetőséget.
10. Kattintson a jobb egérgombbal a tárolóra, majd válassza a **Közös hozzáférésű jogosultságkód megszerzése** lehetőségre.
11. A **Közös hozzáférésű jogosultságkód** párbeszédpanelen másolja és tárolja az értéket az **URI** mezőbe. Ezt az értéket használja a rendszer a következő eljárásban, és *Közös hozzáférésű jogosultságkód URI* néven fog rá hivatkozni.

    ![Az URI-érték kiválasztása és másolása](media/e-Invoicing-services-create-azure-resources-select-and-copy-uri.png)

## <a name="set-up-the-key-vault-to-store-the-storage-account-uri"></a>A kulcstartó beállítása a tárfiók URI-azonosítójának tárolásához

1. Nyissa meg az elektronikus számlázásbővítménnyel használni kívánt kulcstartót.
2. Menjen a **Beállítások** \> **Titkok** lehetőségre, majd válassza a **Létrehozás/importálás** elemet az új titok létrehozásához.
3. A **Titok létrehozása** oldal **Feltöltési beállítások** mezőjében válassza a **Manuális** lehetőséget.
4. Adja meg a titok nevét. Ezt a nevet fogják használni a szolgáltatás Regulatory Configuration Service (RCS) szolgáltatásban történő beállításakor, illetve *kulcstartó titok* néven fognak rá hivatkozni.
5. Az **Érték** mezőben válassza a **Közös hozzáférésű jogosultságkód URI** lehetőséget, majd a **Létrehozás** elemet.
6. Állítsa be a hozzáférési szabályzatot, hogy az Elektronikus számlázásbővítmény megfelelő biztonsági hozzáférési szintet tudjon engedélyezni a létrehozott titoknak. Menjen a **Beállítások \> Hozzáférési szabályzat** lehetőségre, és válassza a **Hozzáférési szabályzat hozzáadása** elemet.
7. Állítsa be a **Megszerzés** és a **Lista** műveleteihez tartozó titkos engedélyeket.

    ![Szolgáltatáshozzáférés megadása](media/e-Invoicing-services-create-azure-resources-grant-service-access.png)

8. Állítsa be a **Megszerzés** és a **Lista** műveleteihez tartozó tanúsítványengedélyeket.

    ![Tanúsítványengedély megadása](media/e-Invoicing-services-create-azure-resources-grant-certificate-permission.png)

9. A **Rendszerbiztonsági tag** párbeszédpanelen válassza ki a rendszerbiztonsági tagot az **Elektronikus számlázásbővítmény** hozzáadásával.
10. Válassza a **Hozzáadás** lehetőséget, majd a **Key Vault-módosítások mentése** elemet.
11. Az **Áttekintés** oldalról másolja át a **DNS név** lehetőséghez tartozó kulcstartó értékét. Ezt az értéket fogják használni a szolgáltatás RCS-ben történő beállításakor, illetve *kulcstartó URI* néven fognak rá hivatkozni.