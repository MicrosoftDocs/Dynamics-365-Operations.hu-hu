---
title: Power BI ER céltípusa
description: Ez a témakör azt mutatja be, hogyan kell a Power BI ER-célhelyet kimenő dokumentumokhoz konfigurálni.
author: NickSelin
manager: AnnBe
ms.date: 01/23/2020
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
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 10.0.09
ms.openlocfilehash: e17ca4eb6b446edd18f4b3c5e697b073f8136a6b
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745537"
---
# <a name="power-bi-destination"></a><span data-ttu-id="6467b-103">Power BI cél</span><span class="sxs-lookup"><span data-stu-id="6467b-103">Power BI destination</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6467b-104">Beállíthat egy archiválási Microsoft Power BI célhelyet a kimenő dokumentumok létrehozásához konfigurált elektronikus jelentési (ER) formátumú fájlok MAPPA vagy FÁJL összetevőihez.</span><span class="sxs-lookup"><span data-stu-id="6467b-104">You can configure a Microsoft Power BI destination for each folder or file component of an Electronic reporting (ER) format that is configured to generate outbound documents.</span></span> <span data-ttu-id="6467b-105">A célhely beállítása alapján a generált dokumentumokat a rendszer egy korábban konfigurált SharePoint-mappában tárolja.</span><span class="sxs-lookup"><span data-stu-id="6467b-105">Based on the setting of the destination, a generated document is stored in a previously configured SharePoint folder.</span></span>

<span data-ttu-id="6467b-106">Állítsa az **Engedélyezve** elemet **Igen** értékre ahhoz, hogy az elektronikus jelentési (ER) konfiguráció adatokat vigyen át a Dynamics 365 Finance-példányból a Microsoft Power BI-szolgáltatásokba.</span><span class="sxs-lookup"><span data-stu-id="6467b-106">Set **Enabled** to **Yes** to use your ER configuration to arrange the transfer of data from your Dynamics 365 Finance instance to Microsoft Power BI services.</span></span> <span data-ttu-id="6467b-107">Az átvitt fájlok tárolása egy Microsoft SharePoint Server példányon történik, amelyet ennek a célnak megfelelően konfigurálni kell.</span><span class="sxs-lookup"><span data-stu-id="6467b-107">The transferred files are stored on a Microsoft SharePoint Server instance that must be configured for that purpose.</span></span> <span data-ttu-id="6467b-108">További információ: [Elektronikus jelentéskészítés (ER) konfigurálása az adatok Power BI szolgáltatásba való lehívásához](general-electronic-reporting-report-configuration-get-data-powerbi.md).</span><span class="sxs-lookup"><span data-stu-id="6467b-108">For more information, see [Configure Electronic reporting (ER) to pull data into Power BI](general-electronic-reporting-report-configuration-get-data-powerbi.md).</span></span>

<span data-ttu-id="6467b-109">[![Célhely beállításai oldal](./media/ER_Destinations-EnablePowerBIDestination.png)](./media/ER_Destinations-EnablePowerBIDestination.png)</span><span class="sxs-lookup"><span data-stu-id="6467b-109">[![Destination setting page](./media/ER_Destinations-EnablePowerBIDestination.png)](./media/ER_Destinations-EnablePowerBIDestination.png)</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6467b-110">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="6467b-110">Additional resources</span></span>

- [<span data-ttu-id="6467b-111">Elektronikus jelentéskészítés (ER) áttekintése</span><span class="sxs-lookup"><span data-stu-id="6467b-111">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="6467b-112">Elektronikus jelentéskészítés (ER) céljai</span><span class="sxs-lookup"><span data-stu-id="6467b-112">Electronic reporting (ER) destinations</span></span>](electronic-reporting-destinations.md)
