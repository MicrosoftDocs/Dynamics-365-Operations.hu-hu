---
title: Üres állapotú csekkek létrehozása
description: Ez a témakör azt mutatja be, hogyan hozhatók létre üres csekkek egy bankszámlához a Csekkek oldalon.
author: abruer
manager: AnnBe
ms.date: 10/26/2017
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankChequeTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 21941
ms.assetid: d7e22bd8-fd0d-47e1-843f-45ab0193ff8d
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2019-09-17
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 47d54524f87cf718b9b41462b5133df267d5dd9e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4459186"
---
# <a name="create-checks-that-have-blank-status"></a><span data-ttu-id="57023-103">Üres állapotú csekkek létrehozása</span><span class="sxs-lookup"><span data-stu-id="57023-103">Create checks that have Blank status</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="57023-104">Ez a témakör azt mutatja be, hogyan hozhatók létre üres csekkek.</span><span class="sxs-lookup"><span data-stu-id="57023-104">This topic explains how to create blank checks.</span></span> <span data-ttu-id="57023-105">Üres csekket például egy megsérült, fizetéshez nem használható csekk rögzítéséhez hozhat létre.</span><span class="sxs-lookup"><span data-stu-id="57023-105">For example, you might create a blank check to record a check that has been damaged and can't be used for payment.</span></span>

<span data-ttu-id="57023-106">A **Csekkek** oldalon hajthatók végre a csekkekhez tartozó karbantartási feladatok.</span><span class="sxs-lookup"><span data-stu-id="57023-106">On the **Checks** page, you perform maintenance tasks for checks.</span></span> <span data-ttu-id="57023-107">Ezen az oldalon létrehozhat például új csekkszámokat, és törölhet csekkeket.</span><span class="sxs-lookup"><span data-stu-id="57023-107">For example, you can create new check numbers and delete checks.</span></span> <span data-ttu-id="57023-108">**Üres** állapotú csekkeket ugyancsak hozhat létre.</span><span class="sxs-lookup"><span data-stu-id="57023-108">You can also create checks that have a status of **Blank**.</span></span> <span data-ttu-id="57023-109">A létrehozott üres csekkek nem törölhetők és nem használhatók fel újra a rendszerben.</span><span class="sxs-lookup"><span data-stu-id="57023-109">After blank checks are created, they can't be deleted or reused in the system.</span></span>

> [!NOTE]
> <span data-ttu-id="57023-110">Ez a funkció csak akkor érhető el a **Csekkek** oldalon, ha a **Funkció kezelése** oldalon bekapcsolja az **Üres állapotú csekkek létrehozása a Csekkek oldalon** szolgáltatást.</span><span class="sxs-lookup"><span data-stu-id="57023-110">This feature is available on the **Checks** page only if you turn on the **Create checks with a blank status on the Checks page** feature on the **Feature management** page.</span></span> <span data-ttu-id="57023-111">Ha nem kapcsolja be a funkciót, akkor **Üres** állapotú csekkek csak a **Fizetés csekkel** párbeszédpanelen, a Kötelezettségek modul kifizetés létrehozására szolgáló folyamata során hozhatók létre.</span><span class="sxs-lookup"><span data-stu-id="57023-111">If the feature isn't turned on, checks that have **Blank** status can be created only from the **Payment by check** dialog box during the payment generation process in Accounts payable.</span></span>

<span data-ttu-id="57023-112">A **Csekkek** oldal megnyitásához lépjen a **Készpénz- és bankkezelés \> Bankszámlák \> Bankszámlák** részre, és a műveleti ablaktábla **Kifizetések kezelése** lapjának **Kapcsolódó információ** csoportjában válassza a **Csekkek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="57023-112">To open the **Checks** page, go to **Cash and bank management \> Bank accounts \> Bank accounts**, and then, on the Action Pane, on the **Manage payments** tab, in the **Related information** group, select **Checks**.</span></span> <span data-ttu-id="57023-113">Egy másik megoldás, hogy a **Készpénz- és bankkezelés \> Lekérdezések és jelentések \> Csekkek** részre lép.</span><span class="sxs-lookup"><span data-stu-id="57023-113">Alternatively, go to **Cash and bank management \> Inquiries and reports \> Checks**.</span></span>

<span data-ttu-id="57023-114">Ezután az **Üres** állapotú csekkek létrehozásához válassza az **Üres csekkek létrehozása** lehetőséget a műveleti ablaktáblán.</span><span class="sxs-lookup"><span data-stu-id="57023-114">Then, to create checks that have **Blank** status, on the Action Pane, select **Create blank checks**.</span></span> <span data-ttu-id="57023-115">Amikor a rendszer üres csekkeket hoz létre, ideiglenesen inaktiválja a társított bankszámlát.</span><span class="sxs-lookup"><span data-stu-id="57023-115">While the system is creating blank checks, the associated bank account is temporarily inactivated.</span></span> <span data-ttu-id="57023-116">Így kisebb annak a kockázata, hogy az üres csekkek létrehozása közben kifizetések jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="57023-116">This behavior reduces the risk that payments will be generated at the same time that blank checks are created.</span></span> <span data-ttu-id="57023-117">A művelet befejezése után a társított bankszámla újra aktiválódik.</span><span class="sxs-lookup"><span data-stu-id="57023-117">When the processing is completed, the associated bank account is reactivated.</span></span>
