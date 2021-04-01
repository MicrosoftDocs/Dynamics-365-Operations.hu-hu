---
title: A visszaadott cikkek továbbadása vizsgálatra
description: Visszáru cikkek rögzítésekor a cikkeket vizsgálatra kell küldeni, mielőtt visszajuttatná azokat a készletbe, vagy valamilyen más intézkedést hozna.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSJournalTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 04b27a5560b6126fde3028f653a89059bb765844
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5254965"
---
# <a name="pass-returned-items-on-to-inspection"></a><span data-ttu-id="d6747-103">A visszaadott cikkek továbbadása vizsgálatra</span><span class="sxs-lookup"><span data-stu-id="d6747-103">Pass returned items on to inspection</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="d6747-104">Visszáru cikkek rögzítésekor a cikkeket vizsgálatra küldheti, mielőtt visszajuttatná azokat a készletbe, vagy valamilyen más intézkedést hozna.</span><span class="sxs-lookup"><span data-stu-id="d6747-104">When registering a returned item, you may determine that an item should be sent for inspection before it is returned to inventory or disposed of in some other way.</span></span>

1.  <span data-ttu-id="d6747-105">Kattintson a következőkre **Készletgazdálkodás** \> **Naplók** \> **Cikkérkeztetés** \> **Cikkérkeztetés**.</span><span class="sxs-lookup"><span data-stu-id="d6747-105">Click **Inventory management** \> **Journals** \> **Item arrival** \> **Item arrival**.</span></span>
    
    <span data-ttu-id="d6747-106">\-vagy-</span><span class="sxs-lookup"><span data-stu-id="d6747-106">\-or-</span></span>
    
    <span data-ttu-id="d6747-107">Kattintson a következőkre **Készletgazdálkodás** \> **Naplók** \> **Cikkérkeztetés** \> **Termelések beérkezése**.</span><span class="sxs-lookup"><span data-stu-id="d6747-107">Click **Inventory management** \> **Journals** \> **Item arrival** \> **Production input**.</span></span>

2.  <span data-ttu-id="d6747-108">A cikkbevételezéseket a szokásos módon regisztrálja a **Helynapló** képernyőn.</span><span class="sxs-lookup"><span data-stu-id="d6747-108">On the **Location journal** form, register the receipt of an item as usual.</span></span>
    

    > [!NOTE]
    > <P><span data-ttu-id="d6747-109">A visszáru cikkek bevételezésének regisztrálásával kapcsolatos tudnivalókat lásd: <A href="register-the-receipt-of-returned-items.md">A visszaadott cikkek bevételezésének rögzítése</A></span><span class="sxs-lookup"><span data-stu-id="d6747-109">For information about registering the receipt of returned items, see <A href="register-the-receipt-of-returned-items.md">Register the receipt of returned items</A></span></span></P>



3.  <span data-ttu-id="d6747-110">Az **Alapértelmezett értékek** lapon, a **Kezelés módja** területen jelölje be a **Karanténkezelés** négyzetet.</span><span class="sxs-lookup"><span data-stu-id="d6747-110">On the **Default values** tab, in the **Mode of handling** area, select the **Quarantine management** box.</span></span>

<span data-ttu-id="d6747-111">Ezzel arra utasítja a rendszert, hogy hozzon létre egy karanténutasítást, és a vizsgálatot végrehajtó személy vagy részleg válaszolni fog a rendelésre a **Karanténutasítás** képernyőn.</span><span class="sxs-lookup"><span data-stu-id="d6747-111">This will prompt the system to create a quarantine order, and the person or department that performs inspections will respond to this order using the **Quarantine order** form.</span></span>

## <a name="see-also"></a><span data-ttu-id="d6747-112">Lásd még</span><span class="sxs-lookup"><span data-stu-id="d6747-112">See also</span></span>

[<span data-ttu-id="d6747-113">A visszaadott cikkek vizsgálatának végigvitele</span><span class="sxs-lookup"><span data-stu-id="d6747-113">Take returned items through inspection</span></span>](take-returned-items-through-inspection.md)

[<span data-ttu-id="d6747-114">A visszaadott cikkek kivezetési módjának megadása</span><span class="sxs-lookup"><span data-stu-id="d6747-114">Specify how to dispose of returned items</span></span>](specify-how-to-dispose-of-returned-items.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]