---
title: 트러스트된 응용 프로그램 서버 구성
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure trusted application servers
ms:assetid: 20c3815f-3048-4940-8c0f-cdfcd0801d5d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204735(v=OCS.15)
ms:contentKeyID: 48183592
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 535d5d9a34d450c964300e9caaa16c6b80734732
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136035"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a><span data-ttu-id="13d08-102">트러스트된 응용 프로그램 서버 구성</span><span class="sxs-lookup"><span data-stu-id="13d08-102">Configure trusted application servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13d08-103">_**마지막으로 수정 된 항목:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="13d08-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="13d08-104">혼합 환경에서 신뢰할 수 있는 응용 프로그램 서버를 새로 만드는 경우에는 다음 홉 풀을 Lync Server 2013 풀로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13d08-104">In a mixed environment, if you create a new trusted application server, you must set the next hop pool to be a Lync Server 2013 pool.</span></span> <span data-ttu-id="13d08-105">혼합 환경에서는 드롭다운 목록에 레거시 Lync Server 2010 풀과 Lync Server 2013 풀이 모두 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13d08-105">In a mixed environment, both the legacy Lync Server 2010 pool and the Lync Server 2013 pool appear in the drop down list.</span></span> <span data-ttu-id="13d08-106">레거시 풀은 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="13d08-106">Selecting the legacy pool is not supported.</span></span>

<span data-ttu-id="13d08-107">**신뢰할 수 있는 응용 프로그램 서버를 만들 때 Lync Server 2013을 다음 홉으로 선택**</span><span class="sxs-lookup"><span data-stu-id="13d08-107">**Select Lync Server 2013 as next hop when creating a Trusted application server**</span></span>

1.  <span data-ttu-id="13d08-108">토폴로지 작성기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="13d08-108">Open Topology Builder.</span></span>

2.  <span data-ttu-id="13d08-109">왼쪽 창에서 **신뢰할 수 있는 응용 프로그램 서버**를 마우스 오른쪽 단추로 클릭하고 **새 신뢰할 수 있는 응용 프로그램 풀**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="13d08-109">In the left pane, right click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>

3.  <span data-ttu-id="13d08-110">신뢰할 수 있는 응용 프로그램 풀에 대한 **풀 FQDN**을 입력하고 단일 서버로 설정할지 다중 서버로 설정할지를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="13d08-110">Enter the **Pool FQDN** of the trusted application pool and select whether it will be a single-server or multiple-server.</span></span>

4.  <span data-ttu-id="13d08-111">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="13d08-111">Click **Next**.</span></span>

5.  <span data-ttu-id="13d08-112">**다음 홉 선택** 페이지의 목록에서 Lync Server 2013 프런트 엔드 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="13d08-112">On the **Select the next hop** page, from the list, select the Lync Server 2013 Front End pool.</span></span>

6.  <span data-ttu-id="13d08-113">**마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="13d08-113">Click **Finish**.</span></span>

7.  <span data-ttu-id="13d08-114">최상위 노드인 **Lync Server**를 선택한 후 **동작** 메뉴에서 **게시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="13d08-114">Select the top node **Lync Server** and from the **Action** menu, select **Publish**.</span></span>
    
    <span data-ttu-id="13d08-115">**신뢰할 수 있는 응용 프로그램 풀**이 성공적으로 만들어졌으며 올바른 프런트 엔드 풀에 연결되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="13d08-115">Verify the **Trusted Application Pool** has been created successfully and is associated with the correct Front End pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

