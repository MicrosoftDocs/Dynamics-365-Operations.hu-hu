---
title: Főszámla-kategóriák beállítása
description: Ez a cikk bemutatja a főszámla-kategóriák beállítását a Dynamics 365 Pénzügyben.
author: aprilolson
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: MainAccountCategory, MainAccountCategoryLink
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c48011c9988bdca694851476540db574efef7909
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8879563"
---
# <a name="set-up-main-account-categories"></a>Főszámla-kategóriák beállítása

[!include [banner](../../includes/banner.md)]

Ez a témakör bemutatja a főszámla-kategóriák beállítását. A Főszámla-kategóriák használhatók a pénzügyi jelentések alapértelmezett jelentéseihez és a Power BI szolgáltatásban. Az alapértelmezés szerint létrejött Főszámla-kategóriákat át lehet nevezni, de nem lehet törölni. További főkönyviszámla-kategóriákat hozhat létre, majd használhatja azokat jelentéshez és elemzéshez. Ez a cikk az USMF bemutató vállalatot használja.

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
