---
title: Kiskereskedelmi tranzakciók konzisztencia-ellenőrzési szabályainak letiltása
description: Ebben a témakörben részletes leírást találhat a kiskereskedelmi tranzakciók konzisztencia-ellenőrzési szabályainak letiltására használatos funkcióról a Microsoft Dynamics 365 Retail szolgáltatásban.
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
ms.openlocfilehash: 4bf8df2fb9f8f5c33ceb13eb012fb6879f81ec66
ms.sourcegitcommit: bdbca89bd9b328c282ebfb681f75b8f1ed96e7a8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/14/2019
ms.locfileid: "2586297"
---
# <a name="disable-rules-in-the-retail-transaction-consistency-checker"></a><span data-ttu-id="f5729-103">Kiskereskedelmi tranzakciók konzisztencia-ellenőrzési szabályainak letiltása</span><span class="sxs-lookup"><span data-stu-id="f5729-103">Disable rules in the retail transaction consistency checker</span></span> 

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="f5729-104">A kiskereskedők csak rájuk jellemző, egyedi üzleti esetekkel és folyamatokkal rendelkezhetnek.</span><span class="sxs-lookup"><span data-stu-id="f5729-104">Retailers can have business scenarios and processes that are unique to them.</span></span> <span data-ttu-id="f5729-105">Ezért nem minden kiskereskedőre érvényes az összes szabály, amely alapértelmezés szerint szerepel a kiskereskedelmi tranzakciós konzisztencia-ellenőrzési funkciójában.</span><span class="sxs-lookup"><span data-stu-id="f5729-105">Therefore, not all the rules that are included by default in the retail transaction consistency checker are applicable to all retailers.</span></span> <span data-ttu-id="f5729-106">A különbségeknek figyelembe vétele érdekében a Microsoft Dynamics 365 Retail szolgáltatásban rendelkezésre áll a funkció, amellyel a nem érvényes szabályok letilthatók.</span><span class="sxs-lookup"><span data-stu-id="f5729-106">To accommodate differences, Microsoft Dynamics 365 Retail provides functionality that can be used to disable the rules that aren't applicable.</span></span>

<span data-ttu-id="f5729-107">Ha meg szeretné tekinteni a kiskereskedelmi tranzakciós konzisztencia-ellenőrzése funkció az Ön környezetében érvényes szabályait, valamint az egyes szabályok állapotát, lépjen a **Kiskereskedelem \> Központ beállítása \> Paraméterek \> Kiskereskedelmi paraméterek** pontra, majd válassza a **Tranzakció-ellenőrzés** lapot.</span><span class="sxs-lookup"><span data-stu-id="f5729-107">To view the list of rules that are available in the retail transaction consistency checker in your environment, and to see the status of each rule, go to **Retail \> Headquarters setup \> Parameters \> Retail parameters**, and select the **Transaction validation** tab.</span></span>

<span data-ttu-id="f5729-108">Alapértelmezés szerint az összes szabály állapota **Engedélyezve**.</span><span class="sxs-lookup"><span data-stu-id="f5729-108">By default, the status of every rule is set to **Enabled**.</span></span> <span data-ttu-id="f5729-109">Ez azt jelenti, hogy a rendszer az összes szabályt alkalmazza a kiskereskedelmi tranzakciók ellenőrzésére, mielőtt kiskereskedelmi kimutatásokba lehívják őket.</span><span class="sxs-lookup"><span data-stu-id="f5729-109">Therefore, all the rules are used to validate retail transactions before they are pulled into the retail statements.</span></span> <span data-ttu-id="f5729-110">Ha az egyik szabályt le szeretné tiltani, módosítsa állapotát **Letiltva** értékre.</span><span class="sxs-lookup"><span data-stu-id="f5729-110">To disable a rule, change its status to **Disabled**.</span></span> <span data-ttu-id="f5729-111">A letiltott szabályokat a program nem veszi figyelembe a kiskereskedelmi tranzakciók ellenőrzésekor a kimutatásszámítási folyamat során.</span><span class="sxs-lookup"><span data-stu-id="f5729-111">Disabled rules aren't considered when retail transactions are validated during the statement calculation process.</span></span>

<span data-ttu-id="f5729-112">Ha a teljes ellenőrzési folyamatot szeretné elkerülni az engedélyezett szabályoktól függetlenül, lépjen a **Kiskereskedelem \> Központ beállítása \> Paraméterek \> Kiskereskedelmi paraméterek** pontra, majd a **Tranzakció-ellenőrzés** lapon állítsa a **Kiskereskedelmi tranzakciók konzisztencia-ellenőrzésének letiltása** beállítást **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="f5729-112">To bypass the whole validation process, regardless of the rules that are enabled, go to **Retail \> Headquarters setup \> Parameters \> Retail parameters**, and then, on the **Transaction validation** tab, set the **Disable consistency checker for Retail transactions** option to **Yes**.</span></span> <span data-ttu-id="f5729-113">Ha ez a lehetőség **Nem** értékre van állítva, akkor a felhasználói felületen (UI) nem állítható vissza **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="f5729-113">After this option is set to **No**, it can't be set back to **Yes** from the user interface (UI).</span></span>
