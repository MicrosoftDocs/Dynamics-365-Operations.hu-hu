---
title: Fizetési számlák létrehozása
description: Ez a témakör bemutatja, hogyan lehet havi lízingszámlákat létrehozni. Létrehozhat számlákat az egyes lízingekhez, vagy kötegelt folyamattal több lízinghez is létrehozhatja őket.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 303fb0e70530fdc29cb129736b01c0e0e8d02075
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969578"
---
# <a name="create-payment-invoices"></a><span data-ttu-id="0b559-104">Fizetési számlák létrehozása</span><span class="sxs-lookup"><span data-stu-id="0b559-104">Create payment invoices</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0b559-105">Létrehozhat havi számlákat az egyes lízingekhez, vagy kötegelt folyamattal több lízinghez is létrehozhatja őket.</span><span class="sxs-lookup"><span data-stu-id="0b559-105">You can create monthly invoices for individual leases, or you can use a batch process to create them for multiple leases.</span></span> <span data-ttu-id="0b559-106">Az alábbi eljárás bemutatja, hogyan hozhat létre egyéni lízingfizetési bejegyzést, ha a **Lízingkönyv beállítás** lapján a **Fizetés szállítónak** paraméter be van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="0b559-106">The following procedure shows how to create an individual lease payment entry when the **Pay to Vendor** parameter on the **Lease book setup** page is turned on.</span></span>

1. <span data-ttu-id="0b559-107">A **Lízing összegzése** lapon válasszon ki egy lízinget, majd válassza a **Könyvek \> Fizetés ütemezése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0b559-107">On the **Lease summary** page, select a lease, and then select **Books \> Payment schedule**.</span></span>
2. <span data-ttu-id="0b559-108">Válassza ki az elvégzendő kifizetést, majd a **Napló létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0b559-108">Select the payment that must be made, and then select **Create journal**.</span></span> <span data-ttu-id="0b559-109">Megjelenik egy üzenet, amely arról szól, hogy a kijelölt kifizetéssel szemben naplót hoztak létre.</span><span class="sxs-lookup"><span data-stu-id="0b559-109">You receive a message that states that a journal was created against the selected payment.</span></span>
3. <span data-ttu-id="0b559-110">Válassza a **Számlanaplók** lehetőséget, majd a kifizetendő számlát.</span><span class="sxs-lookup"><span data-stu-id="0b559-110">Select **Invoice journals**, and then select the invoice that must be paid.</span></span>
4. <span data-ttu-id="0b559-111">A **Sorok** fülön tekintse át a naplóbejegyzést, mielőtt a főkönyvbe feladná.</span><span class="sxs-lookup"><span data-stu-id="0b559-111">On the **Lines** tab, review the journal entry before you post it to the general ledger.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0b559-112">Alapértelmezés szerint a létrehozott szállítói számlasorok a szállító feladási profilt használják a **Kötelezettségek paraméterei** lapból.</span><span class="sxs-lookup"><span data-stu-id="0b559-112">By default, the vendor invoice lines that are created use the vendor posting profile from the **Accounts payable parameters** page.</span></span>

5. <span data-ttu-id="0b559-113">Válassza a napló helyesbítése lehetőséget, majd a kifizetendő számlát.</span><span class="sxs-lookup"><span data-stu-id="0b559-113">Select the correct journal, and then select the invoice that must be paid.</span></span>

    <span data-ttu-id="0b559-114">Ebben a példában a lízingkönyv **Fizetés a szállítónak** paramétere be van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="0b559-114">For this example, the **Pay to Vendor** parameter on the lease book is turned on.</span></span> <span data-ttu-id="0b559-115">Ezért a számla a számlanaplóban lesz.</span><span class="sxs-lookup"><span data-stu-id="0b559-115">Therefore, the invoice will be in the invoice journal.</span></span> <span data-ttu-id="0b559-116">Az **Áttekintés** szakasz a naplóbejegyzés összegzését, a **Sorok** szakasz pedig a tényleges naplósorok részleteit jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="0b559-116">The **Overview** section shows a summary of the journal entry, and the **Lines** section shows details of the actual journal lines.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0b559-117">Ha a **Fizetés a szállítónak** paraméter ki van kapcsolva, a kifizetési napló bejegyzései megjelennek a lízingkönyv **Eszközlízing** oldalán, és a rendszer számla helyett eszközlízing-bejegyzést hoz létre.</span><span class="sxs-lookup"><span data-stu-id="0b559-117">If the **Pay to Vendor** parameter is turned off, payment journal entries will be listed on the **Asset leasing** page for the lease book, and the system will create an asset leasing entry instead of an invoice.</span></span> <span data-ttu-id="0b559-118">A lízingdíjfizetés bejegyzés a **Havi lízingnapló** mezőben megadott naplónévre lesz feladva.</span><span class="sxs-lookup"><span data-stu-id="0b559-118">The lease payment entry will be posted to the journal name that is specified in the **Monthly lease journal** field.</span></span>

6. <span data-ttu-id="0b559-119">A tranzakció feladása után megtekintheti a tranzakció adatainak és a lízingkötelezettség könyv szerinti értékét a **Kötelezettségtranzakciók** lehetőség kiválasztásával a lízingkönyvben.</span><span class="sxs-lookup"><span data-stu-id="0b559-119">After the transaction is posted, you can view the transaction information and the carrying value of the lease liability by selecting **Liability transactions** in the lease book.</span></span>

    <span data-ttu-id="0b559-120">A fizetési ütemezésben be van jelölve a **Feladott napló** jelölőnégyzet, és a sorban megjelenik a számlanapló száma.</span><span class="sxs-lookup"><span data-stu-id="0b559-120">In the payment schedule, the **Journal posted** check box will be selected, and the line will show the invoice journal number.</span></span> <span data-ttu-id="0b559-121">A kifizetési napló és a naplóhoz való bejegyzés létrehozása után a tétel újbóli létrehozása előtt sztornírozásra van szüksége.</span><span class="sxs-lookup"><span data-stu-id="0b559-121">After a payment journal and an entry for that journal have been created, you must reverse the entry before it can be re-created.</span></span>
