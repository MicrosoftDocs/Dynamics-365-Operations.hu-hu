--- 
title: "Szabadszöveges számlasablon hozzárendelése egy ügyfélhez"
description: "A feladat bemutatja, hogyan kell szabadszöveges számlasablont vevőhöz hozzárendelni."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: af9e5f499e6c162189443d95c90b15c17d910739
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# <a name="assign-a-free-text-invoice-template-to-a-customer"></a>Szabadszöveges számlasablon hozzárendelése egy ügyfélhez

[!include[task guide banner](../../includes/task-guide-banner.md)]

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


