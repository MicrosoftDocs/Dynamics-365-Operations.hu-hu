---
title: "Szállítói tranzakciók listája oldal"
description: "Ez a témakör a Microsoft Dynamics 365 for Finance and Operations a Szállítói tranzakció lista oldalát mutatja be."
author: mikefalkner
manager: aolson
ms.date: 08/24/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.translationtype: HT
ms.sourcegitcommit: 98ed3378ab05c0c69c9e5b2a82310113a81c2264
ms.openlocfilehash: 1ef7d97f059801f2fb2c0d451546b57055208f81
ms.contentlocale: hu-hu
ms.lasthandoff: 08/31/2018

---

# <a name="vendor-transaction-list-page"></a><span data-ttu-id="9ce63-103">Szállítói tranzakciók listája oldal</span><span class="sxs-lookup"><span data-stu-id="9ce63-103">Vendor transaction list page</span></span>

[!include [banner](../includes/banner.md)]

## <a name="view-settlements"></a><span data-ttu-id="9ce63-104">Kiegyenlítések megjelenítése</span><span class="sxs-lookup"><span data-stu-id="9ce63-104">View settlements</span></span>

<span data-ttu-id="9ce63-105">A **Kiegyenlítések megjelenítése** a műveleti panelen gyorsan hozzáférhet a kiegyenlítési előzményekhez és a teljes kiegyenlítés tranzakció további adataihoz.</span><span class="sxs-lookup"><span data-stu-id="9ce63-105">The **View settlements** tab on the action pane provides quick access to settlement history and more information about the whole settlement transaction.</span></span> <span data-ttu-id="9ce63-106">További kapcsolódó tranzakciókat is megjeleníthet, amelyek kapcsolódna a kiválasztott tranzakcióhoz vagy azért, mert ugyanazon kiegyenlítés részei vagy azért, mert olyan fizetések, amelyeket ugyanazon fizetési naplóban hoztak létre.</span><span class="sxs-lookup"><span data-stu-id="9ce63-106">You can also show additional transactions that are related to the selected transaction, either because they were part of the same settlement or because they are payments that were created in the same payment journal.</span></span>

1. <span data-ttu-id="9ce63-107">Válassza a **Kötelezettségek \> Minden szállító** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9ce63-107">Select **Accounts payable \> All vendors**.</span></span>
2. <span data-ttu-id="9ce63-108">Válasszon ki egy szállítót, amelyekhez tranzakciók tartoznak, majd válassza a **Szállító \> Tranzakciók** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9ce63-108">Select a vendor that has transactions, and then select **Vendor \> Transactions**.</span></span>
3. <span data-ttu-id="9ce63-109">Válasszon egy tranzakciót a kutatáshoz</span><span class="sxs-lookup"><span data-stu-id="9ce63-109">Select a transaction to research.</span></span>
4. <span data-ttu-id="9ce63-110">Válassza ki a **Kiegyenlítések megjelenítése** lapot a műveleti panelen.</span><span class="sxs-lookup"><span data-stu-id="9ce63-110">Select the **View settlements** tab on the action pane.</span></span>

    <span data-ttu-id="9ce63-111">A **Kiegyenlítések megjelenítése** párbeszédpanel megnyílik, és mutatja a kijelölt tranzakciót minden dokumentumot, amelyek ki lettek egyenlítve vele szemben.</span><span class="sxs-lookup"><span data-stu-id="9ce63-111">The **View settlements** dialog box opens and shows the selected transaction and all documents that are settled against it.</span></span> <span data-ttu-id="9ce63-112">Ezen a párbeszédpanelen hasonlít a kiegyenlítési előzmények nézetre, de az összes kapcsolódó dokumentumot tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="9ce63-112">This dialog box resembles the settlement history view, but it includes all related documents.</span></span>

5. <span data-ttu-id="9ce63-113">Ezen a párbeszédpanelen a különböző feladatok hajthatók végre.</span><span class="sxs-lookup"><span data-stu-id="9ce63-113">You can perform various tasks from this dialog box.</span></span> <span data-ttu-id="9ce63-114">Válasszon ki egy vagy több bizonylatot majd, válassza ki az alábbi menük egyikét:</span><span class="sxs-lookup"><span data-stu-id="9ce63-114">Select one or more vouchers, and then select one of the following menus:</span></span>

   - <span data-ttu-id="9ce63-115">**Könyvelés megtekintése** – A kiválasztott dokumentumhoz kapcsolódó összes bizonylat megtekintése.</span><span class="sxs-lookup"><span data-stu-id="9ce63-115">**View accounting** – All vouchers that are related to the selected documents appear.</span></span> <span data-ttu-id="9ce63-116">A **Bezárás** gombbal zárja be a párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="9ce63-116">Select **Close** to close the dialog box.</span></span>
   - <span data-ttu-id="9ce63-117">**Exportálás** – A kijelölt bizonylatok exportálása az Microsoft Excelbe.</span><span class="sxs-lookup"><span data-stu-id="9ce63-117">**Export** – Export the selected vouchers to Microsoft Excel.</span></span>
   - <span data-ttu-id="9ce63-118">**Kapcsolódó fizetések megtekintése** – a fizetési napló összes tranzakciója jelenik meg, amely a kifizetési naplóban lett létrehozva és kapcsolódik a dokumentumhoz.</span><span class="sxs-lookup"><span data-stu-id="9ce63-118">**View related payments** – All the payment journal transactions that were created in the payment journal that is related to the selected document appear.</span></span> <span data-ttu-id="9ce63-119">Ezenkívül ezek a kifizetésekhez kapcsolódó valamennyi kiegyenlítés jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="9ce63-119">In addition, all the settlements that are related to those payments appear.</span></span> <span data-ttu-id="9ce63-120">A menü címkéje is módosul: **Kiegyenlítések megjelenítése**.</span><span class="sxs-lookup"><span data-stu-id="9ce63-120">The label of this menu also changes to **View settlements**.</span></span> <span data-ttu-id="9ce63-121">Válassza a **Kiegyenlítések megjelenítése** lehetőséget hogy csak azokat a tranzakciókat jelenítse meg, amelyek meg lettek jelenítve amikor először nyitotta meg a  **Kiegyenlítések megjelenítése** párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="9ce63-121">Select **View settlements** to show only the transactions that were shown when you first opened the  **View settlements** dialog box.</span></span>
    - <span data-ttu-id="9ce63-122">**Tranzakciók kiegyenlítése** – Ez a menü jelenik meg, ha a kiválasztott eredeti dokumentum nem lett teljesen kiegyenlítve.</span><span class="sxs-lookup"><span data-stu-id="9ce63-122">**Settle transactions** – This menu appears if the original document that was selected wasn't fully settled.</span></span> <span data-ttu-id="9ce63-123">Ha bejelöli ezt a **Tranzakciók kiegyenlítése** párbeszédpanel jelenik meg, ahol kiválaszthatja a tranzakciókat a kiegyenlítéshez.</span><span class="sxs-lookup"><span data-stu-id="9ce63-123">When you select it, the **Settle transactions** dialog box appears, where you can select transactions for settlement.</span></span>
    - <span data-ttu-id="9ce63-124">**Kiegyenlítések visszavonása** – Ez a menü jelenik meg, ha a kiválasztott eredeti dokumentum teljesen ki lett egyenlítve.</span><span class="sxs-lookup"><span data-stu-id="9ce63-124">**Undo settlements** – This menu appears if the original document that was selected was fully settled.</span></span> <span data-ttu-id="9ce63-125">Ha kiválasztja a **Kiegyenlítések visszavonása** párbeszédpanel jelenik meg, ahol visszavonhatók a dokumentumhoz végrehajtott kiegyenlítések.</span><span class="sxs-lookup"><span data-stu-id="9ce63-125">When you select it, the **Undo settlements** dialog box appears, where you can undo the settlements that were done for that document.</span></span>

