---
title: Eszközdokumentumok
description: Ez a témakör bemutatja az Eszközkezelés eszközdokumentumait.
author: josaw1
manager: AnnBe
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d1c90788da7ad536fb9978db18160ccf6c158033
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783309"
---
# <a name="asset-documents"></a><span data-ttu-id="f3211-103">Eszközdokumentumok</span><span class="sxs-lookup"><span data-stu-id="f3211-103">Asset documents</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="f3211-104">Ez a témakör bemutatja az Eszközkezelés eszközdokumentumait.</span><span class="sxs-lookup"><span data-stu-id="f3211-104">This topic explains asset documents in Asset Management.</span></span>

<span data-ttu-id="f3211-105">Az Eszközkezelés modulban beállíthat dokumentumokat, amelyek automatikusan kapcsolódnak a feladattípusokhoz, eszközgyártókhoz, eszköztípusokhoz vagy például eszközökhöz.</span><span class="sxs-lookup"><span data-stu-id="f3211-105">In Asset Management, you can set up documents so that they are automatically related to job types, asset manufacturers, asset types, or assets, for example.</span></span> <span data-ttu-id="f3211-106">Ez a funkció akkor hasznos, ha a frissített dokumentumverziókat adnak ki.</span><span class="sxs-lookup"><span data-stu-id="f3211-106">This functionality is useful when updated document versions are released.</span></span> <span data-ttu-id="f3211-107">Ebben az esetben a frissített dokumentumot csak el kell helyezni a Microsoft Dynamics 365 for Finance and Operations-dokumentumokhoz használt megszokott helyen, és csatolni a dokumentumot a létrehozott eszközdokumentum-rekordhoz.</span><span class="sxs-lookup"><span data-stu-id="f3211-107">In that case, you just have to put the updated document in the standard location that you use for your Microsoft Dynamics 365 for Finance and Operations documents, and attach the document to the asset document record that you've created.</span></span> <span data-ttu-id="f3211-108">A frissített dokumentum elérhető az **Összes eszköz**, **Aktív eszközök**, **Saját aktív eszközök**, **Összes munkarendelés** és **Aktív munkarendelési feladatok** menüelemekből.</span><span class="sxs-lookup"><span data-stu-id="f3211-108">The updated document can then be accessed from the **All assets**, **Active assets**, **My active assets**, **All work orders**, and **Active work order jobs** menu items.</span></span> <span data-ttu-id="f3211-109">A dokumentumok eszközdokumentum-rekordokhoz történő csatolásának folyamata a szokásos dokumentumkezelő rendszert használja a Finance and Operations modulban.</span><span class="sxs-lookup"><span data-stu-id="f3211-109">The process for attaching documents to an asset document record uses the standard document handling system in Finance and Operations.</span></span>

<span data-ttu-id="f3211-110">**1. példa** : Egy feladattípushoz kapcsolódó dokumentum leírhatja a feladattípushoz tartozó eljárást.</span><span class="sxs-lookup"><span data-stu-id="f3211-110">**Example 1:** A document that is related to a job type might describe a procedure for that job type.</span></span>

<span data-ttu-id="f3211-111">**2. példa** : Egy dokumentum, amely egy eszköztípus, gyártó és modell kombinációjához tartozik, lehet a kiválasztott eszközgyártói modell szabványos kézikönyve.</span><span class="sxs-lookup"><span data-stu-id="f3211-111">**Example 2:** A document that is related to a combination of an asset type, manufacturer, and model might be the standard manual for the selected asset manufacturer model.</span></span>

## <a name="create-asset-document-relation"></a><span data-ttu-id="f3211-112">Eszköz-dokumentum közti kapcsolat létrehozása</span><span class="sxs-lookup"><span data-stu-id="f3211-112">Create asset document relation</span></span>

1. <span data-ttu-id="f3211-113">Válassza ki az **Eszközkezelés** \> **Beállítás** \> **Eszközdokumentumok** elemet.</span><span class="sxs-lookup"><span data-stu-id="f3211-113">Select **Asset management** \> **Setup** \> **Asset documents**.</span></span>
2. <span data-ttu-id="f3211-114">Válassza az **Új** lehetőséget az eszközdokumentum-rekord létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="f3211-114">Select **New** to create an asset document record.</span></span>
3. <span data-ttu-id="f3211-115">A dokumentumkapcsolat specifikusságának szükséges szintjétől függően végezze el a releváns kiválasztásokat egy vagy több mezőn a következő közül: **Eszköztípus**, **Gyártó**, **Modell**, **Eszköz**, **Feladattípus-kategória**, **Feladattípus**, **Feladattípus változata** és **Feladat követelménye**.</span><span class="sxs-lookup"><span data-stu-id="f3211-115">Depending on how specific you want the document relation to be, make relevant selections in one or more of the following fields: **Asset type**, **Manufacturer**, **Model**, **Asset**, **Job type category**, **Job type**, **Job type variant**, and **Job requirement**.</span></span> <span data-ttu-id="f3211-116">A **Feladattípus-változat** és a **Feladat követelménye** mezőkben elérhető lehetőségek a **Feladattípus** mezőben kiválasztott beállítástól függenek.</span><span class="sxs-lookup"><span data-stu-id="f3211-116">The options that are available in the **Job type variant** and **Job requirement** fields depend on your selection in the **Job type** field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f3211-117">Amikor a rendszer olyan dokumentumokat keres, amelyek egy eszközhöz vagy egy munkarendeléshez kapcsolódnak, az Eszközkezelés minden eszközdokumentum-rekordon végigmegy lehetséges egyezést keresve.</span><span class="sxs-lookup"><span data-stu-id="f3211-117">When the system searches for documents that should be related to an asset or a work order, Asset Management goes through all asset document records to check for a possible match.</span></span> <span data-ttu-id="f3211-118">Mindig a leginkább meghatározott kombinációt ellenőrzi először.</span><span class="sxs-lookup"><span data-stu-id="f3211-118">It always checks the most specific combination first.</span></span> <span data-ttu-id="f3211-119">Más szóval az Eszközkezelés modul először a **Feladat követelménye** mezővel való egyezést ellenőrzi.</span><span class="sxs-lookup"><span data-stu-id="f3211-119">In other words, Asset Management first checks for a match for the **Job requirement** field.</span></span> <span data-ttu-id="f3211-120">Ha nem talál egyezést, akkor a **Feladattípus változata** mezővel való egyezést ellenőrzi.</span><span class="sxs-lookup"><span data-stu-id="f3211-120">If no match is found, it checks for a match for the **Job type variant** field.</span></span> <span data-ttu-id="f3211-121">Ha nem talál egyezést, akkor a **Feladattípus** mezővel való egyezést ellenőrzi, és így tovább.</span><span class="sxs-lookup"><span data-stu-id="f3211-121">If no match is found, it checks for a match for the **Job type** field, and so on.</span></span> <span data-ttu-id="f3211-122">Ahogy az az **Eszközdokumentumok** oldal elrendezésében is látható, ez a viselkedésmód azt jelenti, hogy a legspecifikusabb kombináció megkereséséhez az Eszközkezelés minden egyes rekordot jobbról balra ellenőriz egyezést keresve.</span><span class="sxs-lookup"><span data-stu-id="f3211-122">As you can see in the layout of the **Asset documents** page, this behavior means that, to find the most specific combination, Asset Management checks each record from right to left for a match.</span></span> <span data-ttu-id="f3211-123">Egy eszközhöz vagy egy munkarendeléshez több dokumentum is kapcsolódhat.</span><span class="sxs-lookup"><span data-stu-id="f3211-123">Several documents might be related to an asset or a work order.</span></span> <span data-ttu-id="f3211-124">A karbantartási kérés vagy a munkarendelés szolgáltatási szintjét igény szerint módosíthatja.</span><span class="sxs-lookup"><span data-stu-id="f3211-124">You can edit the service level on a maintenance request or a work order as you require.</span></span>

4. <span data-ttu-id="f3211-125">**Mellékletek** kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="f3211-125">Select **Attachments**.</span></span> <span data-ttu-id="f3211-126">A Finance and Operations modulban megjelenik a megszokott **Dokumentumkezelés** oldal.</span><span class="sxs-lookup"><span data-stu-id="f3211-126">The standard **Document handling** page in Finance and Operations appears.</span></span>
5. <span data-ttu-id="f3211-127">Állítsa be az eszközdokumentum-rekordhoz csatolandó dokumentumokat vagy jegyzeteket.</span><span class="sxs-lookup"><span data-stu-id="f3211-127">Set up the documents or notes that should be attached to the asset document record.</span></span> <span data-ttu-id="f3211-128">Dokumentumok csatolása után a **Mellékletek** mező a rekordhoz kapcsolódó dokumentumok számát jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="f3211-128">After you attach documents, the **Attachments** field shows the number of documents that are related to the record.</span></span>
