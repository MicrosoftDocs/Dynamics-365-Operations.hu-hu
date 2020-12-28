---
title: Szállítási mód módosítása a pénztárban
description: Ez a témakör azt mutatja be, hogyan lehet konfigurálni és használni a szállítási mód módosítása műveletet a pénztárban.
author: hhainesms
manager: annbe
ms.date: 03/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: ''
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhaines
ms.search.validFrom: 2020-02-20
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: eaffe7821b60dd787a7d8b7533c1b8599033ba68
ms.sourcegitcommit: 597476103bb695e3cbe6d9ffcd7a466400346636
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/20/2020
ms.locfileid: "4594137"
---
# <a name="change-mode-of-delivery-in-pos"></a><span data-ttu-id="6c21d-103">Szállítási mód módosítása a pénztárban</span><span class="sxs-lookup"><span data-stu-id="6c21d-103">Change mode of delivery in POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="6c21d-104">Ez a témakör azt mutatja be, hogyan lehet beállítani és használni a „szállítási mód módosítása” funkciót a pénztár (POS) környezetében.</span><span class="sxs-lookup"><span data-stu-id="6c21d-104">This topic describes how to set up and use the "change mode of delivery" functionality in your point of sale (POS) environment.</span></span> 

<span data-ttu-id="6c21d-105">A Dynamics 365 Commerce 10.0.10 és a későbbi verziókban **Szállítási mód módosítása** művelet (647) elérhető a hozzáadásra pénztári képernyő-elrendezéseihez.</span><span class="sxs-lookup"><span data-stu-id="6c21d-105">In Dynamics 365 Commerce versions 10.0.10 and later, the **Change mode of delivery** operation (647) is available to add to your POS screen layouts.</span></span>

<span data-ttu-id="6c21d-106">A szállítási mód módosítása funkció a pénztári tranzakcióban egy vagy több szállítmányhoz konfigurált értékesítési sor szállítási módjának módosítását teszi lehetővé.</span><span class="sxs-lookup"><span data-stu-id="6c21d-106">The change mode of delivery feature provides you with the option to change the mode of delivery for one or more shipment-configured sales lines on the POS transaction.</span></span> <span data-ttu-id="6c21d-107">A Commerce korábbi verzióiban végig kellett mennie a teljes **Össze szállítása** vagy **Kijelölt szállítása** konfigurációs folyamatokon ha a szállítási módot módosítani szerette volna egy olyan meglévő sorban, amely már be van állítva a szállításhoz.</span><span class="sxs-lookup"><span data-stu-id="6c21d-107">In previous versions of Commerce, you had to go through the full **Ship all** or **Ship selected** configuration flows if you wanted to change the mode of delivery on an existing line that was configured for shipment.</span></span> <span data-ttu-id="6c21d-108">Ez a folyamat időigényes volt, és a sorhoz tartozó szállítási dátumok véletlen módosítását eredményezhette.</span><span class="sxs-lookup"><span data-stu-id="6c21d-108">This process was time consuming and could result in accidental changes to the delivery origin or delivery dates for the line.</span></span> <span data-ttu-id="6c21d-109">Az új funkciók alternatív módszert biztosítanak a szállítási mód hatékony frissítésére az értékesítési sorokban.</span><span class="sxs-lookup"><span data-stu-id="6c21d-109">The new functionality provides an alternative method for efficiently updating the mode of delivery on these sales lines.</span></span>

<span data-ttu-id="6c21d-110">Ha további tájékoztatást szeretne arról, hogyan lehet hozzáadni egy műveletet a pénztári gombrács egy gombjához, tekintse meg a [Képernyő-elrendezések a pénztár (POS) számára](https://docs.microsoft.com/dynamics365/commerce/pos-screen-layouts) című cikket.</span><span class="sxs-lookup"><span data-stu-id="6c21d-110">For more information about how to add an operation to a button on your POS button grid, see [Screen layouts for the point of sale](https://docs.microsoft.com/dynamics365/commerce/pos-screen-layouts).</span></span>

<span data-ttu-id="6c21d-111">Ha ez a funkció a pénztárban be van állítva, és a **Szállításimód módosítása** lehetőséget választja, akkor egy lista jelenik meg, amely lehetővé teszi, hogy kiválassza azoknak a tranzakcióknak a sorait, amelyekhez a szállítási módot módosítani szeretné.</span><span class="sxs-lookup"><span data-stu-id="6c21d-111">After this feature is configured in POS, when you select **Change mode of delivery**, you will be presented with a list page that allows you to choose the lines of the transaction that you want to change the mode of delivery for.</span></span> <span data-ttu-id="6c21d-112">Egy vagy az összes is kiválaszthatja, illetve módosítás nélkül kiléphet.</span><span class="sxs-lookup"><span data-stu-id="6c21d-112">You can choose some or all of the lines, or exit without making any changes.</span></span> <span data-ttu-id="6c21d-113">A korábban szállítmányként konfigurált értékesítési sorok azok a sorok a listában, amelyeket módosíthat.</span><span class="sxs-lookup"><span data-stu-id="6c21d-113">The sales lines that were previously configured for shipment are the only lines in the list that you can change.</span></span> <span data-ttu-id="6c21d-114">Ha módosítani kívánja a felvételi vagy a kiszállítási sorokat akkor az **Összes szállítása** vagy a **Kijelöltek szállítása** műveleteket kell használnia.</span><span class="sxs-lookup"><span data-stu-id="6c21d-114">If you want to change a line designated for pickup or carryout to ship, you must use the **Ship all** or **Ship selected** operations.</span></span> <span data-ttu-id="6c21d-115">Ha viszont a szállítmányként kijelölt sort egy felvételi vagy kiszállításra szeretné módosítani, akkor az **Összes felvétele**, a **Kijelöltek felvétele**, **Összes kiszállítása** vagy **Kijelöltek kiszállítása** műveleteket kell választania.</span><span class="sxs-lookup"><span data-stu-id="6c21d-115">Conversely, if you want to change a line designated as a shipment to a pickup or carryout, you must use the  **Pickup all**, **Pickup selected**, **Carryout all**, or **Carryout selected** operations.</span></span>

<span data-ttu-id="6c21d-116">Miután kiválasztotta a módosítani kívánt sorokat, kattintson a **Szállítási mód módosítása** lehetőségre, hogy lehetősége legyen a szállítási mód beállításainak kiválasztására.</span><span class="sxs-lookup"><span data-stu-id="6c21d-116">After you select the lines that you want to change, click **Change mode of delivery** to be prompted to select the delivery mode options.</span></span> <span data-ttu-id="6c21d-117">Ha több sort választott ki módosításra, akkor a pénztár csak a kiválasztott termékre vonatkozóan megengedettnek konfigurált szállítási módokat jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="6c21d-117">If you selected multiple lines to change, POS will only display modes of delivery that have been configured as allowable for all of the selected products.</span></span> <span data-ttu-id="6c21d-118">A szállítási módok beállítható meghatározott termékek és szállítási címek támogatásához.</span><span class="sxs-lookup"><span data-stu-id="6c21d-118">Modes of delivery can be configured to support specific products and delivery addresses.</span></span> <span data-ttu-id="6c21d-119">Ha egy olyan szállítási mód van, amely elfogadható egy termék és cím kombináció esetében, de egy másik kiválasztott termék-és címkombináció esetében nem elfogadható, akkor a szállítási mód nem érhető el.</span><span class="sxs-lookup"><span data-stu-id="6c21d-119">If there is a mode of delivery that is acceptable for one product and address combination but is not acceptable for another selected product and address combination, the mode of delivery is not available.</span></span> <span data-ttu-id="6c21d-120">Előfordulhat, hogy egyenként kell kiválasztania a sorokat, és minden egyes sorhoz külön-külön kell módosítani a szállítási módot, ha ki szeretné választani egy olyan szállítási módot,amely egy másik termék által nem támogatott.</span><span class="sxs-lookup"><span data-stu-id="6c21d-120">You may need to select lines one by one and change the mode of delivery for each line separately if you want to select a mode of delivery for one product that is not supported by another product.</span></span>  

<span data-ttu-id="6c21d-121">Miután kiválasztotta az új szállítási módot, megjelenik a tranzakció lap.</span><span class="sxs-lookup"><span data-stu-id="6c21d-121">After you select the new mode of delivery, the transaction page is displayed.</span></span> <span data-ttu-id="6c21d-122">Az új szállítási mód beállításainak áttekintéséhez válassza ki a tranzakció listán a **Szállítás** fület.</span><span class="sxs-lookup"><span data-stu-id="6c21d-122">To review your new delivery mode selections, select the **Delivery** tab on the transaction list.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6c21d-123">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="6c21d-123">Additional resources</span></span>

[<span data-ttu-id="6c21d-124">Hívásközponti rendelések létrehozása</span><span class="sxs-lookup"><span data-stu-id="6c21d-124">Create call center orders</span></span>](tasks/create-call-center-orders.md)

[<span data-ttu-id="6c21d-125">Tranzakciós e-mailek testreszabása szállítási mód szerint</span><span class="sxs-lookup"><span data-stu-id="6c21d-125">Customize transactional emails by mode of delivery</span></span>](customize-email-delivery-mode.md)
