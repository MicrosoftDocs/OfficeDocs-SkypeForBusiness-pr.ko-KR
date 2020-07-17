---
title: 트러스트된 응용 프로그램 서버 구성
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure trusted application servers
ms:assetid: 47a9e72e-566c-4c23-bec2-760a3098a974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204865(v=OCS.15)
ms:contentKeyID: 48184056
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9cbaba4f59a22de6fcee38ee51845d551033cfea
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754486"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a><span data-ttu-id="097a9-102">트러스트된 응용 프로그램 서버 구성</span><span class="sxs-lookup"><span data-stu-id="097a9-102">Configure trusted application servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="097a9-103">_**마지막으로 수정 된 항목:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="097a9-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="097a9-104">혼합 환경에서는 레거시 Office Communications Server 토폴로지를 Lync Server 2013와 병합 한 후에 새 신뢰할 수 있는 응용 프로그램 서버를 만들고 토폴로지 작성기를 사용 하 여 신뢰할 수 있는 응용 프로그램 서버를 새로 정의한 경우 다음 홉 풀을 Lync Server 2013 풀로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="097a9-104">In a mixed environment, if you create a new trusted application server after merging the legacy Office Communications Server topology with Lync Server 2013, and you define a new trusted application server using Topology Builder, you must set the next hop pool to be a Lync Server 2013 pool.</span></span> <span data-ttu-id="097a9-105">병합 된 환경에서는 레거시 Office Communications Server 풀과 Lync Server 2013 풀이 모두 드롭다운 목록에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="097a9-105">In a merged environment, both the legacy Office Communications Server pool and the Lync Server 2013 pool appear in the drop down list.</span></span> <span data-ttu-id="097a9-106">레거시 풀 선택은 지원되지 *않습니다*.</span><span class="sxs-lookup"><span data-stu-id="097a9-106">Selecting the legacy pool is *not* supported.</span></span>

<div>

## <a name="to-select-lync-server-2013-as-next-hop-when-creating-a-trusted-application-server"></a><span data-ttu-id="097a9-107">신뢰할 수 있는 응용 프로그램 서버를 만들 때 Lync Server 2013을 다음 홉으로 선택 하려면</span><span class="sxs-lookup"><span data-stu-id="097a9-107">To select Lync Server 2013 as next hop when creating a Trusted application server</span></span>

1.  <span data-ttu-id="097a9-108">토폴로지 작성기에서 기존 토폴로지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="097a9-108">Open an existing topology in Topology Builder.</span></span>

2.  <span data-ttu-id="097a9-109">왼쪽 창에서 **신뢰할 수 있는 응용 프로그램 서버**를 마우스 오른쪽 단추로 클릭하고 **새 신뢰할 수 있는 응용 프로그램 풀**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="097a9-109">In the left pane, right click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>

3.  <span data-ttu-id="097a9-110">신뢰할 수 있는 응용 프로그램 풀의 **풀 FQDN**을 입력하고 단일 서버 또는 다중 서버 배포인지 여부를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="097a9-110">Enter the **Pool FQDN** of the trusted application pool and select whether it will be a single-server or multiple-server deployment.</span></span>

4.  <span data-ttu-id="097a9-111">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="097a9-111">Click **Next**.</span></span>

5.  <span data-ttu-id="097a9-112">**다음 홉 선택** 페이지의 목록에서 Lync Server 2013 프런트 엔드 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="097a9-112">On the **Select the next hop** page, from the list, select the Lync Server 2013 Front End pool.</span></span>
    
    <span data-ttu-id="097a9-113">![새 신뢰할 수 있는 응용 프로그램 풀 정의 대화 상자](images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "새 신뢰할 수 있는 응용 프로그램 풀 정의 대화 상자")</span><span class="sxs-lookup"><span data-stu-id="097a9-113">![Define New Trusted Application Pool dialog](images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "Define New Trusted Application Pool dialog")</span></span>  

6.  <span data-ttu-id="097a9-114">**마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="097a9-114">Click **Finish**.</span></span>

7.  <span data-ttu-id="097a9-115">최상위 노드 **Lync Server**를 선택하고 **작업** 창에서 **게시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="097a9-115">Select the top node **Lync Server** and from the **Actions** pane, select **Publish**.</span></span>

8.  <span data-ttu-id="097a9-116">**신뢰할 수 있는 응용 프로그램 풀**이 만들어졌고 올바른 프런트 엔드 풀과 연결되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="097a9-116">Verify the **Trusted Application Pool** was created successfully and is associated with the correct Front End pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

