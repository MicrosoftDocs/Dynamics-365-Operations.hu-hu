---
title: "Nyugta minták és nyomtatás"
description: "Ez a cikk ismerteti, hogyan módosíthatja a képernyőelrendezések létrehozását, hogy irányíthassa a nyugták, számlák és egyéb dokumentumok nyomtatását. A Microsoft Dynamics 365 for Retail képernyőelrendezés-tervezője lehetővé teszi különféle képernyőelrendezések egyszerű grafikus létrehozását és módosítását."
author: rubencdelgado
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 57841
ms.assetid: e530dd8e-95e2-4021-90bd-ce1235f9e250
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: c95215af7004606bb3e000f68c56ea5c69bb9582
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="receipt-templates-and-printing"></a><span data-ttu-id="d0845-104">Nyugta minták és nyomtatás</span><span class="sxs-lookup"><span data-stu-id="d0845-104">Receipt templates and printing</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="d0845-105">Ez a cikk ismerteti, hogyan módosíthatja a képernyőelrendezések létrehozását, hogy irányíthassa a nyugták, számlák és egyéb dokumentumok nyomtatását.</span><span class="sxs-lookup"><span data-stu-id="d0845-105">This article describes how to modify form layouts to control how receipts, invoices, and other documents are printed.</span></span> <span data-ttu-id="d0845-106">A Microsoft Dynamics 365 for Retail képernyőelrendezés-tervezője lehetővé teszi különféle képernyőelrendezések egyszerű grafikus létrehozását és módosítását.</span><span class="sxs-lookup"><span data-stu-id="d0845-106">Microsoft Dynamics 365 for Retail includes a form layout designer that you can use to easily create and modify various kinds of form layouts.</span></span>

<span data-ttu-id="d0845-107">**Fontos:** Ahhoz, hogy a Retail Modern POS és a Cloud POS használatával nyugtákat és egyéb bizonylatokat tudjon nyomtatni, be kell állítania a képernyő-elrendezéseket és a nyugtaprofilokat.</span><span class="sxs-lookup"><span data-stu-id="d0845-107">**Important:** You must set up form layouts and receipt profiles to print receipts and other documents from Retail Modern POS and Cloud POS.</span></span> <span data-ttu-id="d0845-108">A nyugtaprofilba több képernyőelrendezést is felvehet.</span><span class="sxs-lookup"><span data-stu-id="d0845-108">You can include multiple form layouts in a receipt profile.</span></span> <span data-ttu-id="d0845-109">Ezután hozzárendelheti a nyugta profilt egy nyomtatóhoz a hardver profil módosításával.</span><span class="sxs-lookup"><span data-stu-id="d0845-109">You can then assign the receipt profile to a printer by modifying a hardware profile.</span></span>

## <a name="set-up-a-receipt-format"></a><span data-ttu-id="d0845-110">Nyugtaformátum beállítása</span><span class="sxs-lookup"><span data-stu-id="d0845-110">Set up a receipt format</span></span>
1.  <span data-ttu-id="d0845-111">Kattintson a **Kiskereskedelem** &gt; **Csatorna beállítása** &gt; **Pénztár beállítása** &gt; **Pénztár** &gt; **Nyugtaformátumok** gombra.</span><span class="sxs-lookup"><span data-stu-id="d0845-111">Click **Retail** &gt; **Channel setup** &gt; **POS setup** &gt; **POS** &gt; **Receipt formats**.</span></span>
2.  <span data-ttu-id="d0845-112">A **Nyugta formátum** oldalon, kattintson az **Új** gombra, új űrlap elrendezés létrehozásához, vagy egy már létező kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="d0845-112">On the **Receipt format** page, click **New** to create a new form layout, or select an existing form layout.</span></span>
3.  <span data-ttu-id="d0845-113">Gépelje be a **Nyugta formátum** mezőbe egy űrlap elrendezés azonosítóját, majd válassza ki az ehhez az elrendezéshez használt nyugta típust.</span><span class="sxs-lookup"><span data-stu-id="d0845-113">In the **Receipt format** field, enter an identifier for the form layout, and then select the type of receipt that this layout is used for.</span></span> <span data-ttu-id="d0845-114">A nyugtához leírást és rövid nevet is megadhat a **Cím** mező segítségével.</span><span class="sxs-lookup"><span data-stu-id="d0845-114">You can also enter a description and a short name for the receipt in the **Title** field.</span></span>
4.  <span data-ttu-id="d0845-115">Az **Általános** gyorslapon, válasszon egy nyomtatási viselkedését meghatározó lehetőséget:</span><span class="sxs-lookup"><span data-stu-id="d0845-115">On the **General** FastTab, select an option to define the print behavior:</span></span>
    -   <span data-ttu-id="d0845-116">**Mindig nyomtasson** – a program automatikusan kinyomtatja a nyugtát.</span><span class="sxs-lookup"><span data-stu-id="d0845-116">**Always print** – The receipt is printed automatically, as appropriate.</span></span>
    -   <span data-ttu-id="d0845-117">**Ne nyomtasson** – Nem nyomtatja ki a nyugtát.</span><span class="sxs-lookup"><span data-stu-id="d0845-117">**Do not print** – The receipt isn't printed.</span></span>
    -   <span data-ttu-id="d0845-118">**Felhasználó megkérdezése** – A felhasználónak engedélyeznie kell a nyugta nyomtatását.</span><span class="sxs-lookup"><span data-stu-id="d0845-118">**Prompt user** – The user is prompted to print the receipt.</span></span>
    -   <span data-ttu-id="d0845-119">**Szükség szerint** – Ez a beállítás csak ajándéknyugták esetén használatos.</span><span class="sxs-lookup"><span data-stu-id="d0845-119">**As required** – This option is used only for gift receipts.</span></span> <span data-ttu-id="d0845-120">Ha ez a beállítás be van jelölve, a felhasználó ajándéknyugtát nyomtathat a **Változtatás** oldalon.</span><span class="sxs-lookup"><span data-stu-id="d0845-120">When this option is selected, the user can print a gift receipt from the **Change** page, if a gift receipt is required.</span></span>

## <a name="design-a-receipt-format"></a><span data-ttu-id="d0845-121">Nyugtaformátum tervezése</span><span class="sxs-lookup"><span data-stu-id="d0845-121">Design a receipt format</span></span>
<span data-ttu-id="d0845-122">A Képernyőelrendezés-tervező segítségével grafikusan hozhatja létre a képernyő-dokumentum elrendezését.</span><span class="sxs-lookup"><span data-stu-id="d0845-122">Use the form layout designer to graphically create the layout of the form document.</span></span> <span data-ttu-id="d0845-123">A **Nyugtaformátum tervező** lap három részből áll: **Fejléc**, **Sorok**, és **Lábléc**.</span><span class="sxs-lookup"><span data-stu-id="d0845-123">The **Receipt format designer** page has three sections: **Header**, **Lines**, and **Footer**.</span></span> <span data-ttu-id="d0845-124">Bizonyos típusú űrlap-elrendezések mindhárom szakaszból használnak fel elemeket, míg más típusok csak egy vagy két szakasz elemeit hasznosítják.</span><span class="sxs-lookup"><span data-stu-id="d0845-124">Some types of form layouts use elements from all three sections, whereas other types use elements from only one or two sections.</span></span> <span data-ttu-id="d0845-125">Az egyes részeknél használható elemek megtekintéséhez kattintson a megfelelő gombra a képernyő bal oldalán található navigációs ablakban.</span><span class="sxs-lookup"><span data-stu-id="d0845-125">To view the elements that are available for each section, click the appropriate button in the navigation pane on the left side of the page.</span></span>

1.  <span data-ttu-id="d0845-126">Kattintson a **Kiskereskedelem** &gt; **Csatorna beállítása** &gt; **Pénztár beállítása** &gt; **Pénztár** &gt; **Nyugtaformátumok** gombra.</span><span class="sxs-lookup"><span data-stu-id="d0845-126">Click **Retail** &gt; **Channel setup** &gt; **POS setup** &gt; **POS** &gt; **Receipt formats**.</span></span>
2.  <span data-ttu-id="d0845-127">A **Nyugtaformátum** oldalon, válasszon egy űrlap elrendezést, majd kattintson **Tervező** opcióra.</span><span class="sxs-lookup"><span data-stu-id="d0845-127">On the **Receipt format** page, select a form layout, and then click **Designer**.</span></span>
3.  <span data-ttu-id="d0845-128">Kattintson a **Futtatás** gombra, hogy elindítsa a Kiskereskedelem tervező telepítését.</span><span class="sxs-lookup"><span data-stu-id="d0845-128">Click **Run** to start to install the Retail designer host.</span></span>
4.  <span data-ttu-id="d0845-129">Az Internet Explorer ablakának alján található Értesítés sávon kattintson a **Megnyitás** gombra, hogy elindítsa az egy-kattintás tervező telepítését.</span><span class="sxs-lookup"><span data-stu-id="d0845-129">On the Notification bar that appears at the bottom of the Internet Explorer window, click **Open** to start to install the one-click designer.</span></span> <span data-ttu-id="d0845-130">(Más böngészőkben előfordulhat, hogy eltérő helyen jelenik meg az Értesítő sáv.) Folyamatjelző mutatja a telepítés folyamat haladását.</span><span class="sxs-lookup"><span data-stu-id="d0845-130">(The Notification bar might appear in a different location in other browsers.) The progress indicator shows the progress of the installation process.</span></span>
5.  <span data-ttu-id="d0845-131">A telepítés befejezése után adja meg a Dynamics 365 for Retail-felhasználónevét és jelszavát, majd kattintson a **Bejelentkezés** gombra a tervező indításához.</span><span class="sxs-lookup"><span data-stu-id="d0845-131">After the installation is completed, enter your Dynamics 365 for Retail user name and password, and then click **Sign in** to start the designer.</span></span>
6.  <span data-ttu-id="d0845-132">Miután a belépő adatai hitelesítésre kerültek és a tervező elindul, megkezdheti a nyugta formátum tervezését vagy a már meglevő módosítását.</span><span class="sxs-lookup"><span data-stu-id="d0845-132">After your credentials are validated and the designer starts, you can start to design the receipt format or modify an existing format.</span></span>
7.  <span data-ttu-id="d0845-133">Az űrlap elemeinek létrehozásához válassza ki a **Fejléc**, a **Sorok** vagy a **Lábléc** szekciót, majd húzza a szekcióban található egyik elemet a munkaterületre.</span><span class="sxs-lookup"><span data-stu-id="d0845-133">To create the elements of the form, select the **Header**, **Lines**, or **Footer** section, and then drag an element from that section to the workspace.</span></span> <span data-ttu-id="d0845-134">A legtöbb elem változókat tartalmaz, amelyekbe a program automatikusan beírja az adatbázis adatait.</span><span class="sxs-lookup"><span data-stu-id="d0845-134">Most elements contain variables that are automatically populated with data from the database.</span></span> <span data-ttu-id="d0845-135">Más elemek – például a **Szöveg** elem – lehetővé teszik egyéni szöveg nyomtatását a nyugtára.</span><span class="sxs-lookup"><span data-stu-id="d0845-135">Other elements, such as **Text**, let you print custom text on the receipt.</span></span> <span data-ttu-id="d0845-136">**Megjegyzés:** A terület jobb alsó sarkában lévő szám módosításával meghatározhatja, hogy az adott szekció hány sorra terjedjen ki.</span><span class="sxs-lookup"><span data-stu-id="d0845-136">**Note:** You can specify how many lines each section spans by adjusting the number in the lower-right corner of that section.</span></span> <span data-ttu-id="d0845-137">Ha egyszerűbbé szeretné tenni a szekció módosítását, akkor növelje meg a szakasz méretét a szekció alján látható méretező sáv segítségével.</span><span class="sxs-lookup"><span data-stu-id="d0845-137">To make it easier to modify a section, increase its height by dragging the sizing bar at the bottom of the section.</span></span> <span data-ttu-id="d0845-138">A szekció munkaterületen látható magassága nem befolyásolja a sorok számát a tényleges nyugtán.</span><span class="sxs-lookup"><span data-stu-id="d0845-138">The height of the section on the workspace doesn't affect the number of lines on the actual receipt.</span></span>
8.  <span data-ttu-id="d0845-139">Miután az elemet a munkaterületre húzta, adja meg a részre vonatkozó tulajdonságokat az oldal alján található **Objektumadatok** ablaktáblában.</span><span class="sxs-lookup"><span data-stu-id="d0845-139">After you drag an element to the workspace, set the properties for the part in the **Object information** pane at the bottom of the page.</span></span> <span data-ttu-id="d0845-140">Adjon meg egyet vagy többet a következő beállítások közük:</span><span class="sxs-lookup"><span data-stu-id="d0845-140">Enter one or more of the following settings:</span></span>
    -   <span data-ttu-id="d0845-141">**Igazítás** – A mező igazításának beállítása **Balra** vagy **Jobbra**.</span><span class="sxs-lookup"><span data-stu-id="d0845-141">**Align** – Set the alignment of the field to either **Left** or **Right**.</span></span>
    -   <span data-ttu-id="d0845-142">**Kitöltő karakter** – Az üres hely karakter megadása.</span><span class="sxs-lookup"><span data-stu-id="d0845-142">**Fill char** – Specify the white space character.</span></span> <span data-ttu-id="d0845-143">Alapértelmezés szerint a program üres szóközt használ, de bármilyen karaktert meg lehet adni.</span><span class="sxs-lookup"><span data-stu-id="d0845-143">By default, an empty space is used, but you can enter any character.</span></span>
    -   <span data-ttu-id="d0845-144">**Előtag** – A mező elején megjelenítendő értéket ide írhatja be.</span><span class="sxs-lookup"><span data-stu-id="d0845-144">**Prefix** – Enter the value that appears at the beginning of the field.</span></span> <span data-ttu-id="d0845-145">Ez a beállítás csak az elrendezés **Sorok** szekciójára vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="d0845-145">This setting applies only to the **Lines** section of the layout.</span></span>
    -   <span data-ttu-id="d0845-146">**Karakterek** – Adja meg a mezőbe írható karakterek maximum számát.</span><span class="sxs-lookup"><span data-stu-id="d0845-146">**Characters** – Specify the maximum number of characters that the field can contain if the element contains a variable.</span></span> <span data-ttu-id="d0845-147">Ha a mezőben a szöveg hosszabb, mint a megadott karakterek száma, a szöveg csonkul, hogy elférjen a mezőben.</span><span class="sxs-lookup"><span data-stu-id="d0845-147">If the text in the field is longer than the number of character that you specify, the text is truncated to fit the field.</span></span>
    -   <span data-ttu-id="d0845-148">**Változó** – Ez a jelölőnégyzet automatikusan be van jelölve, ha az elem tartalmaz változót és nem testre szabható.</span><span class="sxs-lookup"><span data-stu-id="d0845-148">**Variable** – This check box is selected automatically if the element contains a variable and can't be customized.</span></span>
    -   <span data-ttu-id="d0845-149">**Betűtípus** – A betűk stílusának beállítása **Normál** vagy **Félkövér** lehet.</span><span class="sxs-lookup"><span data-stu-id="d0845-149">**Font type** – Set the font style to either **Regular** or **Bold**.</span></span> <span data-ttu-id="d0845-150">A félkövér betűk kétszer annyi helyet foglalnak, mint a normál betűk.</span><span class="sxs-lookup"><span data-stu-id="d0845-150">Bold letters use two times as much space as regular letters.</span></span> <span data-ttu-id="d0845-151">Ezért előfordulhat, hogy néhány karaktert levág a program.</span><span class="sxs-lookup"><span data-stu-id="d0845-151">Therefore, some characters might be truncated.</span></span>
    -   <span data-ttu-id="d0845-152">**Betűtípus** – A betűk méretének beállítása **Normál** vagy **Nagy** lehet.</span><span class="sxs-lookup"><span data-stu-id="d0845-152">**Font size** – Set the font size to either **Regular** or **Large**.</span></span> <span data-ttu-id="d0845-153">A nagy betűk kétszer magasabbak a normál betűknél.</span><span class="sxs-lookup"><span data-stu-id="d0845-153">Large letters are two times higher than regular letters.</span></span> <span data-ttu-id="d0845-154">Ezért a nagybetűk használata átfedő szöveghez vezethet a nyugtán.</span><span class="sxs-lookup"><span data-stu-id="d0845-154">Therefore, using large letters may lead to overlapping text in the receipt.</span></span>
    -   <span data-ttu-id="d0845-155">**Törlés** – erre a gombra kattintva eltávolíthatja a kijelölt részt a képernyőelrendezésből.</span><span class="sxs-lookup"><span data-stu-id="d0845-155">**Delete** – Click this button to remove the selected part from the form layout.</span></span>

## <a name="assign-receipt-profiles"></a><span data-ttu-id="d0845-156">Nyugtaprofilok hozzárendelése</span><span class="sxs-lookup"><span data-stu-id="d0845-156">Assign receipt profiles</span></span>
<span data-ttu-id="d0845-157">A nyugtaprofilok közvetlenül a nyomtatókhoz vannak rendelve a hardver profilon keresztül.</span><span class="sxs-lookup"><span data-stu-id="d0845-157">Receipt profiles are assigned directly to printers through the hardware profile.</span></span>

1.  <span data-ttu-id="d0845-158">A hardverprofil megnyitásához kattintson a **Kiskereskedelem** &gt; **Csatornabeállítások** &gt; **Pénztárbeállítások** &gt; **Pénztárprofilok** &gt; **Hardverprofil** gombra.</span><span class="sxs-lookup"><span data-stu-id="d0845-158">Open the hardware profile by clicking **Retail** &gt; **Channel setup** &gt; **POS setup** &gt; **POS profiles** &gt; **Hardware profile**.</span></span>
2.  <span data-ttu-id="d0845-159">Válassza ki a nyomtatót, majd a **Nyugta profil** mezőben rendelje hozzá a jegyzékben használandó nyugtaprofilt.</span><span class="sxs-lookup"><span data-stu-id="d0845-159">Select the printer, and then, in the **Receipt profile** field, assign the receipt profile to use on the register.</span></span>

<span data-ttu-id="d0845-160">**Megjegyzés:** Két nyomtató használata esetén egy nyomtató használható standard 40-oszlopos hő-papiros nyugta nyomtatására.</span><span class="sxs-lookup"><span data-stu-id="d0845-160">**Note:** If two printers are used, one printer can be used to print standard 40-column thermal receipts.</span></span> <span data-ttu-id="d0845-161">A második nyomtató általában a teljes oldalas, több információt leíró nyugta nyomtatására szolgál.</span><span class="sxs-lookup"><span data-stu-id="d0845-161">The second printer is typically used to print full-page receipt types that require more information.</span></span> <span data-ttu-id="d0845-162">Ezek a nyugta típusok vásárlói rendelés nyugtákat és vevői számlákat tartalmaznak.</span><span class="sxs-lookup"><span data-stu-id="d0845-162">These receipt types include customer order receipts and customer invoices.</span></span>



