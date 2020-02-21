---
title: 'Lync Server 2013: System Center Operations Manager를 사용 하 여 Lync Server 모니터링'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring Lync 2013 with SCOM
ms:assetid: a74bde92-97ff-4d90-acb9-7a70272f0f31
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720343(v=OCS.15)
ms:contentKeyID: 63969636
ms.date: 05/06/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91fd6f11fc080fea89ea736365603ea226e8b68a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184731"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-lync-server-2013-with-system-center-operations-manager"></a><span data-ttu-id="440c6-102">System Center Operations Manager를 사용 하 여 Lync Server 2013 모니터링</span><span class="sxs-lookup"><span data-stu-id="440c6-102">Monitoring Lync Server 2013 with System Center Operations Manager</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="440c6-103">_**마지막으로 수정 된 항목:** 2015-05-06_</span><span class="sxs-lookup"><span data-stu-id="440c6-103">_**Topic Last Modified:** 2015-05-06_</span></span>

<span data-ttu-id="440c6-104">Lync server 관리 팩 (MP)은 Lync 서버 배포를 모니터링 하기 위해 선택할 수 있는 모니터링 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="440c6-104">The Lync Server Management Pack (MP) is your monitoring solution of choice for monitoring any Lync Server deployment.</span></span>

<span data-ttu-id="440c6-105">MP는 일반적인 이벤트 로그 및 성능 카운터 기반 계측을 구현 하며, 몇 가지 주요 상태 표시기에 대 한 쌍 이벤트 (오류/성공)와 같이 Lync Server에서 새로 사용 가능한 계측을 사용 하도록 설정 하 고, 새 가상 트랜잭션\* (테스트-Cs Windows PowerShell cmdlet)을 완벽 하 게 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="440c6-105">The MP implements traditional Event Log and Performance counter-based instrumentation and enables newly available instrumentation in Lync Server, such as pair events (failure/success) for several Key Health Indicators, and also fully implements the new Synthetic Transactions (Test-Cs\* Windows PowerShell cmdlets).</span></span>

<span data-ttu-id="440c6-106">Lync Server 2013 관리 팩과 관련 설명서는에서 [https://go.microsoft.com/fwlink/p/?LinkId=400468](https://go.microsoft.com/fwlink/p/?linkid=400468)찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="440c6-106">You can find the Lync Server 2013 Management Pack and its related documentation at [https://go.microsoft.com/fwlink/p/?LinkId=400468](https://go.microsoft.com/fwlink/p/?linkid=400468).</span></span> <span data-ttu-id="440c6-107">System Center Operations Manager 2012를 실행 하는 경우이 방법이 권장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="440c6-107">This is recommended if you are running System Center Operations Manager 2012.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

