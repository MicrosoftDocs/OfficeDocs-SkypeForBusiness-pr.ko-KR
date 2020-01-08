---
title: 통화 허용 제어 서비스 다시 설정
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Reset call admission control
ms:assetid: 5873f56c-f3d6-4d73-beea-c9f37d5077f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688064(v=OCS.15)
ms:contentKeyID: 49733658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cf7067ba3d130c264ead39ed9d2c044a037960f4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984549"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-call-admission-control"></a><span data-ttu-id="9aced-102">통화 허용 제어 서비스 다시 설정</span><span class="sxs-lookup"><span data-stu-id="9aced-102">Reset call admission control</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9aced-103">_**마지막으로 수정한 주제:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="9aced-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="9aced-104">Lync Server 2010 프론트 엔드 풀이 CAC (통화 허용 제어)를 호스트 하는 경우, lync Server 2010 프런트 엔드 풀을 제거 하려면 먼저 CAC 호스팅을 Lync Server 2013 풀로 이동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9aced-104">If a Lync Server 2010 Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Lync Server 2013 pool before you can remove the Lync Server 2010 Front End pool.</span></span>

<div>

## <a name="to-reset-cac"></a><span data-ttu-id="9aced-105">CAC를 다시 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="9aced-105">To reset CAC</span></span>

1.  <span data-ttu-id="9aced-106">토폴로지 작성기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9aced-106">Open Topology Builder.</span></span>

2.  <span data-ttu-id="9aced-107">사이트 노드를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9aced-107">Right-click the site node, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="9aced-108">**통화 허용 제어 설정**에서 **통화 허용 제어가** 선택 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9aced-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span>

4.  <span data-ttu-id="9aced-109">**프런트 엔드 풀에서 cac (호출 허용 컨트롤)를 실행 하려면**cac를 호스트할 Lync Server 2013 풀을 선택한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9aced-109">Under **Front End pool to run call admission control (CAC)**, select the Lync Server 2013 pool that is to host CAC, and then click **OK**.</span></span>

5.  <span data-ttu-id="9aced-110">토폴로지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="9aced-110">Publish the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

