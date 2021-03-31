---
title: Fő számla kategóriáinak beállítása
description: Ez a témakör bemutatja, hogyan állítsa be a főszámla-kategóriákat a Dynamics 365 Finance szolgáltatásban.
author: aprilolson
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MainAccountCategory, MainAccountCategoryLink
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 957fdc184410dc85f54cd3163799a9003f0727bb
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5222216"
---
# <a name="set-up-main-account-categories"></a>Fő számla kategóriáinak beállítása

[!include [banner](../../includes/banner.md)]

Ez a témakör bemutatja, hogyan állítsa be a főszámla-kategóriákat. A Főszámla-kategóriák használhatók a pénzügyi jelentések alapértelmezett jelentéseihez és a Power BI szolgáltatásban. Az alapértelmezés szerint létrejött Főszámla-kategóriákat át lehet nevezni, de nem lehet törölni. További főkönyviszámla-kategóriákat hozhat létre, majd használhatja azokat jelentéshez és elemzéshez. A témakörben az USMF bemutatóvállalat szerepel.

## <a name="create-a-main-account-category"></a>Főszámla-kategória létrehozása
1. Ugorjon a navigációs ablaktáblán a **Modulok > Főkönyv > Számlatükör > Számlák > Főszámla-kategóriák lehetőségre**.
2. Válassza az **Új** lehetőséget.
3. A **Főszámla-kategória** mezőben adjon meg egy egyedi nevet.
4. A **Leírás mezőben** adja meg a főszámla-kategória leírását.
5. A **Fő számla típusa** mezőben válassza ki azt a főszámlatípust, amelyet össze kíván kapcsolni a kategóriával.

## <a name="link-main-accounts-to-account-category"></a>Fő számlák csatolása számlakategóriához
1. Kattintson a **Fő számlák összekapcsolása** elemre.
2. Az **Összekapcsolt** oszlopban található jelölőnégyzet bejelölésével válassza ki azokat a fő számlákat a listáról, amelyeket a főszámla-kategóriához kíván rendelni. Ha a fú számlákat hozzárendeli a fő számla kategóriájához, azzal összesíti a számlák egyenlegét, amikor a kategóriát pénzügyi jelentéshez és elemzéshez használja.  
3. A fő számlák kiválasztásához jelölje be, vagy törölje a jelölést az **Összekapcsolt** elemnél.
4. Válassza ki az **OK** lehetőséget.
5. Válassza ki az **Igen** lehetőséget.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]