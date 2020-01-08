---
title: 신뢰할 수 있는 응용 프로그램 서버 구성
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Configure trusted application servers
ms:assetid: 47a9e72e-566c-4c23-bec2-760a3098a974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204865(v=OCS.15)
ms:contentKeyID: 48184056
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b28002e8bb060e9ac966121a419d8475b4828258
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "40983402"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a><span data-ttu-id="c008e-102">신뢰할 수 있는 응용 프로그램 서버 구성</span><span class="sxs-lookup"><span data-stu-id="c008e-102">Configure trusted application servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c008e-103">_**마지막으로 수정한 주제:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="c008e-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="c008e-104">혼합 환경에서 레거시 Office 통신 서버 토폴로지를 Lync Server 2013와 병합 한 후에 신뢰할 수 있는 새 응용 프로그램 서버를 만들고 토폴로지 작성기를 사용 하 여 신뢰할 수 있는 새 응용 프로그램 서버를 정의한 경우 다음 홉 풀을 다음으로 설정 해야 합니다. Lync Server 2013 풀.</span><span class="sxs-lookup"><span data-stu-id="c008e-104">In a mixed environment, if you create a new trusted application server after merging the legacy Office Communications Server topology with Lync Server 2013, and you define a new trusted application server using Topology Builder, you must set the next hop pool to be a Lync Server 2013 pool.</span></span> <span data-ttu-id="c008e-105">병합 된 환경에서, 레거시 Office 통신 서버 풀 및 Lync Server 2013 풀이 모두 드롭다운 목록에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="c008e-105">In a merged environment, both the legacy Office Communications Server pool and the Lync Server 2013 pool appear in the drop down list.</span></span> <span data-ttu-id="c008e-106">레거시 풀을 선택 하는 것은 지원 *되지* 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c008e-106">Selecting the legacy pool is *not* supported.</span></span>

<div>

## <a name="to-select-lync-server-2013-as-next-hop-when-creating-a-trusted-application-server"></a><span data-ttu-id="c008e-107">신뢰할 수 있는 응용 프로그램 서버를 만들 때 Lync 서버 2013을 다음 홉으로 선택 하려면</span><span class="sxs-lookup"><span data-stu-id="c008e-107">To select Lync Server 2013 as next hop when creating a Trusted application server</span></span>

1.  <span data-ttu-id="c008e-108">토폴로지 작성기에서 기존 토폴로지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c008e-108">Open an existing topology in Topology Builder.</span></span>

2.  <span data-ttu-id="c008e-109">왼쪽 창에서 **신뢰할 수 있는 응용 프로그램 서버** 를 마우스 오른쪽 단추로 클릭 하 고 **새 신뢰할 수 있는 응용 프로그램 풀**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c008e-109">In the left pane, right click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>

3.  <span data-ttu-id="c008e-110">신뢰할 수 있는 응용 프로그램 풀의 **풀 FQDN** 을 입력 하 고이를 단일 서버 배포로 할지 다중 서버 배포할 것인지 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c008e-110">Enter the **Pool FQDN** of the trusted application pool and select whether it will be a single-server or multiple-server deployment.</span></span>

4.  <span data-ttu-id="c008e-111">**다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c008e-111">Click **Next**.</span></span>

5.  <span data-ttu-id="c008e-112">**다음 홉 선택** 페이지의 목록에서 Lync Server 2013 프런트 엔드 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c008e-112">On the **Select the next hop** page, from the list, select the Lync Server 2013 Front End pool.</span></span>
    
    <span data-ttu-id="c008e-113">![신뢰할 수 있는 새 응용 프로그램 풀 대화 상자 정의](images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "새 신뢰할 수 있는 응용 프로그램 풀 정의 대화 상자")</span><span class="sxs-lookup"><span data-stu-id="c008e-113">![Define New Trusted Application Pool dialog](images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "Define New Trusted Application Pool dialog")</span></span>  

6.  <span data-ttu-id="c008e-114">**마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c008e-114">Click **Finish**.</span></span>

7.  <span data-ttu-id="c008e-115">최상위 노드 **Lync Server** 를 선택 하 고 **작업** 창에서 **게시**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c008e-115">Select the top node **Lync Server** and from the **Actions** pane, select **Publish**.</span></span>

8.  <span data-ttu-id="c008e-116">**신뢰할 수 있는 응용 프로그램 풀이** 성공적으로 생성 되었고 올바른 프런트 엔드 풀에 연결 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c008e-116">Verify the **Trusted Application Pool** was created successfully and is associated with the correct Front End pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

