---
title: Kölcsönzött eszközök
description: Ez a témakör bemutatja, hogyan eszközök kölcsönadását regisztrálni az Eszközkezelés modulban.
author: josaw1
manager: tfehr
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetObjectLoanSend, EntAssetObjectLoanListPage, EntAssetObjectLoanReturn, EntAssetObjectLoanInfoPart
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: cba680d0ad626e0275539d7478a83639a9d22635
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/25/2020
ms.locfileid: "3889649"
---
# <a name="asset-loans"></a><span data-ttu-id="2995a-103">Kölcsönzött eszközök</span><span class="sxs-lookup"><span data-stu-id="2995a-103">Asset loans</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="2995a-104">Ha a vállalat a javítási vagy karbantartási feladatokhoz a belső helyekről vagy a vevőkről kap eszközöket, és ha ideiglenesen kölcsönbe ad eszközöket, ezekre a helyekre vagy ügyfeleknek, az Eszközkezelésben nyomon követheti ezeket az eszközkölcsönzéseket.</span><span class="sxs-lookup"><span data-stu-id="2995a-104">If your company receives assets for repair or maintenance jobs from either internal locations or customers, and if you temporarily loan assets to those locations or customers, Asset Management can track the asset loans.</span></span>

## <a name="register-asset-loans-on-a-maintenance-request"></a><span data-ttu-id="2995a-105">Kölcsönzött eszközök rögzítése karbantartási kéréshez</span><span class="sxs-lookup"><span data-stu-id="2995a-105">Register asset loans on a maintenance request</span></span>

1. <span data-ttu-id="2995a-106">Válassza az **Eszközkezelés** \> **Közös** \> **Karbantartási kérések** \> **Összes karbantartási kérés** vagy **Aktív karbantartási kérések** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2995a-106">Select **Asset management** \> **Common** \> **Maintenance requests** \> **All maintenance requests** or **Active maintenance requests**.</span></span>
2. <span data-ttu-id="2995a-107">Válassza ki azt a karbantartási kérést, amelyre azeszköz kölcsönzését regisztrálni szeretné, majd válassza a **Szerkesztés**parancsot.</span><span class="sxs-lookup"><span data-stu-id="2995a-107">Select the maintenance request to register an asset loan on, and then select **Edit**.</span></span>
3. <span data-ttu-id="2995a-108">A **Kérelem** oldalon válassza a **Kölcsönzött eszköz küldése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2995a-108">On the **Request** page, select **Send loan asset**.</span></span>
4. <span data-ttu-id="2995a-109">Válassza ki az eszközt, és adja meg a várható visszaadási dátumot.</span><span class="sxs-lookup"><span data-stu-id="2995a-109">Select the asset, and enter the expected return date.</span></span>
5. <span data-ttu-id="2995a-110">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2995a-110">Select **OK**.</span></span>

> [!NOTE]
> - <span data-ttu-id="2995a-111">Csak akkor küldhet kölcsönzött eszközt, ha az eszközhöz hasonló eszköz rendelkezésre áll.</span><span class="sxs-lookup"><span data-stu-id="2995a-111">You can send a loan asset only if an asset of the same asset type is available.</span></span>
> - <span data-ttu-id="2995a-112">A kölcsön tárgyát képező eszköznek olyan eszközéletciklus-állapotúnak kell lennie, amely lehetővé teszi, hogy az kölcsön eszközként legyen használva, például **InStorage**.</span><span class="sxs-lookup"><span data-stu-id="2995a-112">The asset that you loan must have an asset lifecycle state that allows it to be used as a loan asset, such as **InStorage**.</span></span> <span data-ttu-id="2995a-113">Amikor a kölcsönzött eszköz regisztrálása megtörtént, a program automatikusan frissíti az eszköz életciklus-állapotát, például **OnLoan** értékre.</span><span class="sxs-lookup"><span data-stu-id="2995a-113">When the asset loan is registered, the asset lifecycle state of the asset is automatically updated to, for example, **OnLoan**.</span></span>

<span data-ttu-id="2995a-114">Ha meg szeretné tekinteni az összes olyan eszköz listáját, amelyet más helyekre vagy vevőknek kölcsönzött akkor válassza az **Eszközkezelés** \> **Közös** \> **Kölcsönzött eszköz** \> **Összes kölcsönzött eszköz** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2995a-114">To view a list of all the assets that you've loaned to other locations or customers, select **Asset management** \> **Common** \> **Asset loan** \> **All asset loans**.</span></span> <span data-ttu-id="2995a-115">Ha egy eszköz esetében be van jelölve a **Befejezve** jelölőnégyzet, akkor a program a vállalatnak visszaküldöttként regisztrálja az eszközt.</span><span class="sxs-lookup"><span data-stu-id="2995a-115">If the **Ended** check box is selected for an asset, the asset has been registered as returned to your company.</span></span>

![Karbantartási kérések kezelése](media/06-manage-maintenance-requests.png)

<span data-ttu-id="2995a-117">Az **Aktív eszköz kölcsönzése** lapon megtekintheti az összes olyan eszköz listáját, amely még nincs visszaküldve a vállalatnak.</span><span class="sxs-lookup"><span data-stu-id="2995a-117">On the **Active asset loans** page, you can view a list of all the loan assets that haven't yet been returned to your company.</span></span>

## <a name="register-loan-assets-as-returned"></a><span data-ttu-id="2995a-118">A kölcsönzött eszköz rögzítése visszaküldöttként</span><span class="sxs-lookup"><span data-stu-id="2995a-118">Register loan assets as returned</span></span>

1. <span data-ttu-id="2995a-119">Válassza az **Eszközkezelés** \> **Általános** \> **Kölcsönzött eszköz** \> **Aktív kölcsönzött eszközök** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2995a-119">Select **Asset management** \> **Common** \> **Asset loan** \> **Active asset loans**.</span></span>
2. <span data-ttu-id="2995a-120">Válassza ki a visszaküldöttként regisztrálni kívánt tárgyi eszközt, majd válassza a **Kölcsönzött eszköz visszaküldése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2995a-120">Select the asset loan to register as returned, and then select **Return asset loan**.</span></span>
3. <span data-ttu-id="2995a-121">A **Visszaadva** mezőben adja meg dátumot és az időt.</span><span class="sxs-lookup"><span data-stu-id="2995a-121">In the **Returned** field, enter the date and time.</span></span>
4. <span data-ttu-id="2995a-122">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2995a-122">Select **OK**.</span></span>
5. <span data-ttu-id="2995a-123">Frissítse az **Aktív eszköz kölcsönzése** listaoldalt és figyelje meg, hogy az eszköz kölcsönzése már nem jelenik meg a listában.</span><span class="sxs-lookup"><span data-stu-id="2995a-123">Refresh the **Active asset loans** list page, and notice that the asset loan no longer appears in the list.</span></span>
