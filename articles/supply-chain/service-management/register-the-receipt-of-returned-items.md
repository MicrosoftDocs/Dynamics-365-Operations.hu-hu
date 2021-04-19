---
title: A visszaadott cikkek bevételezésének rögzítése
description: A visszaküldött cikkek beérkezésének nyilvántartásba vételéhez a Beérkezés áttekintése képernyőt vagy a Regisztráció képernyőt használhatja.
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WMSArrivalOverview, InventTransRegister
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 96532173c003621271f768dcdc64d67b6948ab6c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5836038"
---
# <a name="register-the-receipt-of-returned-items"></a><span data-ttu-id="47150-103">A visszaadott cikkek bevételezésének rögzítése</span><span class="sxs-lookup"><span data-stu-id="47150-103">Register the receipt of returned items</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="47150-104">Kétféle módszerrel lehet regisztrálni a visszajuttatott cikkek bevételezését.</span><span class="sxs-lookup"><span data-stu-id="47150-104">There are two methods for registering the receipt of returned items.</span></span> <span data-ttu-id="47150-105">Az első módszer a **Beérkezés áttekintése** képernyőt használó raktári bevételezési folyamat.</span><span class="sxs-lookup"><span data-stu-id="47150-105">The first method is a warehouse receiving process that uses the **Arrival overview** form.</span></span> <span data-ttu-id="47150-106">A második módszer a **Regisztráció** képernyőt használja.</span><span class="sxs-lookup"><span data-stu-id="47150-106">The second uses the **Registration** form.</span></span>

## <a name="register-the-receipt-of-returned-items-in-the-arrival-overview-form"></a><span data-ttu-id="47150-107">A visszáru bevételezésének regisztrálása a Beérkezés áttekintése képernyőn</span><span class="sxs-lookup"><span data-stu-id="47150-107">Register the receipt of returned items in the Arrival overview form</span></span>

<span data-ttu-id="47150-108">A visszáruk a **Beérkezés áttekintése** képernyő használatával azonosíthatóak a visszáru-jóváhagyási szám (Return Materials Authorization – RMA) alapján.</span><span class="sxs-lookup"><span data-stu-id="47150-108">You can use the **Arrival overview** form to identify a return shipment by its Return Material Authorization (RMA) number.</span></span> <span data-ttu-id="47150-109">Ha a **Beállítás** lapon meg van adva napló neve, és vannak olyan naplósorok, amelyek megfelelnek a **Beérkezés áttekintése** képernyőn kijelölt soroknak, az **Érkeztetés indítása**. elemre történő kattintáskor új naplófejléc jön létre.</span><span class="sxs-lookup"><span data-stu-id="47150-109">If a journal name is defined on the **Setup** tab, and journal lines that correspond to the lines selected on the **Arrival overview** form exist, a new journal header is created when you click **Start arrival**.</span></span>

1.  <span data-ttu-id="47150-110">Kattintson a következőkre: **Készletkezelés** \> **Rendszeres** \> **Beérkezés áttekintése**.</span><span class="sxs-lookup"><span data-stu-id="47150-110">Click **Inventory management** \> **Periodic** \> **Arrival overview**.</span></span>

2.  <span data-ttu-id="47150-111">A **Beállítás neve** mezőben válassza ki a **Visszárurendelés** lehetőséget, és kattintson a **Frissítés** elemre.</span><span class="sxs-lookup"><span data-stu-id="47150-111">In the **Setup name** field, select **Return order**, and then click **Update**.</span></span>
    

    > [!TIP]
    > <P><span data-ttu-id="47150-112">A <STRONG>Tartomány</STRONG> mezők segítségével tovább szűrheti a keresés eredményeit.</span><span class="sxs-lookup"><span data-stu-id="47150-112">You can use the <STRONG>Range</STRONG> fields to narrow the search results.</span></span> <span data-ttu-id="47150-113">Ha tudja a pontos visszáru-jóváhagyási számot, akkor azt is megadhatja az <STRONG>RMA-szám</STRONG> mezőben.</span><span class="sxs-lookup"><span data-stu-id="47150-113">You can type or select the RMA number in the <STRONG>RMA number</STRONG> field for an exact result.</span></span> <span data-ttu-id="47150-114">A megjelenített beérkezések körét korlátozó szűrősorozat megadásához és mentéséhez kattintson a <STRONG>Beállítás</STRONG> lapra. Szűréshez használhatóak többek között a típusok, a raktárak és területek.</span><span class="sxs-lookup"><span data-stu-id="47150-114">To define and save a set of filters that will restrict which incoming arrivals are displayed, click the <STRONG>Setup</STRONG> tab. The available filters include types, warehouses, and docks.</span></span></P>

    

    > [!WARNING]
    > <P><span data-ttu-id="47150-115">A visszárurendelések nem keverhetők más érkeztetési típusokkal a <STRONG>Beérkezés áttekintése</STRONG> képernyőn.</span><span class="sxs-lookup"><span data-stu-id="47150-115">Return orders cannot be mixed with other arrival types in the <STRONG>Arrival overview</STRONG> form.</span></span> <span data-ttu-id="47150-116">Így a hivatkozási alap minden esetben az értékesítési rendelés, a napló fejlécében azonban nem lesz megadva értékesítésirendelés-azonosító.</span><span class="sxs-lookup"><span data-stu-id="47150-116">Therefore, the reference will always be sales order, but no sales order ID will be specified on the journal header.</span></span></P>



3.  <span data-ttu-id="47150-117">A **Bevételezések** rácsban keresse meg azt a sort, amely megfelel a visszajuttatott cikknek, majd jelölje be a **Kijelölés beérkezésre** oszlopban található jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="47150-117">In the **Receipts** grid, locate the line that matches the item being returned, and then select the check box in the **Select for arrival** column.</span></span>

4.  <span data-ttu-id="47150-118">Ahhoz, hogy kizárjon a visszáru-bevételezésből bizonyos sorokat, például olyan cikkeket, amelyek az eredeti rendelésen szerepeltek, de a visszáru-szállítmányban nincsenek benne, akkor törölje a megfelelő sorok **Kijelölés beérkezésre** jelölőnégyzeteit a **Sorok** táblában, a képernyő alsó részén.</span><span class="sxs-lookup"><span data-stu-id="47150-118">To exclude certain lines from the return receipt, such as items from the original order that were not included in the return shipment, clear the associated **Select for arrival** check boxes in the **Lines** table in the lower part of the form.</span></span>

5.  <span data-ttu-id="47150-119">Cikkérkezési napló létrehozásához kattintson az **Érkeztetés indítása** gombra.</span><span class="sxs-lookup"><span data-stu-id="47150-119">Click the **Start arrival** button to create an arrival journal.</span></span>
    

    > [!NOTE]
    > <P><span data-ttu-id="47150-120">Egyszerre több visszáru-rendelést is kijelölhet, és ezeket egy menetben érkeztetheti.</span><span class="sxs-lookup"><span data-stu-id="47150-120">You can select multiple return orders and include them all in a single arrival process.</span></span> <span data-ttu-id="47150-121">A program minden visszáru-rendelési sort átmásol a cikkbeérkezési napló megfelelő sorába.</span><span class="sxs-lookup"><span data-stu-id="47150-121">Each return order line will be copied into a corresponding item arrival journal line.</span></span></P>

    

    > [!NOTE]
    > <P><span data-ttu-id="47150-122">A <STRONG>Cikk érkezése</STRONG> képernyő használatával manuálisan is létrehozhat cikkérkezési naplót.</span><span class="sxs-lookup"><span data-stu-id="47150-122">You can also manually create an arrival journal by using the <STRONG>Item arrival</STRONG> form.</span></span> 



6.  <span data-ttu-id="47150-123">Kattintson a következőkre **Készletgazdálkodás** \> **Naplók** \> **Cikkérkeztetés** \> **Cikkérkeztetés**.</span><span class="sxs-lookup"><span data-stu-id="47150-123">Click **Inventory management** \> **Journals** \> **Item arrival** \> **Item arrival**.</span></span>

7.  <span data-ttu-id="47150-124">A **Naplósorok, helyek** képernyő megnyitásához jelölje ki az imént létrehozott cikkérkezési naplót, és kattintson a **Sorok** elemre.</span><span class="sxs-lookup"><span data-stu-id="47150-124">Select the arrival journal that you just created and then click **Lines** to open the **Journal lines, locations** form.</span></span>

8.  <span data-ttu-id="47150-125">Szükség esetén módosítsa a számot az **Általános** lap **Mennyiség** mezőjében, majd rendeljen hozzá intézkedéskódot az **Intézkedéskód** mezőben.</span><span class="sxs-lookup"><span data-stu-id="47150-125">On the **General** tab, adjust the number in the **Quantity** field, if it is required, and then assign a disposition code in the **Disposition code** field.</span></span>
    
    <span data-ttu-id="47150-126">Másik megoldásként a **Karanténkezelés** jelölőnégyzet bejelölésével a visszaküldött cikkeket karanténutasítás keretében elvégzett, vizsgálati folyamatra utalhatja.</span><span class="sxs-lookup"><span data-stu-id="47150-126">Alternatively, you can select the **Quarantine management** check box to have the returned items sent through an inspection process in the context of a quarantine order.</span></span>
    

    > [!NOTE]
    > <P><span data-ttu-id="47150-127">Ha a visszaküldött cikkeket karanténba küldi, nem adhat meg intézkedési kódot.</span><span class="sxs-lookup"><span data-stu-id="47150-127">If you send the returned items through quarantine, you cannot specify a disposition code.</span></span></P>



9.  <span data-ttu-id="47150-128">Kattintson az **Ellenőrzés** gombra.</span><span class="sxs-lookup"><span data-stu-id="47150-128">Click the **Validate** button.</span></span>

10. <span data-ttu-id="47150-129">Ha az érvényesség-ellenőrzés nem jelez hibát, kattintson a **Feladás** gombra.</span><span class="sxs-lookup"><span data-stu-id="47150-129">If there are no errors in the validation process, click **Post**.</span></span>

## <a name="register-the-receipt-of-returned-items-in-the-registration-form"></a><span data-ttu-id="47150-130">A visszáru bevételezésének regisztrálása a Rögzítés képernyőn</span><span class="sxs-lookup"><span data-stu-id="47150-130">Register the receipt of returned items in the Registration form</span></span>

<span data-ttu-id="47150-131">A **Beérkezés áttekintése** képernyő helyett másik lehetőségként a **Regisztráció** képernyő is használható a visszaküldött cikkek beérkezésének nyilvántartásba vételére.</span><span class="sxs-lookup"><span data-stu-id="47150-131">As an alternative to using the **Arrival overview** form, you can use the **Registration** form to register the arrival of returned items.</span></span>

1.  <span data-ttu-id="47150-132">Kattintson a következőkre: **Értékesítés és marketing** \> **Közös** \> **Visszárurendelések** \> **MInden visszárurendelés**.</span><span class="sxs-lookup"><span data-stu-id="47150-132">Click **Sales and marketing** \> **Common** \> **Return orders** \> **All return orders**.</span></span> <span data-ttu-id="47150-133">Hozzon létre új visszárurendelést, vagy nyissa meg a listáról a visszárurendelést.</span><span class="sxs-lookup"><span data-stu-id="47150-133">Create a new return order or open the return order from the list.</span></span> <span data-ttu-id="47150-134">Válassza ki a visszárurendelés-sort a **Sorok** gyorslapon.</span><span class="sxs-lookup"><span data-stu-id="47150-134">On the **Lines** FastTab, select the return order line.</span></span> <span data-ttu-id="47150-135">Kattintson a **Sor frissítése** gombra, majd kattintson a **Regisztráció** elemre.</span><span class="sxs-lookup"><span data-stu-id="47150-135">Click **Update line**, and then click **Registration**.</span></span>

2.  <span data-ttu-id="47150-136">Rendeljen hozzá intézkedési kódot az **Intézkedéskód** mezőben, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="47150-136">Assign a disposition code in the **Disposition code** field, and then click **OK**.</span></span>
    

    > [!NOTE]
    > <P><span data-ttu-id="47150-137">A <STRONG>Regisztráció</STRONG> képernyő használata esetén a cikket nem lehet karanténutasítás formájában vizsgálatra küldeni.</span><span class="sxs-lookup"><span data-stu-id="47150-137">It is not possible to send the item for inspection as a quarantine order using the <STRONG>Registration</STRONG> form.</span></span></P>



3.  <span data-ttu-id="47150-138">Válasszon ki a rögzítendő tranzakciót a **Tranzakciók** rácsban.</span><span class="sxs-lookup"><span data-stu-id="47150-138">In the **Transactions** grid, select the transaction to be registered.</span></span>

4.  <span data-ttu-id="47150-139">A **Regisztrálás most** rácson kattintson **Hozzáadás** elemre.</span><span class="sxs-lookup"><span data-stu-id="47150-139">In the **Register now** grid, click **Add**.</span></span> <span data-ttu-id="47150-140">Addig ismételje az előző két lépést, amíg az összes visszaküldött cikk meg nem jelenik a **Regisztrálás most** rácsban.</span><span class="sxs-lookup"><span data-stu-id="47150-140">Repeat the previous two steps until all of the returned items appear in the **Register now** grid.</span></span>

5.  <span data-ttu-id="47150-141">Kattintson a **Összes feladása** elemre.</span><span class="sxs-lookup"><span data-stu-id="47150-141">Click **Post all**.</span></span>

## <a name="see-also"></a><span data-ttu-id="47150-142">Lásd még</span><span class="sxs-lookup"><span data-stu-id="47150-142">See also</span></span>

<span data-ttu-id="47150-143">[Beérkezés áttekintése (képernyő)](https://technet.microsoft.com/library/hh227654\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="47150-143">[Arrival overview (form)](https://technet.microsoft.com/library/hh227654\(v=ax.60\))</span></span>

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]