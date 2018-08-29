---
title: "Oldalak egymás melletti megjelenítése a Megnyitás új ablakban funkció használatával"
description: "Ez a cikk ismerteti, hogy hogyan jeleníthet meg lapokat egymás mellett a Microsoft Dynamics 365 for Finance and Operations rendszerben."
author: aneesmsft
manager: AnnBe
ms.date: 09/07/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 17611
ms.assetid: fc589d76-3927-4486-ab83-e86b9b47ba2c
ms.search.region: Global
ms.author: aneesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 764d4c9049d94ebcd55c61654aa2f4133b35bae6
ms.openlocfilehash: 8e3ef29618f11b0f247999e3a24e54bff44bf51a
ms.contentlocale: hu-hu
ms.lasthandoff: 08/09/2018

---

# <a name="show-pages-side-by-side-by-using-the-open-in-new-window-feature"></a><span data-ttu-id="b5ad3-103">Oldalak egymás melletti megjelenítése a Megnyitás új ablakban funkció használatával</span><span class="sxs-lookup"><span data-stu-id="b5ad3-103">Show pages side by side by using the Open in new window feature</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b5ad3-104">Ez a cikk ismerteti, hogy hogyan jeleníthet meg lapokat egymás mellett a Microsoft Dynamics 365 for Finance and Operations rendszerben.</span><span class="sxs-lookup"><span data-stu-id="b5ad3-104">This article explains how to display pages side-by-side in Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="b5ad3-105">A Microsoft Dynamics 365 for Finance and Operations rendszer segít a feladatok hatékony végrehajtásában.</span><span class="sxs-lookup"><span data-stu-id="b5ad3-105">Microsoft Dynamics 365 for Finance and Operations helps you perform tasks efficiently.</span></span> <span data-ttu-id="b5ad3-106">Bizonyos esetekben előfordulhat, hogy több oldalt akar párhuzamosan megjeleníteni, a feladat gyors végrehajtásához.</span><span class="sxs-lookup"><span data-stu-id="b5ad3-106">In some cases, you may want to view multiple pages side-by-side to complete tasks quickly.</span></span> <span data-ttu-id="b5ad3-107">Például szeretne érvényesíteni vagy hozzáadni sorokat egyszerre több naplóhoz.</span><span class="sxs-lookup"><span data-stu-id="b5ad3-107">As an example, you might want to validate or enter lines in more than one journal.</span></span> <span data-ttu-id="b5ad3-108">Általában ehhez folyamatosan váltani kell a lap, ami megjeleníti a naplókat, valamint egy másik lap között, ami megjeleníti a sorokat az adott naplóhoz.</span><span class="sxs-lookup"><span data-stu-id="b5ad3-108">Typically, to do this you would have to go back and forth between the page that displays a list of journals, and the page that displays lines for a given journal.</span></span> <span data-ttu-id="b5ad3-109">Azonban a **Megnyitás új ablakban** funkció lehetővé teszi, hogy ezen lapokat párhuzamosan jelenítse meg, ezzel gyorsítva az elvégzendő feladatot.</span><span class="sxs-lookup"><span data-stu-id="b5ad3-109">However, the **Open in new window** feature enables you to display these pages side-by-side so that you can perform your tasks quickly.</span></span> 

<span data-ttu-id="b5ad3-110">A fenti példánál maradva, a sorok megtekintése közben rákattinthat a **Megnyitás új ablakban** ikonra.</span><span class="sxs-lookup"><span data-stu-id="b5ad3-110">Continuing with the example mentioned above, when viewing the lines, you can click the **Open in new window** icon.</span></span> 

<span data-ttu-id="b5ad3-111">[![open-in-new-window-icon](./media/open-in-new-window-icon.png)](./media/open-in-new-window-icon.png)</span><span class="sxs-lookup"><span data-stu-id="b5ad3-111">[![open-in-new-window-icon](./media/open-in-new-window-icon.png)](./media/open-in-new-window-icon.png)</span></span> 

<span data-ttu-id="b5ad3-112">A **Megnyitás új ablakban** ikonra kattintva a sorokat tartalmazó lap egy új, felugró böngészőben nyílik meg, majd az eredeti böngészőt visszairányítja az előzményekben arra a lapra, ami a naplók listáját tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="b5ad3-112">Clicking the **Open in new window** icon opens the lines page in a new, pop-up browser, and then navigates the original browser back in history to the page that displayed the list of journals.</span></span> <span data-ttu-id="b5ad3-113">Ezután a két oldalt párhuzamosan jelenítheti meg.</span><span class="sxs-lookup"><span data-stu-id="b5ad3-113">You can then display both pages side-by-side.</span></span> <span data-ttu-id="b5ad3-114">Ha befejezte egy napló megtekintését, megváltoztathatja a kiválasztott naplót a naplókat listázó oldalon. Ezután a sorokat megjelenítő felugró ablak automatikusan az újonnan kiválasztott napló sorait jeleníti majd meg.</span><span class="sxs-lookup"><span data-stu-id="b5ad3-114">When you are done viewing a journal, you can change the selected journal on the journal list page, and the lines page in the pop-up window will automatically display the lines of the newly selected journal.</span></span> 

<span data-ttu-id="b5ad3-115">[![pages-show-side-by-side](./media/pages-show-side-by-side.png)](./media/pages-show-side-by-side.png)</span><span class="sxs-lookup"><span data-stu-id="b5ad3-115">[![pages-show-side-by-side](./media/pages-show-side-by-side.png)](./media/pages-show-side-by-side.png)</span></span> 

<span data-ttu-id="b5ad3-116">A dinamikus csatolás és frissítés az oldal biztonságáért felelős adatok közötti kapcsolat miatt történik.</span><span class="sxs-lookup"><span data-stu-id="b5ad3-116">The dynamic linking and refreshing happens due to the relations that exist between the data that is backing these pages.</span></span> <span data-ttu-id="b5ad3-117">Ha a rendszer nem ismeri az adatok közötti kapcsolatot, az előugró ablak nem fog automatikusan frissülni az eredeti ablakban történt változás után.</span><span class="sxs-lookup"><span data-stu-id="b5ad3-117">If the system is not aware of the relation between the data, the pop-up window will not refresh automatically in response to a change in the window it originated from.</span></span> 

<span data-ttu-id="b5ad3-118">Néhány lapnak több nézete is van, mint például a Rács nézet, a Fejléc nézet, vagy a Részletek nézet.</span><span class="sxs-lookup"><span data-stu-id="b5ad3-118">Some pages have multiple views such as the Grid view, Header view, and Details view.</span></span> <span data-ttu-id="b5ad3-119">A **Megnyitás új ablakban** ikon hatására az egész lap egy új böngészőben nyílik meg.</span><span class="sxs-lookup"><span data-stu-id="b5ad3-119">The **Open in new window** icon causes the entire page to be opened in the new browser window.</span></span> <span data-ttu-id="b5ad3-120">Emiatt nem lehet párhuzamosan megjeleníteni ugyan annak a lapnak két különböző nézetét a **Megnyitás új ablakban** szolgáltatás segítségével.</span><span class="sxs-lookup"><span data-stu-id="b5ad3-120">Therefore, you cannot keep two views of the same page side-by-side using the **Open in new window** feature.</span></span> <span data-ttu-id="b5ad3-121">Azonban a legtöbb ilyen oldal rendelkezik egy navigációs listával, aminek a segítségével válthat a rekordok között, egy hasonló eredményt elérve.</span><span class="sxs-lookup"><span data-stu-id="b5ad3-121">However, almost all such pages have a navigation list that you can use to switch between records and achieve a similar experience.</span></span> 

<span data-ttu-id="b5ad3-122">A **Megnyitás új ablakban** funkció használata előtt a böngészőjében engedélyeznie kell a felugró ablakokat a Dynamics 365 for Finance and Operations rendszer weblapján.</span><span class="sxs-lookup"><span data-stu-id="b5ad3-122">Before using the **Open in new window** feature, you should configure your browser's pop-up blocker to allow pop-ups from the URL of the Finance and Operations site.</span></span> <span data-ttu-id="b5ad3-123">Például engedélyezheti a felugró ablakokat a „\*.dynamics.com” helyről.</span><span class="sxs-lookup"><span data-stu-id="b5ad3-123">As an example, you could allow pop-ups from "\*.dynamics.com".</span></span> 

<span data-ttu-id="b5ad3-124">A **Megnyitás új ablakban** funkció csak akkor elérhető, ha több, mint egy oldal van megnyitva az ablakban.</span><span class="sxs-lookup"><span data-stu-id="b5ad3-124">The **Open in new window** feature is only available when there is more than one page open in the window.</span></span> <span data-ttu-id="b5ad3-125">A felugró ablakok is automatikusan bezárulnak, ha nincs több megnyitható lap (ha az ablak utolsó lapja is bezárásra kerül).</span><span class="sxs-lookup"><span data-stu-id="b5ad3-125">Also, the pop-up window automatically closes when there are no more pages open (that is, when the last page in that window is closed).</span></span> <span data-ttu-id="b5ad3-126">A Finance and Operations rendszer bezárja a megnyitott lapokat is, ha Ön az alkalmazás egy másik részére navigál.</span><span class="sxs-lookup"><span data-stu-id="b5ad3-126">Finance and Operations also closes open pages when you navigate to a different area in the application.</span></span> <span data-ttu-id="b5ad3-127">Ezért ha van egy megnyitott felugró ablak, és Ön az alkalmazáson belül egy másik területre navigál, a felugró ablak automatikusan bezárul, mert az ablakon belüli lapokat a rendszer automatikusan bezárta.</span><span class="sxs-lookup"><span data-stu-id="b5ad3-127">Therefore, if you have pop-up windows open and navigate to a different area in the application, the pop-up windows are automatically closed because the pages in those windows were closed by the system.</span></span> 

<span data-ttu-id="b5ad3-128">Az előugró ablak felső sora arról a vállalatról tartalmaz információt, amiben a lap meg lett nyitva, és csak olvasható.</span><span class="sxs-lookup"><span data-stu-id="b5ad3-128">The top bar in the pop-up windows displays information about the company the page was opened in and is read-only.</span></span> <span data-ttu-id="b5ad3-129">A felugró ablak a Finance and Operations rendszer fő böngésző ablakára támaszkodik.</span><span class="sxs-lookup"><span data-stu-id="b5ad3-129">The pop-up windows also rely on the main Finance and Operations browser window.</span></span> <span data-ttu-id="b5ad3-130">Ha a fő ablak bezárásra kerül, vagy frissítve lesz, az összes felugró ablak csak olvasható állapotba kerül.</span><span class="sxs-lookup"><span data-stu-id="b5ad3-130">If the main window is closed or refreshed, all open pop-up windows will become read only.</span></span> <span data-ttu-id="b5ad3-131">Ez azt jelenti, hogy ezután is megtekintheti az információkat ezekben az ablakokban, de nem lesz képes módosítani azokat.</span><span class="sxs-lookup"><span data-stu-id="b5ad3-131">This means that you can still view the information in these windows, but you will not be able to interact with it.</span></span>




