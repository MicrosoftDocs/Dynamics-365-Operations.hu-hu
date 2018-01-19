---
title: "A Microsoft Dynamics 365 for Talent lehetőségeinek bővítése"
description: "Ha létrehozott bármilyen Microsoft PowerApps alkalmazást, ezeket az alkalmazásokat hivatkozásokkal indíthatja el a Microsoft Dynamics 365 for Talent alkalmazásból."
author: rschloma
manager: AnnBe
ms.date: 11/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Talent
ms.custom: 17271
ms.assetid: ba1ad49d-8232-400e-b11f-525423506a3f
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2017-11-28
ms.dyn365.ops.version: Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: ceea24519d641c676521771cee274feb64ca7783
ms.openlocfilehash: e1d0bbd71737001579218068e2ab0e02bc973f38
ms.contentlocale: hu-hu
ms.lasthandoff: 01/19/2018

---
# <a name="extend-the-functionality-of-microsoft-dynamics-365-for-talent"></a><span data-ttu-id="37cc0-103">A Microsoft Dynamics 365 for Talent lehetőségeinek bővítése</span><span class="sxs-lookup"><span data-stu-id="37cc0-103">Extend the functionality of Microsoft Dynamics 365 for Talent</span></span>
<span data-ttu-id="37cc0-104">Ha létrehozott bármilyen Microsoft PowerApps alkalmazást, ezeket az alkalmazásokat hivatkozásokkal indíthatja el a Microsoft Dynamics 365 for Talent alkalmazásból.</span><span class="sxs-lookup"><span data-stu-id="37cc0-104">If you’ve created any Microsoft PowerApps, you can start those applications from links within Microsoft Dynamics 365 for Talent.</span></span> <span data-ttu-id="37cc0-105">Az alkalmazásokhoz való hozzáférés beállításához szükséges bizonyos információk beállítása a Talent alkalmazásban egy konfigurációs lapon, amely a **Rendszerfelügyelet** munkaterületen nyitható meg.</span><span class="sxs-lookup"><span data-stu-id="37cc0-105">To set up access to your applications, you’ll need to set up some information in Talent on a configuration page that you can open from the **System administration** workspace.</span></span>

## <a name="configuring-embedded-powerapps-within-talent"></a><span data-ttu-id="37cc0-106">Beágyazott PowerApps alkalmazások konfigurálása a Talent alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="37cc0-106">Configuring embedded PowerApps within Talent</span></span>
<span data-ttu-id="37cc0-107">Használja a **Beágyazott Microsoft PowerApps beállítása** lapot a Talent alkalmazás oldalainak konfigurálásához a PowerApps alkalmazások indítására.</span><span class="sxs-lookup"><span data-stu-id="37cc0-107">Use the **Set embedded Microsoft PowerApps** page to configure Talent pages to start PowerApps applications.</span></span> <span data-ttu-id="37cc0-108">A **Beágyazott Microsoft PowerApps beállítása** lap megnyitásához nyissa meg a **Rendszerfelügyelet** munkaterületet, majd nyissa meg a **Hivatkozások** lapot. Válassza a **Microsoft PowerApps** elemet a lehetőségek közül a **Setup** csoportban.</span><span class="sxs-lookup"><span data-stu-id="37cc0-108">To open the **Set embedded Microsoft PowerApps** page, open the **System administration** workspace and then open the **Links** tab. Select **Microsoft PowerApps** from the **Setup** group.</span></span> 

<span data-ttu-id="37cc0-109">Az alábbi információkat adhatja meg vagy állíthatja be ezen az oldalon:</span><span class="sxs-lookup"><span data-stu-id="37cc0-109">The following information is entered or set on this page:</span></span> 

> - <span data-ttu-id="37cc0-110">Jól felismerhető név vagy azonosító minden PowerApps alkalmazásnak.</span><span class="sxs-lookup"><span data-stu-id="37cc0-110">A descriptive name or identifier for each PowerApps application.</span></span>
> - <span data-ttu-id="37cc0-111">Egyedi azonosító (GUID) minden alkalmazásnak, amelyet hozzáad valamelyik Talent oldalhoz.</span><span class="sxs-lookup"><span data-stu-id="37cc0-111">A unique identifier (GUID) for each application that you add to a Talent page.</span></span> <span data-ttu-id="37cc0-112">Az alkalmazásazonosító a PowerApps-oldalon érhető el, [powerapps.com](http://powerapps.com/).</span><span class="sxs-lookup"><span data-stu-id="37cc0-112">The app ID is available on the PowerApps site, [powerapps.com](http://powerapps.com/).</span></span> 
> - <span data-ttu-id="37cc0-113">A lap, amelyről a felhasználók megnyithatnak egy alkalmazást vagy jelentést.</span><span class="sxs-lookup"><span data-stu-id="37cc0-113">The page from which users can open an application or report.</span></span> <span data-ttu-id="37cc0-114">Nem minden Talent-lap támogatja a beágyazott PowerAppst és a PowerBI-jelentéseket.</span><span class="sxs-lookup"><span data-stu-id="37cc0-114">Not all Talent pages support embedded PowerApps and Power BI reports.</span></span> 

 > [!NOTE]
 >  <span data-ttu-id="37cc0-115">Adja meg az oldal belső nevét, és nem az oldal tetején megjelenő megjelenítendő nevet.</span><span class="sxs-lookup"><span data-stu-id="37cc0-115">Enter the internal name of the page, rather than the display name that appears at the top of the page.</span></span> <span data-ttu-id="37cc0-116">A belső név megkereséséhez nyissa meg a lapot, amelynek a belső nevére van szüksége, és kattintson a jobb gombbal bárhová az oldalon.</span><span class="sxs-lookup"><span data-stu-id="37cc0-116">To find the internal name, open the page that you need the internal name of, and right-click anywhere on the page.</span></span> <span data-ttu-id="37cc0-117">A menü megnyílásakor vigye az egérmutatót a **Képernyő adatai** elemre.</span><span class="sxs-lookup"><span data-stu-id="37cc0-117">When the menu opens, hover over the **Form information** item.</span></span> <span data-ttu-id="37cc0-118">A belső képernyőnév a **Képernyő adatai** elem mellett jelenik meg a menüben.</span><span class="sxs-lookup"><span data-stu-id="37cc0-118">The internal form name is displayed next to the **Form information** item in the menu.</span></span>
 
> - <span data-ttu-id="37cc0-119">Adja meg az űrlap-vezérlőelemet, amelytől az alkalmazás be tudja beolvasni a környezeti adatokat.</span><span class="sxs-lookup"><span data-stu-id="37cc0-119">Specify the form control from which the application can retrieve context data.</span></span> <span data-ttu-id="37cc0-120">Például egy alkalmazás használhatja egy dolgozó adatait.</span><span class="sxs-lookup"><span data-stu-id="37cc0-120">For example, an application might use data about a worker.</span></span> <span data-ttu-id="37cc0-121">Ha megadja a **Dolgozó** lapot a **Környezet** mezőben, a **Dolgozó** lap megnyílik az alkalmazás indításakor.</span><span class="sxs-lookup"><span data-stu-id="37cc0-121">If you enter the **Worker** page in the **Context** field, the **Worker** page will open when you start the application.</span></span> <span data-ttu-id="37cc0-122">A **Környezetmezőben** nem kötelező megadni bejegyzést.</span><span class="sxs-lookup"><span data-stu-id="37cc0-122">An entry in the **Context field** is optional.</span></span> 
> - <span data-ttu-id="37cc0-123">Állítsa be a párbeszédpanel méretét, amelyen a PowerApps alkalmazás futni fog.</span><span class="sxs-lookup"><span data-stu-id="37cc0-123">Set the size of the dialog box on which the PowerApps application will run.</span></span> <span data-ttu-id="37cc0-124">A párbeszédpanelek lehetnek „kicsik” vagy „nagyok” a felhasználói felületet optimalizálásához, amikor az alkalmazás telefonon vagy nagyobb eszközön fut.</span><span class="sxs-lookup"><span data-stu-id="37cc0-124">The dialog boxes are designated as “small” or “large” to optimize the user interface when your application for running on a phone or a larger device, respectively.</span></span> 

<span data-ttu-id="37cc0-125">Megadhatja azt is, hogy az alkalmazás mely jogi személyek számára legyen elérhető, illetve minden jogi személy számára is elérhetővé teheti.</span><span class="sxs-lookup"><span data-stu-id="37cc0-125">You can also specify which legal entities an application will be available for, or you can make it available to all your legal entities.</span></span> <span data-ttu-id="37cc0-126">Alapértelmezés szerint a PowerApps alkalmazások elérhetők minden jogi személy számára.</span><span class="sxs-lookup"><span data-stu-id="37cc0-126">By default, your PowerApps applications are available to all legal entities.</span></span>

## <a name="opening-an-application"></a><span data-ttu-id="37cc0-127">Alkalmazás megnyitása</span><span class="sxs-lookup"><span data-stu-id="37cc0-127">Opening an application</span></span>
<span data-ttu-id="37cc0-128">Ha beágyazott PowerApps alkalmazásokat állított be, az alkalmazásaira mutatóként megadott hivatkozásokat a rendszer hozzáadja a Talent lapjaihoz.</span><span class="sxs-lookup"><span data-stu-id="37cc0-128">When you’ve configured embedded PowerApps applications, links to the applications that you specified will be added to the pages within Talent.</span></span> <span data-ttu-id="37cc0-129">Kattintson egy hivatkozásra egy alkalmazás megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="37cc0-129">Click a link to open an application.</span></span> 



