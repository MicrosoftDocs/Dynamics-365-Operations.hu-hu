---
title: "POS alkalmazást, és a felhasználó nyelvi beállítások"
description: "Ez a témakör azt mutatja be, hogyan végezhető el a Retail Modern POS (MPOS) és a felhőalapú POS nyelvének módosítása."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: HcmWorker, RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 78891
ms.assetid: 0030940c-e0a5-4345-9511-8c3bd1f487ad
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 20d28e22e4e89d0d864a0cbeaadeb568e73e223e
ms.openlocfilehash: a9b2d8dec04ed3653b2ebcfbd2492fc40d96b77b
ms.contentlocale: hu-hu
ms.lasthandoff: 06/29/2017



---

# <a name="pos-application-and-user-language-settings"></a><span data-ttu-id="c6f8b-103">POS alkalmazást, és a felhasználó nyelvi beállítások</span><span class="sxs-lookup"><span data-stu-id="c6f8b-103">POS application and user language settings</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="c6f8b-104">Ez a témakör azt mutatja be, hogyan végezhető el a Retail Modern POS (MPOS) és a felhőalapú POS nyelvének módosítása.</span><span class="sxs-lookup"><span data-stu-id="c6f8b-104">This topic describes how to change language settings in Retail Modern POS (MPOS) and Cloud POS.</span></span>

<a name="overview"></a><span data-ttu-id="c6f8b-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="c6f8b-105">Overview</span></span>
========

<span data-ttu-id="c6f8b-106">A Retail Modern POS (MPOS) és a felhőalapú POS támogatja az olyan környezeteket, ahol a nyelvi beállítás és a fordítás eltérhetnek egymástól az üzlet- és felhasználói beállításoknál.</span><span class="sxs-lookup"><span data-stu-id="c6f8b-106">Retail Modern POS (MPOS) and Cloud POS support environments where language settings and translations can vary between the store and user settings.</span></span> <span data-ttu-id="c6f8b-107">Például az üzlet olyan területen is lehet, ahol az angol a leggyakrabban használt nyelv az ügyfelek körében, de egyes munkavállalók inkább francia fordításban szeretnék használni az alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="c6f8b-107">For example, the store could be located in a region where English is most common for their customers, but some workers prefer to use the application with French translations.</span></span>

## <a name="data-language"></a><span data-ttu-id="c6f8b-108">Adatnyelv</span><span class="sxs-lookup"><span data-stu-id="c6f8b-108">Data language</span></span>
<span data-ttu-id="c6f8b-109">A felhasználói beállításoktól függetlenül az MPOS és a felhőalapú POS mindig az üzlet nyelvi beállításait használja az adatokhoz használt fordítások meghatározásához.</span><span class="sxs-lookup"><span data-stu-id="c6f8b-109">Regardless of the user’s settings, MPOS and Cloud POS will always use the store's language settings to determine the translations used for data.</span></span> <span data-ttu-id="c6f8b-110">Ez biztosítja, hogy a felhasználók és a vevők következetes felhasználói élményt kapjanak.</span><span class="sxs-lookup"><span data-stu-id="c6f8b-110">This will ensure that all users and customers will have a consistent experience.</span></span>  <span data-ttu-id="c6f8b-111">Néhány példa az adatokra:</span><span class="sxs-lookup"><span data-stu-id="c6f8b-111">Examples of data include:</span></span>

-   <span data-ttu-id="c6f8b-112">Termékek</span><span class="sxs-lookup"><span data-stu-id="c6f8b-112">Products</span></span>
-   <span data-ttu-id="c6f8b-113">Sorattribútumok értékei</span><span class="sxs-lookup"><span data-stu-id="c6f8b-113">Attributes and values</span></span>
-   <span data-ttu-id="c6f8b-114">Kategórianév</span><span class="sxs-lookup"><span data-stu-id="c6f8b-114">Category names</span></span>
-   <span data-ttu-id="c6f8b-115">Nyomtatott vagy e-mailben küldött nyugták</span><span class="sxs-lookup"><span data-stu-id="c6f8b-115">Printed or emailed transaction receipts</span></span>
-   <span data-ttu-id="c6f8b-116">Fizetési mód neve</span><span class="sxs-lookup"><span data-stu-id="c6f8b-116">Payment method names</span></span>
-   <span data-ttu-id="c6f8b-117">Sormegjelenítési paraméterek</span><span class="sxs-lookup"><span data-stu-id="c6f8b-117">Line display messages</span></span>

<span data-ttu-id="c6f8b-118">Az üzlet nyelve lesz a fő POS bejelentkezési képernyő nyelve is, mivel a felhasználó a bejelentkezés előtt nem ismert.</span><span class="sxs-lookup"><span data-stu-id="c6f8b-118">The store’s language will also be used for the main POS login screen, since the user is not known before logging in.</span></span> <span data-ttu-id="c6f8b-119">Ha az üzlet nyelvéhez nem érhető el fordítás, a pénztár visszaáll a vállalat nyelvére.</span><span class="sxs-lookup"><span data-stu-id="c6f8b-119">If a translation is not available for the store’s language, the POS will revert to the company’s language.</span></span>

### <a name="configuring-the-stores-language-setting"></a><span data-ttu-id="c6f8b-120">Az üzlet nyelvbeállítás konfigurálása</span><span class="sxs-lookup"><span data-stu-id="c6f8b-120">Configuring the store’s language setting</span></span>

<span data-ttu-id="c6f8b-121">Az üzlet nyelvének beállítása a **Minden kiskereskedelmi egység** részben történik a **Kiskereskedelmi üzlet** oldalon az **Általános &gt; Területi beállítások &gt; Nyelv részben.</span><span class="sxs-lookup"><span data-stu-id="c6f8b-121">The store’s language setting is set from **All retail stores** on the **Retail Store** page under **General &gt; Regional Settings &gt; Language.</span></span> <span data-ttu-id="c6f8b-122">** Használja a legördülő menüt minden egyes üzlet nyelvének kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="c6f8b-122">**Use the drop down to choose the language for each store.</span></span>

## <a name="user-interface-language"></a><span data-ttu-id="c6f8b-123">Felhasználói felület karbantartása</span><span class="sxs-lookup"><span data-stu-id="c6f8b-123">User interface language</span></span>
<span data-ttu-id="c6f8b-124">A POS-felhasználó nyelvi beállítás határozza meg a felhasználói felületen használt fordításokat.</span><span class="sxs-lookup"><span data-stu-id="c6f8b-124">The POS user’s language setting determines the translations used in the application user interface.</span></span> <span data-ttu-id="c6f8b-125">Ez magában foglalja az összes feliratot, menüt és listát, amelyek nem minősülnek adatnak.</span><span class="sxs-lookup"><span data-stu-id="c6f8b-125">This includes all labels, menus, and lists that are not considered data.</span></span> <span data-ttu-id="c6f8b-126">Egyetlen kivétel ez alól a POS-gombrácson megjelenő szöveg.</span><span class="sxs-lookup"><span data-stu-id="c6f8b-126">One exception is the text that is displayed on POS button grids.</span></span> <span data-ttu-id="c6f8b-127">A gombrácsok nem támogatják a fordításokat, így mindig a gombon definiált szöveget jelenítik meg.</span><span class="sxs-lookup"><span data-stu-id="c6f8b-127">The button grids don't support translations, so they will always show the text as defined on the button.</span></span> <span data-ttu-id="c6f8b-128">A lefordított gombok támogatásához külön gombrácsokat kell másolni és karbantartani, valamint a felhasználókhoz rendelni szükség szerint.</span><span class="sxs-lookup"><span data-stu-id="c6f8b-128">In order to support translated buttons, you'll have to copy and maintain separate button grids and assign them to the users as appropriate.</span></span>

### <a name="configuring-the-users-language-setting"></a><span data-ttu-id="c6f8b-129">Az üzlet nyelvbeállítás konfigurálása</span><span class="sxs-lookup"><span data-stu-id="c6f8b-129">Configuring the user’s language setting</span></span>

<span data-ttu-id="c6f8b-130">A pénztárfelhasználó nyelvének beállítása a **Minden dolgozó** részben történik a **Dolgozó** lapon, a **Kiskereskedelem &gt; Nyelv** alatt.</span><span class="sxs-lookup"><span data-stu-id="c6f8b-130">The POS user’s language setting is set from **All workers** on the **Worker** page under **Retail &gt; Language**.</span></span>  <span data-ttu-id="c6f8b-131">Nincs beállítva a fő Profil lapon.</span><span class="sxs-lookup"><span data-stu-id="c6f8b-131">It is not set on the main Profile tab.</span></span>  <span data-ttu-id="c6f8b-132">Ez a beállítás nincs használatban a pénztár esetében.</span><span class="sxs-lookup"><span data-stu-id="c6f8b-132">This setting is not used by POS.</span></span> <span data-ttu-id="c6f8b-133">A felhasználó nyelve nincs beállítva, vagy a változó értéke egy nyelvet Ha fordítások nem állnak rendelkezésre, ha az üzlet nyelv visszaáll a POS-nál.</span><span class="sxs-lookup"><span data-stu-id="c6f8b-133">If the user’s language is not set or it is set to a language where translations are not available, the POS will revert to the store’s language.</span></span>  

|             |                            |                                                                   |
|-------------|----------------------------|-------------------------------------------------------------------|
| <span data-ttu-id="c6f8b-134">** **</span><span class="sxs-lookup"><span data-stu-id="c6f8b-134">** **</span></span>       | <span data-ttu-id="c6f8b-135">**Felhasználói felület nyelve** ** **</span><span class="sxs-lookup"><span data-stu-id="c6f8b-135">**UI language** ** **</span></span>      | <span data-ttu-id="c6f8b-136">**Adatok nyelv (termékek nyugtaformátumokat, sorkijelző, stb.)**</span><span class="sxs-lookup"><span data-stu-id="c6f8b-136">**Data language (products, receipt formats, line display, etc.)**</span></span> |
| <span data-ttu-id="c6f8b-137">**Vállalat**</span><span class="sxs-lookup"><span data-stu-id="c6f8b-137">**Company**</span></span> | <span data-ttu-id="c6f8b-138">Alapértelmezett</span><span class="sxs-lookup"><span data-stu-id="c6f8b-138">Default</span></span>                    | <span data-ttu-id="c6f8b-139">Alapértelmezett</span><span class="sxs-lookup"><span data-stu-id="c6f8b-139">Default</span></span>                                                           |
| <span data-ttu-id="c6f8b-140">**Üzlet**</span><span class="sxs-lookup"><span data-stu-id="c6f8b-140">**Store**</span></span>   | <span data-ttu-id="c6f8b-141">Felülbírálja a vállalat</span><span class="sxs-lookup"><span data-stu-id="c6f8b-141">Overrides company</span></span>          | <span data-ttu-id="c6f8b-142">Felülbírálja a vállalat</span><span class="sxs-lookup"><span data-stu-id="c6f8b-142">Overrides company</span></span>                                                 |
| <span data-ttu-id="c6f8b-143">**Felhasználó**</span><span class="sxs-lookup"><span data-stu-id="c6f8b-143">**User**</span></span>    | <span data-ttu-id="c6f8b-144">Felülbírálás üzlet vagy a vállalat</span><span class="sxs-lookup"><span data-stu-id="c6f8b-144">Overrides store or company</span></span> | <span data-ttu-id="c6f8b-145">Soha</span><span class="sxs-lookup"><span data-stu-id="c6f8b-145">Never</span></span>                                                             |






