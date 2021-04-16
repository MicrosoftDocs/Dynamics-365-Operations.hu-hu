---
title: Ügyfél GYIK
description: Ez a cikk válaszokat ad a Finance and Operations-klienssel kapcsolatos gyakori kérdésekre.
author: jasongre
ms.date: 09/11/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 12334
ms.assetid: a9a57f0e-a67c-46b1-83c9-5d6350fb3b86
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8f4311e93505f1d59f6beeae01a2a2e796ad47cd
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5749221"
---
# <a name="client-faq"></a><span data-ttu-id="b0312-103">Ügyfél GYIK</span><span class="sxs-lookup"><span data-stu-id="b0312-103">Client FAQ</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b0312-104">Ez a cikk válaszokat ad a Finance and Operations-klienssel kapcsolatos gyakori kérdésekre.</span><span class="sxs-lookup"><span data-stu-id="b0312-104">This article provides answers to frequently asked questions about the Finance and Operations client.</span></span>

## <a name="why-arent-symbols-loaded"></a><span data-ttu-id="b0312-105">Miért nem töltődnek be a szimbólumok?</span><span class="sxs-lookup"><span data-stu-id="b0312-105">Why aren't symbols loaded?</span></span>

<span data-ttu-id="b0312-106">A böngésző biztonsági beállításai megakadályozhatják a szimbólumok megfelelő betöltődését.</span><span class="sxs-lookup"><span data-stu-id="b0312-106">The security settings on your browser might prevent the symbols from being loaded correctly.</span></span> <span data-ttu-id="b0312-107">A probléma megoldásához kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="b0312-107">To resolve this issue, try the following steps:</span></span>

- <span data-ttu-id="b0312-108">Ha a probléma az Internet Explorer programban merül fel, kattintson a **Beállítások**, majd az **Internetbeállítások** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b0312-108">If you're experiencing this issue in Internet Explorer, click **Tools**, and then click **Internet Options**.</span></span> <span data-ttu-id="b0312-109">Az Internetbeállítások párbeszédablakban kattintson az **Adatvédelem** lapra, kattintson az **Egyéni szint** elemre, és ellenőrizze, hogy be van-e jelölve a **Betűtípus letöltése** beállítás.</span><span class="sxs-lookup"><span data-stu-id="b0312-109">In the Internet Options dialog box, on the **Privacy** tab, click **Custom level**, and make sure the **Font download** option is selected.</span></span>
- <span data-ttu-id="b0312-110">Ellenkező esetben előfordulhat, hogy hozzá kell adnia az alkalmazásoldalt a megbízható helyek listájához.</span><span class="sxs-lookup"><span data-stu-id="b0312-110">Otherwise, you might have to add the app site to the list of trusted sites.</span></span>

## <a name="i-miss-the-ribbon-from-dynamics-ax-2012-can-i-keep-action-pane-tabs-open-all-the-time"></a><span data-ttu-id="b0312-111">Hiányolom a menüszalagot a Dynamics AX 2012 rendszerből.</span><span class="sxs-lookup"><span data-stu-id="b0312-111">I miss the ribbon from Dynamics AX 2012.</span></span> <span data-ttu-id="b0312-112">Nyitva tarthatom folyamatosan a Műveleti ablaktáblát?</span><span class="sxs-lookup"><span data-stu-id="b0312-112">Can I keep Action Pane tabs open all the time?</span></span>

<span data-ttu-id="b0312-113">Terveink szerint ez a funkció hamarosan elérhetővé válik.</span><span class="sxs-lookup"><span data-stu-id="b0312-113">We are planning to implement this feature soon.</span></span> <span data-ttu-id="b0312-114">Ezt követően a felhasználók dönthetnek úgy, hogy a lapokat a Műveleti ablaktáblákon folyamatosan nyitva tartják.</span><span class="sxs-lookup"><span data-stu-id="b0312-114">Users will then be able to choose to keep the tabs on Action Panes open all the time.</span></span> <span data-ttu-id="b0312-115">Ellenkező esetben a lapok mindig össze fognak csuklani, ha azokat nem használják, így biztosítva nagyobb felületet a lap számára.</span><span class="sxs-lookup"><span data-stu-id="b0312-115">Otherwise, the tabs will be collapsed when they aren't being used, to gain more screen space for the page.</span></span>

## <a name="why-do-i-sometimes-see-different-shortcut-menus-when-i-right-click"></a><span data-ttu-id="b0312-116">Miért jelennek meg időnként különböző ikonok, ha az egér jobb gombjával kattintok?</span><span class="sxs-lookup"><span data-stu-id="b0312-116">Why do I sometimes see different shortcut menus when I right click?</span></span>

<span data-ttu-id="b0312-117">Ha a jobb gombbal kattint egy szerkeszthető mezőre (vagy kijelölt szövegre), a böngésző helyi menüjének ikonjai jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="b0312-117">If you right-click in an editable field (or if text is selected), the browser's shortcut menu is displayed.</span></span> <span data-ttu-id="b0312-118">Ezen menü segítségével érheti el a **Kivágás**, a **Másolás** és a **Beillesztés** parancsokat.</span><span class="sxs-lookup"><span data-stu-id="b0312-118">This menu gives you access to the **Cut**, **Copy**, and **Paste** commands.</span></span> <span data-ttu-id="b0312-119">Ezeket a parancsokat nem tudjuk beágyazni a helyi menükbe, mert biztonsági okokból a böngészők nem teszik lehetővé számunkra, hogy a vágólapjához a programban hozzáférjünk.</span><span class="sxs-lookup"><span data-stu-id="b0312-119">We can't embed these commands into the shortcut menus because, for security reasons, browsers don't allow us to programmatically access the system clipboard.</span></span>

<span data-ttu-id="b0312-120">Ha a jobb gombbal kattint egy mező címkéjére, vagy egy csak olvasható vezérlőelem értékére, látni fogja a helyi menüt.</span><span class="sxs-lookup"><span data-stu-id="b0312-120">If you right-click a field label or the value of a read-only control, you'll see the shortcut menu.</span></span>

<span data-ttu-id="b0312-121">Annak érdekében, hogy megkönnyítsük a billentyűzetről való hozzáférést, terveink között szerepel egy billentyűparancs létrehozása, amely megnyitja a helyi menüjét.</span><span class="sxs-lookup"><span data-stu-id="b0312-121">To make keyboard access easier, we plan to implement a keyboard shortcut in the future that will open the shortcut menu.</span></span>

## <a name="where-is-the-view-details-functionality"></a><span data-ttu-id="b0312-122">Hol található a Részletek megtekintése funkció?</span><span class="sxs-lookup"><span data-stu-id="b0312-122">Where is the View details functionality?</span></span>

<span data-ttu-id="b0312-123">A **Részletek megtekintése** beállítás több módon is elérhető:</span><span class="sxs-lookup"><span data-stu-id="b0312-123">The **View details** option is available in a couple of ways:</span></span>

- <span data-ttu-id="b0312-124">Ha valamelyik vezérlő rendelkezik **Részletek megtekintése** lehetőséggel, és a vezérlő értékkel is rendelkezik, ez az érték fog megjelenni hivatkozásként.</span><span class="sxs-lookup"><span data-stu-id="b0312-124">If a control has **View details** capabilities, and if the control has a value, that value is displayed as a hyperlink.</span></span> <span data-ttu-id="b0312-125">Rákattinthat a hivatkozásra a további részleteket tartalmazó lap megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="b0312-125">You can click the hyperlink to open a page that contains additional details.</span></span>
- <span data-ttu-id="b0312-126">A **Részletek megtekintése** lehetőség megtalálható továbbá a helyi menüben is.</span><span class="sxs-lookup"><span data-stu-id="b0312-126">**View details** is also an option on shortcut menus.</span></span> <span data-ttu-id="b0312-127">További tájékoztatást talál a jobb kattintáskor megjelenített helyi menükről az előző fejezetben.</span><span class="sxs-lookup"><span data-stu-id="b0312-127">For more information about when shortcut menus are displayed when you right-click, see the previous section.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]