---
title: Az ügyfél kapcsolata megszakad
description: Ez a cikk bemutatja, hogy mi a teendő, ha a vevő kapcsolata megszakad a saját környezetével, és nem tudja, ennek mi az oka.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e9ec43ad0a7d121eb247d81d4b506556a0fa2214
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5794901"
---
# <a name="client-disconnects"></a><span data-ttu-id="8b113-103">Az ügyfél kapcsolata megszakad</span><span class="sxs-lookup"><span data-stu-id="8b113-103">Client disconnects</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="8b113-104">**Környezet részletes adatai**</span><span class="sxs-lookup"><span data-stu-id="8b113-104">**Environment details**</span></span> 

<span data-ttu-id="8b113-105">A probléma bármely környezetben előfordulhat.</span><span class="sxs-lookup"><span data-stu-id="8b113-105">This issue can occur in all environments.</span></span>
 
<span data-ttu-id="8b113-106">**Tünet**</span><span class="sxs-lookup"><span data-stu-id="8b113-106">**Symptom**</span></span> 

<span data-ttu-id="8b113-107">A vevő kapcsolata megszakad saját környezetével, és nem tudja, ennek mi az oka.</span><span class="sxs-lookup"><span data-stu-id="8b113-107">The customer is disconnected from his or her environment and doesn't know why.</span></span> <span data-ttu-id="8b113-108">A vevőnek a következő hibaüzenetek egyike jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="8b113-108">The customer receives one of the following error messages:</span></span>

- <span data-ttu-id="8b113-109">A kapcsolata megszakadt.</span><span class="sxs-lookup"><span data-stu-id="8b113-109">We've lost your connection.</span></span> <span data-ttu-id="8b113-110">A munka folytatásához kattintson a Bezárás gombra.</span><span class="sxs-lookup"><span data-stu-id="8b113-110">Click Close to continue working.</span></span>
- <span data-ttu-id="8b113-111">Úgy tűnik, hogy megszakadt a hálózati kapcsolat. Az újbóli próbálkozáshoz kattintson az Ismét gombra.</span><span class="sxs-lookup"><span data-stu-id="8b113-111">It appears you lost network connectivity, click Retry to try again.</span></span>

<span data-ttu-id="8b113-112">**Piros zászló**</span><span class="sxs-lookup"><span data-stu-id="8b113-112">**Red flag**</span></span>

<span data-ttu-id="8b113-113">A probléma gyakran előfordul, amikor a felhasználók az implementációs fázisban vannak, termelési és tesztkörnyezetek információit hasonlítják össze, és elfelejtik, hogy munkamenetek között mozognak.</span><span class="sxs-lookup"><span data-stu-id="8b113-113">This issue often occurs when users are in the implementation stage, are comparing information across production and test environments, and forget that they are moving between sessions.</span></span> <span data-ttu-id="8b113-114">Ha a felhasználók ebben a fázisban vannak, akkor nagy valószínűséggel felmerül ez a probléma.</span><span class="sxs-lookup"><span data-stu-id="8b113-114">If users are at this stage, they will most likely experience this issue.</span></span>

<span data-ttu-id="8b113-115">**Kibocsátás**</span><span class="sxs-lookup"><span data-stu-id="8b113-115">**Issue**</span></span> 

<span data-ttu-id="8b113-116">**Böngészőtípusok:** Google Chrome, Internet Explorer, és Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="8b113-116">**Browser types:** Google Chrome, Internet Explorer, and Microsoft Edge</span></span>

<span data-ttu-id="8b113-117">A felhasználók kapcsolata a Microsoft Dynamics 365 Human Resources megoldással megszakad, amikor egyszerre két munkamenet van nyitva ugyanahhoz a felhasználóhoz és ugyanolyan típusú böngészőben.</span><span class="sxs-lookup"><span data-stu-id="8b113-117">Microsoft Dynamics 365 Human Resources disconnects users when two different sessions are open at the same time for the same user and the same browser type.</span></span> <span data-ttu-id="8b113-118">(Például A felhasználó Chrome-ban nézi mind az 1. környezetet, mind a 2. környezetet.) Nem számít, ha a felhasználó különböző böngészőablakokat vagy különböző lapokat nyit meg.</span><span class="sxs-lookup"><span data-stu-id="8b113-118">(For example, user A is viewing both environment 1 and environment 2 in Chrome.) It doesn't matter whether the users open different browser windows or different tabs.</span></span> <span data-ttu-id="8b113-119">Ha azonos felhasználói hitelesítő adatokkal van bejelentkezve az 1. és 2. környezetbe ugyanabban a pillanatban és ugyanolyan típusú böngészővel, a Human Resources alkalmazás az egyik munkamenet kapcsolatát megszakítja.</span><span class="sxs-lookup"><span data-stu-id="8b113-119">If the same user credentials are used to sign in to both environment 1 and environment 2 at the same time and in the same browser type, Human Resources disconnects one of the sessions.</span></span>

<span data-ttu-id="8b113-120">**Megoldás**</span><span class="sxs-lookup"><span data-stu-id="8b113-120">**Solution**</span></span>

<span data-ttu-id="8b113-121">Győződjön meg arról, hogy egyszerre az adott típusú böngészőben csak egy környezetet nyisson meg.</span><span class="sxs-lookup"><span data-stu-id="8b113-121">Make sure that only one environment is open at a time for a given browser type.</span></span> <span data-ttu-id="8b113-122">A felhasználók több munkamenetet is megnyithatnak ugyanabban a környezetben (azaz egy böngészőben több lapot).</span><span class="sxs-lookup"><span data-stu-id="8b113-122">Users can open multiple sessions to the same environment (that is, multiple tabs in the same browser).</span></span>

<span data-ttu-id="8b113-123">A felhasználóknak, akik egyszerre két környezet között szeretnének mozogni, minden egyes környezetet különböző típusú böngészőben kell megnyitniuk.</span><span class="sxs-lookup"><span data-stu-id="8b113-123">Users who want to jump between two environments at the same time should open each environment in a different browser type.</span></span> <span data-ttu-id="8b113-124">(Például A felhasználó megnyithatja az 1. környezetet Chrome-ban, és a 2. környezetet Microsoft Edge-ben.)</span><span class="sxs-lookup"><span data-stu-id="8b113-124">(For example, user A can view environment 1 in Chrome and environment 2 in Microsoft Edge.)</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]