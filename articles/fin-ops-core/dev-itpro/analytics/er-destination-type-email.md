---
title: E-mail ER céltípusa
description: Ez a témakör azt mutatja be, hogyan lehet beállítani egy e-mail célhelyet a kimenő dokumentumok létrehozásához konfigurált elektronikus jelentési (ER) formátumú fájlok MAPPA vagy FÁJL összetevőihez.
author: NickSelin
manager: AnnBe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 72f67ad915ba2acc90ecb52bdb97e42504450a03
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745561"
---
# <a name="email-destination"></a><span data-ttu-id="c4a94-103">E-mail célja</span><span class="sxs-lookup"><span data-stu-id="c4a94-103">Email destination</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c4a94-104">Beállíthat egy e-mail célhelyet a kimenő dokumentumok létrehozásához konfigurált elektronikus jelentési (ER) formátumú fájlok MAPPA vagy FÁJL összetevőihez.</span><span class="sxs-lookup"><span data-stu-id="c4a94-104">You can configure an email destination for each FOLDER or FILE component of an Electronic reporting (ER) format that is configured to generate outbound documents.</span></span> <span data-ttu-id="c4a94-105">A célhely beállításai alapján a létrejövő dokumentumot a rendszer egy e-mail csatolmányaként küldi el.</span><span class="sxs-lookup"><span data-stu-id="c4a94-105">Based on the destination setting, a generated document is delivered as an attachment of an electronic mail.</span></span>

<span data-ttu-id="c4a94-106">Állítsa a **Bekapcsolva** opciót **Igen** állapotra egy eredményfájl email-ben történő küldéséhez.</span><span class="sxs-lookup"><span data-stu-id="c4a94-106">Set **Enabled** to **Yes** to send an output file by email.</span></span> <span data-ttu-id="c4a94-107">Ezen beállítás engedélyezése után szerkesztheti az e-mail címzettjeit, tárgyát és szövegét.</span><span class="sxs-lookup"><span data-stu-id="c4a94-107">After this option is enabled, you can specify the email recipients and edit the subject and body of the email message.</span></span> <span data-ttu-id="c4a94-108">Beállíthat állandó szöveget az e-mail tárgyaként és szövegeként, illetve használhat ER-[képleteket](er-formula-language.md) az e-mail szövegének dinamikus létrehozására.</span><span class="sxs-lookup"><span data-stu-id="c4a94-108">You can set up constant texts for the email subject and body, or you can use ER [formulas](er-formula-language.md) to dynamically create email texts.</span></span> 

<span data-ttu-id="c4a94-109">Elektronikus jelentéstételhez e-mail-címeket két módon konfigurálhat.</span><span class="sxs-lookup"><span data-stu-id="c4a94-109">You can configure email addresses for ER in two ways.</span></span> <span data-ttu-id="c4a94-110">A konfiguráció ugyanúgy fejezhető be, mint a Nyomtatás kezelése funkció. Ezenfelül e-mail-címet megoldhat úgy is, hogy képlettel közvetlenül hivatkozik az ER-konfigurációra.</span><span class="sxs-lookup"><span data-stu-id="c4a94-110">The configuration can be completed in the same way that the Print management feature completes it, or you can resolve an email address by using a direct reference to the ER configuration through a formula.</span></span>

<span data-ttu-id="c4a94-111">[![E-mail céljának engedélyezése](./media/ER_Destinations-EnableSingleDestination.png)](./media/ER_Destinations-EnableSingleDestination.png)</span><span class="sxs-lookup"><span data-stu-id="c4a94-111">[![Enable email destination](./media/ER_Destinations-EnableSingleDestination.png)](./media/ER_Destinations-EnableSingleDestination.png)</span></span>

## <a name="email-address-types"></a><span data-ttu-id="c4a94-112">E-mail-címek típusai</span><span class="sxs-lookup"><span data-stu-id="c4a94-112">Email address types</span></span>

<span data-ttu-id="c4a94-113">Amikor kiválasztja a **Szerkesztés** elemet a **Címzett** vagy **Másolatot kap** mezőkben, megjelenik az **E-mail címzettje** párbeszédpanel.</span><span class="sxs-lookup"><span data-stu-id="c4a94-113">When you select **Edit** in the **To** or **Cc** fields, the **Email to** dialog box appears.</span></span> <span data-ttu-id="c4a94-114">Ezután kiválaszthatja a használandó e-mail-cím típusát.</span><span class="sxs-lookup"><span data-stu-id="c4a94-114">You can then select the type of email address to use.</span></span> <span data-ttu-id="c4a94-115">A jelenleg támogatott e-mail-típusok: **Konfigurációs e-mail** és **Nyomtatás kezelése**.</span><span class="sxs-lookup"><span data-stu-id="c4a94-115">The **Configuration email** and **Print Management** email types are currently supported.</span></span>

<span data-ttu-id="c4a94-116">[![E-mail típusának kiválasztása](./media/ER_Destinations-EmailSelectAddressType.png)](./media/ER_Destinations-EmailSelectAddressType.png)</span><span class="sxs-lookup"><span data-stu-id="c4a94-116">[![Select email type](./media/ER_Destinations-EmailSelectAddressType.png)](./media/ER_Destinations-EmailSelectAddressType.png)</span></span>

### <a name="print-management"></a><span data-ttu-id="c4a94-117">Nyomtatás kezelése</span><span class="sxs-lookup"><span data-stu-id="c4a94-117">Print management</span></span>

<span data-ttu-id="c4a94-118">Ha bejelöli a **Nyomtatás kezelése** e-mail-típust, fix e-mail-címeket adhat meg a **Címzett** mezőben.</span><span class="sxs-lookup"><span data-stu-id="c4a94-118">If you select the **Print Management** email type, you can enter fixed email addresses in the **To** field.</span></span> 

<span data-ttu-id="c4a94-119">[![Fix e-mail-címek konfigurálása](./media/ER_Destinations-EmailFixedAddress.png)](./media/ER_Destinations-EmailFixedAddress.png)</span><span class="sxs-lookup"><span data-stu-id="c4a94-119">[![Configure fixed email addresses](./media/ER_Destinations-EmailFixedAddress.png)](./media/ER_Destinations-EmailFixedAddress.png)</span></span>

<span data-ttu-id="c4a94-120">Nem rögzített email-cím használatához válassza ki az e-mail forrástípusát a fájlcélponthoz.</span><span class="sxs-lookup"><span data-stu-id="c4a94-120">To use email addresses that aren't fixed, you must select the email source type for a file destination.</span></span> <span data-ttu-id="c4a94-121">A következő értékek használhatók: **Vevő**, **Szállító**, **Potenciális vevő**, **Kapcsolat**, **Versenytárs**, **Dolgozó**, **Kérelmező**, **Potenciális szállító** és **Nem engedélyezett szállító**.</span><span class="sxs-lookup"><span data-stu-id="c4a94-121">The following values are supported: **Customer**, **Vendor**, **Prospect**, **Contact**, **Competitor**, **Worker**, **Applicant**, **Prospective vendor**, and **Disallowed vendor**.</span></span> <span data-ttu-id="c4a94-122">Miután kiválasztott egy e-mail-forrástípust, használja az **E-mail származási fiókja** mező melletti gombot a **Képletszerkesztő** képernyő megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="c4a94-122">After you select an email source type, use the button next to the **Email source account** field to open the **Formula designer** form.</span></span> <span data-ttu-id="c4a94-123">Ez az űrlap olyan képlet csatolására használható, amely futásidőben visszatéríti a kiválasztott forrástípus **partnerfiókját** a feldolgozott dokumentumból az e-mail célhelyre.</span><span class="sxs-lookup"><span data-stu-id="c4a94-123">You can use this form to attach a formula that returns at runtime, the **party account** of the selected source type from the processed document to the email destination.</span></span>

<span data-ttu-id="c4a94-124">[![E-mail-forrásfiók konfigurálása](./media/ER_Destinations-EmailDefineAddressSource.png)](./media/ER_Destinations-EmailDefineAddressSource.png)</span><span class="sxs-lookup"><span data-stu-id="c4a94-124">[![Configure email source account](./media/ER_Destinations-EmailDefineAddressSource.png)](./media/ER_Destinations-EmailDefineAddressSource.png)</span></span>

<span data-ttu-id="c4a94-125">A receptúrák ER-konfigurációspecifikusak.</span><span class="sxs-lookup"><span data-stu-id="c4a94-125">Formulas are specific to the ER configuration.</span></span> <span data-ttu-id="c4a94-126">A **Receptúra** mezőben adja meg a vevői vagy szállítói féltípusra történő dokumentumspecifikus hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="c4a94-126">In the **Formula** field, enter a document-specific reference to a customer or vendor party type.</span></span> <span data-ttu-id="c4a94-127">Gépelés helyett megkeresheti a vevőt vagy szállítót reprezentáló adatforrás-csomópontokat, és az **Adatforrás hozzáadása** lehetőséget kiválasztva frissítheti a receptúrát.</span><span class="sxs-lookup"><span data-stu-id="c4a94-127">Instead of typing, you can find the data source node that represents the customer or vendor account, and then select **Add data source** to update the formula.</span></span> <span data-ttu-id="c4a94-128">Például ha az **ISO 20022 Jóváírás átutalása** konfigurációt használja, a szállító számláját reprezentáló csomópont a következő: `'\$PaymentsForCoveringLetter'.Creditor.Identification.SourceID`.</span><span class="sxs-lookup"><span data-stu-id="c4a94-128">For example, if you use the **ISO 20022 Credit Transfer** configuration, the node that represents a vendor account is `'\$PaymentsForCoveringLetter'.Creditor.Identification.SourceID`.</span></span>

<span data-ttu-id="c4a94-129">Ha karakterláncot ad meg, például `"DE-001"`, és ment egy receptúrát, akkor a program elküld egy e-mailt a szállító kapcsolattartójának: **DE-001**.</span><span class="sxs-lookup"><span data-stu-id="c4a94-129">If you enter a string value, such as `"DE-001"`, and save a formula, an email will be sent to the contact person of the vendor, **DE-001**.</span></span>


<span data-ttu-id="c4a94-130">[![ER-receptúra szerkesztő oldala](./media/ER_Destinations-EmailDefineAddressSourceFormula.png)](./media/ER_Destinations-EmailDefineAddressSourceFormula.png)</span><span class="sxs-lookup"><span data-stu-id="c4a94-130">[![ER formula designer page](./media/ER_Destinations-EmailDefineAddressSourceFormula.png)](./media/ER_Destinations-EmailDefineAddressSourceFormula.png)</span></span>

<span data-ttu-id="c4a94-131">[![E-mail-forrásattribútum-fiók konfigurálása](./media/ER_Destinations-EmailDefineAddressSourceAttributes.png)](./media/ER_Destinations-EmailDefineAddressSourceAttributes.png)</span><span class="sxs-lookup"><span data-stu-id="c4a94-131">[![Configure email source attributes account](./media/ER_Destinations-EmailDefineAddressSourceAttributes.png)](./media/ER_Destinations-EmailDefineAddressSourceAttributes.png)</span></span>



### <a name="configuration-email"></a><span data-ttu-id="c4a94-132">Konfigurációs e-mail</span><span class="sxs-lookup"><span data-stu-id="c4a94-132">Configuration email</span></span>

<span data-ttu-id="c4a94-133">Használja ezt az e-mail-típust, ha a használt konfiguráció tartalmaz egy **e-mail-címet** visszatérítő csomópontot az adatforrásokban.</span><span class="sxs-lookup"><span data-stu-id="c4a94-133">Use this email type if the configuration that you use has a node in the data sources that returns an **email address**.</span></span> <span data-ttu-id="c4a94-134">A Képletszerkesztő adatforrásainak és függvényeinek használatával helyesen formázott e-mail-címet állíthat elő.</span><span class="sxs-lookup"><span data-stu-id="c4a94-134">You can use data sources and functions in the formula designer to get a correctly formatted email address.</span></span> <span data-ttu-id="c4a94-135">Például ha az **ISO 20022 Jóváírás átutalása** konfigurációt használja, a szállító kapcsolattartójának e-mail-címét reprezentáló csomópont a következő: `'$PaymentsForCoveringLetter'.Creditor.ContactDetails.Email`.</span><span class="sxs-lookup"><span data-stu-id="c4a94-135">For example, if you use the **ISO 20022 Credit Transfer** configuration, the node that represents an email address of a vendor's contact person is `'$PaymentsForCoveringLetter'.Creditor.ContactDetails.Email`.</span></span>

<span data-ttu-id="c4a94-136">[![E-mail-cím forrásának konfigurálása](./media/ER_Destinations-EmailDefineAddressSource2.png)](./media/ER_Destinations-EmailDefineAddressSource2.png)</span><span class="sxs-lookup"><span data-stu-id="c4a94-136">[![Configure email address source](./media/ER_Destinations-EmailDefineAddressSource2.png)](./media/ER_Destinations-EmailDefineAddressSource2.png)</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c4a94-137">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="c4a94-137">Additional resources</span></span>

- [<span data-ttu-id="c4a94-138">Elektronikus jelentéskészítés (ER) áttekintése</span><span class="sxs-lookup"><span data-stu-id="c4a94-138">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="c4a94-139">Elektronikus jelentéskészítés (ER) céljai</span><span class="sxs-lookup"><span data-stu-id="c4a94-139">Electronic reporting (ER) destinations</span></span>](electronic-reporting-destinations.md)
- [<span data-ttu-id="c4a94-140">Képletszerkesztő elektronikus jelentésekhez (ER)</span><span class="sxs-lookup"><span data-stu-id="c4a94-140">Formula designer in Electronic reporting (ER)</span></span>](general-electronic-reporting-formula-designer.md)
