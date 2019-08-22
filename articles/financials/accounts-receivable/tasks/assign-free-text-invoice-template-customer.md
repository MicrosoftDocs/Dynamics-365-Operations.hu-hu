---
title: Szabadszöveges számlasablon hozzárendelése vevőhöz
description: A feladat bemutatja, hogyan kell szabadszöveges számlasablont vevőhöz hozzárendelni.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustTable, CustRecurrenceInvoice
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 53bff33083a78c0bb1c7d243fe9965fb264d209e
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1843049"
---
# <a name="assign-free-text-invoice-template-to-a-customer"></a>Szabadszöveges számlasablon hozzárendelése vevőhöz

[!include [task guide banner](../../includes/task-guide-banner.md)]

A feladat bemutatja, hogyan kell szabadszöveges számlasablont vevőhöz hozzárendelni. Ez a feladat az USMF bemutató vállalatot veszi alapul, és az a felhasználó használja, aki felelős a kintlévőségek számláinak kezeléséért és feldolgozásáért.

1. Ugorjon a Kinnlevőségek > Vevők > Minden vevő pontra.
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
3. A Művelet panelen kattintson a Számla lehetőségre.
4. Kattintson az Ismétlődő számlák lehetőségre.
    * Ezen a lapon szabadszöveges számlasablonokat rendelhet hozzá a vevőkhöz, és megadhatja, hogy milyen gyakran történjen számlázás a vevő részére.  
5. Az Új gombra kattintva új sablont rendel a vevőhöz.
6. Válassza ki a szabadszöveges számlasablont, amelyet hozzá kíván rendelni a vevőhöz.
7. A kívánt rekord megkeresése és kijelölése a listán
8. A listában kattintson a kijelölt sorban lévő hivatkozásra.
9. Írja be az első számla létrehozásának dátumát.
    * Ismétlődő záró dátum megadása.  
    * Válassza ki a következők valamelyikét: Nincs záró dátum – A számlázás folyamatosan történik, amíg a sablont el nem távolítja a vevői fiókból.  Számlázás záró dátuma – Válassza ezt az opciót, ha szeretné megadni, mi az a legutolsó dátum, amikor még generálható számla.  
    * Maximális halmozott összeg, amely után a számlák létrehozása leáll.  
    * Adja meg a maximális halmozott összeget, amely a kiválasztott sablon használatával elérhető. Ha például 1000,00-t ad meg és havonta 100,00-ról állít ki számlát, a tizedik számla után nem jön létre több számla.  
    * A szabadszöveges számlasablon vagy a vevői fiók alapértelmezett értékeit felhasználva ismétlődő számlákat állíthat ki.  
    * Válassza ki, hogy a rendszer a szabadszöveges számlasablon vagy a vevői számla alapján határozza meg a nyelvet, a feladási profilt, az áfacsoportot, a cikkáfacsoportot, a listakód, a szállítási országot/területet, a pénznemet, a fizetési feltételeket, a fizetési módot, a fizetési specifikációt, a részletfizetést, a készpénzfizetési engedményt, a pénzügyi dimenziókat, illetve a zsíró alapú pénzátutalási bizonylatot a számlák létrehozásakor.  
10. Válasszon ki egy ismétlődési szabályt.
    * Napi – Válassza ezt az opciót, majd adja meg a napok számát a / mezőben. Ha például a 15 értéket adja meg, akkor a rendszer 15 naponta generál számlát ehhez a vevőhöz.  Hetente – Válassza a Hetente opciót, majd adja meg a hetek számát a / mezőben. Ha például a 2 értéket adja meg, akkor a rendszer kéthetente generál számlát ehhez a vevőhöz.  Havonta – Válassza a Havonta opciót, majd adja meg a hónapok számát a / mezőben. Ha például a 6 értéket adja meg, akkor a rendszer félévente generál számlát ehhez a vevőhöz.  Évente – Válassza az Évente opciót, majd adja meg az évek számát a / mezőben. Ha például a 2 értéket adja meg, akkor a rendszer kétévente generál számlát ehhez a vevőhöz.  
11. A / mezőben adjon meg egy számot.

