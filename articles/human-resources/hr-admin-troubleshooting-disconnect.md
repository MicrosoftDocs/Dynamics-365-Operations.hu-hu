---
title: Az ügyfél kapcsolata megszakad
description: Ez a cikk bemutatja, hogy mi a teendő, ha a vevő kapcsolata megszakad a saját környezetével, és nem tudja, ennek mi az oka.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
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
ms.openlocfilehash: d02916283bbd4cee6502942020df1b275a0242b3
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2021
ms.locfileid: "5112847"
---
# <a name="client-disconnects"></a><span data-ttu-id="11c94-103">Az ügyfél kapcsolata megszakad</span><span class="sxs-lookup"><span data-stu-id="11c94-103">Client disconnects</span></span>

<span data-ttu-id="11c94-104">**Környezet részletes adatai**</span><span class="sxs-lookup"><span data-stu-id="11c94-104">**Environment details**</span></span> 

<span data-ttu-id="11c94-105">A probléma bármely környezetben előfordulhat.</span><span class="sxs-lookup"><span data-stu-id="11c94-105">This issue can occur in all environments.</span></span>
 
<span data-ttu-id="11c94-106">**Tünet**</span><span class="sxs-lookup"><span data-stu-id="11c94-106">**Symptom**</span></span> 

<span data-ttu-id="11c94-107">A vevő kapcsolata megszakad saját környezetével, és nem tudja, ennek mi az oka.</span><span class="sxs-lookup"><span data-stu-id="11c94-107">The customer is disconnected from his or her environment and doesn't know why.</span></span> <span data-ttu-id="11c94-108">A vevőnek a következő hibaüzenetek egyike jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="11c94-108">The customer receives one of the following error messages:</span></span>

- <span data-ttu-id="11c94-109">A kapcsolata megszakadt.</span><span class="sxs-lookup"><span data-stu-id="11c94-109">We've lost your connection.</span></span> <span data-ttu-id="11c94-110">A munka folytatásához kattintson a Bezárás gombra.</span><span class="sxs-lookup"><span data-stu-id="11c94-110">Click Close to continue working.</span></span>
- <span data-ttu-id="11c94-111">Úgy tűnik, hogy megszakadt a hálózati kapcsolat. Az újbóli próbálkozáshoz kattintson az Ismét gombra.</span><span class="sxs-lookup"><span data-stu-id="11c94-111">It appears you lost network connectivity, click Retry to try again.</span></span>

<span data-ttu-id="11c94-112">**Piros zászló**</span><span class="sxs-lookup"><span data-stu-id="11c94-112">**Red flag**</span></span>

<span data-ttu-id="11c94-113">A probléma gyakran előfordul, amikor a felhasználók az implementációs fázisban vannak, termelési és tesztkörnyezetek információit hasonlítják össze, és elfelejtik, hogy munkamenetek között mozognak.</span><span class="sxs-lookup"><span data-stu-id="11c94-113">This issue often occurs when users are in the implementation stage, are comparing information across production and test environments, and forget that they are moving between sessions.</span></span> <span data-ttu-id="11c94-114">Ha a felhasználók ebben a fázisban vannak, akkor nagy valószínűséggel felmerül ez a probléma.</span><span class="sxs-lookup"><span data-stu-id="11c94-114">If users are at this stage, they will most likely experience this issue.</span></span>

<span data-ttu-id="11c94-115">**Kibocsátás**</span><span class="sxs-lookup"><span data-stu-id="11c94-115">**Issue**</span></span> 

<span data-ttu-id="11c94-116">**Böngészőtípusok:** Google Chrome, Internet Explorer, és Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="11c94-116">**Browser types:** Google Chrome, Internet Explorer, and Microsoft Edge</span></span>

<span data-ttu-id="11c94-117">A felhasználók kapcsolata a Microsoft Dynamics 365 Human Resources megoldással megszakad, amikor egyszerre két munkamenet van nyitva ugyanahhoz a felhasználóhoz és ugyanolyan típusú böngészőben.</span><span class="sxs-lookup"><span data-stu-id="11c94-117">Microsoft Dynamics 365 Human Resources disconnects users when two different sessions are open at the same time for the same user and the same browser type.</span></span> <span data-ttu-id="11c94-118">(Például A felhasználó Chrome-ban nézi mind az 1. környezetet, mind a 2. környezetet.) Nem számít, ha a felhasználó különböző böngészőablakokat vagy különböző lapokat nyit meg.</span><span class="sxs-lookup"><span data-stu-id="11c94-118">(For example, user A is viewing both environment 1 and environment 2 in Chrome.) It doesn't matter whether the users open different browser windows or different tabs.</span></span> <span data-ttu-id="11c94-119">Ha azonos felhasználói hitelesítő adatokkal van bejelentkezve az 1. és 2. környezetbe ugyanabban a pillanatban és ugyanolyan típusú böngészővel, a Human Resources alkalmazás az egyik munkamenet kapcsolatát megszakítja.</span><span class="sxs-lookup"><span data-stu-id="11c94-119">If the same user credentials are used to sign in to both environment 1 and environment 2 at the same time and in the same browser type, Human Resources disconnects one of the sessions.</span></span>

<span data-ttu-id="11c94-120">**Megoldás**</span><span class="sxs-lookup"><span data-stu-id="11c94-120">**Solution**</span></span>

<span data-ttu-id="11c94-121">Győződjön meg arról, hogy egyszerre az adott típusú böngészőben csak egy környezetet nyisson meg.</span><span class="sxs-lookup"><span data-stu-id="11c94-121">Make sure that only one environment is open at a time for a given browser type.</span></span> <span data-ttu-id="11c94-122">A felhasználók több munkamenetet is megnyithatnak ugyanabban a környezetben (azaz egy böngészőben több lapot).</span><span class="sxs-lookup"><span data-stu-id="11c94-122">Users can open multiple sessions to the same environment (that is, multiple tabs in the same browser).</span></span>

<span data-ttu-id="11c94-123">A felhasználóknak, akik egyszerre két környezet között szeretnének mozogni, minden egyes környezetet különböző típusú böngészőben kell megnyitniuk.</span><span class="sxs-lookup"><span data-stu-id="11c94-123">Users who want to jump between two environments at the same time should open each environment in a different browser type.</span></span> <span data-ttu-id="11c94-124">(Például A felhasználó megnyithatja az 1. környezetet Chrome-ban, és a 2. környezetet Microsoft Edge-ben.)</span><span class="sxs-lookup"><span data-stu-id="11c94-124">(For example, user A can view environment 1 in Chrome and environment 2 in Microsoft Edge.)</span></span>
