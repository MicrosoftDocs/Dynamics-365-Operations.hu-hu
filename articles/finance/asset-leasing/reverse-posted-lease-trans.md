---
title: Fordítva feladott lízingtranzakciók
description: Ez a témakör a feladott lízingtranzakciók sztornírozását ismerteti. Az eszközlízing útján létrehozott tranzakciók sztornírozhatók.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseLeaseTransactions
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 55eb7c5f2419bf1cb2ac0a33a82ab931a3ef380f
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881542"
---
# <a name="reverse-posted-lease-transactions"></a><span data-ttu-id="c8043-104">Fordítva feladott lízingtranzakciók</span><span class="sxs-lookup"><span data-stu-id="c8043-104">Reverse posted lease transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c8043-105">Az eszközlízing útján létrehozott tranzakciók sztornírozhatók.</span><span class="sxs-lookup"><span data-stu-id="c8043-105">Any transaction that is created through Asset leasing can be reversed.</span></span> <span data-ttu-id="c8043-106">Az eszközlízing-szolgáltatás által sztornírozott tranzakciók frissítik a lízingadatokat.</span><span class="sxs-lookup"><span data-stu-id="c8043-106">Transactions that are reversed through Asset leasing update your lease data.</span></span> <span data-ttu-id="c8043-107">Ezért frissítik továbbá a lízingkötelezettség és a használatijog-eszköz (ROU) könyv szerinti értékét is.</span><span class="sxs-lookup"><span data-stu-id="c8043-107">Therefore, they also update the carrying values of the lease liability and right-of-use (ROU) asset.</span></span>

<span data-ttu-id="c8043-108">Sztornírozási tranzakció létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="c8043-108">To create a reversing transaction for a lease, follow these steps.</span></span>

1. <span data-ttu-id="c8043-109">Az **Eszköztranzakciók** vagy a **Kötelezettségtranzakciók** lapon válassza ki a tranzakciót, majd válassza a **Tranzakció sztornírozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c8043-109">On either the **Asset transactions** page or the **Liability transactions** page, select the transaction, and then select **Reverse transaction**.</span></span>
2. <span data-ttu-id="c8043-110">A megjelenő párbeszédpanelen módosíthatja a sztornírozó bejegyzés feladásának dátumát.</span><span class="sxs-lookup"><span data-stu-id="c8043-110">In the dialog box that appears, you can edit the date when the reversing entry will be posted.</span></span> <span data-ttu-id="c8043-111">Alapértelmezés szerint a **Dátum mező** a kiválasztott tranzakció tranzakciófeladási dátumára van beállítva.</span><span class="sxs-lookup"><span data-stu-id="c8043-111">By default, the **Date** field is set to the transaction posting date of the transaction that you selected.</span></span> <span data-ttu-id="c8043-112">A sztornírozó tétel nem adható fel a kijelölt tranzakció eredeti könyvelési dátumánál korábban.</span><span class="sxs-lookup"><span data-stu-id="c8043-112">The reversing entry can't be posted earlier than the original posting date of the selected transaction.</span></span>
3. <span data-ttu-id="c8043-113">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c8043-113">Select **OK**.</span></span> <span data-ttu-id="c8043-114">A program olyan naplóbejegyzést ad fel, amely sztornírozza a kijelölt tételt.</span><span class="sxs-lookup"><span data-stu-id="c8043-114">A journal entry is posted that reverses the entry that you selected.</span></span> <span data-ttu-id="c8043-115">A sztornírozás az **Eszköztranzakciók** vagy a **Kötelezettségtranzakciók** oldalon jelenik meg, és frissül az oldalon megjelenő aktuális egyenleg nettó összege.</span><span class="sxs-lookup"><span data-stu-id="c8043-115">The reversal is shown on the **Asset transactions** or **Liability transactions** page, and the net total of the current balance that is shown on the page is updated.</span></span>

<span data-ttu-id="c8043-116">Ha a **Sztornírozott nyomkövetés** lehetőséget választja, megjelenik egy párbeszédpanel, amely az eredeti és a sztornírozott tranzakciókat is megjeleníti, valamint egy kapcsolódó számot, amelyet *nyomkövetési számnak* nevezünk.</span><span class="sxs-lookup"><span data-stu-id="c8043-116">When you select **Reverse tracing**, a dialog box appears that shows both the original transactions and the reversed transactions, together with a linked number that is known as a *trace number*.</span></span> <span data-ttu-id="c8043-117">A sztornírozás megkönnyítése és a láthatóság javítása érdekében a lízingütemezések használatával is nyomon követheti a sztornírozásokat.</span><span class="sxs-lookup"><span data-stu-id="c8043-117">To make the reversals easier to understand and to improve visibility, you can also track reversals by using the lease schedules.</span></span>

<span data-ttu-id="c8043-118">Az **Ütemezés** lap **Legutóbbi naplószáma** mezője a tranzakciók naplószámait mutatja.</span><span class="sxs-lookup"><span data-stu-id="c8043-118">The **Latest journal number** field on the **Schedule** page shows the journal numbers of transactions.</span></span> <span data-ttu-id="c8043-119">A tranzakció sztornírozása esetén ez a mező a sztornírozási tranzakció naplószámával frissül.</span><span class="sxs-lookup"><span data-stu-id="c8043-119">When a transaction is reversed, this field is updated with the journal number of a reversing transaction.</span></span> <span data-ttu-id="c8043-120">Ezenkívül a **Sztornírozott** jelölőnégyzet be van jelölve, jelezve, hogy a tranzakció sztornírozott, és a **Feladott** mező be van jelölve.</span><span class="sxs-lookup"><span data-stu-id="c8043-120">Additionally, the **Reversed** check box is selected to indicate that the transaction is reversed, and the **Posted** field is selected.</span></span>

## <a name="revoke-a-reversed-transaction"></a><span data-ttu-id="c8043-121">Sztornírozott tranzakció visszavonása</span><span class="sxs-lookup"><span data-stu-id="c8043-121">Revoke a reversed transaction</span></span>

<span data-ttu-id="c8043-122">Sztornírozott tranzakció visszavonásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="c8043-122">To revoke a reversed transaction, follow these steps.</span></span>

1. <span data-ttu-id="c8043-123">Az **Ütemezés** vagy a **Tranzakciók** lapon jelölje ki az eredeti tranzakciót.</span><span class="sxs-lookup"><span data-stu-id="c8043-123">On either the **Schedule** page or the **Transactions** page, select the original transaction.</span></span>
2. <span data-ttu-id="c8043-124">Tegye a következők egyikét:</span><span class="sxs-lookup"><span data-stu-id="c8043-124">Follow one of these steps:</span></span>

    - <span data-ttu-id="c8043-125">Ha a tranzakciót az **Ütemezés** lapon jelölte ki, kövesse a napló létrehozásának lépéseit a [Havi naplóbejegyzések létrehozása kötegben](create-monthly-journals-batch.md) című részben.</span><span class="sxs-lookup"><span data-stu-id="c8043-125">If you selected the transaction on the **Schedule** page, follow the steps for creating a journal in [Create monthly journal entries in a batch](create-monthly-journals-batch.md).</span></span> <span data-ttu-id="c8043-126">A naplót manuálisan kell feladnia.</span><span class="sxs-lookup"><span data-stu-id="c8043-126">You must manually post the journal.</span></span>
    - <span data-ttu-id="c8043-127">Ha a tranzakciót a **Tranzakciók** lapon választotta ki, válassza a **Tranzakció sztornírozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c8043-127">If you selected the transaction on the **Transactions** page, select **Reverse transaction**.</span></span> <span data-ttu-id="c8043-128">Megjelenik egy üzenet, amely szerint ez a visszavonás egy korábbi sztornírozás visszavonása, és hogy szerkesztheti a visszavonás feladási dátumát.</span><span class="sxs-lookup"><span data-stu-id="c8043-128">You receive a message that states that this revocation is a revocation of an earlier reversal, and that you can edit the posting date for this revocation.</span></span> <span data-ttu-id="c8043-129">Az általános üzleti ellenőrzések azonban hatással vannak a **Dátum** mezőben beírható dátumokra.</span><span class="sxs-lookup"><span data-stu-id="c8043-129">However, general business validations affect the dates that can be entered in the **Date** field.</span></span> 

3. <span data-ttu-id="c8043-130">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c8043-130">Select **OK**.</span></span> <span data-ttu-id="c8043-131">A program olyan naplóbejegyzést ad fel, amely sztornírozza a kijelölt tételt.</span><span class="sxs-lookup"><span data-stu-id="c8043-131">A journal entry is posted that reverses the entry that you selected.</span></span> <span data-ttu-id="c8043-132">A sztornírozás a **Tranzakciók** lapon jelenik meg, és a nettó teljes aktuális egyenleg visszaáll az első sztornírozás előtti helyre.</span><span class="sxs-lookup"><span data-stu-id="c8043-132">The reversal is shown on the **Transactions** page, and the net total current balance is restored to what it was before the first reversal.</span></span> <span data-ttu-id="c8043-133">Ezért a visszavonásnak az egyenlegre gyakorolt hatása egyértelmű.</span><span class="sxs-lookup"><span data-stu-id="c8043-133">Therefore, the impact that the reversal had on the balances is negated.</span></span>

<span data-ttu-id="c8043-134">Ha a **Sztornírozott nyomkövetés** lehetőséget választja, megjelenik egy párbeszédpanel, amely az eredeti és a sztornírozott tranzakciókat is megjeleníti egy nyomkövetési számmal együtt.</span><span class="sxs-lookup"><span data-stu-id="c8043-134">When you select **Reverse tracing**, a dialog box appears that shows both the original transactions and the reversed transactions, together with a linked trace number.</span></span>

<span data-ttu-id="c8043-135">A visszavonásokat a megfelelő **Ütemezések** lapon is nyomon követheti.</span><span class="sxs-lookup"><span data-stu-id="c8043-135">You can also track revocations by using the appropriate **Schedules** page.</span></span> <span data-ttu-id="c8043-136">A **Sztornírozott** mező törlődik, míg a **Feladott napló** mező be van jelölve.</span><span class="sxs-lookup"><span data-stu-id="c8043-136">The **Reverse** field is cleared, whereas the **Journal posted** field is selected.</span></span> <span data-ttu-id="c8043-137">Ezenkívül a **Legkésőbbi naplószám** mező frissül a visszavonási tranzakció naplószámával, és a **Naplószám** mező a sztornírozási naplószámmal frissül.</span><span class="sxs-lookup"><span data-stu-id="c8043-137">Additionally, the **Latest journal number** field is updated with the journal number of the revocation transaction, and the **Journal number** field is updated with the reversal journal number.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
