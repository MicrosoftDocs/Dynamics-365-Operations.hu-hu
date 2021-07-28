---
title: Power BI ER céltípusa
description: Ez a témakör azt mutatja be, hogyan kell a Power BI ER-célhelyet kimenő dokumentumokhoz konfigurálni.
author: NickSelin
ms.date: 01/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 10.0.09
ms.openlocfilehash: 20f3c04e5a916524c2c2e8fcb49dfbcd41eb6bb6
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2021
ms.locfileid: "6347900"
---
# <a name="power-bi-destination"></a>Power BI cél

[!include [banner](../includes/banner.md)]

Beállíthat egy archiválási Microsoft Power BI célhelyet a kimenő dokumentumok létrehozásához konfigurált elektronikus jelentési (ER) formátumú fájlok MAPPA vagy FÁJL összetevőihez. A célhely beállítása alapján a generált dokumentumokat a rendszer egy korábban konfigurált SharePoint-mappában tárolja.

Állítsa az **Engedélyezve** elemet **Igen** értékre ahhoz, hogy az elektronikus jelentési (ER) konfiguráció adatokat vigyen át a Dynamics 365 Finance-példányból a Microsoft Power BI-szolgáltatásokba. Az átvitt fájlok tárolása egy Microsoft SharePoint Server példányon történik, amelyet ennek a célnak megfelelően konfigurálni kell. További információ: [Elektronikus jelentéskészítés (ER) konfigurálása az adatok Power BI szolgáltatásba való lehívásához](general-electronic-reporting-report-configuration-get-data-powerbi.md).

[![Célhely beállításai oldal.](./media/ER_Destinations-EnablePowerBIDestination.png)](./media/ER_Destinations-EnablePowerBIDestination.png)

## <a name="additional-resources"></a>További erőforrások

- [Elektronikus jelentéskészítés (ER) áttekintése](general-electronic-reporting.md)
- [Elektronikus jelentéskészítés (ER) céljai](electronic-reporting-destinations.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]