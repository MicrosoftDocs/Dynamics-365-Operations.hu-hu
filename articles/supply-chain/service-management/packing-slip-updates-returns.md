---
title: Visszárura vonatkozó csomagjegyzék-frissítés
description: Ahhoz, hogy a visszaküldött cikkeket bevételezni lehessen a készletbe, frissíteni kell annak a rendelésnek a csomagjegyzékét, amelyhez a cikkek tartoznak.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPackingSlipJournalHistory, SalesParmPackingSlipTrackingInformation
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e7f5bf5adb603d7edb40960b70cb71e25a2f0456
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2020
ms.locfileid: "3983867"
---
# <a name="packing-slip-updates-for-returns"></a><span data-ttu-id="ea30c-103">Visszárura vonatkozó csomagjegyzék-frissítés</span><span class="sxs-lookup"><span data-stu-id="ea30c-103">Packing slip updates for returns</span></span>  

[!include [banner](../includes/banner.md)]


<span data-ttu-id="ea30c-104">Ahhoz, hogy a visszaküldött cikkeket bevételezni lehessen a készletbe, frissíteni kell annak a rendelésnek a csomagjegyzékét, amelyhez a cikkek tartoznak.</span><span class="sxs-lookup"><span data-stu-id="ea30c-104">Before returned items can be received into inventory, the packing slip for the order to which they belong must be updated.</span></span> <span data-ttu-id="ea30c-105">Ahogyan a számlafrissítés folyamata a pénzügyi tranzakció frissítése, úgy a csomagjegyzék-frissítés folyamata a készletrekord fizikai frissítése, ami azt jelenti, hogy az véglegesíti a készlet változásait.</span><span class="sxs-lookup"><span data-stu-id="ea30c-105">Just as the invoice update process is the update to the financial transaction, the packing slip update process is the physical update of the inventory record, which means that it commits the changes to inventory.</span></span> <span data-ttu-id="ea30c-106">Visszaküldés esetén a csomagjegyzék frissítésekor az intézkedési művelethez tartozó lépéseket is végrehajtják.</span><span class="sxs-lookup"><span data-stu-id="ea30c-106">In the case of returns, the steps that are assigned to the disposition action are implemented during the packing slip update.</span></span>

<span data-ttu-id="ea30c-107">A csomagjegyzékek frissítése a cikkérkezési naplóban és a visszárurendelésben is elvégezhető.</span><span class="sxs-lookup"><span data-stu-id="ea30c-107">The packing slip update can be processed in either the item arrival journal or the return order.</span></span>

<span data-ttu-id="ea30c-108">A szállítólevelek könyvelési folyamata részeként a csomagjegyzék hivatkozási száma a vevő szállítási dokumentumokból is társíthat a rendelési sorokhoz.</span><span class="sxs-lookup"><span data-stu-id="ea30c-108">As part of the process for posting packing slips, the packing slip reference number from the customer’s shipping documents can be associated with the order lines.</span></span> <span data-ttu-id="ea30c-109">Ez a társítás nem kötelező, és csak referenciaként szolgál.</span><span class="sxs-lookup"><span data-stu-id="ea30c-109">This association is optional and for reference only.</span></span> <span data-ttu-id="ea30c-110">Nem hoz létre tranzakciós frissítéseket.</span><span class="sxs-lookup"><span data-stu-id="ea30c-110">It does not create any transactional updates.</span></span>

<span data-ttu-id="ea30c-111">Ha nem érkezik meg minden várt visszáru, akkor a csomagjegyzék frissítésekor csak a kapott mennyiséget kell rögzítenie.</span><span class="sxs-lookup"><span data-stu-id="ea30c-111">If not all of the expected return items have arrived, you should include only the quantity that has been received in the packing slip update.</span></span> <span data-ttu-id="ea30c-112">A fennmaradó mennyiséget hagyja a rendelésben, amíg a visszáruszállítmány meg nem érkezik.</span><span class="sxs-lookup"><span data-stu-id="ea30c-112">Leave the remaining items on the order until the rest of the return shipment has arrived.</span></span>

<span data-ttu-id="ea30c-113">Ha a cikket karanténból küldik vissza a szállítási részleghez, például mert a karantén felügyelője nem tudja, hogy hol tárolja a cikket a készletben, akkor szintén frissíteni kell a megfelelő csomagjegyzéket, hogy a karantén eredményeként meghatározott intézkedési kódot helyesen regisztrálják, és az intézkedést végrehajtsák.</span><span class="sxs-lookup"><span data-stu-id="ea30c-113">If an item is sent back from quarantine to the Shipping and Receiving department, such as when the quarantine inspector does not know where to store the item in inventory, the corresponding packing slip must be updated to correctly register and act on the disposition code that is specified as a result of the quarantine.</span></span>

<span data-ttu-id="ea30c-114">Amikor frissíti egy értékesítési szerződéshez tartozó visszáru csomagjegyzékét, az adott cikkhez kapcsolódó értékesítési szerződés automatikusan frissül, hogy jelezze a mennyiség vagy összeg változását.</span><span class="sxs-lookup"><span data-stu-id="ea30c-114">When you update a packing slip for a returned item that is from a sales agreement, the sales agreement commitment for that item is automatically updated to reflect the change in the quantity or the amount.</span></span> 

## <a name="see-also"></a><span data-ttu-id="ea30c-115">Lásd még</span><span class="sxs-lookup"><span data-stu-id="ea30c-115">See also</span></span>

[<span data-ttu-id="ea30c-116">Visszárura vonatkozó számlafrissítés végrehajtása</span><span class="sxs-lookup"><span data-stu-id="ea30c-116">Perform invoice updates for returns</span></span>](perform-invoice-updates-for-returns.md)

  


