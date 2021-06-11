---
title: Folyamatautomatizálási folyamatok meghívása minőségi rendelések létrehozásához
description: Ez a témakör olyan erőforrásokat tartalmaz, amelyekkel a Power Automate-ben, a minőségi rendelések példájának használatával automatizálhatók az üzleti folyamatok.
author: cabeln
ms.date: 05/28/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: cabeln
ms.search.validFrom: 2021-05-28
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: f35adab3075ba810964a41899ba95ae40c115e83
ms.sourcegitcommit: 588f8343aaa654309d2ff735fd437dba6acd9d46
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/28/2021
ms.locfileid: "6115189"
---
# <a name="invoke-process-automation-flows-to-create-quality-orders"></a><span data-ttu-id="11c01-103">Folyamatautomatizálási folyamatok meghívása minőségi rendelések létrehozásához</span><span class="sxs-lookup"><span data-stu-id="11c01-103">Invoke process automation flows to create quality orders</span></span>

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

<span data-ttu-id="11c01-104">A szervezetek számára egyre fontosabb a szabványos üzleti folyamatok automatizálására, a munkatársak számára biztosított kényelmesebb kommunikációs környezet, és a különféle adatjelek és rendszerek használata az üzleti folyamatok automatizálásához.</span><span class="sxs-lookup"><span data-stu-id="11c01-104">Organizations have an increasing demand to automate standard business processes, provide more convenient interactions to the staff, and utilize various data signals and systems to drive business processes automatically.</span></span> <span data-ttu-id="11c01-105">A robotikus folyamatautomatizálással (RPA) és a Microsoft Power Automate rendszerrel a cégek kód nélkül automatizálhatják az ismétlődő folyamatokat, így hatékonyabbá és pontosabbá válhat a munkavégzés.</span><span class="sxs-lookup"><span data-stu-id="11c01-105">With robotic process automation (RPA) and Microsoft Power Automate, businesses can use a no-code experience to automate repetitive processes, thus gaining efficiency and accuracy.</span></span>

<span data-ttu-id="11c01-106">A Supply Chain Management automatizálási megoldásokhoz használható, letölthető sablonja jól példázza, hogy a Power Automate hogyan használható az üzleti folyamatok minőségi rendelések példaként való használatával történő automatizálásához.</span><span class="sxs-lookup"><span data-stu-id="11c01-106">The downloadable automation solution template for Supply Chain Management showcases how Power Automate can be used to automate business processes using quality orders as an example.</span></span>

<span data-ttu-id="11c01-107">Az automatizálási megoldás sablonja [itt](https://aka.ms/D365SCMQualityOrderRPASolution) tölthető le.</span><span class="sxs-lookup"><span data-stu-id="11c01-107">You can download the automation solution template [here](https://aka.ms/D365SCMQualityOrderRPASolution).</span></span>

<span data-ttu-id="11c01-108">A funkció és a funkció előnyeinek ismertetése a következő videóban tekinthető meg: [Minőségi rendelések készítése a Dynamics 365 Supply Chain Management rendszerben az RPA használatával](https://www.youtube.com/watch?v=LFbzJ6-H89w)</span><span class="sxs-lookup"><span data-stu-id="11c01-108">For an overview of this feature and its capabilities, see the following video: [Utilize RPA to create quality orders in Dynamics 365 Supply Chain Management](https://www.youtube.com/watch?v=LFbzJ6-H89w)</span></span>

<span data-ttu-id="11c01-109">![Az RPA automatizálási beállításai](media/rpa-automation-options.png "Az RPA automatizálási beállításai")</span><span class="sxs-lookup"><span data-stu-id="11c01-109">![Automation options with RPA](media/rpa-automation-options.png "Automation options with RPA")</span></span>

<span data-ttu-id="11c01-110">A Power Automate megoldássablonja olyan felhőautomatizálási folyamatot és asztali automatizálási folyamatot tartalmaz, amely automatizálja a minőségi rendelések létrehozását a Supply Chain Management szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="11c01-110">The Power Automate solution template includes a cloud automation flow and a desktop automation flow that automate the creation of quality orders in Supply Chain Management.</span></span>

<span data-ttu-id="11c01-111">Az automatizálás számos eseményre és jelre – többek között felhasználó bevitelre vagy gépi jelekre (többek között az eszközök internetes hálózata) – adott válaszként indítható.</span><span class="sxs-lookup"><span data-stu-id="11c01-111">The automation can be started in response to many events and signals, including user input or machine signals (including the Internet of Things (IoT)).</span></span> <span data-ttu-id="11c01-112">A *Q-rendelés* Power Application-példa a megoldássablon része.</span><span class="sxs-lookup"><span data-stu-id="11c01-112">The *Q-Order* Power Application example is included in the solution template.</span></span> <span data-ttu-id="11c01-113">Lehetővé teszi a felhasználó számára, hogy beolvassa egy cikk QR-kódját, megadja a mennyiséget, és képeket csatoljon kamera használatával.</span><span class="sxs-lookup"><span data-stu-id="11c01-113">It allows the user to scan an item QR code, enter quantity, and attach pictures using a camera.</span></span>

<span data-ttu-id="11c01-114">Olyan megoldásparaméterek is rendelkezésre állnak, amelyekkel konfigurálni lehet egy termelési létesítményben egy adott használati esetre vonatkozó automatizálást.</span><span class="sxs-lookup"><span data-stu-id="11c01-114">Solution parameters are included to configure the automation for a specific use case in a production facility.</span></span>

<span data-ttu-id="11c01-115">![Minőségi rendelés létrehozása](media/rpa-create-quality-roder.png "Minőségi rendelés létrehozása")</span><span class="sxs-lookup"><span data-stu-id="11c01-115">![Create quality order](media/rpa-create-quality-roder.png "Create quality order")</span></span>

<span data-ttu-id="11c01-116">A minőségi rendelés automatizálásához használható mintamegoldás letöltésével, telepítésével és használatával kapcsolatban a következő útmutató nyújt részletes útmutatást: [Minőségi rendelés létrehozásának automatizálása a Dynamics 365 Supply Chain Management rendszerben robotikus folyamatautomatizálással a Power Automate Desktop rendszerben](/power-automate/desktop-flows/dynamics365-scm-rpa).</span><span class="sxs-lookup"><span data-stu-id="11c01-116">For a complete step-by-step guide about how to download, install, and use the sample solution for automating quality order creation, see [Automate quality order creation on Dynamics 365 Supply Chain Management with Robotic Process Automation using Power Automate Desktop](/power-automate/desktop-flows/dynamics365-scm-rpa).</span></span>

