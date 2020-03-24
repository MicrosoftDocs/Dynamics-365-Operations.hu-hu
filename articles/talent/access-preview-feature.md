---
title: Szolgáltatások kezelése
description: Ez a témakör leírja, hogy a rendszergazda hogyan engedélyezheti az előzetes funkciókat a Microsoft Dynamics 365 Talent alkalmazásban, és felsorolja azokat a funkciókat, amelyek jelenleg előnézetre engedélyezettek.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.1.0, Talent
ms.openlocfilehash: d818e9e04ce88e5ab285ef8176334809447fb477
ms.sourcegitcommit: 1d5a4f70a931e78b06811add97c1962e8d93689b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/13/2020
ms.locfileid: "3124796"
---
# <a name="manage-features"></a><span data-ttu-id="ae6a9-103">Szolgáltatások kezelése</span><span class="sxs-lookup"><span data-stu-id="ae6a9-103">Manage features</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ae6a9-104">A Microsoft Dynamics 365 Human Resources emberierőforrás-menedzsment (HCM) lehetőségeit folyamatosan bővítjük, ennek részeként azt szeretnénk, hogy az ügyfelek a lehető leghamarabb használhassák az új funkciókat.</span><span class="sxs-lookup"><span data-stu-id="ae6a9-104">As part of our continuous rollout of human capital management (HCM) capabilities for Microsoft Dynamics 365 Human Resources, we want to let customers experience new features as soon as possible.</span></span> <span data-ttu-id="ae6a9-105">A rendszergazdák láthatják és környezetükben használhatják az előnézeti szolgáltatásokat.</span><span class="sxs-lookup"><span data-stu-id="ae6a9-105">Administrators can see and use preview features in their environments.</span></span> <span data-ttu-id="ae6a9-106">Ezek a funkciók majdnem általános rendelkezésre állnak, és kiterjedt tesztelésen mentek keresztül.</span><span class="sxs-lookup"><span data-stu-id="ae6a9-106">These features are almost ready for general availability and have gone through extensive testing.</span></span> <span data-ttu-id="ae6a9-107">Az általánosan elérhető kibocsátás előtt egy utolsó visszajelzési és ellenőrzési kört végzünk az ügyfelekkel.</span><span class="sxs-lookup"><span data-stu-id="ae6a9-107">We're just looking for a final round of customer feedback and validation before we release them for general availability.</span></span>

<span data-ttu-id="ae6a9-108">Ez a témakör leírja, hogy hogyan engedélyezheti az előzetes funkciókat, és felsorolja azokat a funkciókat, amelyek előnézet céljára jelenleg rendelkezésre állnak.</span><span class="sxs-lookup"><span data-stu-id="ae6a9-108">This topic describes how you can enable preview features, and it lists the features that are currently available for preview.</span></span> <span data-ttu-id="ae6a9-109">Ez a lista frissül, ahogy a funkciókat általánosan elérhetővé tesszük, és ahogy új szolgáltatások előzetes kiadása történik meg.</span><span class="sxs-lookup"><span data-stu-id="ae6a9-109">This list will be updated as features are released to general availability and as new features are released to preview.</span></span> <span data-ttu-id="ae6a9-110">Nincsenek értesítések új funkciók előzetes kiadásakor.</span><span class="sxs-lookup"><span data-stu-id="ae6a9-110">No notification is given when new features are released to preview.</span></span> <span data-ttu-id="ae6a9-111">A felhasználók egyszerűen csak látni fogják a szolgáltatásokat.</span><span class="sxs-lookup"><span data-stu-id="ae6a9-111">Users will just start to see the features.</span></span> <span data-ttu-id="ae6a9-112">A Talent új funkcióival kapcsolatos információkért lásd: [Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban](./whats-new.md) és [Dynamics 365 és Power Platform kibocsátási megjegyzések](https://docs.microsoft.com/business-applications-release-notes).</span><span class="sxs-lookup"><span data-stu-id="ae6a9-112">For more information about new features in Talent, see [What's new or changed in Dynamics 365 Talent](./whats-new.md) and [Dynamics 365 and Power Platform Release Notes](https://docs.microsoft.com/business-applications-release-notes).</span></span>

## <a name="enable-or-disable-preview-features"></a><span data-ttu-id="ae6a9-113">Előnézeti szolgáltatások engedélyezése vagy letiltása</span><span class="sxs-lookup"><span data-stu-id="ae6a9-113">Enable or disable preview features</span></span>

<span data-ttu-id="ae6a9-114">Az előzetes funkciók eléréséhez előbb engedélyeznie kell azokat a környezetben.</span><span class="sxs-lookup"><span data-stu-id="ae6a9-114">To access preview features, you must first enable them in your environment.</span></span> <span data-ttu-id="ae6a9-115">Az előzetes funkciók engedélyezése és letiltása környezetfüggő.</span><span class="sxs-lookup"><span data-stu-id="ae6a9-115">Enabling or disabling preview features is environment-specific.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ae6a9-116">Az **Előzetes funkciók** beállításá bekapcsolása során a szervezet összes olyan felhasználója számára engedélyezi az előzetes funkciókat, akik az adott környezetben vannak.</span><span class="sxs-lookup"><span data-stu-id="ae6a9-116">When you turn on the **Preview Features** setting, you enable preview features for all users in your organization who are in that environment.</span></span> <span data-ttu-id="ae6a9-117">A beállítás kikapcsolása során letiltja le az előzetes funkciókat, és azok a felhasználók számára nem érhetők el.</span><span class="sxs-lookup"><span data-stu-id="ae6a9-117">When you turn off the setting, you disable preview features and make them inaccessible to your users.</span></span> <span data-ttu-id="ae6a9-118">Az előnézeti funkciók támogatása korlátozott a Talentben.</span><span class="sxs-lookup"><span data-stu-id="ae6a9-118">Preview features have limited support in Talent.</span></span> <span data-ttu-id="ae6a9-119">Előfordulhat, hogy ezek kevesebb adatvédelmi és biztonsági intézkedést használnak, és azok nem szerepelnek a Talent szolgáltatásiszint-szerződésében (SLA).</span><span class="sxs-lookup"><span data-stu-id="ae6a9-119">They might use fewer privacy and security measures, and they aren't included in the Talent service level agreement (SLA).</span></span> <span data-ttu-id="ae6a9-120">Ne használja az előnézeti funkciókat személyes adatok (azaz az Önt bármilyen módon azonosítani képes adatok) feldolgozására, illetve más jogi vagy szabályozási, megfelelési követelmények hatálya alá tartozó adatok feldolgozására.</span><span class="sxs-lookup"><span data-stu-id="ae6a9-120">You should not use preview features to process personal data (that is, any information that could identify you), or to process other data that is subject to legal or regulatory compliance requirements.</span></span>

### <a name="attract"></a><span data-ttu-id="ae6a9-121">Attract</span><span class="sxs-lookup"><span data-stu-id="ae6a9-121">Attract</span></span>

1. <span data-ttu-id="ae6a9-122">Jelentkezzen be a Microsoft Dynamics 365 Talent: Attract szolgáltatásba.</span><span class="sxs-lookup"><span data-stu-id="ae6a9-122">Sign in to Microsoft Dynamics 365 Talent: Attract.</span></span>
2. <span data-ttu-id="ae6a9-123">A jobb felső sarokban a **Beállítás** menüben (fogaskerék szimbólum) válassza ki a **Felügyeleti központ** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ae6a9-123">On the **Setup** menu (the gear symbol) in the upper-right corner, select **Admin center**.</span></span>
3. <span data-ttu-id="ae6a9-124">A **Funkciókezelés** lapon válassza ki az **Előzetes funkciók** beállítás melletti lehetőséget úgy, hogy az kékre változzon és a **Be** feliratot mutassa.</span><span class="sxs-lookup"><span data-stu-id="ae6a9-124">On the **Feature management** tab, select the option next to **Preview features** so that it turns blue and says **On**.</span></span>

    ![Az előzetes funkciók engedélyezése az Attract szolgáltatásban](./media/attract-enable-preview-features.png)

4. <span data-ttu-id="ae6a9-126">Jelölje ki vagy törölje a jelölést az egyes előzetes funkcióknál.</span><span class="sxs-lookup"><span data-stu-id="ae6a9-126">Select or cancel the selection of individual preview features.</span></span> <span data-ttu-id="ae6a9-127">Ha nem tesz semmit, akkor az összes elérhető előzetes funkció engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="ae6a9-127">If you do nothing, all available preview features are enabled.</span></span>
5. <span data-ttu-id="ae6a9-128">Frissítse a böngészőjét, hogy elindítsa el az új szolgáltatások megjelenítését.</span><span class="sxs-lookup"><span data-stu-id="ae6a9-128">Refresh your browser to start to see the new features.</span></span> <span data-ttu-id="ae6a9-129">Bármely, már bejelentkezett felhasználó számára a következő bejelentkezéskor jelenik meg a funkció, illetve frissíthetik a böngészőt a szolgáltatások azonnali megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="ae6a9-129">Any users who are already signed in will see the features the next time they sign in, or they can refresh their browser to see the features immediately.</span></span>

> [!NOTE]
> <span data-ttu-id="ae6a9-130">Előfordulhat, hogy egyes előzetes funkciók további konfigurációt igényelnek.</span><span class="sxs-lookup"><span data-stu-id="ae6a9-130">Some preview features might require additional configuration.</span></span> <span data-ttu-id="ae6a9-131">A beállítás végrehajtásához kövesse az előzetes funkció melletti hivatkozásokat.</span><span class="sxs-lookup"><span data-stu-id="ae6a9-131">Follow the links next to the preview feature to complete the setup for it.</span></span>

## <a name="feedback"></a><span data-ttu-id="ae6a9-132">Visszajelzés</span><span class="sxs-lookup"><span data-stu-id="ae6a9-132">Feedback</span></span>

<span data-ttu-id="ae6a9-133">Szívesen vesszük visszajelzését bármely előzetes funkcióval kapcsolatos tapasztalatairól.</span><span class="sxs-lookup"><span data-stu-id="ae6a9-133">We want to hear from you about your experience with any of these preview features.</span></span> <span data-ttu-id="ae6a9-134">Javasoljuk, hogy a rendszeresen küldje el a visszajelzését a következő webhelyeken, amikor ezeket a funkciókat használja vagy bármilyen más funkciót használ:</span><span class="sxs-lookup"><span data-stu-id="ae6a9-134">We encourage you to regularly post your feedback on the following sites as you use these or any other features:</span></span>

- <span data-ttu-id="ae6a9-135">[Közösségi](https://community.dynamics.com/enterprise/f/759?pi53869=0&category=Talent) – Ez a webhely remek fórum, ahol a felhasználók megbeszélhetik az eseteket, kérdéseket tehetnek fel és segítséget kaphatnak a közösségtől.</span><span class="sxs-lookup"><span data-stu-id="ae6a9-135">[Community](https://community.dynamics.com/enterprise/f/759?pi53869=0&category=Talent) – This site is a great resource where users can discuss use cases, ask questions, and get community help.</span></span>
- <span data-ttu-id="ae6a9-136">Tájékoztasson bennünket, hogy mely funkciókat szeretné látni a termékben, illetve milyen változásokat végezzünk a meglévő funkciókon.</span><span class="sxs-lookup"><span data-stu-id="ae6a9-136">Let us know about features that you want to see in the product, or let us know about any changes you think we should make to existing features.</span></span> <span data-ttu-id="ae6a9-137">A következő webhelyeken küldheti el az ötleteit a termékkel kapcsolatban:</span><span class="sxs-lookup"><span data-stu-id="ae6a9-137">Suggest product ideas on the following sites:</span></span>

    - [<span data-ttu-id="ae6a9-138">Attract ötletek</span><span class="sxs-lookup"><span data-stu-id="ae6a9-138">Attract ideas</span></span>](https://powerusers.microsoft.com/t5/Ideas-for-Attract/idb-p/Attract)
    - [<span data-ttu-id="ae6a9-139">Onboard ötletek</span><span class="sxs-lookup"><span data-stu-id="ae6a9-139">Onboard ideas</span></span>](https://powerusers.microsoft.com/t5/Ideas-for-Onboard/idb-p/Onboard)

<span data-ttu-id="ae6a9-140">Semmiképpen ne adjon meg személyes adatokat (azaz az Önt bármilyen módon azonosítani képes adatokat) a visszajelzésében vagy a termékértékelés benyújtásakor.</span><span class="sxs-lookup"><span data-stu-id="ae6a9-140">Make sure that you don't include personal data (any information that could identify you) in your feedback or product review submissions.</span></span> <span data-ttu-id="ae6a9-141">Előfordulhat, hogy az összegyűjtött információkat tovább elemzik, és azokat nem használjuk fel kérdések megválaszolására az alkalmazandó adatvédelmi törvényekkel összhangban.</span><span class="sxs-lookup"><span data-stu-id="ae6a9-141">Collected information might be analyzed further and isn't used to answer requests under applicable privacy laws.</span></span> <span data-ttu-id="ae6a9-142">A programokhoz kapcsolódóan külön gyűjtött személyes adatokra a [Microsoft adatvédelmi nyilatkozat](https://privacy.microsoft.com/privacystatement) vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="ae6a9-142">Personal data that is collected separately under these programs is subject to the [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement).</span></span>

> [!TIP]
> <span data-ttu-id="ae6a9-143">Tegyen Könyvjelzőt ehhez a témakörhöz, és a jöjjön vissza gyakran, hogy naprakész legyen az előnézeti funkciókkal kapcsolatban, ahogy azok megjelennek.</span><span class="sxs-lookup"><span data-stu-id="ae6a9-143">Bookmark this topic, and check back often to stay up to date about new preview features as we release them.</span></span>

## <a name="see-also"></a><span data-ttu-id="ae6a9-144">Lásd még</span><span class="sxs-lookup"><span data-stu-id="ae6a9-144">See also</span></span>

- [<span data-ttu-id="ae6a9-145">Talent alkalmazások kipróbálása vagy megvásárlása</span><span class="sxs-lookup"><span data-stu-id="ae6a9-145">Try or buy Talent apps</span></span>](https://dynamics.microsoft.com/talent/overview/)
- [<span data-ttu-id="ae6a9-146">Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="ae6a9-146">What's new or changed in Dynamics 365 Talent</span></span>](./whats-new.md)
- [<span data-ttu-id="ae6a9-147">Kiadási tervek</span><span class="sxs-lookup"><span data-stu-id="ae6a9-147">Release plans</span></span>](https://docs.microsoft.com/business-applications-release-notes/index)
- [<span data-ttu-id="ae6a9-148">Támogatás kérése a Microsoft Dynamics 365 Talent alkalmazáshoz</span><span class="sxs-lookup"><span data-stu-id="ae6a9-148">Get support for Microsoft Dynamics 365 Talent</span></span>](./talent-support.md)
