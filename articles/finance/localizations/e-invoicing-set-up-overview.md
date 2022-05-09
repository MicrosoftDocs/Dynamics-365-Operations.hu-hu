---
title: Elektronikus számlázás beállítása
description: Ez a témakör áttekintést nyújt az elektronikus számlázás beállításának és beállításának folyamatával kapcsolatban.
author: dkalyuzh
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 42e617e26e7658fae9ee54cb8a4dee45314fddaa
ms.sourcegitcommit: 5f7177b9ab192b5a6554bfc2f285f7cf0b046264
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/30/2022
ms.locfileid: "8661692"
---
# <a name="electronic-invoicing-setup"></a>Elektronikus számlázás beállítása

[!include [banner](../includes/banner.md)]

Ez a témakör áttekintést nyújt az elektronikus számlázás beállításának és beállításának folyamatával kapcsolatban. A beállítási lépéseket az itt megadott sorrendben kell végrehajtani. Ha egy lépés kötelező, de kihagyja, a funkció nem működik megfelelően, és több hiba történik a következő lépések során vagy a funkció használata során. 

Mielőtt hozzákezd, győződjön meg arról, hogy minden fő összetevő helyesen van beállítva, hogy jelentkezett-e be a konfigurációs szolgáltatásra (RCS), illetve hogy telepítve van-e Microsoft Dynamics az RCS egy példánya, valamint hogy a 365 Dynamics 365 Supply Chain Management Pénzügy vagy a környezet elektronikus számlázási bővítménye telepítve van-e. A további tudnivalókat lásd [az Elektronikus számlázás regisztrációja és telepítése oldalon](e-invoicing-install-add-in-microservices-lcs.md).

Ezután állítsa be az Azure-erőforrásokat, amelyeken az elektronikus számlázásnak szüksége van a munkához. A további tudnivalókat lásd [Az Azure-erőforrások beállítása elektronikus számlázáshoz](e-invoicing-set-up-azure-resources.md).

A fő összetevők konfigurálása után az RCS segítségével állítsa be az elektronikus számlázás fő logikai összetevőit. Először adja meg a karbantartott szolgáltatási környezetek számát. Ily módon definiálni kell a logikai adatokat és a konfigurációk particionálását, így garantálható, hogy legyen határ a fejlesztői vagy tesztkörnyezet és a gyártási környezet között. Ha rugalmasan kell beállítani a fejlesztési folyamatot, több különálló fejlesztői és tesztkörnyezetre lehet szükség. A szolgáltatási környezetek meghatározásán túl kapcsolhatja az üzleti alkalmazásokat, például a Pénzügy vagy az Ellátásilánc-kezelés modult, közvetlenül az RCS rendszerből, hogy beállítsa az elektronikus számlázással való helyes működéshez szükséges paramétereket. A környezetekkel kapcsolatos további tudnivalókat lásd: Szolgáltatási [környezetek](e-invoicing-service-environments.md).

Miután minden beállítását beállította, létrehozhat saját globalizációs funkciókat, amelyek az elektronikus dokumentumok feldolgozásának és az adatok átalakításának, illetve a globális tárházból történő importálásának különböző helyzeteket határozzák meg. A globalizációs funkciókkal való munkáról [a "Globalizációs funkciók használata" funkció tartalmaz további tudnivalókat](e-invoicing-working-globalization-features.md).

Ha a helyzet esetén integrálni kell az e-mail SharePoint címeket, vagy fel kell használni a bejövő elektronikus dokumentumokat, [a](e-invoicing-process-incoming-electronic-documents.md) bejövő elektronikus dokumentumok feldolgozásával kapcsolatban a csatornák beállításával és használatával kapcsolatos tudnivalókat lásd.
