---
title: Állapotok és életciklus-dokumentálás
description: Ez a témakör a Microsoft Dynamics 365 Commerce oldalelemeinek különböző dokumentumállapotait mutatja be.
author: phinneyridge
manager: annbe
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 8aad7ef8425e46182c669686710dfc178abc418f
ms.sourcegitcommit: 83ec80382bfeb693d5c5949b6f65296bd50eed12
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/09/2020
ms.locfileid: "3974030"
---
# <a name="document-states-and-lifecycle"></a><span data-ttu-id="70cb0-103">Állapotok és életciklus-dokumentálás</span><span class="sxs-lookup"><span data-stu-id="70cb0-103">Document states and lifecycle</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="70cb0-104">Ez a témakör a Microsoft Dynamics 365 Commerce oldalelemeinek különböző dokumentumállapotait mutatja be.</span><span class="sxs-lookup"><span data-stu-id="70cb0-104">This topic covers the various document states of page elements in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="document-state-descriptions"></a><span data-ttu-id="70cb0-105">Dokumentumállapotok leírásai</span><span class="sxs-lookup"><span data-stu-id="70cb0-105">Document state descriptions</span></span>

<span data-ttu-id="70cb0-106">Az [Oldalelemek](page-elements-overview.md) témakör a tartalomkezelő rendszerben (CMS) található, különböző típusú dokumentumokat sorolja fel.</span><span class="sxs-lookup"><span data-stu-id="70cb0-106">The [Page elements](page-elements-overview.md) topic lists various documents types in the content management system (CMS).</span></span> <span data-ttu-id="70cb0-107">Ezek a dokumentumtípusok a szerkesztési eszközben számos állapotot felvehetnek.</span><span class="sxs-lookup"><span data-stu-id="70cb0-107">These document types can have several states in the authoring tool.</span></span> <span data-ttu-id="70cb0-108">A dokumentumállapotok segítenek az adatütközések elkerülésében és a verziókövetés betartatásában.</span><span class="sxs-lookup"><span data-stu-id="70cb0-108">The document states help prevent data conflicts and enforce version control.</span></span> <span data-ttu-id="70cb0-109">Meghatározzák, hogy kik módosíthatják a dokumentumokat, mikor módosíthatók a dokumentumok, és a változtatások mikor lesznek mások által is megtekinthetők.</span><span class="sxs-lookup"><span data-stu-id="70cb0-109">They determine who can change the documents, when the documents can be changed, and when changes can be viewed by other people.</span></span>

<span data-ttu-id="70cb0-110">A következő táblázat bemutatja a Commerce oldalelemeinek lehetséges dokumentumállapotait.</span><span class="sxs-lookup"><span data-stu-id="70cb0-110">The following table shows the possible document states of page elements in Commerce.</span></span>

| <span data-ttu-id="70cb0-111">Dokumentum állapota</span><span class="sxs-lookup"><span data-stu-id="70cb0-111">Document state</span></span>      | <span data-ttu-id="70cb0-112">Webhelykészítő művelet</span><span class="sxs-lookup"><span data-stu-id="70cb0-112">Site builder action</span></span>        | <span data-ttu-id="70cb0-113">Leírás</span><span class="sxs-lookup"><span data-stu-id="70cb0-113">Description</span></span>                                                  |
| ------------------- | -------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="70cb0-114">Felelősnél</span><span class="sxs-lookup"><span data-stu-id="70cb0-114">Checked out</span></span>         | <span data-ttu-id="70cb0-115">Válassza ki a **Szerkesztés** opciót.</span><span class="sxs-lookup"><span data-stu-id="70cb0-115">Select **Edit** .</span></span>           | <span data-ttu-id="70cb0-116">Ön kivette a vonatkozó dokumentumot.</span><span class="sxs-lookup"><span data-stu-id="70cb0-116">The applicable document is checked out to you.</span></span> <span data-ttu-id="70cb0-117">Amikor egy dokumentum ebben az állapotban van, nem módosíthatja a többi hitelesített rendszerfelhasználó, és a dokumentumban elvégzett módosítások csak az Ön számára láthatók.</span><span class="sxs-lookup"><span data-stu-id="70cb0-117">While a document is in this state, it can't be changed by other authenticated system users, and any changes that you make to the document are visible only to you.</span></span> |
| <span data-ttu-id="70cb0-118">Mentve</span><span class="sxs-lookup"><span data-stu-id="70cb0-118">Saved</span></span>               | <span data-ttu-id="70cb0-119">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="70cb0-119">Select **Save** .</span></span>           | <span data-ttu-id="70cb0-120">A kivett dokumentum módosításait az adatbázisba menti a program, de a dokumentum még nincs beküldve vagy közzétéve.</span><span class="sxs-lookup"><span data-stu-id="70cb0-120">Changes that have been made to a checked-out document are saved to the database, but the document isn't yet checked in or published.</span></span> <span data-ttu-id="70cb0-121">A mentett változtatások nem láthatók a többi hitelesített rendszerfelhasználó számára mindaddig a szerző ki nem választja a **Szerkesztés befejezése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="70cb0-121">The saved changes aren't visible to other authenticated system users until the author selects **Finish editing** .</span></span> <span data-ttu-id="70cb0-122">Ezek addig nem láthatók a külső felhasználók számára, amíg nem teszik közzé.</span><span class="sxs-lookup"><span data-stu-id="70cb0-122">They aren't visible to external users until the item is published.</span></span> |
| <span data-ttu-id="70cb0-123">Elvetett kivétel</span><span class="sxs-lookup"><span data-stu-id="70cb0-123">Discarded check out</span></span> | <span data-ttu-id="70cb0-124">Válassza a **Módosítások elvetése** parancsot.</span><span class="sxs-lookup"><span data-stu-id="70cb0-124">Select **Discard edits** .</span></span>  | <span data-ttu-id="70cb0-125">A kivett dokumentum minden módosítását elveti, és a rendszer visszaállítja az utolsó beküldött verzióra.</span><span class="sxs-lookup"><span data-stu-id="70cb0-125">All changes to the checked-out document are discarded, and the item reverts to the last version that was checked in.</span></span> |
| <span data-ttu-id="70cb0-126">Bejelentkezve</span><span class="sxs-lookup"><span data-stu-id="70cb0-126">Checked in</span></span>          | <span data-ttu-id="70cb0-127">Válassza a **Szerkesztés befejezése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="70cb0-127">Select **Finish editing** .</span></span> | <span data-ttu-id="70cb0-128">A szerkesztett dokumentum be van küldve.</span><span class="sxs-lookup"><span data-stu-id="70cb0-128">The edited document is checked in.</span></span> <span data-ttu-id="70cb0-129">Minden változtatás látható a többi hitelesített rendszerfelhasználó számára is, és ezek a felhasználók is módosíthatják a dokumentumot.</span><span class="sxs-lookup"><span data-stu-id="70cb0-129">All changes are visible to other authenticated system users, and those users can then edit the document.</span></span> <span data-ttu-id="70cb0-130">Az egyes beadások az elemek előzményeiben létrehoznak egy dokumentumverzió-rekordot.</span><span class="sxs-lookup"><span data-stu-id="70cb0-130">Each check-in creates a document version record in the item's history.</span></span> |
| <span data-ttu-id="70cb0-131">Közzétéve</span><span class="sxs-lookup"><span data-stu-id="70cb0-131">Published</span></span>           | <span data-ttu-id="70cb0-132">Válassza a **Közzététel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="70cb0-132">Select **Publish** .</span></span>        | <span data-ttu-id="70cb0-133">A program közzéteszi a dokumentumot, és a változtatások át lesznek küldve az élő webhelyre, és külső felhasználók számára is láthatóvá válnak.</span><span class="sxs-lookup"><span data-stu-id="70cb0-133">The document is published, and the changes are pushed to your live site and become discoverable by external users.</span></span> <span data-ttu-id="70cb0-134">A cikkek csak akkor tehetők közzé, ha először be lettek küldve **Szerkesztés befejezése** lehetőség kiválasztásával.</span><span class="sxs-lookup"><span data-stu-id="70cb0-134">Items can be published only if they have first been checked in by selecting **Finish editing** .</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="70cb0-135">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="70cb0-135">Additional resources</span></span>

[<span data-ttu-id="70cb0-136">A tartalom hozzáadásának módjai</span><span class="sxs-lookup"><span data-stu-id="70cb0-136">Ways to add content</span></span>](add-manage-content.md)

[<span data-ttu-id="70cb0-137">Oldal modellszószedete</span><span class="sxs-lookup"><span data-stu-id="70cb0-137">Page model glossary</span></span>](page-elements-overview.md)

[<span data-ttu-id="70cb0-138">A közzétételi csoportokkal végzett munka</span><span class="sxs-lookup"><span data-stu-id="70cb0-138">Work with publish groups</span></span>](publish-groups.md)

[<span data-ttu-id="70cb0-139">Csatornaközi megosztás engedélyezése és használata</span><span class="sxs-lookup"><span data-stu-id="70cb0-139">Enable and use cross-channel sharing</span></span>](cross-channel-sharing.md)

[<span data-ttu-id="70cb0-140">Modulok használata</span><span class="sxs-lookup"><span data-stu-id="70cb0-140">Work with modules</span></span>](work-with-modules.md)

[<span data-ttu-id="70cb0-141">Töredékek használata</span><span class="sxs-lookup"><span data-stu-id="70cb0-141">Work with fragments</span></span>](work-with-fragments.md)

[<span data-ttu-id="70cb0-142">Sablonok és elrendezések áttekintése</span><span class="sxs-lookup"><span data-stu-id="70cb0-142">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="70cb0-143">Webhely-navigáció testreszabása</span><span class="sxs-lookup"><span data-stu-id="70cb0-143">Customize site navigation</span></span>](customize-site-navigation.md)
