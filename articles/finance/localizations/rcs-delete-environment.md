---
title: Regulatory Configuration Service (RCS) – RCS-környezet törlése
description: Ez a témakör bemutatja, hogy a Regulatory Configuration Service (RCS) rendszegazdái hogyan törölhetik az RCS-környezeteket és a kapcsolódó adatokat.
author: JaneA07
ms.date: 06/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization, Global
audience: Application User, System Admin
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2021-01-01
ms.dyn365.ops.version: AX 10.0.15
ms.openlocfilehash: 637962cf63bfd8c2330726f33545f939ec91d58d
ms.sourcegitcommit: dbffde1944b9d037124415c28053036c9ef1ecb7
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2021
ms.locfileid: "6295818"
---
# <a name="regulatory-configuration-service-rcs---delete-an-rcs-environment"></a><span data-ttu-id="5cf96-103">Regulatory Configuration Service (RCS) – RCS-környezet törlése</span><span class="sxs-lookup"><span data-stu-id="5cf96-103">Regulatory Configuration Service (RCS) - Delete an RCS environment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5cf96-104">Ez a témakör bemutatja, hogy a Regulatory Configuration Service (RCS) rendszegazdái hogyan törölhetik az RCS-környezeteket és a kapcsolódó adatokat.</span><span class="sxs-lookup"><span data-stu-id="5cf96-104">This topic explains how a Regulatory Configuration Service (RCS) system administrator can delete an RCS environment and related data.</span></span>

<span data-ttu-id="5cf96-105">A témakörben ismertetett eljárás használatához a következő előfeltételeknek kell megfelelni:</span><span class="sxs-lookup"><span data-stu-id="5cf96-105">Before you can complete the procedure in this topic, the following prerequisites must be met:</span></span>

- <span data-ttu-id="5cf96-106">Az RCS-környezethez **adminisztrátori** szerepkörrel kell rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="5cf96-106">You must have the **System Admin** role assigned to you for the RCS environment.</span></span>
- <span data-ttu-id="5cf96-107">Az **adminisztrátor** szerepkörhöz **RCSDeleteEnvironmentDuty** szerepkört kell hozzárendelni.</span><span class="sxs-lookup"><span data-stu-id="5cf96-107">The **System Admin** role must have the **RCSDeleteEnvironmentDuty** role assigned to it.</span></span>

## <a name="delete-an-rcs-environment"></a><span data-ttu-id="5cf96-108">RCS-környezet frissítése</span><span class="sxs-lookup"><span data-stu-id="5cf96-108">Delete an RCS environment</span></span>

1. <span data-ttu-id="5cf96-109">Nyissa meg az RCS-t, és válassza ki az **Elektronikus jelentéskészítés** munkaterület csempéjét.</span><span class="sxs-lookup"><span data-stu-id="5cf96-109">Open RCS, and select the **Electronic reporting** workspace tile.</span></span>
2. <span data-ttu-id="5cf96-110">A **Kapcsolódó hivatkozások** szakaszban válassza az **RCS-környezet törlése** elemet.</span><span class="sxs-lookup"><span data-stu-id="5cf96-110">In the **Related links** section, select **Delete RCS environment**.</span></span>

    ![Az RCS-környezet törlése hivatkozás a Kapcsolódó hivatkozások szakaszban](media/01_RCS-Delete-Environ-Related-Link.PNG)

3. <span data-ttu-id="5cf96-112">A megjelenő párbeszédpanelen ellenőrizze a környezet törlésének hatókörével kapcsolatos üzeneteket.</span><span class="sxs-lookup"><span data-stu-id="5cf96-112">In the dialog box that appears, review the messages about the scope of environment deletion.</span></span>

    ![Az RCS-környezet törlése párbeszédpanelen megjelenő üzenetek](media/01_RCS-Delete-Environ-Msg_noGUID.PNG)

    > [!IMPORTANT]
    > <span data-ttu-id="5cf96-114">Az RCS-környezetek törlése nem vonható vissza.</span><span class="sxs-lookup"><span data-stu-id="5cf96-114">Deletion of an RCS environment can't be reversed.</span></span>
    >
    > <span data-ttu-id="5cf96-115">A művelet törli a kiválasztott RCS-környezetet és a hozzá kapcsolódó adatokat, például a globális adattárban tárolt funkciókat és konfigurációkat.</span><span class="sxs-lookup"><span data-stu-id="5cf96-115">The operation deletes the selected RCS environment and any related data, including features and configurations that are stored in the Global repository.</span></span> <span data-ttu-id="5cf96-116">A más szervezetekkel megosztott funkciók és konfigurációk megosztása megszűnik, és az elemek törlődnek, ha nincs függőségük.</span><span class="sxs-lookup"><span data-stu-id="5cf96-116">Features and configurations that are shared with other organizations will be unshared and deleted if they have no dependencies.</span></span> <span data-ttu-id="5cf96-117">A függőséggel rendelkező funkciókat és konfigurációkat megszüntetettként jelöli meg a rendszer.</span><span class="sxs-lookup"><span data-stu-id="5cf96-117">Features and configurations that have dependencies will be marked as discontinued.</span></span>

4. <span data-ttu-id="5cf96-118">A megadott mezőben adja meg az RCS-környezet globálisan egyedi azonosítóját (GUID), és erősítse meg, hogy törölni szeretné a környezetet.</span><span class="sxs-lookup"><span data-stu-id="5cf96-118">In the field that is provided, enter the globally unique identifier (GUID) of the RCS environment to confirm that you want to delete it.</span></span> <span data-ttu-id="5cf96-119">A környezet GUID azonosítója a törlési üzenetben található.</span><span class="sxs-lookup"><span data-stu-id="5cf96-119">The environment's GUID is included in the deletion message.</span></span>
5. <span data-ttu-id="5cf96-120">Válassza a **Környezet törlése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5cf96-120">Select **Delete environment**.</span></span>
    
<span data-ttu-id="5cf96-121">Ezzel törli az RCS-környezetet és a hozzá kapcsolódó adatokat.</span><span class="sxs-lookup"><span data-stu-id="5cf96-121">Your RCS environment and any related data are now deleted.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5cf96-122">Az RCS-környezet törlése után nem lehet visszaállítani az adatokat.</span><span class="sxs-lookup"><span data-stu-id="5cf96-122">After you delete an RCS environment, there is no way to recover the data.</span></span> <span data-ttu-id="5cf96-123">Új RCS-környezet bármelyik elérhető RCS-régióban létrehozható.</span><span class="sxs-lookup"><span data-stu-id="5cf96-123">A new RCS environment can be created in any available RCS region.</span></span>