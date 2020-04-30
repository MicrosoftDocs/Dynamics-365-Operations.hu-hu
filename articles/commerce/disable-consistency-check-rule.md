---
title: Kiskereskedelmi tranzakciók konzisztencia-ellenőrzési szabályainak letiltása
description: Ebben a témakörben részletes leírást találhat a tranzakciók konzisztencia-ellenőrzési szabályainak letiltására használatos funkcióról a Microsoft Dynamics 365 Commerce szolgáltatásban.
author: josaw1
manager: AnnBe
ms.date: 10/15/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 37209f1c1de19335f5f9fa6636ab55dd8b2fccc1
ms.sourcegitcommit: 02640a0f63daa9e509146641824ed623c4d69c7f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2020
ms.locfileid: "3265526"
---
# <a name="disable-rules-in-the-retail-transaction-consistency-checker"></a><span data-ttu-id="ca41f-103">Kiskereskedelmi tranzakciók konzisztencia-ellenőrzési szabályainak letiltása</span><span class="sxs-lookup"><span data-stu-id="ca41f-103">Disable rules in the retail transaction consistency checker</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ca41f-104">A kiskereskedők csak rájuk jellemző, egyedi üzleti esetekkel és folyamatokkal rendelkezhetnek.</span><span class="sxs-lookup"><span data-stu-id="ca41f-104">Retailers can have business scenarios and processes that are unique to them.</span></span> <span data-ttu-id="ca41f-105">Ezért nem minden kiskereskedőre érvényes az összes szabály, amely alapértelmezés szerint szerepel a kereskedelmi tranzakciós konzisztencia-ellenőrzési funkciójában.</span><span class="sxs-lookup"><span data-stu-id="ca41f-105">Therefore, not all the rules that are included by default in the commerce transaction consistency checker are applicable to all retailers.</span></span> <span data-ttu-id="ca41f-106">A különbségeknek figyelembe vétele érdekében a Microsoft Dynamics 365 Commerce szolgáltatásban rendelkezésre áll a funkció, amellyel a nem érvényes szabályok letilthatók.</span><span class="sxs-lookup"><span data-stu-id="ca41f-106">To accommodate differences, Microsoft Dynamics 365 Commerce provides functionality that can be used to disable the rules that aren't applicable.</span></span>

<span data-ttu-id="ca41f-107">Ha meg szeretné tekinteni a tranzakciók konzisztencia-ellenőrzése funkció az Ön környezetében érvényes szabályait, valamint az egyes szabályok állapotát, lépjen a **Retail és Commerce \> Központ beállítása \> Paraméterek \> Commerce-paraméterek** pontra, majd válassza a **Tranzakció-ellenőrzés** lapot.</span><span class="sxs-lookup"><span data-stu-id="ca41f-107">To view the list of rules that are available in the transaction consistency checker in your environment, and to see the status of each rule, go to **Retail and Commerce \> Headquarters setup \> Parameters \> Commerce parameters**, and select the **Transaction validation** tab.</span></span>

<span data-ttu-id="ca41f-108">Alapértelmezés szerint az összes szabály állapota **Engedélyezve**.</span><span class="sxs-lookup"><span data-stu-id="ca41f-108">By default, the status of every rule is set to **Enabled**.</span></span> <span data-ttu-id="ca41f-109">Ez azt jelenti, hogy a rendszer az összes szabályt alkalmazza a tranzakciók ellenőrzésére, mielőtt kereskedelmi kimutatásokba lehívják őket.</span><span class="sxs-lookup"><span data-stu-id="ca41f-109">Therefore, all the rules are used to validate transactions before they are pulled into the commerce statements.</span></span> <span data-ttu-id="ca41f-110">Ha az egyik szabályt le szeretné tiltani, módosítsa állapotát **Letiltva** értékre.</span><span class="sxs-lookup"><span data-stu-id="ca41f-110">To disable a rule, change its status to **Disabled**.</span></span> <span data-ttu-id="ca41f-111">A letiltott szabályokat a program nem veszi figyelembe a tranzakciók ellenőrzésekor a kimutatásszámítási folyamat során.</span><span class="sxs-lookup"><span data-stu-id="ca41f-111">Disabled rules aren't considered when transactions are validated during the statement calculation process.</span></span>

<span data-ttu-id="ca41f-112">Ha a teljes ellenőrzési folyamatot szeretné elkerülni az engedélyezett szabályoktól függetlenül, lépjen a **Retail és Commerce \> Központ beállítása \> Paraméterek \> Commerce-paraméterek** pontra, majd a **Tranzakció-ellenőrzés** lapon állítsa a **Commerce-tranzakciók konzisztencia-ellenőrzésének letiltása** beállítást **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="ca41f-112">To bypass the whole validation process, regardless of the rules that are enabled, go to **Retail and Commerce \> Headquarters setup \> Parameters \> Commerce parameters**, and then, on the **Transaction validation** tab, set the **Disable consistency checker for Commerce transactions** option to **Yes**.</span></span> <span data-ttu-id="ca41f-113">Ha ez a lehetőség **Nem** értékre van állítva, akkor a felhasználói felületen (UI) nem állítható vissza **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="ca41f-113">After this option is set to **No**, it can't be set back to **Yes** from the user interface (UI).</span></span>
