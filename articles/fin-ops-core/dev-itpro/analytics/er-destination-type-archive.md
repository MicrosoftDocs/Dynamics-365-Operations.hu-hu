---
title: Archivált ER céltípusa
description: Ez a témakör azt mutatja be, hogyan lehet beállítani egy archiválási célhelyet a kimenő dokumentumok létrehozásához konfigurált elektronikus jelentési (ER) formátumú fájlok MAPPA vagy FÁJL összetevőihez.
author: NickSelin
manager: AnnBe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 8797a68507a5116c6adbf1f2d805838fa507958c
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745585"
---
# <a name="archive-destination"></a>Archív cél

[!include [banner](../includes/banner.md)]

Beállíthat egy archiválási célhelyet a kimenő dokumentumok létrehozásához konfigurált elektronikus jelentési (ER) formátumú fájlok MAPPA vagy FÁJL összetevőihez. A célhely beállításai alapján a létrejövő dokumentumot a rendszer az ER-feladatok listájának egy rekordja csatolmányaként tárolja.

Ezen opcióval a generált dokumentum elküldhető egy Microsoft SharePoint vagy Microsoft Azure Storage mappába. A kiválasztott dokumentumtípus által meghatározott célra történő eredményküldéshez állítsa a **Bekapcsolva** opciót **Igen** állapotba. Csak azok a dokumentumtípusok választhatók ki, amelyeknél a csoport beállítása **File**. A dokumentumok [típusait](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) itt határozhatja meg: **Szervezeti adminisztráció** \> **Dokumentumkezelés** \> **Dokumentumtípusok**. Az ER célok konfigurálásának folyamata megegyezik a dokumentumkezelő rendszer konfigurálásával.

[![Dokumentumtípusok lapja](./media/ER_Destinations-SharePointDocuType.png)](./media/ER_Destinations-SharePointDocuType.png)

A hely határozza meg, hogy a file hol kerül tárolásra. Az **Archívum** cél engedélyezése után az eredmény menthető a Feladat archívumba. Az eredményeket a **Szervezeti adminisztráció** \> **Elektronikus jelentés** \> **Elektronikus jelentéskészítési archivált feladatok** elemnél tekintheti meg.

> [!NOTE]
> A Feladatarchívum ponthoz a dokumentumtípust az alkalmazásban a következő helyen választhatja ki: **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** \> **Elektronikus jelentéskészítés paraméterei**. További információ: [Az elektronikus jelentéskészítési (ER) keretrendszer konfigurálása](electronic-reporting-er-configure-parameters.md#prerequisites-for-er-setup).

## <a name="sharepoint"></a>SharePoint

A fájlt egy kijelölt SharePoint mappába is mentheti. Az alapértelmezett SharePoint kiszolgálót itt határozhatja meg: **Szervezeti adminisztráció** \> **Dokumentumkezelés** \> **Dokumentumkezelés paraméterei**. A **SharePoint** lapon konfigurálja a SharePoint mappát. Ezt követően kiválaszthatja azt azon mappaként, ahova az ER-kimenetet menti a rendszer. Ezen dokumentumtípus esetén ki kell választani a **SharePoint**-helyet.

[![SharePoint-mappa kiválasztása](./media/ER_Destinations-SharePointDocuTypeLocation.png)](./media/ER_Destinations-SharePointDocuTypeLocation.png)

## <a name="azure-storage"></a>Azure Storage

Ha a dokumentumtípus helye **Azure tárhely**, a fájl menthető az Azure Storage tárhelyre.

## <a name="additional-resources"></a>További erőforrások

- [Elektronikus jelentéskészítés (ER) áttekintése](general-electronic-reporting.md)
- [Elektronikus jelentéskészítés (ER) céljai](electronic-reporting-destinations.md)
- [A dokumentumkezelés konfigurálása](../../fin-ops/organization-administration/configure-document-management.md)
