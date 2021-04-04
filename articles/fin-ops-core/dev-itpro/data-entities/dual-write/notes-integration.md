---
title: Megjegyzésintegráció
description: Ez a témakör a megjegyzésadatok integrációját ismerteti a kettős írásban.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 02/22/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2021-02-22
ms.openlocfilehash: 221be52b4d66aaa47f9a1919d5d0b9f8459b7ff9
ms.sourcegitcommit: db9b35ce6968cad8874b3c13d4c02d84e2617c8b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/11/2021
ms.locfileid: "5577606"
---
# <a name="note-integration"></a><span data-ttu-id="3b0c1-103">Megjegyzésintegráció</span><span class="sxs-lookup"><span data-stu-id="3b0c1-103">Note integration</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="3b0c1-104">Az üzleti folyamatok során a Microsoft Dynamics 365 felhasználói gyakran gyűjtenek információkat a vevőikről.</span><span class="sxs-lookup"><span data-stu-id="3b0c1-104">During business processes, Microsoft Dynamics 365 users often gather information about their customers.</span></span> <span data-ttu-id="3b0c1-105">Ezt az információt tevékenységekként és megjegyzésekként rögzíti a rendszer.</span><span class="sxs-lookup"><span data-stu-id="3b0c1-105">This information is recorded as activities and notes.</span></span> <span data-ttu-id="3b0c1-106">Ez a témakör a megjegyzésadatok integrációját ismerteti a kettős írásban.</span><span class="sxs-lookup"><span data-stu-id="3b0c1-106">This topic describes the integration of note data in dual-write.</span></span>

<span data-ttu-id="3b0c1-107">A vevői adatok a következőképpen osztályozhatók:</span><span class="sxs-lookup"><span data-stu-id="3b0c1-107">Customer information can be classified in the following ways:</span></span>

+ <span data-ttu-id="3b0c1-108">**Egy Dynamics 365-felhasználó által a vevő nevében kezelhető információk** – például a Contoso (Dynamics 365-ös felhasználó) játékbemutatót vezet.</span><span class="sxs-lookup"><span data-stu-id="3b0c1-108">**Actionable information that a Dynamics 365 user handles on behalf of a customer** – For example, Contoso (a Dynamics 365 user) is conducting a game show.</span></span> <span data-ttu-id="3b0c1-109">A Contoso egyik ügyfele (egy vevő) részt szeretne venni a játékbemutatón.</span><span class="sxs-lookup"><span data-stu-id="3b0c1-109">One of Contoso's customers (a customer) wants to attend the game show.</span></span> <span data-ttu-id="3b0c1-110">A vevő megkéri a Contoso egyik alkalmazottját, hogy foglaljon helyet neki a bemutatón.</span><span class="sxs-lookup"><span data-stu-id="3b0c1-110">The customer asks a Contoso employee to book a slot in the game show for them.</span></span> <span data-ttu-id="3b0c1-111">A foglalás a Contoso rendezvény résztvevőinek naptárában történik.</span><span class="sxs-lookup"><span data-stu-id="3b0c1-111">The booking occurs in Contoso's event attendee's calendar.</span></span>
+ <span data-ttu-id="3b0c1-112">**A Dynamics 365 felhasználója esetében kezelhető adatok** – például egy olyan vevő, aki egy Felületi egységet vásárol, különleges utasításokat ad meg, amelyek azt jelzik, hogy az eszközt ajándékcsomagolással kell ellátni a szállítás előtt.</span><span class="sxs-lookup"><span data-stu-id="3b0c1-112">**Actionable information for a Dynamics 365 user** – For example, a customer who is purchasing a Surface unit enters special instructions that indicate that the device should be gift wrapped before delivery.</span></span> <span data-ttu-id="3b0c1-113">Ezek az utasítások olyan kezelhető információkat tartalmaznak, amelyet a csomagolásért felelős Contoso alkalmazottnak kell kezelnie.</span><span class="sxs-lookup"><span data-stu-id="3b0c1-113">These instructions are actionable information that should be handled by the Contoso employee who is responsible for packaging.</span></span>
+ <span data-ttu-id="3b0c1-114">**Nem műveletre használható adatok** – például egy vevő felkeresi a Contoso üzletét, és az üzlet egyik munkatársával folytatott beszélgetés során kifejezi érdeklődését a *Halo* játék és különböző videojáték-kiegészítők iránt.</span><span class="sxs-lookup"><span data-stu-id="3b0c1-114">**Non-actionable information** – For example, a customer visits the Contoso store and, during their conversation with a store associate, expresses interest in *Halo* games and gaming accessories.</span></span> <span data-ttu-id="3b0c1-115">Az üzlet munkatársa feljegyzi ezt az információt.</span><span class="sxs-lookup"><span data-stu-id="3b0c1-115">The store associate makes a note of this information.</span></span> <span data-ttu-id="3b0c1-116">A termékajánlási motor ezt arra használja, hogy ajánlatokat jelenítsen meg a vevőnek.</span><span class="sxs-lookup"><span data-stu-id="3b0c1-116">The product recommendations engine then uses it to make recommendations to the customer.</span></span>

<span data-ttu-id="3b0c1-117">Általános szabály, hogy a használható adatok *tevékenységekként* vannak rögzítve a Finance and Operations alkalmazásokban és az ügyfélkapcsolati alkalmazásokban.</span><span class="sxs-lookup"><span data-stu-id="3b0c1-117">In general, actionable information is captured as *activities* in Finance and Operations apps and customer engagement apps.</span></span> <span data-ttu-id="3b0c1-118">A nem használható adatok *megjegyzésekként* vannak rögzítve a Finance and Operations alkalmazásokban és *jegyzetekként* az ügyfélkapcsolati alkalmazásokban.</span><span class="sxs-lookup"><span data-stu-id="3b0c1-118">Non-actionable information is captured as *notes* in Finance and Operations apps, and as *annotations* in customer engagement apps.</span></span>

> [!TIP]
> <span data-ttu-id="3b0c1-119">Bár a megjegyzések nem használható adatok, az alkalmazások nem akadályozzák meg abban, hogy ezeket az adatokat kezelhető információkként tárolj és kezelje, ha ezt szeretné.</span><span class="sxs-lookup"><span data-stu-id="3b0c1-119">Although notes are intended for non-actionable information, the apps won't prevent you from using them to store and handle actionable information if you want to use them in that way.</span></span>

<span data-ttu-id="3b0c1-120">A Microsoft jelenleg a megjegyzésintegrációs funkció kiadásán dolgozik.</span><span class="sxs-lookup"><span data-stu-id="3b0c1-120">Microsoft is currently releasing functionality for note integration.</span></span> <span data-ttu-id="3b0c1-121">(A tevékenységintegrációs funkciók kiadása később következik.) A megjegyzésintegráció a vevőkhöz, szállítókhoz, értékesítési rendelésekhez és beszerzési rendelésekhez használható.</span><span class="sxs-lookup"><span data-stu-id="3b0c1-121">(Functionality for activity integration will be released later.) Note integration is available for customers, vendors, sales orders, and purchase orders.</span></span>

## <a name="create-a-note-in-a-customer-engagement-app"></a><span data-ttu-id="3b0c1-122">Megjegyzés létrehozása egy ügyfélkapcsolati alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="3b0c1-122">Create a note in a customer engagement app</span></span>

<span data-ttu-id="3b0c1-123">Ha megjegyzést szeretne létrehozni egy ügyfélkapcsolati alkalmazásban, majd szinkronizálni azt a Finance and Operations alkalmazással, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="3b0c1-123">To create a note in a customer engagement app and then sync it to a Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="3b0c1-124">Nyissa meg egy vevő számlarekordját az ügyfélkapcsolati alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="3b0c1-124">In the customer engagement app, open the account record for a customer.</span></span>
2. <span data-ttu-id="3b0c1-125">Az **Idősor** ablaktáblán válassza a pluszjelet (**+**), majd a **Megjegyzés** gombra kattintva hozzon létre egy megjegyzést.</span><span class="sxs-lookup"><span data-stu-id="3b0c1-125">In the **Timeline** pane, select the plus sign (**+**), and then select **Note** to create a note.</span></span>

    ![Megjegyzés létrehozása az ügyfélkapcsolati alkalmazásban](media/notes-ce-1.png)

3. <span data-ttu-id="3b0c1-127">Írja be a kívánt címet és leírást, majd válassza a **Megjegyzés hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3b0c1-127">Enter a title and description, and then select **Add note**.</span></span>

    ![A kívánt cím és leírás megadása](media/notes-ce-2.png)

    <span data-ttu-id="3b0c1-129">Az új megjegyzés hozzáadódik a vevői idősorhoz.</span><span class="sxs-lookup"><span data-stu-id="3b0c1-129">The new note is added to the customer timeline.</span></span>

    ![Új megjegyzés a vevői idősoron](media/notes-ce-3.png)

4. <span data-ttu-id="3b0c1-131">Jelentkezzen be a Finance and Operations alkalmazásba, és nyissa meg ugyanazt a vevői rekordot.</span><span class="sxs-lookup"><span data-stu-id="3b0c1-131">Sign in to the Finance and Operations app, and open the same customer record.</span></span> <span data-ttu-id="3b0c1-132">Láthatja, hogy jobb felső sarokban látható **Mellékletek** gomb (gemkapocs szimbólum) jelzi, hogy a rekordhoz melléklet van csatolva.</span><span class="sxs-lookup"><span data-stu-id="3b0c1-132">Notice that the **Attachments** button (paperclip symbol) in the upper-right corner indicates that the record has an attachment.</span></span>

    ![Értesítés mellékletről](media/notes-ce-4.png)

5. <span data-ttu-id="3b0c1-134">Kattintson a **Mellékletek** gombra a **Mellékletek** oldal megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="3b0c1-134">Select the **Attachments** button to open the **Attachments** page.</span></span> <span data-ttu-id="3b0c1-135">Az ügyfélkapcsolati alkalmazásban meg kell találnia a létrehozott megjegyzést.</span><span class="sxs-lookup"><span data-stu-id="3b0c1-135">You should find the note that you created in the customer engagement app.</span></span>

    ![Megjegyzés az ügyfélkapcsolati alkalmazásból](media/notes-ce-5.png)

<span data-ttu-id="3b0c1-137">A megjegyzés frissítései oda-vissza szinkronizálódnak az alkalmazás és a Finance and Operations alkalmazás és az ügyfélkapcsolati alkalmazás között.</span><span class="sxs-lookup"><span data-stu-id="3b0c1-137">Any updates to the note are synced back and forth between the Finance and Operations app and the customer engagement app.</span></span>

## <a name="create-a-note-in-a-finance-and-operations-app"></a><span data-ttu-id="3b0c1-138">Megjegyzés létrehozása egy Finance and Operations alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="3b0c1-138">Create a note in a Finance and Operations app</span></span>

<span data-ttu-id="3b0c1-139">Létrehozhat egy megjegyzést egy Finance and Operations alkalmazásban, majd szinkronizálhatja az ügyfélkapcsolati alkalmazással.</span><span class="sxs-lookup"><span data-stu-id="3b0c1-139">You can also create a note in a Finance and Operations app, and it will be synced to a customer engagement app.</span></span>

<span data-ttu-id="3b0c1-140">Ha megjegyzést szeretne létrehozni egy Finance and Operations alkalmazásban, majd szinkronizálni azt egy ügyfélkapcsolati alkalmazással, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="3b0c1-140">To create a note in a Finance and Operations app and then sync it to a customer engagement app, follow these steps.</span></span>

1. <span data-ttu-id="3b0c1-141">A Finance and Operations alkalmazásban a **Mellékletek** oldalon válassza az **Új** \> **Megjegyzés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3b0c1-141">In the Finance and Operations app, on the **Attachments** page, select **New** \> **Note**.</span></span>

    ![Megjegyzés létrehozása a Finance and Operations alkalmazásban](media/notes-fo-1.png)

2. <span data-ttu-id="3b0c1-143">Adjon meg egy címet és egy rövid utasításkészletet, majd válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3b0c1-143">Enter a title and a brief set of instructions, and then select **Save**.</span></span>

    ![A kívánt cím és az utasítások megadása](media/notes-fo-2.png)

3. <span data-ttu-id="3b0c1-145">Frissítse a rekordot az ügyfélkapcsolati alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="3b0c1-145">In the customer engagement app, update the record.</span></span> <span data-ttu-id="3b0c1-146">Az új megjegyzésnek az idősorban kell lennie.</span><span class="sxs-lookup"><span data-stu-id="3b0c1-146">You should find the new note on the timeline.</span></span>

    ![Új megjegyzés az ügyfélkapcsolati alkalmazás idősorán](media/notes-fo-3.png)

<span data-ttu-id="3b0c1-148">A megjegyzéseket belsőként és külsőként is osztályozhatja.</span><span class="sxs-lookup"><span data-stu-id="3b0c1-148">You can classify a note as either internal or external.</span></span>

- <span data-ttu-id="3b0c1-149">Nyissa meg a megjegyzést a Finance and Operations alkalmazásban a **Mellékletek** oldalon, majd a **Korlátozás** mezőben válassza a **Belső** vagy a **Külső** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3b0c1-149">In the Finance and Operations app, on the **Attachments** page, open the note, and then, in the **Restriction** field, select **Internal** or **External**.</span></span>

    ![Korlátozás mező](media/notes-fo-4.png)

<span data-ttu-id="3b0c1-151">URL-címet is létrehozhat</span><span class="sxs-lookup"><span data-stu-id="3b0c1-151">You can also create a URL.</span></span>

1. <span data-ttu-id="3b0c1-152">A Finance and Operations alkalmazásban a **Mellékletek** oldalon válassza az **Új** \> **URL** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3b0c1-152">In the Finance and Operations app, on the **Attachments** page, select **New** \> **URL**.</span></span>
2. <span data-ttu-id="3b0c1-153">Adja meg a címet és az URL-t.</span><span class="sxs-lookup"><span data-stu-id="3b0c1-153">Enter a title and the URL.</span></span>
3. <span data-ttu-id="3b0c1-154">A **Korlátozás** mezőben válassza a **Belső** vagy a **Külső** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3b0c1-154">In the **Restriction** field, select **Internal** or **External**.</span></span>

    ![URL létrehozása a Finance and Operations alkalmazásban](media/notes-fo-5.png)

4. <span data-ttu-id="3b0c1-156">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3b0c1-156">Select **Save**.</span></span>

    <span data-ttu-id="3b0c1-157">Mivel az ügyfélkapcsolati alkalmazásoknak nincs URL-típusa, az URL-cím megjegyzésként kettős írással van integrálva.</span><span class="sxs-lookup"><span data-stu-id="3b0c1-157">Because customer engagement apps don't have a URL type, the URL is integrated with dual-write as a note.</span></span>

    ![URL megjegyzésként jelenik meg az ügyfélkapcsolati alkalmazásban](media/notes-ce-6.png)

> [!NOTE]
> <span data-ttu-id="3b0c1-159">A fájlmellékletek nem támogatottak.</span><span class="sxs-lookup"><span data-stu-id="3b0c1-159">File attachments aren't supported.</span></span>

## <a name="templates"></a><span data-ttu-id="3b0c1-160">Sablonok</span><span class="sxs-lookup"><span data-stu-id="3b0c1-160">Templates</span></span>

<span data-ttu-id="3b0c1-161">A megjegyzésintegráció tartalmazza azokat a táblaleképezéseket, amelyek – az alábbi táblázatban látható módon – együttműködnek az adatok interakciója során.</span><span class="sxs-lookup"><span data-stu-id="3b0c1-161">Note integration includes a collection of table maps that work together during data interaction, as shown in the following table.</span></span>

| <span data-ttu-id="3b0c1-162">Finance and Operations alkalmazás</span><span class="sxs-lookup"><span data-stu-id="3b0c1-162">Finance and Operations app</span></span> | <span data-ttu-id="3b0c1-163">Customer Engagement alkalmazás</span><span class="sxs-lookup"><span data-stu-id="3b0c1-163">Customer engagement app</span></span> | <span data-ttu-id="3b0c1-164">Leírás</span><span class="sxs-lookup"><span data-stu-id="3b0c1-164">Description</span></span> |
|----------------------------|-------------------------|-------------|
| [<span data-ttu-id="3b0c1-165">Vevői mellékletek</span><span class="sxs-lookup"><span data-stu-id="3b0c1-165">Customer Attachments</span></span>](mapping-reference.md#230) | <span data-ttu-id="3b0c1-166">Jegyzetek</span><span class="sxs-lookup"><span data-stu-id="3b0c1-166">Annotations</span></span> | <span data-ttu-id="3b0c1-167">Azon vállalatok, amelyek egyszerű szöveges és URL-címekkel rögzítik a vevőspecifikus információkat (szervezetek és személyek számára is).</span><span class="sxs-lookup"><span data-stu-id="3b0c1-167">Businesses that use plain text and URLs to capture customer-specific information (for both organizations and persons).</span></span> |
| [<span data-ttu-id="3b0c1-168">Szállítóidokumentum-mellékletek</span><span class="sxs-lookup"><span data-stu-id="3b0c1-168">Vendor document attachments</span></span>](mapping-reference.md#231) | <span data-ttu-id="3b0c1-169">Jegyzetek</span><span class="sxs-lookup"><span data-stu-id="3b0c1-169">Annotations</span></span> | <span data-ttu-id="3b0c1-170">Azon vállalatok, amelyek egyszerű szöveges és URL-címekkel rögzítik a szállítóspecifikus információkat (szervezetek és személyek számára is).</span><span class="sxs-lookup"><span data-stu-id="3b0c1-170">Businesses that use plain text and URLs to capture vendor-specific information (for both organizations and persons).</span></span> |
| [<span data-ttu-id="3b0c1-171">Értékesítési rendelési fejléc bizonylatmellékletei</span><span class="sxs-lookup"><span data-stu-id="3b0c1-171">Sales order header document attachments</span></span>](mapping-reference.md#229) | <span data-ttu-id="3b0c1-172">Jegyzetek</span><span class="sxs-lookup"><span data-stu-id="3b0c1-172">Annotations</span></span> | <span data-ttu-id="3b0c1-173">Azok a vállalatok, amelyek egyszerű szöveges és URL-címekkel rögzítik az értékesítési rendelésekre jellemző adatokat.</span><span class="sxs-lookup"><span data-stu-id="3b0c1-173">Businesses that use plain text and URLs to capture sales order–specific information.</span></span> |
| [<span data-ttu-id="3b0c1-174">Beszerzési rendelési fejléc bizonylatmellékletei</span><span class="sxs-lookup"><span data-stu-id="3b0c1-174">Purchase order header document attachments</span></span>](mapping-reference.md#232) | <span data-ttu-id="3b0c1-175">Jegyzetek</span><span class="sxs-lookup"><span data-stu-id="3b0c1-175">Annotations</span></span> | <span data-ttu-id="3b0c1-176">Azok a vállalatok, amelyek egyszerű szöveges és URL-címekkel rögzítik a beszerzési rendelésekre jellemző adatokat.</span><span class="sxs-lookup"><span data-stu-id="3b0c1-176">Businesses that use plain text and URLs to capture purchase order–specific information.</span></span> |

<span data-ttu-id="3b0c1-177">További tájékoztatás: [Kettős írású leképezési hivatkozás](mapping-reference.md).</span><span class="sxs-lookup"><span data-stu-id="3b0c1-177">For more information, see [Dual-write mapping reference](mapping-reference.md).</span></span>