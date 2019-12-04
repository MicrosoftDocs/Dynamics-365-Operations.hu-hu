---
title: Intézkedési kódok beállítása
description: Az intézkedéskódok beállításával adhatja meg, hogyan kell feldolgozni egy vevő által visszaküldött cikket.
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReturnDispositionCode
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a85f804344abec37d85e1ce15f064c8a0b901546
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/18/2019
ms.locfileid: "2813109"
---
# <a name="set-up-disposition-codes"></a><span data-ttu-id="6b345-103">Intézkedési kódok beállítása</span><span class="sxs-lookup"><span data-stu-id="6b345-103">Set up disposition codes</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="6b345-104">Az intézkedéskódok beállításával adhatja meg, hogyan kell feldolgozni egy vevő által visszaküldött cikket.</span><span class="sxs-lookup"><span data-stu-id="6b345-104">You can set up disposition codes to specify how to process an item that is returned by a customer.</span></span> <span data-ttu-id="6b345-105">Hozzon létre például egy **Javítás és visszaküldés** intézkedéskódot annak jelzésére, hogy a visszaküldött cikket megjavítják, majd visszaküldik a vevőnek.</span><span class="sxs-lookup"><span data-stu-id="6b345-105">For example, create a disposition code named **Repair and return** to indicate that the returned item will be repaired and then returned to the customer.</span></span> <span data-ttu-id="6b345-106">A vevők által visszaküldött cikkek esetében használt tipikus intézkedéskódokra további példákért lásd: [A visszaadott cikkek kivezetési módjának megadása](specify-how-to-dispose-of-returned-items.md).</span><span class="sxs-lookup"><span data-stu-id="6b345-106">For more examples of disposition codes that are typically used for items that are returned by customers, see [Specify how to dispose of returned items](specify-how-to-dispose-of-returned-items.md).</span></span>

<span data-ttu-id="6b345-107">Okkód beállításával segíthet megmagyarázni, miért került sor egy cikk visszaküldésére.</span><span class="sxs-lookup"><span data-stu-id="6b345-107">You can also set up a reason code to help explain why an item was returned.</span></span> <span data-ttu-id="6b345-108">Az okkódokkal kapcsolatos további tudnivalókat lásd: [Visszaadási okkódok beállítása](set-up-return-reason-code.md).</span><span class="sxs-lookup"><span data-stu-id="6b345-108">For more information about reason codes, see [Set up return reason codes](set-up-return-reason-code.md).</span></span>

1.  <span data-ttu-id="6b345-109">Kattintson az **Értékesítés és marketing** \> **Beállítás** \> **Értékesítési rendelések** \> **Visszaadás** \> **Intézkedési kódok**.</span><span class="sxs-lookup"><span data-stu-id="6b345-109">Click **Sales and marketing** \> **Setup** \> **Sales orders** \> **Returns** \> **Disposition codes**.</span></span>

2.  <span data-ttu-id="6b345-110">Kattintson az **Új** elemre, vagy nyomja le a CTRL+N billentyűkombinációt egy új intézkedéskód létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="6b345-110">Click **New** or press CTRL+N to create a new disposition code.</span></span>

3.  <span data-ttu-id="6b345-111">Adjon meg egy egyedi, jellemző nevet, válasszon ki egy műveletet, majd adja meg az intézkedéskód leírását.</span><span class="sxs-lookup"><span data-stu-id="6b345-111">Enter a unique, descriptive name, select an action, and enter a description for the disposition code.</span></span>

4.  <span data-ttu-id="6b345-112">Ha az intézkedési kódhoz bármilyen díjat szeretne meghatározni a vevők számára, a **Költségek** gombra kattintva nyissa meg a **Költségek beállítása** képernyőt.</span><span class="sxs-lookup"><span data-stu-id="6b345-112">If you want to associate any customer charges with this disposition code, click the **Charges** button to open the **Set up charges** form.</span></span>

5.  <span data-ttu-id="6b345-113">Ha a vállalat saját intézkedési kódjainak egyeztetése céljából külső kódokat is meg szeretne határozni, a **Külső kódok** gombra kattintva nyissa meg a **Külső kódok** képernyőt.</span><span class="sxs-lookup"><span data-stu-id="6b345-113">If you want to define any external codes to match with the company's own disposition codes, click the **External codes** button to open the **External codes** form.</span></span>

## <a name="see-also"></a><span data-ttu-id="6b345-114">Lásd még</span><span class="sxs-lookup"><span data-stu-id="6b345-114">See also</span></span>

[<span data-ttu-id="6b345-115">Vevői visszáru áttekintése</span><span class="sxs-lookup"><span data-stu-id="6b345-115">Customer returns overview</span></span>](disposition-and-return-reason-codes.md)

<span data-ttu-id="6b345-116">[Intézkedési kódok (képernyő)](https://technet.microsoft.com/library/hh597113\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="6b345-116">[Disposition codes (form)](https://technet.microsoft.com/library/hh597113\(v=ax.60\))</span></span>

<span data-ttu-id="6b345-117">[Automatikus költségek (képernyő)](https://technet.microsoft.com/library/aa582856\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="6b345-117">[Auto charges (form)](https://technet.microsoft.com/library/aa582856\(v=ax.60\))</span></span>

<span data-ttu-id="6b345-118">[Külső kódok (képernyő)](https://technet.microsoft.com/library/aa583814\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="6b345-118">[External codes (form)](https://technet.microsoft.com/library/aa583814\(v=ax.60\))</span></span>

  


