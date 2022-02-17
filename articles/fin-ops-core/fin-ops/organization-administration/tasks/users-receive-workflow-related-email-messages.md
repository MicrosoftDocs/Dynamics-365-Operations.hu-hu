---
title: Segítségével a felhasználók a munkafolyamattal kapcsolatos e-mail üzeneteket.
description: Beállítható, hogy a rendszer küldjön e-maileket a felhasználók számára, amikor a munkafolyamattal kapcsolatos események zajlanak le.
author: jasongre
ms.date: 06/01/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysUserManagement, SysUserSetup
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 368fe2fbf1f8a1adcabe37ced5ed942f9fb86fc8
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8070425"
---
# <a name="enable-users-to-receive-workflow-related-email-messages"></a>Segítségével a felhasználók a munkafolyamattal kapcsolatos e-mail üzeneteket.

[!include [banner](../../includes/banner.md)]


[!INCLUDE [PEAP](../../../../includes/peap-1.md)]

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