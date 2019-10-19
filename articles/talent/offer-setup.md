---
title: Az ajánlatkezelés beállítása
description: Ez a témakör az ajánlatok beállítását írja le a Microsoft Dynamics 365 Talent alkalmazásban.
author: andreabichsel
manager: AnnBe
ms.date: 02/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-18
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 706766ba5133af03d00df99dba1c2a7b0405cd86
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/23/2019
ms.locfileid: "2010844"
---
# <a name="set-up-offer-management"></a><span data-ttu-id="992d5-103">Az ajánlatkezelés beállítása</span><span class="sxs-lookup"><span data-stu-id="992d5-103">Set up offer management</span></span> 

[!include [banner](includes/banner.md)]

<span data-ttu-id="992d5-104">Amikor egy jelölt átkerül a Dynamics 365 Talent: Attract alkalmazásban az ajánlati fázisba, győződjön meg arról, hogy az ajánlatokat gyorsan létre lehet hozni a pályázó számára, szükség szerint jóváhagyni, és a jelentkezőnek küldeni.</span><span class="sxs-lookup"><span data-stu-id="992d5-104">When a candidate is moved to the offer stage in Dynamics 365 Talent: Attract, you need to ensure that the offers can be quickly created for the candidate, approved as necessary, and sent out to the candidate.</span></span> <span data-ttu-id="992d5-105">Mivel a legtöbb ajánlat szabványos, azok újra felhasználható sablonokból is létrehozhatók.</span><span class="sxs-lookup"><span data-stu-id="992d5-105">Because most offers are standard, they can be created from reusable templates.</span></span> <span data-ttu-id="992d5-106">Az Attract szolgáltatásban valamennyi ajánlat belekerül egy ajánlatcsomagba, amely egy vagy több ajánlati dokumentum gyűjteménye.</span><span class="sxs-lookup"><span data-stu-id="992d5-106">In Attract, all offers are rolled into an offer package, which is a collection of one or more offer documents.</span></span> 

<span data-ttu-id="992d5-107">Ez a témakör felsorolja azokat a lépéseket, amelyeket az Attract rendszergazdának követnie kell különböző ajánlatcsomag-sablonok beállításához, amely az ajánlatkezelési lehetőségek része az Attract szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="992d5-107">This topic lists all the steps that an Attract administrator would follow to set up different offer package templates as part of the offer management capability in Attract.</span></span> <span data-ttu-id="992d5-108">A nem rendszergazdai szerepkörrel rendelkező felhasználóknak nincs hozzáférésük ezekhez a funkciókhoz.</span><span class="sxs-lookup"><span data-stu-id="992d5-108">Users with non-administrator roles will not have access to these capabilities.</span></span>

>[!NOTE]
> <span data-ttu-id="992d5-109">Az ajánlatkezelési lehetőségek rendelkezésre állnak az Átfogó felvételi bővítmény részeként.</span><span class="sxs-lookup"><span data-stu-id="992d5-109">Offer management capabilities are available as part of the Comprehensive Hiring Add-On.</span></span>

## <a name="offer-data"></a><span data-ttu-id="992d5-110">Ajánlat adatai</span><span class="sxs-lookup"><span data-stu-id="992d5-110">Offer data</span></span> 

<span data-ttu-id="992d5-111">Az ajánlati adat az ajánlatcsomag-sablonban található legkisebb egység.</span><span class="sxs-lookup"><span data-stu-id="992d5-111">Offer data is the smallest unit inside the offer package template.</span></span> <span data-ttu-id="992d5-112">Egy szokványos ajánlati szabványos szövegből és egy értékkészletből áll.</span><span class="sxs-lookup"><span data-stu-id="992d5-112">A typical offer consists of standard text and a set of values.</span></span> <span data-ttu-id="992d5-113">Az értékkészletek az egyedüli elemek, amelyeket módosítani lehet az ajánlatok között.</span><span class="sxs-lookup"><span data-stu-id="992d5-113">The sets of values are the only pieces that could change between offers.</span></span> <span data-ttu-id="992d5-114">Az ajánlat létrehozásakor a legfontosabb szempont, hogy az ajánlatot létrehozó az ajánlati adatok helyőrzőinek listájára összpontosíthat egy ajánlaticsomag-sablonban.</span><span class="sxs-lookup"><span data-stu-id="992d5-114">During the offer creation, the most important aspect that the offer creator can focus on is the list of offer data placeholders present in an offer package template.</span></span> <span data-ttu-id="992d5-115">Ajánlati adatok beállításához tegye a következőket.</span><span class="sxs-lookup"><span data-stu-id="992d5-115">To set up offer data, do the following.</span></span>

1.  <span data-ttu-id="992d5-116">Ugorjon az **Ajánlatkezelés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="992d5-116">Go to **Offer management**.</span></span>

1.  <span data-ttu-id="992d5-117">Bontsa ki a **Könyvtár** szakaszt a bal oldali navigációs panelen, majd ugorjon az **Ajánlati adatok** részre.</span><span class="sxs-lookup"><span data-stu-id="992d5-117">Expand the **Library** section in the left navigation pane, then go to **Offer data**.</span></span>

    >[!NOTE]
    > <span data-ttu-id="992d5-118">Az **Ajánlati adatok** lapon vannak a **Jelölt adatai** és a **Projekt részletei** szakaszok.</span><span class="sxs-lookup"><span data-stu-id="992d5-118">On the **Offer data** page are the **Candidate details** and **Job details** sections.</span></span> <span data-ttu-id="992d5-119">Az Attract néhány nem megszokott ajánlatiadat-helyőrzőt is kínál.</span><span class="sxs-lookup"><span data-stu-id="992d5-119">Attract provides a few offer data placeholders out-of-the-box.</span></span>
    
    > <span data-ttu-id="992d5-120">A lapon a különböző ajánlatiadat-helyőrzőket szakaszok rendezik logikai csoportokba.</span><span class="sxs-lookup"><span data-stu-id="992d5-120">There are sections on the page to organize different offer data placeholders together in logical groups.</span></span> <span data-ttu-id="992d5-121">Ezek a szakaszok segíthetnek az ajánlati adatok és az adatok kitöltésének karbantartásában az ajánlat-létrehozási folyamat során.</span><span class="sxs-lookup"><span data-stu-id="992d5-121">These sections can help with maintenance of offer data and population of data during the offer creation process.</span></span>

1.  <span data-ttu-id="992d5-122">Új ajánlati adatok szakasz létrehozásához kattintson a **Szakasz hozzáadása** lehetőségre, és adjon meg egy egyedi nevet a szakasznak.</span><span class="sxs-lookup"><span data-stu-id="992d5-122">To create a new offer data section, click **Add a section** and enter a unique name for the section.</span></span>

1.  <span data-ttu-id="992d5-123">Ajánlati adatok helyőrzőinek bármely szakaszhoz való hozzáadásához kattintson az **Ajánlati adatok hozzáadása** lehetőségre, és adjon meg egy egyedi nevet a helyőrzőnek.</span><span class="sxs-lookup"><span data-stu-id="992d5-123">To add offer data placeholders to any section, click **Add offer data** and enter a unique name for the placeholder.</span></span>

1.  <span data-ttu-id="992d5-124">Szakasz nevének szerkesztéséhez vigye a kurzort a szakasz neve fölé, és frissítse a nevet.</span><span class="sxs-lookup"><span data-stu-id="992d5-124">To edit the name of any section, hover over the section name and update the name.</span></span>

1.  <span data-ttu-id="992d5-125">Bármely meglévő ajánlatiadat-helyőrző nevének módosításához először győződjön meg arról, hogy a helyőrző még nem része bármely sablonnak.</span><span class="sxs-lookup"><span data-stu-id="992d5-125">To edit the name of any existing offer data placeholder, first make sure that the placeholder is not already part of any template.</span></span> <span data-ttu-id="992d5-126">Ezt követően vigye a kurzort az ajánlati adatok helyőrzőjének neve fölé, és frissítse a nevet szükség szerint.</span><span class="sxs-lookup"><span data-stu-id="992d5-126">Then, hover over the name of the offer data placeholder and update the name as needed.</span></span>

1. <span data-ttu-id="992d5-127">Bármely meglévő ajánlatiadat-helyőrző törléséhez először győződjön meg arról, hogy a helyőrző még nem része bármely más sablonnak.</span><span class="sxs-lookup"><span data-stu-id="992d5-127">To delete an existing offer data placeholder, first make sure that the placeholder is not part of any other template.</span></span> <span data-ttu-id="992d5-128">Ezután vigye a kurzprt helyőrző fölé, és amikor a szemeteskuka ikon látható, kattintson a szemeteskukára az ajánlati adatok helyőrző törléséhez.</span><span class="sxs-lookup"><span data-stu-id="992d5-128">Then, hover over the placeholder and when the trash can icon appears, click the trash can to delete the offer data placeholder.</span></span>
    >[!NOTE]
    > <span data-ttu-id="992d5-129">Megtekintheti, hogy egy ajánlatiadat-helyőrző hány sablon része, mégpedig az ajánlati adatok mellett található számindikátor alapján.</span><span class="sxs-lookup"><span data-stu-id="992d5-129">You can see how many templates an offer data placeholder is part of by the number indicator next to each offer data.</span></span> 

1. <span data-ttu-id="992d5-130">A szakasz törléséhez vigye a kurzort a neve fölé.</span><span class="sxs-lookup"><span data-stu-id="992d5-130">To delete any section, hover over the name.</span></span> <span data-ttu-id="992d5-131">Ha a szakaszban levő ajánlati adatok helyőrzőinek egyike sem jelenik meg egy sablonban sem, rákattinthat a szemeteskuka ikonra a törléshez.</span><span class="sxs-lookup"><span data-stu-id="992d5-131">If none of the offer data placeholders inside the section appear in any template, you can click the trash can icon to delete it.</span></span> 
    >[!NOTE]
    > <span data-ttu-id="992d5-132">A szakasz törlése a szakaszon belül az összes ajánlatiadat-helyőrzőket is törli.</span><span class="sxs-lookup"><span data-stu-id="992d5-132">Deleting the section will also delete all the offer data placeholders inside that section.</span></span>

<span data-ttu-id="992d5-133">Az ajánlati adatok helyőrzőinek beállítását követően bármely dokumentumsablonban felhasználhatja őket.</span><span class="sxs-lookup"><span data-stu-id="992d5-133">After the offer data placeholders have been set up, you can use them across any document template.</span></span> <span data-ttu-id="992d5-134">Az ajánlati adatok helyőrzői nem korlátozódnak egy adott sablonra – ugyanaz a készlet az összes sablonban alkalmazható.</span><span class="sxs-lookup"><span data-stu-id="992d5-134">Offer data placeholders are not restricted to a specific template -- the same set can be used across all templates.</span></span>

## <a name="offer-data-rules"></a><span data-ttu-id="992d5-135">Ajánlat adataira vonatkozó szabályok</span><span class="sxs-lookup"><span data-stu-id="992d5-135">Offer data rules</span></span>

<span data-ttu-id="992d5-136">A legtöbb szervezet rendelkezik szabályokkal, hogy hogyan kell létrehozni az ajánlatokat.</span><span class="sxs-lookup"><span data-stu-id="992d5-136">Most organization have rules for how offers must be created.</span></span> <span data-ttu-id="992d5-137">Például egy szervezet megkövetelheti, hogy egy bizonyos hely és szolgálati idő kombinációjához tartozó maximális éves fizetési ajánlata egy bizonyos tartományba tartozzon, hogy csak néhány meghatározott érték lehetséges az újonnan felvett dolgozó ajánlati szintjén.</span><span class="sxs-lookup"><span data-stu-id="992d5-137">For example, an organization may want to require that the maximum annual salary offer for a specific location and seniority level combination has to be within a certain range, or that there are only a few specific values possible for the offer level for the new hire.</span></span> <span data-ttu-id="992d5-138">Az Attract jelenleg támogatja az összes adatszabályozást, amely CSV-fájlt használ.</span><span class="sxs-lookup"><span data-stu-id="992d5-138">Attract currently supports all such data rules using a CSV file.</span></span>

<span data-ttu-id="992d5-139">A CSV-fájlból az adatszabályok létrehozásához tegye a következőket.</span><span class="sxs-lookup"><span data-stu-id="992d5-139">To prepare the data rules CSV file, do the following.</span></span>

1.  <span data-ttu-id="992d5-140">Határozza meg az ajánlati adatok helyőrzőjét a szabálykészlethez.</span><span class="sxs-lookup"><span data-stu-id="992d5-140">Determine the offer data placeholder for the rule set.</span></span> <span data-ttu-id="992d5-141">Például **Éves fizetés**.</span><span class="sxs-lookup"><span data-stu-id="992d5-141">For example, **Annual Salary**.</span></span>

1.  <span data-ttu-id="992d5-142">Azonosítsa az ettől függő ajánlati adatok helyőrzőjének értékeit.</span><span class="sxs-lookup"><span data-stu-id="992d5-142">Identify the dependent offer data placeholder values.</span></span> <span data-ttu-id="992d5-143">Például **Munkavégzési hely** és **Szint**.</span><span class="sxs-lookup"><span data-stu-id="992d5-143">For example, **Job Location** and **Level**.</span></span>

1.  <span data-ttu-id="992d5-144">Határozza meg az 1. és 2. oszlopot mint **Munkavégzési hely** és **Szint**.</span><span class="sxs-lookup"><span data-stu-id="992d5-144">Specify columns 1 and 2 as **Job Location** and **Level**.</span></span>

1.  <span data-ttu-id="992d5-145">Tartományérték feltöltéséhez legyen a 3. és 4. oszlop az **Éves fizetés**.</span><span class="sxs-lookup"><span data-stu-id="992d5-145">To upload a range value, make columns 3 and 4 **Annual Salary**.</span></span> <span data-ttu-id="992d5-146">Ha tartomány helyett egy meghatározott értéket szeretne feltölteni, legyen csak a 3. oszlop az **Éves fizetés**.</span><span class="sxs-lookup"><span data-stu-id="992d5-146">To upload a specific value instead of a range, only make column 3 **Annual Salary**.</span></span>

1.  <span data-ttu-id="992d5-147">A szükséges szerepkörök alapján töltse fel a Microsoft Excel-fájlt.</span><span class="sxs-lookup"><span data-stu-id="992d5-147">Populate the Microsoft Excel file based on your required roles.</span></span>

1.  <span data-ttu-id="992d5-148">Ellenőrizze, hogy minden sor az összes érték egyedi kombinációja.</span><span class="sxs-lookup"><span data-stu-id="992d5-148">Ensure that each row is a unique combination of all the values put together.</span></span>

1.  <span data-ttu-id="992d5-149">Mentse el a fájlt CSV-formátumban.</span><span class="sxs-lookup"><span data-stu-id="992d5-149">Save the file as a CSV format.</span></span>

<span data-ttu-id="992d5-150">Az ajánlati adatokra vonatkozó szabályfájl feltöltéséhez tegye a következőket.</span><span class="sxs-lookup"><span data-stu-id="992d5-150">To upload the offer data rules file, do the following.</span></span>

1.  <span data-ttu-id="992d5-151">Ugorjon az **Ajánlatkezelés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="992d5-151">Go to **Offer management**.</span></span>

1.  <span data-ttu-id="992d5-152">Bontsa ki a **Könyvtár** szakaszt a bal oldali navigációs panelen, majd ugorjon az **Ajánlati adatszabályok** részre.</span><span class="sxs-lookup"><span data-stu-id="992d5-152">Expand the **Library** section in the left navigation panel, then go to **Offer data rules**.</span></span>

1.  <span data-ttu-id="992d5-153">Kattintson az **Új adatkészlet** lehetőségre, hogy megjelenítse a **Feltöltés** párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="992d5-153">Click **New data set** to display the **Upload** dialog box.</span></span>

1.  <span data-ttu-id="992d5-154">Adjon egyedi nevet a szabálykészletnek, majd töltse fel a mentett CSV-fájlt.</span><span class="sxs-lookup"><span data-stu-id="992d5-154">Specify a unique name for the rule set and then upload the saved CSV file.</span></span>

1.  <span data-ttu-id="992d5-155">Kattintson a **Hozzáadás** gombra.</span><span class="sxs-lookup"><span data-stu-id="992d5-155">Click **Add**.</span></span>
    <span data-ttu-id="992d5-156">A szabálykészletet a rendszer fel fogja dolgozni a háttérben, és értesítést fog küldeni az alkalmazáson belül és e-mailben a befejezés után.</span><span class="sxs-lookup"><span data-stu-id="992d5-156">The rule set will be processed in the background and you will be notified in-app and via email once it completes.</span></span>

    <span data-ttu-id="992d5-157">Értesítést fog kapni, ha hibák fordulnak elő a feltöltés feldolgozása közben.</span><span class="sxs-lookup"><span data-stu-id="992d5-157">You will be notified if there are errors while processing the upload.</span></span> <span data-ttu-id="992d5-158">Ezután letöltheti a hibanaplót, javítsa ki a fájlt, és újból töltse fel.</span><span class="sxs-lookup"><span data-stu-id="992d5-158">You can then download the error log, fix the file, and upload it again.</span></span>

1.  <span data-ttu-id="992d5-159">A három pont (ellipszis) gomb (**...**) lehetőség használatával letöltheti a szabálykészletet és frissítheti az értékkészletet.</span><span class="sxs-lookup"><span data-stu-id="992d5-159">Use the ellipses button (**…**) option if you want to download the rule set and update the set of values.</span></span> <span data-ttu-id="992d5-160">Frissítés után újra lehet feltölteni a fájlt.</span><span class="sxs-lookup"><span data-stu-id="992d5-160">After updating, you can upload the file again.</span></span>

1.  <span data-ttu-id="992d5-161">Egy meglévő szabálykészlet feltöltését törölheti, ha egy másik dokumentumsablonban nincs használatban az éppen definiált helyőrző.</span><span class="sxs-lookup"><span data-stu-id="992d5-161">You can delete an existing rule set upload if the placeholder being defined is not being used in another document template.</span></span>

>[!NOTE]
> - <span data-ttu-id="992d5-162">Minden helyőrző csak egy egyedi oszlopkészlettel rendelkezhet, amelytől függő.</span><span class="sxs-lookup"><span data-stu-id="992d5-162">Each placeholder can only have one unique set of columns that it is dependent on.</span></span> <span data-ttu-id="992d5-163">Például ha az **Éves fizetés** függ a **Munkavégzési hely** és **Szint** oszlopoktól, nem tölthető fel egy másik szabálykészlet, ahol az **Éves fizetés** egy másik oszlopkészlettől függ.</span><span class="sxs-lookup"><span data-stu-id="992d5-163">For example, if **Annual Salary** is dependent on **Job Location** and **Level**, you can't upload another rule set where **Annual Salary** is dependent on a different set of columns.</span></span>

> - <span data-ttu-id="992d5-164">Letölthet ajánlati adatokra vonatkozó szabálykészlet-mintákat a **Minták** lapon az **Ajánlatiadat-szabályok** oldalon.</span><span class="sxs-lookup"><span data-stu-id="992d5-164">You can download sample offer data rule sets on the **Samples** tab on the **Offer data rules** page.</span></span>

> - <span data-ttu-id="992d5-165">Ha az ajánlat létrehozója felülbírálja az értékeket, amelyek az ajánlati adatokra vonatkozó szabályok által ajánlottak, az ajánlat nem szabványosként lesz megjelölve, és ez az ajánlat-jóváhagyási munkafolyamat előírását eredményezi.</span><span class="sxs-lookup"><span data-stu-id="992d5-165">When an offer creator overrides the values that are recommended by the offer data rules, the offer is flagged as non-standard and offer approval workflow will be mandated.</span></span>

## <a name="document-templates"></a><span data-ttu-id="992d5-166">Dokumentumsablonok</span><span class="sxs-lookup"><span data-stu-id="992d5-166">Document templates</span></span>

<span data-ttu-id="992d5-167">Az ajánlatdokumentum-sablon segíti a rendszergazdákat az ajánlólevelek létrehozásában.</span><span class="sxs-lookup"><span data-stu-id="992d5-167">An offer document template can help administrators create offer letters.</span></span> <span data-ttu-id="992d5-168">Az ajánlatdokumentum-sablon az ajánlat részének szánt szöveg és a meghatározott ajánlati adatok helyőrzőinek kombinációja.</span><span class="sxs-lookup"><span data-stu-id="992d5-168">The offer document template is a combination of the text that will be part of the offer as well as the defined offer data placeholders.</span></span> 

<span data-ttu-id="992d5-169">Az ajánlatdokumentum-sablon létrehozásához tegye a következőket.</span><span class="sxs-lookup"><span data-stu-id="992d5-169">To create an offer document template, do the following.</span></span>

1.  <span data-ttu-id="992d5-170">Ugorjon az **Ajánlatkezelés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="992d5-170">Go to **Offer management**.</span></span>

1.  <span data-ttu-id="992d5-171">Bontsa ki a **Könyvtár** szakaszt a bal oldali navigációs panelen, és ugorjon a **Sablonok** részre.</span><span class="sxs-lookup"><span data-stu-id="992d5-171">Expand the **Library** section in the left navigation pane and go to **Templates**.</span></span>

    <span data-ttu-id="992d5-172">A **Sablonok** lap megjeleníti a már definiált dokumentumsablonok listáját.</span><span class="sxs-lookup"><span data-stu-id="992d5-172">The **Templates** page will display a list of document templates that have already been defined.</span></span>

1.  <span data-ttu-id="992d5-173">Új dokumentumsablon létrehozásához kattintson az **Új sablon** elemre.</span><span class="sxs-lookup"><span data-stu-id="992d5-173">To create a new document template, click **New Template**.</span></span>

1.  <span data-ttu-id="992d5-174">Adjon egyedi nevet a sablonnak, majd kattintson a **Létrehozás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="992d5-174">Enter a unique name for the template and click **Create**.</span></span>

1.  <span data-ttu-id="992d5-175">Rich text szerkesztővel beszúrhatja vagy szerkesztheti az ajánlati dokumentum tartalmát.</span><span class="sxs-lookup"><span data-stu-id="992d5-175">Use the rich text editor to insert or edit the offer document content.</span></span> <span data-ttu-id="992d5-176">Táblák, képek és hivatkozások beszúrhatók az elérhető beállítások segítségével, amelyek a szövegszerkesztő tetején találhatók.</span><span class="sxs-lookup"><span data-stu-id="992d5-176">You can insert tables, images, and hyperlinks using the options available at the top of the text editor.</span></span>

1.  <span data-ttu-id="992d5-177">Az ajánlatsablon-dokumentumba ajánlati adatok helyőrzőit is beillesztheti a következő módon:</span><span class="sxs-lookup"><span data-stu-id="992d5-177">You can insert offer data placeholders in the offer template document by:</span></span>

    - <span data-ttu-id="992d5-178">Húzza át a jobb panelből.</span><span class="sxs-lookup"><span data-stu-id="992d5-178">Dragging and dropping from the right pane.</span></span>

    - <span data-ttu-id="992d5-179">A hashtag segítségével helyezze a megfelelő helyre az ajánlatiadat-helyőrzőt.</span><span class="sxs-lookup"><span data-stu-id="992d5-179">Hashtag the offer data placeholder directly into position.</span></span> <span data-ttu-id="992d5-180">Gépelje be, hogy **\#**, majd kezdje el beírni az ajánlatiadat-helyőrző nevét.</span><span class="sxs-lookup"><span data-stu-id="992d5-180">Type **\#** and then start typing the name of the offer data placeholder.</span></span> <span data-ttu-id="992d5-181">Lehetőségek jelennek meg a legördülő listából.</span><span class="sxs-lookup"><span data-stu-id="992d5-181">Options will appear in the drop-down list.</span></span> <span data-ttu-id="992d5-182">Nyomja le vagy kattintson az **Enter** gombra az ajánlatiadat-helyőrző beszúrásához.</span><span class="sxs-lookup"><span data-stu-id="992d5-182">Click or press **Enter** to insert the offer data placeholder.</span></span>

    >[!NOTE]
    > - <span data-ttu-id="992d5-183">Ahhoz, hogy egy helyőrzőt az ajánlatidokumentum-sablonhoz társítsa anélkül, hogy értékét felfedje a jelölt előtt, vigye a kurzort az ajánlatiadat-helyőrző fölé, majd kattintson a **Rögzítés** ikonra.</span><span class="sxs-lookup"><span data-stu-id="992d5-183">To associate a placeholder to the offer document template without exposing its value to the candidate, hover over the offer data placeholder and click the **Pin** icon.</span></span> <span data-ttu-id="992d5-184">Ez a helyőrzőt elküldi a **Rögzített ajánlati adatok** szakaszba az ajánlatdokumentum-sablonban.</span><span class="sxs-lookup"><span data-stu-id="992d5-184">This will push the placeholder to the **Pinned offer data** section of the offer document template.</span></span> <span data-ttu-id="992d5-185">A rögzítés feloldásához kövesse ugyanazokat a lépéseket, de az ajánlatiadat-helyőrzők listájában kattintson a **Rögzítés feloldása** elemre.</span><span class="sxs-lookup"><span data-stu-id="992d5-185">To unpin, follow the same steps but click **Unpin** in the list of offer data placeholders.</span></span>

    > - <span data-ttu-id="992d5-186">Az aktív ajánlati adatok helyőrzői listájának megtekintéséhez váltson át az **Aktív** lapon a jobb oldali panelen.</span><span class="sxs-lookup"><span data-stu-id="992d5-186">To view the list of active offer data placeholders, switch to the **Active** tab in the right pane.</span></span>

    > - <span data-ttu-id="992d5-187">Ha beszúr egy helyőrzőt, amelyet egy ajánlati adatokra vonatkozó szabálykészlet vezérlik megtekintheti a függőséget, amely az adott ajánlatiadat-helyőrző és más értékek között fennáll.</span><span class="sxs-lookup"><span data-stu-id="992d5-187">If you insert a placeholder that is driven by an offer data rule set, you can see the dependency of that offer data placeholder on other values.</span></span>

    > - <span data-ttu-id="992d5-188">Egyéb esetben **importálhatja** egy .docx fájl tartalmát a helyi számítógépére, ahol szükség szerint szerkesztheti.</span><span class="sxs-lookup"><span data-stu-id="992d5-188">Alternatively, you can **Import** the content from a .docx file on your local machine and edit as required.</span></span> <span data-ttu-id="992d5-189">Ezzel a módszerrel nem kell begépelnie a szerkesztőbe minden tartalmat.</span><span class="sxs-lookup"><span data-stu-id="992d5-189">That way, you don’t have to type in all the content in the editor.</span></span>

1. <span data-ttu-id="992d5-190">Az ajánlati dokumentum előnézetének megtekintéséhez használja az **Előnézet** lehetőséget az oldal tetején.</span><span class="sxs-lookup"><span data-stu-id="992d5-190">To preview the offer document, use the **Preview** option at the top of the page.</span></span>

1. <span data-ttu-id="992d5-191">Szabályozhatja, hogy az ajánlat létrehozó szerkesztheti-e az ajánlati dokumentum tartalmát az oldal tetején található **Engedélyek kezelése** lehetőséggel.</span><span class="sxs-lookup"><span data-stu-id="992d5-191">To control whether an offer creator can edit the offer document content, use the **Manage permission** option at the top of the page.</span></span> <span data-ttu-id="992d5-192">Ha azt szeretné, hogy az ajánlat létrehozója ne módosíthassa a szöveget, és csak a helyőrző értékeit illeszthesse be, állítsa az engedély értékét **Nem** beállításra.</span><span class="sxs-lookup"><span data-stu-id="992d5-192">If you want the offer creator to only insert placeholder values and not edit text, set the permission value to **No**.</span></span>

1. <span data-ttu-id="992d5-193">A folyamat előrehaladásának mentéséhez kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="992d5-193">Click **Save** to save your progress.</span></span> <span data-ttu-id="992d5-194">A sablont a rendszer vázlat állapotúként menti.</span><span class="sxs-lookup"><span data-stu-id="992d5-194">The template will be saved in a draft state.</span></span>

1. <span data-ttu-id="992d5-195">A dokumentum véglegesítéséhez és közzétett állapotúként való megjelöléséhez kattintson a **Befejezés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="992d5-195">To finalize and mark the document as published, click **Finish**.</span></span>

1. <span data-ttu-id="992d5-196">Megtekintheti, melyik dokumentumsablonok jelenleg aktívak, melyek vannak vázlat módban, melyeket archiváltak és melyek már nincsenek használatban a dokumentumsablonok könyvtár érkezési élményében.</span><span class="sxs-lookup"><span data-stu-id="992d5-196">You can see which document templates are currently active, in draft mode, and have been archived and are no longer in use on the document templates library landing experience.</span></span>

>[!NOTE]
> <span data-ttu-id="992d5-197">Bármely ajánlat dokumentumsablonját törölheti, amely nem szerepel egy meglévő ajánlaticsomag-sablonban.</span><span class="sxs-lookup"><span data-stu-id="992d5-197">You can delete any offer document template that is not part of an existing offer package template.</span></span>


## <a name="offer-package-templates"></a><span data-ttu-id="992d5-198">Ajánlaticsomag-sablonok</span><span class="sxs-lookup"><span data-stu-id="992d5-198">Offer package templates</span></span>

<span data-ttu-id="992d5-199">Az ajánlatcsomagok olyan ajánlati műtermékek, amelyek a jelölttel meg vannak osztva, és egy vagy több ajánlati dokumentumsablon kombinációját tartalmazzák.</span><span class="sxs-lookup"><span data-stu-id="992d5-199">Offer packages are the offer artifacts that are shared with the candidate and consist of a combination of one or more offer document templates.</span></span> <span data-ttu-id="992d5-200">Az ajánlatcsomag létrehozásához tegye a következőket.</span><span class="sxs-lookup"><span data-stu-id="992d5-200">To create an offer package, do the following.</span></span>

1.  <span data-ttu-id="992d5-201">Ugorjon az **Ajánlatkezelés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="992d5-201">Go to **Offer management**.</span></span>

1.  <span data-ttu-id="992d5-202">Ugorjon a **Csomagok** lehetőségre a bal oldali navigációs panelben.</span><span class="sxs-lookup"><span data-stu-id="992d5-202">Go to **Packages** from the left navigation pane.</span></span>

    <span data-ttu-id="992d5-203">Az ajánlat-létrehozók számára elérhető aktív csomagsablonok listája jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="992d5-203">A list of active package templates that are available for offer creators to use is displayed.</span></span>

1.  <span data-ttu-id="992d5-204">Ha új ajánlati csomagot szeretne létrehozni, kattintson az **Új csomag** gombra.</span><span class="sxs-lookup"><span data-stu-id="992d5-204">To create a new offer package, click **New Package**.</span></span>

1.  <span data-ttu-id="992d5-205">Adjon egyedi nevet, majd kattintson a **Létrehozás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="992d5-205">Enter a unique name and click **Create**.</span></span>

1.  <span data-ttu-id="992d5-206">Kattintson a **Sablon hozzáadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="992d5-206">Click **Add template**.</span></span>

    >[!NOTE]
    > - <span data-ttu-id="992d5-207">Választhat, hogy létrehoz egy új sablont, vagy választ egy már meglévőt.</span><span class="sxs-lookup"><span data-stu-id="992d5-207">You can choose to create a new template or choose from an existing one.</span></span>

    > - <span data-ttu-id="992d5-208">Ha a meglévő sablon hozzáadását választja, akkor győződjön meg arról, hogy az ajánlati dokumentumsablont mentették, véglegesítették és aktívként megjelölték.</span><span class="sxs-lookup"><span data-stu-id="992d5-208">If you choose to add an existing template, you need to make sure that the   offer document template was saved, finalized, and marked as   active.</span></span>
    
    > - <span data-ttu-id="992d5-209">Tetszőleges számú dokumentumsablont lehet kiválasztani.</span><span class="sxs-lookup"><span data-stu-id="992d5-209">You can choose as many document templates as you want.</span></span> 
    
1.  <span data-ttu-id="992d5-210">Kattintson a **Kész** lehetőségre a **Csomag kezelése** ponthoz való visszatéréshez.</span><span class="sxs-lookup"><span data-stu-id="992d5-210">Click **Done** to return to **Package management**.</span></span>

    <span data-ttu-id="992d5-211">A dokumentumok sorrendjét beállíthatja, és azt is bejelölheti, hogy az adott ajánlati dokumentumra szükség van-e ajánlat létrehozása során.</span><span class="sxs-lookup"><span data-stu-id="992d5-211">You can configure the sequence of the documents and also mark whether the specific offer document is required during offer creation.</span></span> <span data-ttu-id="992d5-212">Az ajánlat létrehozójának lesz lehetőségre, hogy törölje a dokumentumokat, amelyek **Nem szükséges**-ként vannak megjelölve.</span><span class="sxs-lookup"><span data-stu-id="992d5-212">The offer creator will have an option to delete the documents marked as **Not required**.</span></span>

1. <span data-ttu-id="992d5-213">Az ajánlati csomag sablonjának olyan módon való mentéséhez, hogy azt az összes ajánlatkészítő használhassa, kattintson a **Mentés és közzététel** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="992d5-213">To save the offer package template so that it's usable by all offer creators, click **Save and publish**.</span></span>

   <span data-ttu-id="992d5-214">Vázlatos ajánlaticsomag-sablonok megtekintéséhez ugorjon a **Vázlatok** lapra. Ha az ajánlaticsomag-sablon módosul, el kell menteni és újra közzétenni.</span><span class="sxs-lookup"><span data-stu-id="992d5-214">To view draft offer package templates, go to the **Drafts** tab. If a change is made to the offer package template, it must be  saved and republished.</span></span>

## <a name="configure-an-offer-process"></a><span data-ttu-id="992d5-215">Ajánlati folyamat konfigurálása</span><span class="sxs-lookup"><span data-stu-id="992d5-215">Configure an offer process</span></span>

<span data-ttu-id="992d5-216">Az ajánlatkészítési folyamatnak számos olyan része van, amelyet egy Attract-rendszergazda konfigurálhat.</span><span class="sxs-lookup"><span data-stu-id="992d5-216">There are several parts of the offer creation process that can be configured by an Attract administrator.</span></span>

- <span data-ttu-id="992d5-217">**Ajánlatok jóváhagyása** – Válassza ki, hogy az ajánlatok jóváhagyása szükséges-e, mielőtt az ajánlat elküldhető a jelöltnek.</span><span class="sxs-lookup"><span data-stu-id="992d5-217">**Offer approvals** - Choose whether offer approvals are required before the offer can be sent to the candidate.</span></span> <span data-ttu-id="992d5-218">Rendszergazdaként eldöntheti azt is, hogy az összes ajánlatra vonatkozó jóváhagyás egymás utáni sorrendben vagy párhuzamos jóváhagyási munkafolyamattal történjen.</span><span class="sxs-lookup"><span data-stu-id="992d5-218">As an administrator, you can also decide whether all offer approvals will happen in a sequential manner or parallel approval workflow.</span></span> <span data-ttu-id="992d5-219">Azt is előírhatja, hogy az ajánlatok jóváhagyóinak kell-e megjegyzést hozzáadniuk az ajánlat jóváhagyásához.</span><span class="sxs-lookup"><span data-stu-id="992d5-219">You can also mandate whether offer approvers must add a comment along with their offer approval.</span></span> <span data-ttu-id="992d5-220">A nem szabványos ajánlatok esetén az ajánlat-jóváhagyások kötelezőek.</span><span class="sxs-lookup"><span data-stu-id="992d5-220">Offer approvals are mandatory for all non-standard offers.</span></span>

- <span data-ttu-id="992d5-221">**Jelölt ajánlati élménye** - rendszergazdaként, lehetősége van azt beállítani, hogy minden ajánlathoz tartozik-e lejárati dátum, és ha igen, mi legyen az alapértelmezett eltolás a lejárati dátum esetén.</span><span class="sxs-lookup"><span data-stu-id="992d5-221">**Candidate’s offer experience** - As administrator, you can choose to set whether all offers have an expiration date, and if so, what the default offset for the expiration date should be.</span></span> <span data-ttu-id="992d5-222">Az is konfigurálható, hogy a pályázók elutasíthatja-e az ajánlatot.</span><span class="sxs-lookup"><span data-stu-id="992d5-222">You can also configure whether candidates can decline an offer.</span></span>

- <span data-ttu-id="992d5-223">**e-aláírások** – Rendszergazdaként,kiválaszthatja, hogy a pályázók milyen módot használhatnak az aláírásokhoz.</span><span class="sxs-lookup"><span data-stu-id="992d5-223">**e-Signatures** - As an administrator, you can also choose the method that candidates can use to sign offers.</span></span>
    - <span data-ttu-id="992d5-224">Adobe Sign – Az összes ajánlati csomag küldése és aláírása az Adobe Sign használatával történik.</span><span class="sxs-lookup"><span data-stu-id="992d5-224">Adobe Sign - All offer packages will be sent and signed via Adobe Sign.</span></span> <span data-ttu-id="992d5-225">Minden egyes ajánlatot létrehozó esetében kapcsolni kell Adobe Sign fiókot az Attract alkalmazáshoz.</span><span class="sxs-lookup"><span data-stu-id="992d5-225">Each offer creator publishing the offer needs to have their Adobe Sign account connected to Attract.</span></span> <span data-ttu-id="992d5-226">Adobe Sign licencekért és ingyenes próbaverzióért keresse fel ezt a [hivatkozást](https://acrobat.adobe.com/us/en/business/integrations/microsoft-dynamics-365-for-talent.html).</span><span class="sxs-lookup"><span data-stu-id="992d5-226">For Adobe Sign licenses and a free Trial, please visit this [link](https://acrobat.adobe.com/us/en/business/integrations/microsoft-dynamics-365-for-talent.html).</span></span>

    - <span data-ttu-id="992d5-227">DocuSign – Az összes ajánlati csomag küldése és aláírása a DocuSign használatával történik.</span><span class="sxs-lookup"><span data-stu-id="992d5-227">DocuSign - All offer packages will be sent and signed via DocuSign.</span></span> <span data-ttu-id="992d5-228">Minden egyes ajánlatot létrehozó esetében kapcsolni kell DocuSign fiókot az Attract alkalmazáshoz.</span><span class="sxs-lookup"><span data-stu-id="992d5-228">Each offer creator publishing the offer needs to have their DocuSign account connected to Attract.</span></span> 
    
    - <span data-ttu-id="992d5-229">ESign – Ez az alapértelmezett beállítás, amelyet az alkalmazás tartalmaz, a felhasználó neve és monogramja beírásával írhatja alá az ajánlatot.</span><span class="sxs-lookup"><span data-stu-id="992d5-229">ESign - This is the default option, provided out of the box, where the user can sign an offer by typing their name and initials.</span></span>


<span data-ttu-id="992d5-230">Az ajánlat-létrehozási folyamat kapcsolatos további tudnivalókért tekintse meg az [Ajánlatok létrehozása, jóváhagyása és aláírása](./creating-offers.md) című részt.</span><span class="sxs-lookup"><span data-stu-id="992d5-230">To learn more about the offer creation process, see [Creating, approving, and signing offers](./creating-offers.md).</span></span>
