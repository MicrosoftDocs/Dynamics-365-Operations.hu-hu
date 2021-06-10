---
title: Készségek feltérképezése
description: 'A megfelelően képzett személyek megkereséséhez szakértelem-feltérképezéseket hozhat létre a Dynamics 365 Human Resources rendszerben:'
author: andreabichsel
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType, HcmEmployeeDevelopmentWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 03b7860fbde89097141cfe48f2c240dc127aa9c3
ms.sourcegitcommit: 48528233e0f02dbd47e96e030254ef65f2bb899e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/20/2021
ms.locfileid: "6076595"
---
# <a name="map-skills"></a><span data-ttu-id="79299-103">Készségek feltérképezése</span><span class="sxs-lookup"><span data-stu-id="79299-103">Map skills</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="79299-104">A megfelelően képzett személyek megkereséséhez szakértelem-feltérképezéseket hozhat létre a Dynamics 365 Human Resources rendszerben:</span><span class="sxs-lookup"><span data-stu-id="79299-104">You can create a skill-mapping search to find a qualified person in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="79299-105">A szakértelem-feltérképezés a következő információk áttekintésével, a megadott feltételek alapján ad vissza eredményeket:</span><span class="sxs-lookup"><span data-stu-id="79299-105">Skill-mapping searches return results for criteria you enter by looking through the following information:</span></span>

- <span data-ttu-id="79299-106">Szakértelem</span><span class="sxs-lookup"><span data-stu-id="79299-106">Skills</span></span>
- <span data-ttu-id="79299-107">Végzettség</span><span class="sxs-lookup"><span data-stu-id="79299-107">Education</span></span>
- <span data-ttu-id="79299-108">Diplomák</span><span class="sxs-lookup"><span data-stu-id="79299-108">Certificates</span></span>
- <span data-ttu-id="79299-109">Beosztások</span><span class="sxs-lookup"><span data-stu-id="79299-109">Positions</span></span>
- <span data-ttu-id="79299-110">Projekttapasztalat</span><span class="sxs-lookup"><span data-stu-id="79299-110">Project experience</span></span>

<span data-ttu-id="79299-111">Megkereshet például olyan személyeket a szervezetnél, akik CPA-t szereztek.</span><span class="sxs-lookup"><span data-stu-id="79299-111">For example, you can find people in your organization who have earned their CPA.</span></span>

<span data-ttu-id="79299-112">A készségleképező profilokkal olyan jelenlegi alkalmazottakra vagy jelöltekre kereshet, akiknek olyan végzettségei vannak, amelyek közvetlenül megfelelnek az üzleti szükségleteknek.</span><span class="sxs-lookup"><span data-stu-id="79299-112">Skill-mapping profiles allow you to find current employees or candidates with qualifications that directly correspond to business needs.</span></span>

> [!NOTE]
> <span data-ttu-id="79299-113">Csak a kereséshez kiválasztott dolgozók, pályázók és kapcsolattartó személyek jelennek meg a szakértelem-feltérképezés eredménylistájában és kerülnek bele szakértelemprofilba.</span><span class="sxs-lookup"><span data-stu-id="79299-113">Only workers, applicants, and contact persons who are selected to be included in skill-mapping searches will display in a skill-mapping results list, or be included in a skill profile.</span></span> <span data-ttu-id="79299-114">Ha azt szeretné, hogy egy személy szerepeljen a szakértelem-feltérképezési keresésekben, akkor a **Felvétel a szakértelem-leképezés** értékeként adja meg az **Igent** a következő oldalakon:</span><span class="sxs-lookup"><span data-stu-id="79299-114">To include a person in skill mapping searches, set the **Include in skill mapping** selection to **Yes** in the following pages:</span></span><br>
> - <span data-ttu-id="79299-115">Dolgozó</span><span class="sxs-lookup"><span data-stu-id="79299-115">Worker</span></span><br>
> - <span data-ttu-id="79299-116">Alkalmazott</span><span class="sxs-lookup"><span data-stu-id="79299-116">Employee</span></span><br>
> - <span data-ttu-id="79299-117">Pályázó</span><span class="sxs-lookup"><span data-stu-id="79299-117">Applicant</span></span><br>
> - <span data-ttu-id="79299-118">Kapcsolattartók</span><span class="sxs-lookup"><span data-stu-id="79299-118">Contacts</span></span><br>

<span data-ttu-id="79299-119">Szakértelem-feltérképezés létrehozásához lépjen az **Alkalmazotti fejlesztés > Hivatkozások > Szakértelem feltérképezése** részre.</span><span class="sxs-lookup"><span data-stu-id="79299-119">To create a skill mapping, go to **Employee development > Links > Skill mapping**.</span></span> <span data-ttu-id="79299-120">Szakértelem-feltérképezési profil létrehozásához lépjen az **Alkalmazotti fejlesztés > Hivatkozások > Szakértelem-feltérképezési profilok** részre.</span><span class="sxs-lookup"><span data-stu-id="79299-120">To create a skill-mapping profile, go to **Employee development > Links > Skill mapping profiles**.</span></span>

## <a name="skill-gap-analysis-and-skill-profile-analysis"></a><span data-ttu-id="79299-121">Szakértelemhiány-elemzések és szakértelemprofil-elemzések</span><span class="sxs-lookup"><span data-stu-id="79299-121">Skill gap analysis and skill profile analysis</span></span>

<span data-ttu-id="79299-122">A szakértelemprofil elemzésével megtekintheti egy személy kompetenciáinak listáját.</span><span class="sxs-lookup"><span data-stu-id="79299-122">You can create a skill profile analysis to view a list of a person's competencies.</span></span> <span data-ttu-id="79299-123">Létrehozhat szakértelemhiány-elemzést, amellyel összehasonlíthatja egy személy szakértelmeit az adott feladathoz szükséges szakértelmi szintekkel.</span><span class="sxs-lookup"><span data-stu-id="79299-123">You can create a skill gap analysis to compare a person’s skills and the skills required for a job.</span></span>

<span data-ttu-id="79299-124">Hiányelemzés létrehozásához lépjen az **Alkalmazotti fejlesztés > Hivatkozások > Szakértelemhiány-elemzés munkakör és személy szerint**.</span><span class="sxs-lookup"><span data-stu-id="79299-124">To create a gap analysis, go to **Employee development > Links > Skill gap analysis job - person**.</span></span> <span data-ttu-id="79299-125">Szakértelem-feltérképezési elemzés létrehozásához lépjen az **Alkalmazotti fejlesztés > Hivatkozások > Szakértelem-feltérképezési elemzés** részre.</span><span class="sxs-lookup"><span data-stu-id="79299-125">To create a skill profile analysis, go to **Employee development > Links > Skill profile analysis**.</span></span>

## <a name="see-also"></a><span data-ttu-id="79299-126">Lásd még</span><span class="sxs-lookup"><span data-stu-id="79299-126">See also</span></span>

[<span data-ttu-id="79299-127">Készségek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="79299-127">Configure skills</span></span>](hr-develop-skills.md)<br>
[<span data-ttu-id="79299-128">Készségek megadása</span><span class="sxs-lookup"><span data-stu-id="79299-128">Enter skills</span></span>](hr-develop-enter-skills.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]