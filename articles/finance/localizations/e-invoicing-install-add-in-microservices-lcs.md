---
title: A mikroszolgáltatások bővítményének telepítése a Lifecycle Services szolgáltatásba
description: Ez a cikk bemutatja, hogyan lehet telepíteni az Elektronikus számlázás bővítményt a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban.
author: gionoder
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 938b00192acc0ff5534239f2f280792471181fad
ms.sourcegitcommit: 1ecfc1d8afb2201ab895ae6f93304ba2b120f14b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/21/2022
ms.locfileid: "9710808"
---
# <a name="install-the-add-in-for-microservices-in-lifecycle-services"></a>A mikroszolgáltatások bővítményének telepítése a Lifecycle Services szolgáltatásba

[!include [banner](../includes/banner.md)]

Microsoft Dynamics Az elektronikus számlázási szolgáltatás hitelesítéséhez regisztrálnia kell a 365 Dynamics 365 Supply Chain Management Pénzügy vagy környezet szolgáltatást a szolgáltatási platformon Microsoft Dynamics azáltal, hogy telepíti a környezet bővítményét a Lifecycle Services (LCS) szolgáltatásban.

A következő lépések szerint regisztrálhat egy környezetet.

1. Jelentkezzen be a LCS-fiók.
2. A projekt-irányítópulton válasszon ki egy LCS-projektet.
2. A projektben, a **Környezet** irányítópulton válassza ki a saját telepített környezetet. A kiválasztott környezetnek futnia kell.
3. Az Integráció **Power Platform lap Környezeti bővítmények** **szakaszában válassza az Új bővítmény telepítése lehetőséget**.**·**
4. Válassza az **Elektronikus számlázás** lehetőséget.
5. **Az AAD alkalmazásazonosító mezőben** adja meg a rögzített értéket **091c98b0-a1c9-4b02-b62c-7753395ccabe**. Ez az érték mindig rögzítve van. Győződjön meg róla, hogy csak egy globálisan egyedi azonosítót (GUID) ad meg. Ne szerepeljenek más szimbólumok, például szóközök, vesszők, időszakok és idézőjelek.
6. Az **AAD-bérlőazonosító** mezőbe írja be az Azure előfizetési fiókja bérlőazonosítóját. A Azure Active Directory megadott (Azure AD) bérlőnek ugyanannak a bérlőnek kell lennie, mint aki a szabályozó konfigurációs szolgáltatás (RCS) számára használatos.
7. Ellenőrizze a feltételeket, majd jelölje be a jelölőnégyzetet.
8. Válassza a **Telepítés** parancsot. Néhány perc múlva az állapotot változik **Telepítés folyamatban** állapotról **Telepítve** értékre. Lehet, hogy frissítenie kell a lapot, hogy látssa ezt a változtatást.

Az elektronikus számlázás már használatra kész.

> [!NOTE]
> A vállalatok általában több pénzügyi és ellátásilánc-kezelési környezetben is működnek. Ilyen környezetek például a termelési környezetek, a felhasználói elfogadási teszt (UAT) környezetek és a fejlesztői (box) környezetek. Az előző eljárást minden olyan környezetben végre kell végrehajtania, amely elektronikus számlázáshoz kíván kapcsolódni.
