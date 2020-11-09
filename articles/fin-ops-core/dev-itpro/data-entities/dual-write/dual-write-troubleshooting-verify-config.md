---
title: Ellenőrizze, hogy a kettős írás be van-e állítva a(z) Finance and Operations alkalmazásokban és a(z) Common Data Service
description: Ez a témakör azt mutatja be, hogyan lehet meghatározni, hogy a kettős írás konfigurálva van-e a Finance and Operations alkalmazásokban és a Common Data Service szolgáltatásban.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 2ddac76871a3ac574a1edcb5446be6c64e5e4682
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997230"
---
# <a name="verify-that-dual-write-is-configured-in-finance-and-operations-apps-and-common-data-service"></a><span data-ttu-id="51779-103">Ellenőrizze, hogy a kettős írás be van-e állítva a(z) Finance and Operations alkalmazásokban és a(z) Common Data Service</span><span class="sxs-lookup"><span data-stu-id="51779-103">Verify that dual-write is configured in Finance and Operations apps and Common Data Service</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="51779-104">Ez a cikk a Finance and Operations és a Common Data Service alkalmazások közötti kettős írású adatintegrációk során felmerülő hibák elhárításával kapcsolatos információkat tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="51779-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="51779-105">Pontosan elmagyarázza, hogyan lehet meghatározni, hogy a kettős írás konfigurálva van-e a Finance and Operations alkalmazásokban és a Common Data Service szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="51779-105">Specifically, it explains how you can determine whether dual-write is configured in Finance and Operations apps and in Common Data Service.</span></span>

## <a name="verify-that-dual-write-is-configured-in-a-finance-and-operations-app"></a><span data-ttu-id="51779-106">Annak ellenőrzése hogy a kettős írás be van-e állítva a Finance and Operations alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="51779-106">Verify that dual-write is configured in a Finance and Operations app</span></span>

<span data-ttu-id="51779-107">Annak eldöntéséhez, hogy a rekordok frissítésre való mentéskor megjelenő hibák a kettős írásból származnak-e, először ellenőrizze, hogy a kettős írás konfigurálva van-e.</span><span class="sxs-lookup"><span data-stu-id="51779-107">To determine whether the errors that you see when you try to save records for update come from dual-write, first verify that dual-write is configured.</span></span>

+ <span data-ttu-id="51779-108">Ha Finance and Operations alkalmazásban rendszergazdai jogosultságokkal rendelkezik nyissa meg a **Munkaterületek \> Adatkezelés** modulját, és válassza ki a **Kettős írás** csempét.</span><span class="sxs-lookup"><span data-stu-id="51779-108">If you have admin privileges in the Finance and Operations app, go to **Workspaces \> Data management** , and select the **Dual-write** tile.</span></span> <span data-ttu-id="51779-109">Ha megjelenik a csatolt környezetek részletei és a futó entitások listája, akkor a kettős írás konfigurálva van.</span><span class="sxs-lookup"><span data-stu-id="51779-109">If the details of the linked environments and the list of entity maps that are running are shown, dual-write is configured.</span></span>

    ![A Finance and Operations alkalmazás kapcsolatának ellenőrzése adminisztrátori jogosultságok birtokában](media/verify_fin_ops_1.png)

+ <span data-ttu-id="51779-111">Ha nincs rendszergazdai jogosultsága, a következő hibaüzenet jelenik meg: *Nem lehet adatokat írni az \<entity name\>* entitásba.</span><span class="sxs-lookup"><span data-stu-id="51779-111">If you don't have admin privileges, you will receive an error message, *Unable to write data to entity \<entity name\>*.</span></span> <span data-ttu-id="51779-112">A következő ábrán szereplő példában nem lehet vevői rekordot létrehozni az Finance and Operations alkalmazásban, mert a kettős írás konfigurálva van de a vevőcsoport és a fizetési feltételek hivatkozási adatai nem szerepelnek a Common Data Service szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="51779-112">In the example in the following illustration, you can't create a customer record in the Finance and Operations app, because dual-write is configured, but the customer group and payment terms reference data don't exist in Common Data Service.</span></span>

    ![A Finance and Operations alkalmazás kapcsolatának ellenőrzése adminisztrátori jogosultságok nélkül](media/verify_fin_ops_2.png)

<span data-ttu-id="51779-114">Az Finance and Operations alkalmazásokban adatok létrehozásakor jelentkező problémák megoldásával kapcsolatos tudnivalókat lásd az [Élő szinkronizálási problémák elhárítása](dual-write-troubleshooting-live-sync.md) című témakörben.</span><span class="sxs-lookup"><span data-stu-id="51779-114">For information about how to fix issues when you create data in Finance and Operations apps, see [Troubleshoot live synchronization issues](dual-write-troubleshooting-live-sync.md).</span></span>

## <a name="verify-that-dual-write-is-configured-in-common-data-service"></a><span data-ttu-id="51779-115">Ellenőrizze, hogy a kettős írás be van-e állítva a Common Data Service szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="51779-115">Verify that dual-write is configured in Common Data Service</span></span>

<span data-ttu-id="51779-116">Amikor adatokat hoz létre, ha a **Vállalat** mezőt látja a Common Data Service lapjain, akkor a kettős írás konfigurálva van.</span><span class="sxs-lookup"><span data-stu-id="51779-116">When you create data, if you see the **Company** field on pages in Common Data Service, dual-write is configured.</span></span>

![A Common Data Service kapcsolatának ellenőrzése](media/verify_cds.png)

<span data-ttu-id="51779-118">Az Common Data Service szolgáltatásban adatok létrehozásakor jelentkező problémák megoldásával kapcsolatos tudnivalókat lásd az [Élő szinkronizálási problémák elhárítása](dual-write-troubleshooting-live-sync.md) című témakörben.</span><span class="sxs-lookup"><span data-stu-id="51779-118">For information about how to fix issues when you create data in Common Data Service, see [Troubleshoot live synchronization issues](dual-write-troubleshooting-live-sync.md).</span></span>

<span data-ttu-id="51779-119">Azzal kapcsolatosan, hogy hogyan tekinteti meg a hibák részleteit, amikor a Common Data Service szolgáltatásban hoz létre adatokat következő témakörben talál: [A beépülő modul nyomkövetési naplójának engedélyezése és megtekintése a Common Data Service szolgáltatásban a hiba részleteinek megtekintéséhez](dual-write-troubleshooting.md#enable-and-view-the-plug-in-trace-log-in-common-data-service-to-view-error-details).</span><span class="sxs-lookup"><span data-stu-id="51779-119">For information about how to view error details if you encounter any errors while you create data in Common Data Service, see [Enable and view the plug-in trace log in Common Data Service to view error details](dual-write-troubleshooting.md#enable-and-view-the-plug-in-trace-log-in-common-data-service-to-view-error-details).</span></span>
