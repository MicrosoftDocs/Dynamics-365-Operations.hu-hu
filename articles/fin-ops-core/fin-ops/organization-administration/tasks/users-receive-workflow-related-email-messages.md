---
title: Segítségével a felhasználók a munkafolyamattal kapcsolatos e-mail üzeneteket.
description: Beállítható, hogy a rendszer küldjön e-maileket a felhasználók számára, amikor a munkafolyamattal kapcsolatos események zajlanak le.
author: jasongre
manager: AnnBe
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
ms.openlocfilehash: 9a81e01c36081ce7131ee65344f583755fa3bfd3
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5564190"
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