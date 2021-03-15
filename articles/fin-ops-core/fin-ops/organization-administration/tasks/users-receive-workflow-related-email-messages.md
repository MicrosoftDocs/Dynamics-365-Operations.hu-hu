---
title: Segítségével a felhasználók a munkafolyamattal kapcsolatos e-mail üzeneteket.
description: Beállítható, hogy a rendszer küldjön e-maileket a felhasználók számára, amikor a munkafolyamattal kapcsolatos események zajlanak le.
author: jasongre
manager: AnnBe
ms.date: 06/01/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, SysUserSetup
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 221e38cbe31e2ad24a56cb2e71206a1ebcdd619e
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/19/2020
ms.locfileid: "4799004"
---
# <a name="enable-users-to-receive-workflow-related-email-messages"></a>Segítségével a felhasználók a munkafolyamattal kapcsolatos e-mail üzeneteket.

[!include [banner](../../includes/banner.md)]

Beállítható, hogy a rendszer küldjön e-maileket a felhasználók számára, amikor a munkafolyamattal kapcsolatos események zajlanak le. Például e-mail üzenetek küldhetők a felhasználók számára, amikor dokumentumok vannak hozzájuk rendelve jóváhagyásra. Ez az eljárás az USMF bemutatócéget használja.

1. Ugorjon a **Navigációs ablaktábla > Modulok > Rendszerfelügyelet > Felhasználók > Felhasználók** lehetőségre.
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
3. A **Műveleti ablaktáblán** kattintson a **Felhasználói beállítások** elemre.
4. Kattintson a **Munkafolyamat** fülre. Győződjön meg róla, hogy az **Értesítések** szakasz ki van bontva. Az **Értesítések** szakaszban megadhatja, hogy a felhasználó hogyan kapjon értesítést a munkafolyamattal kapcsolatos eseményekről.  
5. A **Sortétel-munkafolyamat értesítési típusa** mezőben válasszon ki egy lehetőséget.
    - Csoportosított – A sortételek értesítései egyetlen e-mailbe vannak csoportosítva.
    - Egyedi – Az egyes sortételekhez egy e-mailt küld.  
    - Jelölje be az **Értesítések küldése e-mailben** jelölőnégyzetet, ha azt szeretné, hogy a felhasználó értesítések kapjon a kliensben.  
6. Kattintson a **Mentés** gombra.
7. Zárja be a lapot.

> [!NOTE]
> A munkafolyamat e-mail sablonjait a rendszer az e-mailek sablonjaiból vagy a szervezet e-mail sablonjaiból határozza meg attól függően, hogy a munkafolyamat rendszerszintű (nem vállalati specifikus) vagy szervezeti szintű (vállalatra jellemző) munkafolyamat-e.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]