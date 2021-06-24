---
title: Pénztár (POS) alkalmazás és felhasználói nyelvi beállítások
description: Ez a témakör azt mutatja be, hogyan végezhető el a Modern POS (MPOS) és a felhőalapú POS nyelvének módosítása.
author: jblucher
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmWorker, RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.custom: 78891
ms.assetid: 0030940c-e0a5-4345-9511-8c3bd1f487ad
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: bdd03dff359e7c2799eff53b0e999580ce8b1c06
ms.sourcegitcommit: 74e47075eab2b0b28f82b0d57f439719847ecb01
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/07/2021
ms.locfileid: "6193103"
---
# <a name="point-of-sale-pos-application-and-user-language-settings"></a><span data-ttu-id="d2dc9-103">Pénztár (POS) alkalmazás és felhasználói nyelvi beállítások</span><span class="sxs-lookup"><span data-stu-id="d2dc9-103">Point of sale (POS) application and user language settings</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d2dc9-104">Ez a témakör azt mutatja be, hogyan végezhető el a Modern POS (MPOS) és a felhőalapú POS nyelvének módosítása.</span><span class="sxs-lookup"><span data-stu-id="d2dc9-104">This topic describes how to change language settings in Modern POS (MPOS) and Cloud POS.</span></span>

## <a name="overview"></a><span data-ttu-id="d2dc9-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="d2dc9-105">Overview</span></span>
<span data-ttu-id="d2dc9-106">A Modern POS (MPOS) és a felhőalapú POS támogatja az olyan környezeteket, ahol a nyelvi beállítás és a fordítás eltérhetnek egymástól az üzlet- és felhasználói beállításoknál.</span><span class="sxs-lookup"><span data-stu-id="d2dc9-106">Modern POS (MPOS) and Cloud POS support environments where language settings and translations can vary between the store and user settings.</span></span> <span data-ttu-id="d2dc9-107">Például az üzlet olyan területen is lehet, ahol az angol a leggyakrabban használt nyelv az ügyfelek körében, de egyes munkavállalók inkább francia fordításban szeretnék használni az alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="d2dc9-107">For example, the store could be located in a region where English is most common for their customers, but some workers prefer to use the application with French translations.</span></span>

## <a name="data-language"></a><span data-ttu-id="d2dc9-108">Adatnyelv</span><span class="sxs-lookup"><span data-stu-id="d2dc9-108">Data language</span></span>

<span data-ttu-id="d2dc9-109">A felhasználói beállításoktól függetlenül az MPOS és a felhőalapú POS mindig az üzlet nyelvi beállításait használja az adatokhoz használt fordítások meghatározásához.</span><span class="sxs-lookup"><span data-stu-id="d2dc9-109">Regardless of the user's settings, MPOS and Cloud POS will always use the store's language settings to determine the translations used for data.</span></span> <span data-ttu-id="d2dc9-110">Ez biztosítja, hogy a felhasználók és a vevők következetes felhasználói élményt kapjanak.</span><span class="sxs-lookup"><span data-stu-id="d2dc9-110">This will ensure that all users and customers will have a consistent experience.</span></span> <span data-ttu-id="d2dc9-111">Néhány példa az adatokra:</span><span class="sxs-lookup"><span data-stu-id="d2dc9-111">Examples of data include:</span></span>

- <span data-ttu-id="d2dc9-112">Termékek</span><span class="sxs-lookup"><span data-stu-id="d2dc9-112">Products</span></span>
- <span data-ttu-id="d2dc9-113">Sorattribútumok értékei</span><span class="sxs-lookup"><span data-stu-id="d2dc9-113">Attributes and values</span></span>
- <span data-ttu-id="d2dc9-114">Kategórianév</span><span class="sxs-lookup"><span data-stu-id="d2dc9-114">Category names</span></span>
- <span data-ttu-id="d2dc9-115">Nyomtatott vagy e-mailben küldött nyugták</span><span class="sxs-lookup"><span data-stu-id="d2dc9-115">Printed or emailed transaction receipts</span></span>
- <span data-ttu-id="d2dc9-116">Fizetési mód neve</span><span class="sxs-lookup"><span data-stu-id="d2dc9-116">Payment method names</span></span>
- <span data-ttu-id="d2dc9-117">Sormegjelenítési paraméterek</span><span class="sxs-lookup"><span data-stu-id="d2dc9-117">Line display messages</span></span>

<span data-ttu-id="d2dc9-118">Az üzlet nyelve lesz a fő POS bejelentkezési képernyő nyelve is, mivel a felhasználó a bejelentkezés előtt nem ismert.</span><span class="sxs-lookup"><span data-stu-id="d2dc9-118">The store's language will also be used for the main POS login screen, since the user is not known before logging in.</span></span> <span data-ttu-id="d2dc9-119">Ha az üzlet nyelvéhez nem érhető el fordítás, a pénztár visszaáll a vállalat nyelvére.</span><span class="sxs-lookup"><span data-stu-id="d2dc9-119">If a translation is not available for the store's language, the POS will revert to the company's language.</span></span>

### <a name="configuring-the-stores-language-setting"></a><span data-ttu-id="d2dc9-120">Az üzlet nyelvbeállítás konfigurálása</span><span class="sxs-lookup"><span data-stu-id="d2dc9-120">Configuring the store's language setting</span></span>

<span data-ttu-id="d2dc9-121">Az üzlet nyelvének beállítása a **Minden üzlet** részben történik az **Üzlet** oldalon az **Általános &gt; Területi beállítások &gt; Nyelv** részben.</span><span class="sxs-lookup"><span data-stu-id="d2dc9-121">The store's language setting is set from **All stores** on the **Store** page under **General &gt; Regional Settings &gt; Language**.</span></span> <span data-ttu-id="d2dc9-122">Használja a legördülő menüt minden egyes üzlet nyelvének kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="d2dc9-122">Use the drop-down list to choose the language for each store.</span></span>

## <a name="user-interface-language"></a><span data-ttu-id="d2dc9-123">Felhasználói felület karbantartása</span><span class="sxs-lookup"><span data-stu-id="d2dc9-123">User interface language</span></span>

<span data-ttu-id="d2dc9-124">A POS-felhasználó nyelvi beállítás határozza meg a felhasználói felületen használt fordításokat.</span><span class="sxs-lookup"><span data-stu-id="d2dc9-124">The POS user's language setting determines the translations used in the application user interface.</span></span> <span data-ttu-id="d2dc9-125">Ez magában foglalja az összes feliratot, menüt és listát, amelyek nem minősülnek adatnak.</span><span class="sxs-lookup"><span data-stu-id="d2dc9-125">This includes all labels, menus, and lists that are not considered data.</span></span> <span data-ttu-id="d2dc9-126">Egyetlen kivétel ez alól a POS-gombrácson megjelenő szöveg.</span><span class="sxs-lookup"><span data-stu-id="d2dc9-126">One exception is the text that is displayed on POS button grids.</span></span> <span data-ttu-id="d2dc9-127">A gombrácsok nem támogatják a fordításokat, így mindig a gombon definiált szöveget jelenítik meg.</span><span class="sxs-lookup"><span data-stu-id="d2dc9-127">The button grids don't support translations, so they will always show the text as defined on the button.</span></span> <span data-ttu-id="d2dc9-128">A lefordított gombok támogatásához külön gombrácsokat kell másolni és karbantartani, valamint a felhasználókhoz rendelni szükség szerint.</span><span class="sxs-lookup"><span data-stu-id="d2dc9-128">In order to support translated buttons, you'll have to copy and maintain separate button grids and assign them to the users as appropriate.</span></span>

### <a name="configuring-the-users-language-setting"></a><span data-ttu-id="d2dc9-129">Az üzlet nyelvbeállítás konfigurálása</span><span class="sxs-lookup"><span data-stu-id="d2dc9-129">Configuring the user's language setting</span></span>

<span data-ttu-id="d2dc9-130">A POS felhasználói nyelv beállítása a **Minden dolgozó** helyről történik a **Dolgozó** lap **Kiskereskedelem és kereskedelem &gt; Nyelv** részében.</span><span class="sxs-lookup"><span data-stu-id="d2dc9-130">The POS user's language setting is set from **All workers** on the **Worker** page under **Retail and Commerce &gt; Language**.</span></span> <span data-ttu-id="d2dc9-131">Ez nem a fő profil lapon van beállítva. A pénztár nem használja ezt a beállítást.</span><span class="sxs-lookup"><span data-stu-id="d2dc9-131">It is not set on the main Profile tab. This setting is not used by POS.</span></span> <span data-ttu-id="d2dc9-132">A felhasználó nyelve nincs beállítva, vagy a változó értéke egy nyelvet Ha fordítások nem állnak rendelkezésre, ha az üzlet nyelv visszaáll a POS-nál.</span><span class="sxs-lookup"><span data-stu-id="d2dc9-132">If the user's language is not set or it is set to a language where translations are not available, the POS will revert to the store's language.</span></span>

| &nbsp;      | <span data-ttu-id="d2dc9-133">Felhasználói felület nyelv</span><span class="sxs-lookup"><span data-stu-id="d2dc9-133">UI language</span></span>                | <span data-ttu-id="d2dc9-134">Adatok nyelv (termékek nyugtaformátumokat, sorkijelző, stb.)</span><span class="sxs-lookup"><span data-stu-id="d2dc9-134">Data language (products, receipt formats, line display, etc.)</span></span> |
|-------------|----------------------------|---------------------------------------------------------------|
| <span data-ttu-id="d2dc9-135">**Vállalat**</span><span class="sxs-lookup"><span data-stu-id="d2dc9-135">**Company**</span></span> | <span data-ttu-id="d2dc9-136">Alapértelmezett</span><span class="sxs-lookup"><span data-stu-id="d2dc9-136">Default</span></span>                    | <span data-ttu-id="d2dc9-137">Alapértelmezett</span><span class="sxs-lookup"><span data-stu-id="d2dc9-137">Default</span></span>                                                       |
| <span data-ttu-id="d2dc9-138">**Üzlet**</span><span class="sxs-lookup"><span data-stu-id="d2dc9-138">**Store**</span></span>   | <span data-ttu-id="d2dc9-139">Felülbírálja a vállalat</span><span class="sxs-lookup"><span data-stu-id="d2dc9-139">Overrides company</span></span>          | <span data-ttu-id="d2dc9-140">Felülbírálja a vállalat</span><span class="sxs-lookup"><span data-stu-id="d2dc9-140">Overrides company</span></span>                                             |
| <span data-ttu-id="d2dc9-141">**Felhasználó**</span><span class="sxs-lookup"><span data-stu-id="d2dc9-141">**User**</span></span>    | <span data-ttu-id="d2dc9-142">Felülbírálás üzlet vagy a vállalat</span><span class="sxs-lookup"><span data-stu-id="d2dc9-142">Overrides store or company</span></span> | <span data-ttu-id="d2dc9-143">Soha</span><span class="sxs-lookup"><span data-stu-id="d2dc9-143">Never</span></span>                                                         |


[!INCLUDE[footer-include](../includes/footer-banner.md)]