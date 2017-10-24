---
title: "Szervezeti adminisztráció kezdőlap"
description: "Ebből a témakörből olyan erőforrásokat érhet el, amelyek segítségével a szervezete hatékonyabban használhatja a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition rendszert."
author: sericks007
manager: AnnBe
ms.date: 08/18/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 20421
ms.assetid: 7aa24a03-d172-47e9-81f8-ebd39e80bc60
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: c73eeaaf28df8db720431d4bcd317c9721baa99d
ms.openlocfilehash: eb8674a6401b11e8e33d3cba54add1fb4bca1cd3
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="organization-administration-home-page"></a><span data-ttu-id="42d28-103">Szervezeti adminisztráció kezdőlap</span><span class="sxs-lookup"><span data-stu-id="42d28-103">Organization administration home page</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="42d28-104">Ebből a témakörből olyan erőforrásokat érhet el, amelyek segítségével a kiemelt felhasználók és rendszergazdák hatékonyabban használhatják a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition rendszert.</span><span class="sxs-lookup"><span data-stu-id="42d28-104">This topic points to content that will help power users and administrators configure Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span></span> <span data-ttu-id="42d28-105">A tartalom segítséget nyújt nekik a rendszer folyamatos és hatékony működésének konfigurálásában a szervezet és a cég számára.</span><span class="sxs-lookup"><span data-stu-id="42d28-105">This content will help them configure the system to work smoothly and effectively for your organization and business.</span></span>

<span data-ttu-id="42d28-106">A itt felsorolt tartalom java része a **Szervezeti adminisztráció** modul szolgáltatásaira vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="42d28-106">Much of the content listed here applies to features in the **Organizational administration** module.</span></span> <span data-ttu-id="42d28-107">Vannak azonban feladatok, például rekordsablon létrehozása és használata, amelyek a szervezet minél hatékonyabb segítésére bármely modulból elvégezhetők.</span><span class="sxs-lookup"><span data-stu-id="42d28-107">However, there are a couple of tasks, such as creating and using a record template, that can be performed in any module to help your organization run more efficiently.</span></span> 

<a name="number-sequences"></a><span data-ttu-id="42d28-108">Számsorozatok</span><span class="sxs-lookup"><span data-stu-id="42d28-108">Number sequences</span></span>
----------------
<span data-ttu-id="42d28-109">A számsorozatokat az azonosítókat igénylő alapadatrekordok és tranzakciórekordok olvasható, egyedi azonosítóinak létrehozására használja a rendszer.</span><span class="sxs-lookup"><span data-stu-id="42d28-109">Number sequences are used to generate readable, unique identifiers for master data records and transaction records that require identifiers.</span></span> <span data-ttu-id="42d28-110">Az azonosítókat igénylő alapadatokrekordokat és tranzakciós bejegyzéseket *hivatkozásnak* nevezik.</span><span class="sxs-lookup"><span data-stu-id="42d28-110">A master data record or transaction record that requires an identifier is referred to as a *reference*.</span></span> <span data-ttu-id="42d28-111">Egy hivatkozáshoz tartozó új rekordok létrehozása előtt be kell állítania egy számsorozatot, és a hivatkozáshoz társítani.</span><span class="sxs-lookup"><span data-stu-id="42d28-111">Before you can create new records for a reference, you must set up a number sequence and associate it with the reference.</span></span>

-   [<span data-ttu-id="42d28-112">Számsorozatok áttekintése</span><span class="sxs-lookup"><span data-stu-id="42d28-112">Number sequence overview</span></span>](number-sequence-overview.md)
-   <span data-ttu-id="42d28-113">[Számsorozatok beállítása varázsló segítségével](tasks/set-up-number-sequences-wizard.md) (Feladat-útmutató)</span><span class="sxs-lookup"><span data-stu-id="42d28-113">[Set up number sequences by using a wizard](tasks/set-up-number-sequences-wizard.md) (Task guide)</span></span>
-   <span data-ttu-id="42d28-114">[Számsorozatok beállítása egyedi alapon](tasks/set-up-number-sequences-individual-basis.md) (Feladat-útmutató)</span><span class="sxs-lookup"><span data-stu-id="42d28-114">[Set up number sequences on an individual basis](tasks/set-up-number-sequences-individual-basis.md) (Task guide)</span></span>

## <a name="organizations"></a><span data-ttu-id="42d28-115">Szervezetek</span><span class="sxs-lookup"><span data-stu-id="42d28-115">Organizations</span></span>
<span data-ttu-id="42d28-116">Egy szervezet olyan emberek csoportja, akik valamely üzleti folyamat végrehajtása vagy egy cél elérése érdekében együtt dologoznak</span><span class="sxs-lookup"><span data-stu-id="42d28-116">An organization is a group of people who are working together to carry out a business process or achieve a goal.</span></span> <span data-ttu-id="42d28-117">Szervezeti hierarchiák a vállalkozását alkotó szervezetek közötti kapcsolatotat jelölik.</span><span class="sxs-lookup"><span data-stu-id="42d28-117">Organizational hierarchies represent the relationships between the organizations that make up your business.</span></span>

<span data-ttu-id="42d28-118">Szervezetek és szervezeti hierarchiák beállítása előtt a Finance and Operations programban, győződjön meg arról, hogy megtervezi, hogyan lehet modellezni vállalatát.</span><span class="sxs-lookup"><span data-stu-id="42d28-118">Before you set up organizations and organization hierarchies in Finance and Operations, make sure that you plan how your business will be modeled.</span></span> <span data-ttu-id="42d28-119">A szervezeti modellnek jelentős hatása van a Microsoft Dynamics 365 for Finance and Operations és az üzleti folyamatok végrehajtására.</span><span class="sxs-lookup"><span data-stu-id="42d28-119">The organization model has a significant effect on the implementation of Finance and Operations and on business processes.</span></span>

-   [<span data-ttu-id="42d28-120">Szervezetek és szervezeti hierarchiák</span><span class="sxs-lookup"><span data-stu-id="42d28-120">Organizations and organizational hierarchies</span></span>](organizations-organizational-hierarchies.md)
-   [<span data-ttu-id="42d28-121">Szervezeti hierarchia megtervezése</span><span class="sxs-lookup"><span data-stu-id="42d28-121">Plan your organizational hierarchy</span></span>](plan-organizational-hierarchy.md)
-   <span data-ttu-id="42d28-122">[Szervezeti hierarchia létrehozása](tasks/create-organization-hierarchy.md) (Feladat-útmutató)</span><span class="sxs-lookup"><span data-stu-id="42d28-122">[Create an organization hierarchy](tasks/create-organization-hierarchy.md) (Task guide)</span></span>
-   <span data-ttu-id="42d28-123">[Jogi személy létrehozása](tasks/create-legal-entity.md) (Feladat-útmutató)</span><span class="sxs-lookup"><span data-stu-id="42d28-123">[Create a legal entity](tasks/create-legal-entity.md) (Task guide)</span></span>
-   <span data-ttu-id="42d28-124">[Üzemi egység létrehozása](tasks/create-operating-unit.md) (Feladat-útmutató)</span><span class="sxs-lookup"><span data-stu-id="42d28-124">[Create an operating unit](tasks/create-operating-unit.md) (Task guide)</span></span>

## <a name="address-books"></a><span data-ttu-id="42d28-125">Címjegyzékek</span><span class="sxs-lookup"><span data-stu-id="42d28-125">Address books</span></span>
<span data-ttu-id="42d28-126">A globális címjegyzék központi tárház olyan alapadatok számára, amelyeket minden külső és belső személy és szervezet esetén tárolni kell, amelyekkel a vállalat kommunikál.</span><span class="sxs-lookup"><span data-stu-id="42d28-126">The global address book is a centralized repository for master data that must be stored for all internal and external persons and organizations that the company interacts with.</span></span> <span data-ttu-id="42d28-127">Partnerrekordokhoz kapcsolódó adatok a fél neve, címe és a kapcsolattartási adatai.</span><span class="sxs-lookup"><span data-stu-id="42d28-127">The data that is associated with party records includes the party's name, address, and contact information.</span></span> 

<span data-ttu-id="42d28-128">Miután létrehozta a globális címjegyzéket, további címjegyzéket hozhat létre szükség szerint, például vállalatonként vagy az üzlet sorainként külön címjegyzéket hozhat létre a szervezetben.</span><span class="sxs-lookup"><span data-stu-id="42d28-128">After you create the global address book, you can create additional address books as you require, such as a separate address book for each company in your organization or for each line of business.</span></span> 

-   [<span data-ttu-id="42d28-129">Globális címjegyzék</span><span class="sxs-lookup"><span data-stu-id="42d28-129">Global address book</span></span>](overview-global-address-book.md)
-   [<span data-ttu-id="42d28-130">A globális címjegyzék és további címjegyzékek beállításának megtervezése</span><span class="sxs-lookup"><span data-stu-id="42d28-130">Plan how to configure the global address book and additional address books</span></span>](plan-configuration-global-address-book-additional-address-books.md)
- [<span data-ttu-id="42d28-131">Globális címjegyzék konfigurálása</span><span class="sxs-lookup"><span data-stu-id="42d28-131">Configure the global address book</span></span>](tasks/configure-global-address-book.md)
-   [<span data-ttu-id="42d28-132">Címjegyzékek GYIK</span><span class="sxs-lookup"><span data-stu-id="42d28-132">Address books FAQ</span></span>](qa-address-books.md)


## <a name="workflow"></a><span data-ttu-id="42d28-133">Munkafolyamat</span><span class="sxs-lookup"><span data-stu-id="42d28-133">Workflow</span></span>
<span data-ttu-id="42d28-134">A munkafolyamat egy olyan rendszer, amelyet a Finance and Operations alkalmazással együtt telepített, és amelynek segítségével létrehozhat egyes munkafolyamatokat vagy üzleti eljárásokat.</span><span class="sxs-lookup"><span data-stu-id="42d28-134">Workflow is a system that is installed with Finance and Operations that you can use to create individual workflows, or business processes.</span></span> <span data-ttu-id="42d28-135">Munkafolyamat létrehozásakor megadja, hogyan halad vagy mozog egy dokumentum a rendszeren keresztül annak jelzésével, hogy kinek a feladata a feladat végrehajtása, a döntéshozatal, illetve a dokumentum jóváhagyása.</span><span class="sxs-lookup"><span data-stu-id="42d28-135">When you create a workflow, you specify how a document flows, or moves, through the system by showing who must complete a task, make a decision, or approve a document.</span></span> 

-   [<span data-ttu-id="42d28-136">Munkafolyamat – áttekintés</span><span class="sxs-lookup"><span data-stu-id="42d28-136">Workflow overview</span></span>](overview-workflow-system.md)
-   [<span data-ttu-id="42d28-137">Munkafolyamat-elemek</span><span class="sxs-lookup"><span data-stu-id="42d28-137">Workflow elements</span></span>](workflow-elements.md)
-   [<span data-ttu-id="42d28-138">Munkafolyamat-műveletek</span><span class="sxs-lookup"><span data-stu-id="42d28-138">Workflow actions</span></span>](workflow-actions.md)
-   [<span data-ttu-id="42d28-139">Munkafolyamat létrehozása</span><span class="sxs-lookup"><span data-stu-id="42d28-139">Create a workflow</span></span>](create-workflow.md)

## <a name="electronic-signatures"></a><span data-ttu-id="42d28-140">Elektronikus aláírások</span><span class="sxs-lookup"><span data-stu-id="42d28-140">Electronic signatures</span></span>
<span data-ttu-id="42d28-141">Az elektronikus aláírás igazolja annak a személynek a személyazonosságát, aki egy számítási folyamat elindítása vagy jóváhagyása előtt áll.</span><span class="sxs-lookup"><span data-stu-id="42d28-141">An electronic signature confirms the identity of a person who is about to start or approve a computing process.</span></span> <span data-ttu-id="42d28-142">Egyes ágazatokban az elektronikus aláírás ugyanúgy jogilag kötelező érvényű, mint a kézzel írott aláírás.</span><span class="sxs-lookup"><span data-stu-id="42d28-142">In some industries, an electronic signature is as legally binding as a handwritten signature.</span></span> <span data-ttu-id="42d28-143">Az elektronikus aláírás használatát törvény írja elő számos szabályozott iparágban, például a gyógyszeriparban, az élelmiszer- és italgyártás, a repülőgépgyártás és a honvédelem területén.</span><span class="sxs-lookup"><span data-stu-id="42d28-143">Electronic signatures are a regulations compliance requirement for several regulated industries, such as pharmaceuticals, food and beverage, and aerospace and defense.</span></span>

<span data-ttu-id="42d28-144">A Finance and Operations rendszerben a kritikus üzleti folyamatoknál használhatja az elektronikus aláírásokat.</span><span class="sxs-lookup"><span data-stu-id="42d28-144">In Finance and Operations, you can use electronic signatures for critical business processes.</span></span> <span data-ttu-id="42d28-145">Egyes folyamatokba be vannak építve az elektronikus aláírási funkciók.</span><span class="sxs-lookup"><span data-stu-id="42d28-145">Some processes have built-in electronic signature capabilities.</span></span> <span data-ttu-id="42d28-146">Ugyanezen a képernyőn egyéni elektronikus aláírási követelményeket is létrehozhat, tetszőleges adatbázis-táblára és mezőre vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="42d28-146">You can also create custom signature requirements for any database table and field.</span></span>

-   [<span data-ttu-id="42d28-147">Az elektronikus aláírás áttekintése</span><span class="sxs-lookup"><span data-stu-id="42d28-147">Electronic signature overview</span></span>](electronic-signature-overview.md)
-   <span data-ttu-id="42d28-148">[Az elektronikus aláírások beállítása](tasks/set-up-electronic-signatures.md) (Feladat-útmutató)</span><span class="sxs-lookup"><span data-stu-id="42d28-148">[Set up electronic signatures](tasks/set-up-electronic-signatures.md) (Task guide)</span></span>

## <a name="case-management"></a><span data-ttu-id="42d28-149">Esetkezelés</span><span class="sxs-lookup"><span data-stu-id="42d28-149">Case management</span></span>
<span data-ttu-id="42d28-150">Az esetek tervezésével, nyomon követésével és elemzésével hatékony megoldásokat hozhat létre, amelyeket aztán használhat a hasonló problémákhoz.</span><span class="sxs-lookup"><span data-stu-id="42d28-150">By planning, tracking, and analyzing cases, you can develop efficient resolutions that can be used for similar issues.</span></span> <span data-ttu-id="42d28-151">Például amikor az ügyfélszolgálati képviselők vagy az emberi erőforrások létrehozói eseteket hoznak létre, az adatokat a tudásbáziscikkekben találják meg arra vonatkozóan, hogyan tudnak egy eseten dolgozni, és azt hatékonyan megoldani.</span><span class="sxs-lookup"><span data-stu-id="42d28-151">For example, when customer service representatives or Human Resources generalists create cases, they can find information in knowledge articles to help them work with or resolve a case more efficiently.</span></span> 

-   [<span data-ttu-id="42d28-152">Esetkezelés – áttekintés</span><span class="sxs-lookup"><span data-stu-id="42d28-152">Case management overview</span></span>](cases.md)
-   [<span data-ttu-id="42d28-153">Esetbiztonság, folyamatok és kategóriák konfigurálása</span><span class="sxs-lookup"><span data-stu-id="42d28-153">Configure case security, processes, and categories</span></span>](plan-case-management.md)

## <a name="record-templates"></a><span data-ttu-id="42d28-154">Rekordsablonok</span><span class="sxs-lookup"><span data-stu-id="42d28-154">Record templates</span></span>
<span data-ttu-id="42d28-155">A rekordsablonok segítenek a rekordok gyorsabb létrehozásában.</span><span class="sxs-lookup"><span data-stu-id="42d28-155">Record templates can help you to create records more quickly.</span></span> <span data-ttu-id="42d28-156">Rekordsablon létrehozásával a gyakran használt mezőértékeket nem kell minden új rekordhoz kifejezett módon megadni.</span><span class="sxs-lookup"><span data-stu-id="42d28-156">You can create a record template so that field values that are used often do not have to be entered explicitly for each new record.</span></span> 

-   [<span data-ttu-id="42d28-157">Rekordsablonok</span><span class="sxs-lookup"><span data-stu-id="42d28-157">Record templates</span></span>](record-templates.md)
- <span data-ttu-id="42d28-158">[Adatbevitel megkönnyítése érdekében rekordsablon létrehozása](../../dev-itpro/data-entities/tasks/create-record-template-facilitate-data-entry.md) (Feladat-útmutató)</span><span class="sxs-lookup"><span data-stu-id="42d28-158">[Create a record template to facilitate data entry](../../dev-itpro/data-entities/tasks/create-record-template-facilitate-data-entry.md) (Task guide)</span></span>
- <span data-ttu-id="42d28-159">[Rekordsablon használata egy új rekord létrehozásához](../../dev-itpro/data-entities/tasks/use-record-template-new-record.md) (Feladat-útmutató)</span><span class="sxs-lookup"><span data-stu-id="42d28-159">[Use a record template to create a new record](../../dev-itpro/data-entities/tasks/use-record-template-new-record.md) (Task guide)</span></span>

## <a name="general-organization-administration"></a><span data-ttu-id="42d28-160">Általános szervezeti adminisztráció</span><span class="sxs-lookup"><span data-stu-id="42d28-160">General organization administration</span></span>
-   <span data-ttu-id="42d28-161">[A fejléc vagy embléma módosítása](../get-started/tasks/change-banner-or-logo.md) (Feladat-útmutató)</span><span class="sxs-lookup"><span data-stu-id="42d28-161">[Change the banner or logo](../get-started/tasks/change-banner-or-logo.md) (Task guide)</span></span>
- [<span data-ttu-id="42d28-162">A dokumentumkezelés konfigurálása</span><span class="sxs-lookup"><span data-stu-id="42d28-162">Configure document management</span></span>](configure-document-management.md)
- [<span data-ttu-id="42d28-163">E-mail konfigurálása és küldése</span><span class="sxs-lookup"><span data-stu-id="42d28-163">Configure and send email</span></span>](configure-email.md)
-   [<span data-ttu-id="42d28-164">Dátum-/időadatok és időzónák</span><span class="sxs-lookup"><span data-stu-id="42d28-164">Date/time data and time zones</span></span>](date-time-zones.md)







