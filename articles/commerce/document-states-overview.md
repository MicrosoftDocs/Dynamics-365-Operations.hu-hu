---
title: Állapotok és életciklus-dokumentálás
description: Ez a témakör a Microsoft Dynamics 365 Commerce oldalelemeinek különböző dokumentumállapotait mutatja be.
author: phinneyridge
manager: annbe
ms.date: 12/12/2019
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
ms.openlocfilehash: edb81efc45fc5e7eed32cb7d9b8fda5ade987dd4
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914887"
---
# <a name="document-states-and-lifecycle"></a><span data-ttu-id="e7369-103">Állapotok és életciklus-dokumentálás</span><span class="sxs-lookup"><span data-stu-id="e7369-103">Document states and lifecycle</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="e7369-104">Ez a témakör a Microsoft Dynamics 365 Commerce oldalelemeinek különböző dokumentumállapotait mutatja be.</span><span class="sxs-lookup"><span data-stu-id="e7369-104">This topic covers the various document states of page elements in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="document-state-descriptions"></a><span data-ttu-id="e7369-105">Dokumentumállapotok leírásai</span><span class="sxs-lookup"><span data-stu-id="e7369-105">Document state descriptions</span></span>

<span data-ttu-id="e7369-106">Az [Oldalelemek](page-elements-overview.md) témakör a tartalomkezelő rendszerben (CMS) található, különböző típusú dokumentumokat sorolja fel.</span><span class="sxs-lookup"><span data-stu-id="e7369-106">The [Page elements](page-elements-overview.md) topic lists various documents types in the content management system (CMS).</span></span> <span data-ttu-id="e7369-107">Ezek a dokumentumtípusok a szerkesztési eszközben számos állapotot felvehetnek.</span><span class="sxs-lookup"><span data-stu-id="e7369-107">These document types can have several states in the authoring tool.</span></span> <span data-ttu-id="e7369-108">A dokumentumállapotok segítenek az adatütközések elkerülésében és a verziókövetés betartatásában.</span><span class="sxs-lookup"><span data-stu-id="e7369-108">The document states help prevent data conflicts and enforce version control.</span></span> <span data-ttu-id="e7369-109">Meghatározzák, hogy kik módosíthatják a dokumentumokat, mikor módosíthatók a dokumentumok, és a változtatások mikor lesznek mások által is megtekinthetők.</span><span class="sxs-lookup"><span data-stu-id="e7369-109">They determine who can change the documents, when the documents can be changed, and when changes can be viewed by other people.</span></span>

<span data-ttu-id="e7369-110">A következő táblázat bemutatja a Commerce oldalelemeinek lehetséges dokumentumállapotait.</span><span class="sxs-lookup"><span data-stu-id="e7369-110">The following table shows the possible document states of page elements in Commerce.</span></span>

| <span data-ttu-id="e7369-111">Dokumentum állapota</span><span class="sxs-lookup"><span data-stu-id="e7369-111">Document state</span></span> | <span data-ttu-id="e7369-112">Leírás</span><span class="sxs-lookup"><span data-stu-id="e7369-112">Description</span></span> |
|---|---|
| <span data-ttu-id="e7369-113">Lefoglalva</span><span class="sxs-lookup"><span data-stu-id="e7369-113">Checked out</span></span> | <span data-ttu-id="e7369-114">Ha Ön kivesz egy CMS-elemet, akkor azt más hitelesített rendszerfelhasználók nem szerkeszthetik.</span><span class="sxs-lookup"><span data-stu-id="e7369-114">When a CMS item is checked out to you, it can't be edited by any other authenticated system users.</span></span> <span data-ttu-id="e7369-115">Az elemen Ön által végzett módosításokat csak Ön láthatja.</span><span class="sxs-lookup"><span data-stu-id="e7369-115">Any changes that you make to the item are visible only to you.</span></span> |
| <span data-ttu-id="e7369-116">Bejelentkezve</span><span class="sxs-lookup"><span data-stu-id="e7369-116">Checked in</span></span> | <span data-ttu-id="e7369-117">Ha egy CMS-elemet beadnak, akkor az összes többi hitelesített rendszerfelhasználó láthatja az összes módosítást, valamint ezek a felhasználók ki is vehetik ezeket az elemeket, és szerkeszthetik őket.</span><span class="sxs-lookup"><span data-stu-id="e7369-117">When a CMS item is checked in, all changes are visible to other authenticated system users, and those users can then check out the item and edit it.</span></span> <span data-ttu-id="e7369-118">Az egyes beadások az elemek előzményeiben létrehoznak egy dokumentumverzió-rekordot.</span><span class="sxs-lookup"><span data-stu-id="e7369-118">Each check-in creates a document version record in the item's history.</span></span> |
| <span data-ttu-id="e7369-119">Közzétéve</span><span class="sxs-lookup"><span data-stu-id="e7369-119">Published</span></span> | <span data-ttu-id="e7369-120">Egy CMS-elem közzétételekor a rendszer feltolja az Ön éles webhelyére, és így az interneten a nem hitelesített külső felhasználók számára is felfedezhetővé válik.</span><span class="sxs-lookup"><span data-stu-id="e7369-120">When a CMS item is published, it's pushed to your live site and becomes discoverable on the internet by non-authenticated external users.</span></span> <span data-ttu-id="e7369-121">A cikkeket csak akkor lehet közzétenni, ha beadták őket.</span><span class="sxs-lookup"><span data-stu-id="e7369-121">Items can be published only if they have been checked in.</span></span> |
| <span data-ttu-id="e7369-122">Mentve</span><span class="sxs-lookup"><span data-stu-id="e7369-122">Saved</span></span> | <span data-ttu-id="e7369-123">A kivett CMS-elemek módosításait a program a CMS-be mentheti, mielőtt a elemet beadták vagy közzétették.</span><span class="sxs-lookup"><span data-stu-id="e7369-123">Changes that have been made to a checked-out CMS item can be saved to the CMS before the item is checked in or published.</span></span> <span data-ttu-id="e7369-124">Ezek a mentett változtatások nem láthatók a többi hitelesített rendszerfelhasználó számára mindaddig, amíg be nem adták az elemet.</span><span class="sxs-lookup"><span data-stu-id="e7369-124">These saved changes aren't visible to other authenticated system users until the item is checked in.</span></span> <span data-ttu-id="e7369-125">Ezek addig nem láthatók a külső felhasználók számára, amíg nem teszik közzé.</span><span class="sxs-lookup"><span data-stu-id="e7369-125">They aren't visible to external users until the item is published.</span></span> |
| <span data-ttu-id="e7369-126">Elvetett kivétel</span><span class="sxs-lookup"><span data-stu-id="e7369-126">Discarded check out</span></span> | <span data-ttu-id="e7369-127">Amikor egy kivett CMS-elemet ekvetnek, az összes mentett módosítás törlődik, és az elemet a rendszer visszaállítja arra a verzióra, amelyet legutóbb adtak be.</span><span class="sxs-lookup"><span data-stu-id="e7369-127">When a checked-out CMS item is discarded, all saved changes are deleted, and the item reverts to the version that was most recently checked in.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="e7369-128">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="e7369-128">Additional resources</span></span>

[<span data-ttu-id="e7369-129">A tartalom hozzáadásának módjai</span><span class="sxs-lookup"><span data-stu-id="e7369-129">Ways to add content</span></span>](add-manage-content.md)

[<span data-ttu-id="e7369-130">Oldal modellszószedete</span><span class="sxs-lookup"><span data-stu-id="e7369-130">Page model glossary</span></span>](page-elements-overview.md)

[<span data-ttu-id="e7369-131">A közzétételi csoportokkal végzett munka</span><span class="sxs-lookup"><span data-stu-id="e7369-131">Work with publish groups</span></span>](publish-groups.md)

[<span data-ttu-id="e7369-132">Modulok használata</span><span class="sxs-lookup"><span data-stu-id="e7369-132">Work with modules</span></span>](work-with-modules.md)

[<span data-ttu-id="e7369-133">Töredékek használata</span><span class="sxs-lookup"><span data-stu-id="e7369-133">Work with fragments</span></span>](work-with-fragments.md)

[<span data-ttu-id="e7369-134">Sablonok és elrendezések áttekintése</span><span class="sxs-lookup"><span data-stu-id="e7369-134">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="e7369-135">Webhely-navigáció testreszabása</span><span class="sxs-lookup"><span data-stu-id="e7369-135">Customize site navigation</span></span>](customize-site-navigation.md)
