---
title: Ellenőrizze, hogy a kettős írás be van-e állítva a(z) Finance and Operations alkalmazásokban és a(z) Dataverse
description: Ez a témakör azt mutatja be, hogyan lehet meghatározni, hogy a kettős írás konfigurálva van-e a Finance and Operations alkalmazásokban és a Dataverse szolgáltatásban.
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
ms.openlocfilehash: f389bcf133cc7e6a086167d5e26c1b8795d0fa30
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685539"
---
# <a name="verify-that-dual-write-is-configured-in-finance-and-operations-apps-and-dataverse"></a><span data-ttu-id="2450c-103">Ellenőrizze, hogy a kettős írás be van-e állítva a(z) Finance and Operations alkalmazásokban és a(z) Dataverse</span><span class="sxs-lookup"><span data-stu-id="2450c-103">Verify that dual-write is configured in Finance and Operations apps and Dataverse</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



<span data-ttu-id="2450c-104">Ez a cikk a Finance and Operations és a Dataverse alkalmazások közötti kettős írású adatintegrációk során felmerülő hibák elhárításával kapcsolatos információkat tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="2450c-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Dataverse.</span></span> <span data-ttu-id="2450c-105">Pontosan elmagyarázza, hogyan lehet meghatározni, hogy a kettős írás konfigurálva van-e a Finance and Operations alkalmazásokban és a Dataverse szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="2450c-105">Specifically, it explains how you can determine whether dual-write is configured in Finance and Operations apps and in Dataverse.</span></span>

## <a name="verify-that-dual-write-is-configured-in-a-finance-and-operations-app"></a><span data-ttu-id="2450c-106">Annak ellenőrzése hogy a kettős írás be van-e állítva a Finance and Operations alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="2450c-106">Verify that dual-write is configured in a Finance and Operations app</span></span>

<span data-ttu-id="2450c-107">Annak eldöntéséhez, hogy a sorok frissítésre való mentéskor megjelenő hibák a kettős írásból származnak-e, először ellenőrizze, hogy a kettős írás konfigurálva van-e.</span><span class="sxs-lookup"><span data-stu-id="2450c-107">To determine whether the errors that you see when you try to save rows for update come from dual-write, first verify that dual-write is configured.</span></span>

+ <span data-ttu-id="2450c-108">Ha Finance and Operations alkalmazásban rendszergazdai jogosultságokkal rendelkezik nyissa meg a **Munkaterületek \> Adatkezelés** modulját, és válassza ki a **Kettős írás** csempét.</span><span class="sxs-lookup"><span data-stu-id="2450c-108">If you have admin privileges in the Finance and Operations app, go to **Workspaces \> Data management**, and select the **Dual-write** tile.</span></span> <span data-ttu-id="2450c-109">Ha megjelenik a csatolt környezetek részletei és a futó táblaleképezések listája, akkor a kettős írás konfigurálva van.</span><span class="sxs-lookup"><span data-stu-id="2450c-109">If the details of the linked environments and the list of table maps that are running are shown, dual-write is configured.</span></span>

    ![A Finance and Operations alkalmazás kapcsolatának ellenőrzése adminisztrátori jogosultságok birtokában](media/verify_fin_ops_1.png)

+ <span data-ttu-id="2450c-111">Ha nincs rendszergazdai jogosultsága, a következő hibaüzenet jelenik meg: *Nem lehet adatokat írni az \<entity name\>* entitásba.</span><span class="sxs-lookup"><span data-stu-id="2450c-111">If you don't have admin privileges, you will receive an error message, *Unable to write data to entity \<entity name\>*.</span></span> <span data-ttu-id="2450c-112">A következő ábrán szereplő példában nem lehet vevői sort létrehozni az Finance and Operations alkalmazásban, mert a kettős írás konfigurálva van de a vevőcsoport és a fizetési feltételek hivatkozási adatai nem szerepelnek a Dataverse szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="2450c-112">In the example in the following illustration, you can't create a customer row in the Finance and Operations app, because dual-write is configured, but the customer group and payment terms reference data don't exist in Dataverse.</span></span>

    ![A Finance and Operations alkalmazás kapcsolatának ellenőrzése adminisztrátori jogosultságok nélkül](media/verify_fin_ops_2.png)

<span data-ttu-id="2450c-114">Az Finance and Operations alkalmazásokban adatok létrehozásakor jelentkező problémák megoldásával kapcsolatos tudnivalókat lásd az [Élő szinkronizálási problémák elhárítása](dual-write-troubleshooting-live-sync.md) című témakörben.</span><span class="sxs-lookup"><span data-stu-id="2450c-114">For information about how to fix issues when you create data in Finance and Operations apps, see [Troubleshoot live synchronization issues](dual-write-troubleshooting-live-sync.md).</span></span>

## <a name="verify-that-dual-write-is-configured-in-dataverse"></a><span data-ttu-id="2450c-115">Ellenőrizze, hogy a kettős írás be van-e állítva a Dataverse szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="2450c-115">Verify that dual-write is configured in Dataverse</span></span>

<span data-ttu-id="2450c-116">Amikor adatokat hoz létre, ha a **Vállalat** mezőt látja a Dataverse lapjain, akkor a kettős írás konfigurálva van.</span><span class="sxs-lookup"><span data-stu-id="2450c-116">When you create data, if you see the **Company** field on pages in Dataverse, dual-write is configured.</span></span>

![A Dataverse kapcsolatának ellenőrzése](media/verify_cds.png)

<span data-ttu-id="2450c-118">Az Dataverse szolgáltatásban adatok létrehozásakor jelentkező problémák megoldásával kapcsolatos tudnivalókat lásd az [Élő szinkronizálási problémák elhárítása](dual-write-troubleshooting-live-sync.md) című témakörben.</span><span class="sxs-lookup"><span data-stu-id="2450c-118">For information about how to fix issues when you create data in Dataverse, see [Troubleshoot live synchronization issues](dual-write-troubleshooting-live-sync.md).</span></span>

<span data-ttu-id="2450c-119">Azzal kapcsolatosan, hogy hogyan tekinteti meg a hibák részleteit, amikor a Dataverse szolgáltatásban hoz létre adatokat következő témakörben talál: [A beépülő modul nyomkövetési naplójának engedélyezése és megtekintése a Dataverse szolgáltatásban a hiba részleteinek megtekintéséhez](dual-write-troubleshooting.md#enable-view-trace).</span><span class="sxs-lookup"><span data-stu-id="2450c-119">For information about how to view error details if you encounter any errors while you create data in Dataverse, see [Enable and view the plug-in trace log in Dataverse to view error details](dual-write-troubleshooting.md#enable-view-trace).</span></span>
