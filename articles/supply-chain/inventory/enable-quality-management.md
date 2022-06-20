---
title: A minőség- és a szabálytalanságkezelés engedélyezése
description: Ez a cikk a Microsoft minőség- és szabálytalanságkezelési szolgáltatásainak beállításához és konfigurálásához nyújt áttekintést Dynamics 365 Supply Chain Management.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestAssociationTable, InventTestGroup, InventTestItemQualityGroup, InventTestTable, InventTestVariable, InventTestVariableOutcome, InventParameters, InventProblemType, InventProblemTypeSetup, InventQuarantineZone, InventTestDiagnosticType, InventTestReportSetup, SysUserManagement, InventTestRelatedOperations
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 66229e3692e87f774c553eae955794330602598c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8874043"
---
# <a name="enable-quality-and-nonconformance-management"></a>A minőség- és a szabálytalanságkezelés engedélyezése

[!include [banner](../includes/banner.md)]

Ez a cikk a Microsoft minőség- és szabálytalanságkezelési szolgáltatásainak beállításához és konfigurálásához nyújt áttekintést Dynamics 365 Supply Chain Management.

## <a name="enable-quality-and-nonconformance-management"></a><a name="enable-qm"></a>A minőség- és a szabálytalanságkezelés engedélyezése

A következő lépések elvégzésével engedélyezheti a minőségkezelést a rendszerben.

1. Válassz a **Készletkezelés \> Beállítás \> Készlet- és raktárkezelési paraméterek** lehetőséget.
1. A **Minőségkezelés** fülön állítsa **Igen** értékre a *Minőségkezelés használata* beállítást.
1. Az **Órabér** mezőben adhatja meg az óradíjat, helyi pénznemben. A rendszer az óradíjjal számítja ki a szabálytalansággal kapcsolatos műveletek költségeit. Az óradíj és a számított költségek csak a szabálytalanságokra vonatkoznak. Más funkciókat nem érintenek.
1. Válassza a **Beállítás jelentése** lehetőséget.
1. Új sorok hozzáadása a különböző jelentéstípusokhoz, és az egyes jelentésekhez használt dokumentumtípus kiválasztása.
1. Zárja be a lapot.
1. Zárja be a lapot.

## <a name="quality-management-configuration-process"></a>Minőségkezelési konfiguráció folyamata

Ahhoz, hogy használni tudja a minőségkezelési funkciókat, és minőségi rendeléseket hozzon létre, konfigurálnia kell a rendszert és az előfeltételeket. Az alábbiakban találja a minőségkezelés konfigurálához szükséges lépéseket.

1. [A minőség- és a szabálytalanságkezelés engedélyezése](#enable-qm).
1. Választható: [Tesztszerek konfigurálása](quality-test-instruments.md).
1. [Tesztek konfigurálása](quality-tests.md).
1. [Tesztváltozók és kimenetelek konfigurálása](quality-test-variables.md).
1. [Tesztcsoportok konfigurálása](quality-test-groups.md).
1. Választható: [Állítsa be a minőségi csoportokat, és csatolja hozzájuk a termékeket](quality-groups.md).
1. Választható: [Minőségi társítások konfigurálása](quality-associations.md).

A konfiguráció befejezése után elindíthatja és feldolgozhatja a minőségi rendeléseket. A minőségi rendelések létrehozásával és használatával kapcsolatos további tudnivalókért tanulmányozza a [Minőségi rendelések](quality-orders.md) című témakört.

## <a name="nonconformance-management-configuration-process"></a>Szabálytalanságkezelési konfiguráció folyamata

Ahhoz, hogy használni tudja a szabálytalanságkezelési funkciókat, és szabálytalanságokat hozzon létre, konfigurálnia kell a rendszert és az előfeltételeket. Az alábbiakban találja a szabálytalanságkezelés konfigurálához szükséges lépéseket.

1. [A minőség- és a szabálytalanságkezelés engedélyezése](#enable-qm).
1. [A szabálytalanságok jóváhagyásáért felelős dolgozók konfigurálása](quality-responsible-workers.md).
1. [Problématípusok konfigurálása](quality-problem-types.md).
1. [Karanténzónák konfigurálása](quality-quarantine-zones.md).
1. [Diagnosztikatípusok konfigurálása](quality-diagnostic-types.md).
1. [Műveletek konfigurálása](quality-operations.md).
1. Választható: [Minőségi költségek konfigurálása](quality-charges.md).

A konfiguráció befejezése után elindíthatja és feldolgozhatja a szabálytalanságokat. További információkért a szabálytalanságok létrehozásáról és használatáról lásd: [Szabálytalanságok létrehozása és feldolgozása](tasks/create-process-non-conformance.md).

## <a name="additional-resources"></a>További erőforrások

- [Minőségkezelés áttekintése](quality-management-processes.md)
- [A minőség- és a szabálytalanságkezelés engedélyezése](enable-quality-management.md)
- [Raktári folyamatok minőségkezelése](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
