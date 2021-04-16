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
ms.openlocfilehash: 964ed05eaba2a4dbba904b4ce0e0be33d0925fb5
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753456"
---
# <a name="power-bi-destination"></a><span data-ttu-id="054e6-103">Power BI cél</span><span class="sxs-lookup"><span data-stu-id="054e6-103">Power BI destination</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="054e6-104">Beállíthat egy archiválási Microsoft Power BI célhelyet a kimenő dokumentumok létrehozásához konfigurált elektronikus jelentési (ER) formátumú fájlok MAPPA vagy FÁJL összetevőihez.</span><span class="sxs-lookup"><span data-stu-id="054e6-104">You can configure a Microsoft Power BI destination for each folder or file component of an Electronic reporting (ER) format that is configured to generate outbound documents.</span></span> <span data-ttu-id="054e6-105">A célhely beállítása alapján a generált dokumentumokat a rendszer egy korábban konfigurált SharePoint-mappában tárolja.</span><span class="sxs-lookup"><span data-stu-id="054e6-105">Based on the setting of the destination, a generated document is stored in a previously configured SharePoint folder.</span></span>

<span data-ttu-id="054e6-106">Állítsa az **Engedélyezve** elemet **Igen** értékre ahhoz, hogy az elektronikus jelentési (ER) konfiguráció adatokat vigyen át a Dynamics 365 Finance-példányból a Microsoft Power BI-szolgáltatásokba.</span><span class="sxs-lookup"><span data-stu-id="054e6-106">Set **Enabled** to **Yes** to use your ER configuration to arrange the transfer of data from your Dynamics 365 Finance instance to Microsoft Power BI services.</span></span> <span data-ttu-id="054e6-107">Az átvitt fájlok tárolása egy Microsoft SharePoint Server példányon történik, amelyet ennek a célnak megfelelően konfigurálni kell.</span><span class="sxs-lookup"><span data-stu-id="054e6-107">The transferred files are stored on a Microsoft SharePoint Server instance that must be configured for that purpose.</span></span> <span data-ttu-id="054e6-108">További információ: [Elektronikus jelentéskészítés (ER) konfigurálása az adatok Power BI szolgáltatásba való lehívásához](general-electronic-reporting-report-configuration-get-data-powerbi.md).</span><span class="sxs-lookup"><span data-stu-id="054e6-108">For more information, see [Configure Electronic reporting (ER) to pull data into Power BI](general-electronic-reporting-report-configuration-get-data-powerbi.md).</span></span>

<span data-ttu-id="054e6-109">[![Célhely beállításai oldal](./media/ER_Destinations-EnablePowerBIDestination.png)](./media/ER_Destinations-EnablePowerBIDestination.png)</span><span class="sxs-lookup"><span data-stu-id="054e6-109">[![Destination setting page](./media/ER_Destinations-EnablePowerBIDestination.png)](./media/ER_Destinations-EnablePowerBIDestination.png)</span></span>

## <a name="additional-resources"></a><span data-ttu-id="054e6-110">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="054e6-110">Additional resources</span></span>

- [<span data-ttu-id="054e6-111">Elektronikus jelentéskészítés (ER) áttekintése</span><span class="sxs-lookup"><span data-stu-id="054e6-111">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="054e6-112">Elektronikus jelentéskészítés (ER) céljai</span><span class="sxs-lookup"><span data-stu-id="054e6-112">Electronic reporting (ER) destinations</span></span>](electronic-reporting-destinations.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]