---
title: Tranzakció felfüggesztése és újraindítása a pénztárban (POS)
description: Ez a témakör bemutatja, a felhasználók, hogyan függeszthetnek fel folyamatban lévő tranzakciókat, majd folytathatják azokat később egy másik jegyzék használatával a Dynamics 365 Commerce használatával.
author: jblucher
manager: AnnBe
ms.date: 11/27/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 261234
ms.assetid: 7cd68ecc-cc09-48ab-8cb8-48d5c304effa
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: f513e2d857908f2b95d27bf48ff1e826724d7cbf
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2020
ms.locfileid: "3022832"
---
# <a name="suspend-and-resume-a-transaction-in-the-point-of-sale-pos"></a><span data-ttu-id="ca60b-103">Tranzakció felfüggesztése és újraindítása a pénztárban (POS)</span><span class="sxs-lookup"><span data-stu-id="ca60b-103">Suspend and resume a transaction in the point of sale (POS)</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="ca60b-104">A pénztár (POS) felhasználók a folyamatban lévő tranzakciókat felfüggeszthetik, majd később folytathatják azokat később vagy egy másik jegyzékben.</span><span class="sxs-lookup"><span data-stu-id="ca60b-104">Point of sale (POS) users can suspend in-progress transactions, and then resume them later or on a different register.</span></span> <span data-ttu-id="ca60b-105">Tranzakciókat gyakran azért függesztik fel, hogy gyorsan felszabadítsanak egy jegyzéket egy másik feladathoz, anélkül, hogy elveszítenék az aktuális tranzakcióban a haladást.</span><span class="sxs-lookup"><span data-stu-id="ca60b-105">Transactions are often suspended to quickly free up a register for a different task without losing any progress on the current transaction.</span></span> <span data-ttu-id="ca60b-106">Például egy bolti alkalmazott elkezd feldolgozni egy ügyféltranzakciót egy mobileszközön, de készpénzfiókos kasszán kell azt befejeznie.</span><span class="sxs-lookup"><span data-stu-id="ca60b-106">For example, a store associate starts to process a customer's transaction on a mobile device but must complete it on a register that has a cash drawer.</span></span> <span data-ttu-id="ca60b-107">Ebben az esetben a bolti alkalmazott felfüggesztheti a tranzakciót a mobileszközön, majd előhívhatja, és folytathatja egy pénztárgépen.</span><span class="sxs-lookup"><span data-stu-id="ca60b-107">In this case, the store associate can suspend the transaction on the mobile device, and then recall and resume it on a register.</span></span>

## <a name="configure-suspend-and-resume-functionality"></a><span data-ttu-id="ca60b-108">A felfüggesztés folytatás funkció beállítása</span><span class="sxs-lookup"><span data-stu-id="ca60b-108">Configure suspend and resume functionality</span></span>

### <a name="pos-operations"></a><span data-ttu-id="ca60b-109">Pénztári műveletek</span><span class="sxs-lookup"><span data-stu-id="ca60b-109">POS operations</span></span>

<span data-ttu-id="ca60b-110">Két [pénztári művelet](pos-operations.md) teszi lehetővé a pénztárnak az esetek felfüggesztését és folytatását.</span><span class="sxs-lookup"><span data-stu-id="ca60b-110">Two [POS operations](pos-operations.md) let the POS support suspend and resume scenarios.</span></span> <span data-ttu-id="ca60b-111">Ezeket a műveleteke, hozzárendelheti [gombrácsokhoz](pos-screen-layouts.md) tranzakció lapon vagy a kezdőlapon.</span><span class="sxs-lookup"><span data-stu-id="ca60b-111">You can assign these operations to [button grids](pos-screen-layouts.md) on the transaction page or the welcome page.</span></span>

- <span data-ttu-id="ca60b-112">503: Tranzakció felfüggesztése</span><span class="sxs-lookup"><span data-stu-id="ca60b-112">503: Suspend transaction</span></span>
- <span data-ttu-id="ca60b-113">504: Tranzakció visszahívása</span><span class="sxs-lookup"><span data-stu-id="ca60b-113">504: Recall transaction</span></span>

### <a name="receipt-template"></a><span data-ttu-id="ca60b-114">Nyugtasablon</span><span class="sxs-lookup"><span data-stu-id="ca60b-114">Receipt template</span></span>

<span data-ttu-id="ca60b-115">A pénztár beállítható úgy, hogy létrehozzon egy nyomtatott blokkot, ha a tranzakció fel van függesztve.</span><span class="sxs-lookup"><span data-stu-id="ca60b-115">The POS can be configured to generate a printed slip when a transaction is suspended.</span></span> <span data-ttu-id="ca60b-116">A blokkal később gyorsan lehet azonosítani és előhívni a tranzakciót.</span><span class="sxs-lookup"><span data-stu-id="ca60b-116">That slip can then be used to quickly identify and recall the transaction later.</span></span>

<span data-ttu-id="ca60b-117">Ahhoz, hogy a pénztár blokkot nyomtathasson a **Felfüggesztett tranzakció** nyugtaformátumot hozzá kell adnia a bolt nyugtaprofiljához.</span><span class="sxs-lookup"><span data-stu-id="ca60b-117">To enable the POS to print a slip, you must add the **Suspended transaction** receipt format to the store's receipt profile.</span></span> <span data-ttu-id="ca60b-118">A nyugtaformátumot megtervezheti úgy, hogy az tartalmazza vagy ne tartalmazza a tranzakció részleteit.</span><span class="sxs-lookup"><span data-stu-id="ca60b-118">You can design the receipt format so that it includes or excludes specific details about the transaction.</span></span> <span data-ttu-id="ca60b-119">A formátum például tartalmazhat vonalkódot a beolvasás támogatásához.</span><span class="sxs-lookup"><span data-stu-id="ca60b-119">For example, the format can include a barcode to support scanning.</span></span>

### <a name="receipt-numbering"></a><span data-ttu-id="ca60b-120">Nyugta számozása</span><span class="sxs-lookup"><span data-stu-id="ca60b-120">Receipt numbering</span></span>

<span data-ttu-id="ca60b-121">Egyéb pénztártranzakció-típusok esetében, amelyek nyomtatott nyugtát hoznak létre, meghatározhat egy számsorozatot a felfüggesztett tranzakciókhoz a bolt működési profiljának **Nyugta számozása** részében.</span><span class="sxs-lookup"><span data-stu-id="ca60b-121">As for other POS transaction types that generate a printed receipt, you can define a number sequence for suspended transactions in the **Receipt numbering** section of the store's functionality profile.</span></span>

### <a name="void-when-closing-shift"></a><span data-ttu-id="ca60b-122">Érvénytelenítés műszakzáráskor</span><span class="sxs-lookup"><span data-stu-id="ca60b-122">Void when closing shift</span></span>

<span data-ttu-id="ca60b-123">Használhatja a **Érvénytelenítés műszakzáráskor** lehetőséget, így megkövetelheti a felhasználóktól, hogy befejezzék vagy érvénytelenítsék a felfüggesztett tranzakciókat műszakjuk zárásakor.</span><span class="sxs-lookup"><span data-stu-id="ca60b-123">You can use the **Void when closing shift** option to require that users either complete or void any suspended transactions before they close their shift.</span></span> <span data-ttu-id="ca60b-124">A **Műszakzárás** művelet során, a pénztár felkéri a felhasználókat, hogy tekintsék meg vagy érvénytelenítsék a függőben lévő felfüggesztett tranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="ca60b-124">During the **Close shift** operation, the POS will prompt users to either view or void any outstanding suspended transactions.</span></span>

## <a name="suspend-and-resume-a-transaction"></a><span data-ttu-id="ca60b-125">Tranzakció felfüggesztése és folytatása</span><span class="sxs-lookup"><span data-stu-id="ca60b-125">Suspend and resume a transaction</span></span>

### <a name="suspend-a-transaction"></a><span data-ttu-id="ca60b-126">Tranzakció felfüggesztése</span><span class="sxs-lookup"><span data-stu-id="ca60b-126">Suspend a transaction</span></span>

<span data-ttu-id="ca60b-127">A felhasználók, akik rendelkezik a megfelelő jogosultságokkal, és akiknek képernyő-elrendezése tartalmazza a **Tranzakció felfüggesztése** műveletet, felfüggeszthetnek egy tranzakciót, hogy később azt egy másik pénztárban előhívhassák.</span><span class="sxs-lookup"><span data-stu-id="ca60b-127">Users who have sufficient privileges, and who have a screen layout that includes the **Suspend transaction** operation, can suspend a transaction so that it can be recalled later or on a different register.</span></span>

<span data-ttu-id="ca60b-128">Tranzakciók csak akkor függeszthetők fel, ha **nem** tartalmazzák a következő sortípusokat:</span><span class="sxs-lookup"><span data-stu-id="ca60b-128">Transactions can be suspended only if they do **not** contain the following types of lines:</span></span>

- <span data-ttu-id="ca60b-129">Aktív Fizetési sorok</span><span class="sxs-lookup"><span data-stu-id="ca60b-129">Active payment lines</span></span>
- <span data-ttu-id="ca60b-130">Ajándékutalvány-sorok (akár ajándékutalvány kibocsátása, akár hozzáadás ajándékkártya egyenlegéhez)</span><span class="sxs-lookup"><span data-stu-id="ca60b-130">Gift card lines (either to issue a gift card or to add to the gift card balance)</span></span>

<span data-ttu-id="ca60b-131">Felfüggesztett tranzakció nincs hatással a bolt értékesítési információira vagy raktárelérhetőséggel kapcsolatos információira.</span><span class="sxs-lookup"><span data-stu-id="ca60b-131">A suspended transaction doesn't affect sales information or inventory availability information for the store.</span></span>

### <a name="resume-a-suspended-transaction"></a><span data-ttu-id="ca60b-132">Felfüggesztett tranzakció visszahívása</span><span class="sxs-lookup"><span data-stu-id="ca60b-132">Resume a suspended transaction</span></span>

<span data-ttu-id="ca60b-133">Felfüggesztett tranzakciók visszahívhatók, és folytathatók ugyanabban az áruházban minden felhasználó által, aki rendelkezik a megfelelő jogosultságokkal és képernyő-elrendezése tartalmazza a **Tranzakció visszahívása** műveletet.</span><span class="sxs-lookup"><span data-stu-id="ca60b-133">Suspended transactions can be recalled and resumed in the same store by any user who has sufficient privileges, and who also has a layout that includes the **Recall transaction** operation.</span></span>

<span data-ttu-id="ca60b-134">Egy felfüggesztett tranzakció gyors és könnyű visszahívásához olvassa be a kinyomtatott nyugta vonalkódját, amikor megtekinti a tranzakciók listáját a **Tranzakció visszahívása** műveletnél.</span><span class="sxs-lookup"><span data-stu-id="ca60b-134">To quickly and easily recall a suspended transaction, scan the barcode on the printed slip while you're viewing the list of transactions from the **Recall transaction** operation.</span></span>

### <a name="considerations-for-offline-mode"></a><span data-ttu-id="ca60b-135">Információk offline módhoz</span><span class="sxs-lookup"><span data-stu-id="ca60b-135">Considerations for offline mode</span></span>

- <span data-ttu-id="ca60b-136">A pénztár online módjában felfüggesztetett tranzakciók kapcsolat nélküli módban nem folytatható, mert az adatok nincsenek szinkronizálva az offline adatbázissal.</span><span class="sxs-lookup"><span data-stu-id="ca60b-136">Any transaction that is suspended while the POS is in online mode can't be resumed in offline mode, because the data isn't synced to the offline database.</span></span>
- <span data-ttu-id="ca60b-137">Ha felfüggeszt egy tranzakciót, amíg a pénztár offline módban van, visszahívhatja azt offline módban, feltéve, hogy a pénztár nem váltott vissza online módba bármikor, amíg a tranzakció fel volt függesztve.</span><span class="sxs-lookup"><span data-stu-id="ca60b-137">If you suspend a transaction while the POS is in offline mode, you can recall it in offline mode, provided that the POS wasn't switched back to online mode at any time since you suspended the transaction.</span></span> <span data-ttu-id="ca60b-138">A pénztár online módba kapcsolásakor felfüggesztett tranzakciók adatait átkerülnek az online adatbázis és az offline adatbázisból el lesznek távolítva.</span><span class="sxs-lookup"><span data-stu-id="ca60b-138">When the POS is switched back to online mode, data about suspended transactions is moved to the online database and removed from the offline database.</span></span> <span data-ttu-id="ca60b-139">Emiatt a tranzakciók csak online módban folytathatók.</span><span class="sxs-lookup"><span data-stu-id="ca60b-139">Therefore, the transactions can be resumed only in online mode.</span></span> <span data-ttu-id="ca60b-140">Ha pénztárt offline módba váltja vissza, nem tudja folytatni ezeket a felfüggesztett tranzakciókat, mert azok már el lettek távolítva az offline adatbázisból.</span><span class="sxs-lookup"><span data-stu-id="ca60b-140">If you switch the POS back to offline mode, you won't be able to resume those suspended transaction, because they have already been removed from the offline database.</span></span>

### <a name="void-a-suspended-transaction"></a><span data-ttu-id="ca60b-141">Felfüggesztett tranzakció érvénytelenítése</span><span class="sxs-lookup"><span data-stu-id="ca60b-141">Void a suspended transaction</span></span>

<span data-ttu-id="ca60b-142">A felfüggesztett tranzakciókat érvénytelenítheti úgy, hogy előhívja a tranzakciót,.majd elvégzi a **Tranzakció érvénytelenítése** műveletet, vagy a tranzakció kiválasztásával a **Tranzakció visszahívása** listán, majd az **Érvénytelenítés** kiválasztásával az alkalmazás sávján.</span><span class="sxs-lookup"><span data-stu-id="ca60b-142">You can void suspended transactions either by recalling the transaction and then performing the **Void transaction** operation, or by selecting the transaction in the **Recall transaction** list and selecting **Void** on the app bar.</span></span> <span data-ttu-id="ca60b-143">Másik lehetőségként az üzlet beállítható úgy, hogy felkérje a felhasználókat a függőben lévő tranzakciók érvénytelenítésére, amikor lezárják műszakjukat.</span><span class="sxs-lookup"><span data-stu-id="ca60b-143">Alternatively, the store can be configured to prompt users to void suspended transactions when they close their shift.</span></span>