---
title: "Vevői tranzakciók listája oldal"
description: "Ez a témakör a Microsoft Dynamics 365 for Finance and Operations a vevői tranzakció lista oldalát mutatja be."
author: mikefalkner
manager: aolson
ms.date: 08/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: 8.0.4
ms.translationtype: HT
ms.sourcegitcommit: 98ed3378ab05c0c69c9e5b2a82310113a81c2264
ms.openlocfilehash: e828cb292ad48bb4690117b41589b25edcdf28bc
ms.contentlocale: hu-hu
ms.lasthandoff: 08/31/2018

---

# <a name="customer-transaction-list-page"></a><span data-ttu-id="1e2cb-103">Vevői tranzakciók listája oldal</span><span class="sxs-lookup"><span data-stu-id="1e2cb-103">Customer transaction list page</span></span>

[!include [banner](../includes/banner.md)]

## <a name="view-settlements"></a><span data-ttu-id="1e2cb-104">Kiegyenlítések megjelenítése</span><span class="sxs-lookup"><span data-stu-id="1e2cb-104">View settlements</span></span>

<span data-ttu-id="1e2cb-105">A **Kiegyenlítések megjelenítése** a műveleti panelen gyorsan hozzáférhet a kiegyenlítési előzményekhez és a teljes kiegyenlítés tranzakció további adataihoz.</span><span class="sxs-lookup"><span data-stu-id="1e2cb-105">The **View settlements** tab on the action pane provides quick access to settlement history and more information about the whole settlement transaction.</span></span> <span data-ttu-id="1e2cb-106">További kapcsolódó tranzakciókat is megjeleníthet, amelyek kapcsolódna a kiválasztott tranzakcióhoz vagy azért, mert ugyanazon kiegyenlítés részei vagy azért, mert olyan fizetések, amelyeket ugyanazon fizetési naplóban hoztak létre.</span><span class="sxs-lookup"><span data-stu-id="1e2cb-106">You can also show additional transactions that are related to the selected transaction, either because they were part of the same settlement or because they are payments that were created in the same payment journal.</span></span>

1. <span data-ttu-id="1e2cb-107">Válassza a **Kinnlévőségek \> Ügyfelek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1e2cb-107">Select **Accounts receivable \> Customers**.</span></span>
2. <span data-ttu-id="1e2cb-108">Válasszon ki egy vevőt, amelyekhez tranzakciók tartoznak, majd válassza a **Vevő \> Tranzakciók** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1e2cb-108">Select a customer that has transactions, and then select **Customer \> Transactions**.</span></span>
3. <span data-ttu-id="1e2cb-109">Válasszon egy tranzakciót a kutatáshoz</span><span class="sxs-lookup"><span data-stu-id="1e2cb-109">Select a transaction to research.</span></span>
4. <span data-ttu-id="1e2cb-110">Válassza ki a **Kiegyenlítések megjelenítése** lapot a műveleti panelen.</span><span class="sxs-lookup"><span data-stu-id="1e2cb-110">Select the **View settlements** tab on the action pane.</span></span>

    <span data-ttu-id="1e2cb-111">A **Kiegyenlítések megjelenítése** párbeszédpanel mutatja a kijelölt tranzakciót minden dokumentumot, amelyek ki lettek egyenlítve vele szemben.</span><span class="sxs-lookup"><span data-stu-id="1e2cb-111">The **View settlements** dialog box shows the selected transaction and all documents that have been settled against it.</span></span> <span data-ttu-id="1e2cb-112">Ezen a párbeszédpanelen hasonlít a kiegyenlítési előzmények nézetre, de az összes kapcsolódó dokumentumot tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="1e2cb-112">This dialog box resembles the settlement history view, but it includes all related documents.</span></span> 

5. <span data-ttu-id="1e2cb-113">Ezen a párbeszédpanelen a különböző feladatok hajthatók végre.</span><span class="sxs-lookup"><span data-stu-id="1e2cb-113">You can perform various tasks from this dialog box.</span></span> <span data-ttu-id="1e2cb-114">Válasszon ki egy vagy több bizonylatot majd, válassza ki az alábbi menük egyikét:</span><span class="sxs-lookup"><span data-stu-id="1e2cb-114">Select one or more vouchers, and then select one of the following menus:</span></span>

   - <span data-ttu-id="1e2cb-115">**Könyvelés megtekintése** – A kiválasztott dokumentumhoz kapcsolódó összes bizonylat megtekintése.</span><span class="sxs-lookup"><span data-stu-id="1e2cb-115">**View accounting** – All vouchers that are related to the selected documents appear.</span></span> <span data-ttu-id="1e2cb-116">A **Bezárás** gombbal zárja be a párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="1e2cb-116">Select **Close** to close the dialog box.</span></span>
   - <span data-ttu-id="1e2cb-117">**Exportálás** – A kijelölt bizonylatok exportálása az Microsoft Excelbe.</span><span class="sxs-lookup"><span data-stu-id="1e2cb-117">**Export** – Export the selected vouchers to Microsoft Excel.</span></span>
   - <span data-ttu-id="1e2cb-118">**Kapcsolódó fizetések megtekintése** – a fizetési napló összes tranzakciója jelenik meg, amely a kifizetési naplóban lett létrehozva és kapcsolódik a dokumentumhoz.</span><span class="sxs-lookup"><span data-stu-id="1e2cb-118">**View related payments** – All the payment journal transactions that were created in the payment journal that is related to the selected document appear.</span></span> <span data-ttu-id="1e2cb-119">Ezenkívül ezek a kifizetésekhez kapcsolódó valamennyi kiegyenlítés jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="1e2cb-119">In addition, all the settlements that are related to those payments appear.</span></span> <span data-ttu-id="1e2cb-120">A menü címkéje is módosul: **Kiegyenlítések megjelenítése**.</span><span class="sxs-lookup"><span data-stu-id="1e2cb-120">The label of this menu also changes to **View settlements**.</span></span> <span data-ttu-id="1e2cb-121">Válassza a **Kiegyenlítések megjelenítése** lehetőséget hogy csak azokat a tranzakciókat jelenítse meg, amelyek meg lettek jelenítve amikor először nyitotta meg a  **Kiegyenlítések megjelenítése** párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="1e2cb-121">Select **View settlements** to show only the transactions that were shown when you first opened the  **View settlements** dialog box.</span></span>
    - <span data-ttu-id="1e2cb-122">**Tranzakciók kiegyenlítése** – Ez a menü jelenik meg, ha a kiválasztott eredeti dokumentum nem lett teljesen kiegyenlítve.</span><span class="sxs-lookup"><span data-stu-id="1e2cb-122">**Settle transactions** – This menu appears if the original document that was selected wasn't fully settled.</span></span> <span data-ttu-id="1e2cb-123">Ha bejelöli ezt a **Tranzakciók kiegyenlítése** párbeszédpanel jelenik meg, ahol kiválaszthatja a tranzakciókat a kiegyenlítéshez.</span><span class="sxs-lookup"><span data-stu-id="1e2cb-123">When you select it, the **Settle transactions** dialog box appears, where you can select transactions for settlement.</span></span>
    - <span data-ttu-id="1e2cb-124">**Kiegyenlítések visszavonása** – Ez a menü jelenik meg, ha a kiválasztott eredeti dokumentum teljesen ki lett egyenlítve.</span><span class="sxs-lookup"><span data-stu-id="1e2cb-124">**Undo settlements** – This menu appears if the original document that was selected was fully settled.</span></span> <span data-ttu-id="1e2cb-125">Ha kiválasztja a **Kiegyenlítések visszavonása** párbeszédpanel jelenik meg, ahol visszavonhatók a dokumentumhoz végrehajtott kiegyenlítések.</span><span class="sxs-lookup"><span data-stu-id="1e2cb-125">When you select it, the **Undo settlements** dialog box appears, where you can undo the settlements that were done for that document.</span></span>
    

