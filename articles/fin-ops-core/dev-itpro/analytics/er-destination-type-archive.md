---
title: Archivált ER céltípusa
description: Ez a témakör arról tartalmaz tájékoztatást, hogyan kell konfigurálni egy archiválási célt az Elektronikus jelentéskészítési (ER) formátumok egyes MAPPA vagy FÁJL összetevőihez.
author: NickSelin
manager: AnnBe
ms.date: 11/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 0067024d7a29e2a1db3b7fdba9ea3c6a63aad648
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/30/2021
ms.locfileid: "5094129"
---
# <a name="archive-er-destination-type"></a>Archivált ER céltípusa

[!include [banner](../includes/banner.md)]

Beállíthat egy archiválási célhelyet a kimenő dokumentumok létrehozásához konfigurált elektronikus jelentési (ER) formátumú fájlok **Mappa** vagy **Fájl** összetevőihez. A célhely beállításai alapján a létrejövő dokumentumot a rendszer az ER-feladatok listájának egy rekordja csatolmányaként tárolja. Az eredményeket a **Szervezeti adminisztráció** \> **Elektronikus jelentés** \> **Elektronikus jelentéskészítési feladatok** elemnél tekintheti meg.

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

> [!NOTE] 
> Az ER-keretrendszer véglegesen tárolja a fájlokat az Azure Blob tárolóban ellentétben az Adatkezelési keretrendszerrel, amely a hét napos adatmegőrzési szabályzatot alkalmazza a feldolgozandó dokumentumokra. További információ: [API az üzenetek állapotának lekéréséhez](../data-entities/recurring-integrations.md#api-for-getting-message-status) és [Állapot-ellenőrző API](../data-entities/data-management-api.md#status-check-api). Az ER-vel kapcsolatos fájlok az Azure Blob storage-ban lesznek tárolva az alkalmazástábla-rekordok mellékleteként, amíg szükséges. Egyetlen fájl törlődik az Azure Blob storage-ból az alkalmazástábla-rekorddal együtt, amelyhez ez a fájl csatolva volt.

## <a name="additional-resources"></a>További erőforrások

- [Elektronikus jelentéskészítés (ER) áttekintése](general-electronic-reporting.md)
- [Elektronikus jelentéskészítés (ER) céljai](electronic-reporting-destinations.md)
- [A dokumentumkezelés konfigurálása](../../fin-ops/organization-administration/configure-document-management.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]