---
title: 신뢰할 수 있는 응용 프로그램 서버 구성
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Configure trusted application servers
ms:assetid: 20c3815f-3048-4940-8c0f-cdfcd0801d5d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204735(v=OCS.15)
ms:contentKeyID: 48183592
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cab126429fc5ec77a2308fdc1e1f8965fdfccb5b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "40983628"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a><span data-ttu-id="6a11e-102">신뢰할 수 있는 응용 프로그램 서버 구성</span><span class="sxs-lookup"><span data-stu-id="6a11e-102">Configure trusted application servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a11e-103">_**마지막으로 수정한 주제:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="6a11e-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="6a11e-104">혼합 환경에서 신뢰할 수 있는 새 응용 프로그램 서버를 만드는 경우 다음 홉 풀을 Lync Server 2013 풀로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a11e-104">In a mixed environment, if you create a new trusted application server, you must set the next hop pool to be a Lync Server 2013 pool.</span></span> <span data-ttu-id="6a11e-105">혼합 환경에서는 레거시 Lync Server 2010 풀과 Lync Server 2013 풀이 모두 드롭다운 목록에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="6a11e-105">In a mixed environment, both the legacy Lync Server 2010 pool and the Lync Server 2013 pool appear in the drop down list.</span></span> <span data-ttu-id="6a11e-106">레거시 풀을 선택 하는 것은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6a11e-106">Selecting the legacy pool is not supported.</span></span>

<span data-ttu-id="6a11e-107">**신뢰할 수 있는 응용 프로그램 서버를 만들 때 Lync 서버 2013을 다음 홉으로 선택**</span><span class="sxs-lookup"><span data-stu-id="6a11e-107">**Select Lync Server 2013 as next hop when creating a Trusted application server**</span></span>

1.  <span data-ttu-id="6a11e-108">토폴로지 작성기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6a11e-108">Open Topology Builder.</span></span>

2.  <span data-ttu-id="6a11e-109">왼쪽 창에서 **신뢰할 수 있는 응용 프로그램 서버** 를 마우스 오른쪽 단추로 클릭 하 고 **새 신뢰할 수 있는 응용 프로그램 풀**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a11e-109">In the left pane, right click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>

3.  <span data-ttu-id="6a11e-110">신뢰할 수 있는 응용 프로그램 풀의 **풀 FQDN** 을 입력 하 고이를 단일 서버 또는 다중 서버 중에서 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a11e-110">Enter the **Pool FQDN** of the trusted application pool and select whether it will be a single-server or multiple-server.</span></span>

4.  <span data-ttu-id="6a11e-111">**다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a11e-111">Click **Next**.</span></span>

5.  <span data-ttu-id="6a11e-112">**다음 홉 선택** 페이지의 목록에서 Lync Server 2013 프런트 엔드 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a11e-112">On the **Select the next hop** page, from the list, select the Lync Server 2013 Front End pool.</span></span>

6.  <span data-ttu-id="6a11e-113">**마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6a11e-113">Click **Finish**.</span></span>

7.  <span data-ttu-id="6a11e-114">최상위 노드 **Lync Server** 를 선택 하 고 **동작** 메뉴에서 **게시**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a11e-114">Select the top node **Lync Server** and from the **Action** menu, select **Publish**.</span></span>
    
    <span data-ttu-id="6a11e-115">**신뢰할 수 있는 응용 프로그램 풀이** 성공적으로 생성 되었고 올바른 프런트 엔드 풀에 연결 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a11e-115">Verify the **Trusted Application Pool** has been created successfully and is associated with the correct Front End pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

