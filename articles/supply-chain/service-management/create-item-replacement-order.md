---
title: Csererendelés létrehozása egy cikkre vonatkozóan
description: A cserecikkrendeléseket általában a visszajuttatott termék kivizsgálása után hozzák létre.
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReturnTableListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 784a2522c27e8131f211ffc52319552b3b928cc3
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1556829"
---
# <a name="create-an-item-replacement-order"></a><span data-ttu-id="dda65-103">Csererendelés létrehozása egy cikkre vonatkozóan</span><span class="sxs-lookup"><span data-stu-id="dda65-103">Create an item replacement order</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="dda65-104">A cserecikkrendeléseket általában a visszajuttatott termék kivizsgálása után hozzák létre.</span><span class="sxs-lookup"><span data-stu-id="dda65-104">Item replacement orders are usually created after a product is returned and inspected.</span></span> <span data-ttu-id="dda65-105">Előfordulhat azonban, hogy a cikket még a visszajuttatás előtt ki kell cserélni, vagy az eredeti cikket egyáltalán nem juttatják vissza, ezért ilyenkor a cserecikkrendelést közvetlenül a visszárurendelés után létre lehet hozni.</span><span class="sxs-lookup"><span data-stu-id="dda65-105">However, when an item must be replaced before it has been returned, or when the original item will not be returned, you can create an item replacement order immediately after you create a return order.</span></span>

## <a name="create-a-replacement-order-after-you-receive-an-item-that-is-returned"></a><span data-ttu-id="dda65-106">Csererendelés létrehozása visszáru beérkezése után</span><span class="sxs-lookup"><span data-stu-id="dda65-106">Create a replacement order after you receive an item that is returned</span></span>

1.  <span data-ttu-id="dda65-107">Kattintson a következőkre: **Értékesítés és marketing** \> **Közös** \> **Visszárurendelések** \> **MInden visszárurendelés**.</span><span class="sxs-lookup"><span data-stu-id="dda65-107">Click **Sales and marketing** \> **Common** \> **Return orders** \> **All return orders**.</span></span>

2.  <span data-ttu-id="dda65-108">Hozzon létre új visszárurendelést, vagy a **Visszárurendelések - RMA-szám: %1, %2** képernyő megnyitásához válasszon ki a listáról egy visszárurendelést.</span><span class="sxs-lookup"><span data-stu-id="dda65-108">Create a new return order, or select a returned order from the list to open the **Return order - RMA number: %1, %2** form.</span></span>

3.  <span data-ttu-id="dda65-109">Kattintson a **Visszárusor** lehetőségre, majd válassza ki a **Helyettesítő cikk** opciót.</span><span class="sxs-lookup"><span data-stu-id="dda65-109">Click **Return line**, and then select **Replacement item**.</span></span>

4.  <span data-ttu-id="dda65-110">Jelölje ki a cikket, amellyel cseréli a visszáruzott cikket.</span><span class="sxs-lookup"><span data-stu-id="dda65-110">Select the item to replace the returned item with.</span></span> <span data-ttu-id="dda65-111">Adja meg a cikk adatait, majd kattintson az **Alkalmaz** gombra.</span><span class="sxs-lookup"><span data-stu-id="dda65-111">Enter the item specifications, and then click **Apply**.</span></span>

5.  <span data-ttu-id="dda65-112">A visszárurendelés szállítólevelének létrehozásához kattintson a **Visszárurendelés szállítólevele** elemre.</span><span class="sxs-lookup"><span data-stu-id="dda65-112">Click **Packing slip** to generate the packing slip for the return order.</span></span> <span data-ttu-id="dda65-113">A kijelölt cserecikkhez értékesítési rendelés jön létre.</span><span class="sxs-lookup"><span data-stu-id="dda65-113">A sales order is generated for the replacement item that you selected.</span></span>
    
    <span data-ttu-id="dda65-114">A rendszer a cserecikk értékesítési rendelésének létrejötte után automatikusan keresést végez az értékesítési szerződések között, és ha van megfelelő értékesítési szerződés, akkor azt alkalmazza az értékesítési rendelésen.</span><span class="sxs-lookup"><span data-stu-id="dda65-114">After the sales order is created for the replacement item, sales agreements are automatically searched and if there is an applicable sales agreement, it is applied to the sales order.</span></span>

## <a name="create-a-replacement-order-before-you-receive-an-item-that-will-be-returned"></a><span data-ttu-id="dda65-115">Csererendelés létrehozása visszáruzott cikkhez annak beérkezése előtt </span><span class="sxs-lookup"><span data-stu-id="dda65-115">Create a replacement order before you receive an item that will be returned</span></span>

1.  <span data-ttu-id="dda65-116">Kattintson a következőkre: **Értékesítés és marketing** \> **Közös** \> **Visszárurendelések** \> **MInden visszárurendelés**.</span><span class="sxs-lookup"><span data-stu-id="dda65-116">Click **Sales and marketing** \> **Common** \> **Return orders** \> **All return orders**.</span></span>

2.  <span data-ttu-id="dda65-117">Hozzon létre új visszárurendelést, vagy a **Visszárurendelések - RMA-szám: %1, %2** képernyő megnyitásához válasszon ki a listáról egy visszárurendelést.</span><span class="sxs-lookup"><span data-stu-id="dda65-117">Create a new return order, or select a return order from the list to open the **Return order - RMA number: %1, %2** form.</span></span>

3.  <span data-ttu-id="dda65-118">A visszaküldött cikkre vonatkozó értékesítési rendelés azonosításához kattintson az **Értékesítési rendelés megkeresése** elemre.</span><span class="sxs-lookup"><span data-stu-id="dda65-118">Click **Find sales order** if you want to identify the sales order for the returned item.</span></span> <span data-ttu-id="dda65-119">Töltse ki az **Értékesítési rendelés megkeresése** képernyőt, majd kattintson az **OK** gombra a képernyő bezárásához és a **Visszárurendelések - RMA-szám: %1, %2** képernyőre való visszatéréshez.</span><span class="sxs-lookup"><span data-stu-id="dda65-119">Complete the **Find sales order** form and then click **OK** to close the form and return to the **Return order - RMA number: %1, %2** form.</span></span> <span data-ttu-id="dda65-120">A visszárucikkhez tartozó értékesítésirendelés-sor a visszárurendelésbe másolódik.</span><span class="sxs-lookup"><span data-stu-id="dda65-120">The sales order line for the returned item is copied to the return order.</span></span>

4.  <span data-ttu-id="dda65-121">Az **Értékesítési rendelés** képernyő megnyitásához kattintson a **Csererendelés** elemre.</span><span class="sxs-lookup"><span data-stu-id="dda65-121">Click **Replacement order** to open the **Create sales order** form.</span></span>

5.  <span data-ttu-id="dda65-122">Jelölje be a **Visszárurendelés-sorok másolása** jelölőnégyzetet, hogy az értékesítési rendelésbe másolja a **Visszárurendelések - RMA-szám: %1, %2** képernyőn kijelölt visszárurendelés adatait.</span><span class="sxs-lookup"><span data-stu-id="dda65-122">Select the **Copy return order lines** check box to transfer details from the return order you selected on the **Return order - RMA number: %1, %2** form to this sales order.</span></span>

6.  <span data-ttu-id="dda65-123">Szükség esetén adja meg és módosítsa az adatokat.</span><span class="sxs-lookup"><span data-stu-id="dda65-123">Enter or modify details, as required.</span></span>
    
    <span data-ttu-id="dda65-124">Amennyiben a 3. lépésben azonosította az értékesítési rendelést, valamint ha a visszaküldött cikkre vonatkozó értékesítésirendelés-sor értékesítési szerződéshez kapcsolódik, a csererendelésre vonatkozó értékesítési szerződés azonosítója automatikusan megjelenik az **Értékesítési szerződés azonosítója** mezőben.</span><span class="sxs-lookup"><span data-stu-id="dda65-124">If you identified the sales order in step 3, and if the sales order line for the returned item is linked to a sales agreement, the identifier of the applicable sales agreement for the item replacement order will be automatically displayed in the **Sales agreement ID** field.</span></span>

7.  <span data-ttu-id="dda65-125">Kattintson az **OK** gombra az **Értékesítési rendelés létrehozása** képernyő bezárásához és az **Értékesítési rendelés** képernyő megnyitásához, ahol folytathatja az új értékesítési rendelés adatainak megadását.</span><span class="sxs-lookup"><span data-stu-id="dda65-125">Click **OK** to close the **Create sales order** form and open the **Sales order** form, where you can continue to enter information for the new sales order.</span></span> <span data-ttu-id="dda65-126">Az alkalmazandó visszárurendelés-sorok az új értékesítési rendelésbe másolódnak.</span><span class="sxs-lookup"><span data-stu-id="dda65-126">Any applicable return order lines will be copied to the new sales order.</span></span> 
    
    <span data-ttu-id="dda65-127">Ha az értékesítési szerződés azonosítója automatikusan megjelent az **Értékesítési szerződés azonosítója** mezőben, akkor az értékesítési szerződés össze van kapcsolva a cikk csererendelésére vonatkozó értékesítési rendelés fejlécével.</span><span class="sxs-lookup"><span data-stu-id="dda65-127">If the identifier of the sales agreement is automatically displayed in the **Sales agreement ID** field, then the sales agreement has been linked to the sales order header for the item replacement order.</span></span> <span data-ttu-id="dda65-128">Ha az értékesítési szerződésben még nem teljesített kötelezettség szerepel, és az értékesítési rendelés még az értékesítési szerződés lejárata előtt létrejön, az értékesítési szerződés és az értékesítési rendelési sor között kapcsolat jön létre.</span><span class="sxs-lookup"><span data-stu-id="dda65-128">If there is an applicable commitment in the sales agreement that has not been fulfilled yet, and the sales order is created before the sales agreement expires, a link is established between the sales agreement line and the sales order line.</span></span> <span data-ttu-id="dda65-129">Így az új értékesítésirendelés-sorba belemásolódnak az értékesítési szerződés adatai, például a cikk ára.</span><span class="sxs-lookup"><span data-stu-id="dda65-129">Therefore, information from the sales agreement, such as item price, is copied to the new sales order line.</span></span> 
  


