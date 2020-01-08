---
title: Office Communications Server 2007 R2 Edge 서버에 대 한 연결 권한 부여
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Authorize connection to Office Communications Server 2007 R2 Edge Server
ms:assetid: 14f6798a-28d6-4b3d-8734-942192e1bbf5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204702(v=OCS.15)
ms:contentKeyID: 48183493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04bc5d92b45f65c864da046951ce7ebd42155ed2
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "40982315"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="authorize-connection-to-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="03e3a-102">Office Communications Server 2007 R2 Edge 서버에 대 한 연결 권한 부여</span><span class="sxs-lookup"><span data-stu-id="03e3a-102">Authorize connection to Office Communications Server 2007 R2 Edge Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03e3a-103">_**마지막으로 수정한 주제:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="03e3a-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="03e3a-104">파일럿 풀의 각 Lync Server 2013 프런트 엔드 서버 또는 Standard Edition 서버에 대해 Office Communications Server 2007 R2 Edge 서버에 연결할 수 있는 내부 서버 목록을 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e3a-104">For each Lync Server 2013 Front End Server or Standard Edition server in your pilot pool, you must update the list of internal servers that are authorized to connect to the Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="03e3a-105">이러한 업데이트가 없으면 레거시 Edge 서버를 사용 하 여 참가 하는 사용자를 위한 외부 오디오/시각적 (A/V) 회의는 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03e3a-105">Without these updates, external audio/visual (A/V) conferencing for users joining by using the legacy Edge Server will not work.</span></span>

<div>

## <a name="to-authorize-connection-to-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="03e3a-106">Office Communications Server 2007 R2 Edge 서버에 대 한 연결을 승인 하려면</span><span class="sxs-lookup"><span data-stu-id="03e3a-106">To Authorize Connection to Office Communications Server 2007 R2 Edge Server</span></span>

1.  <span data-ttu-id="03e3a-107">Office Communications Server 2007 R2 Edge 서버에서 **관리 도구** 그룹에 있는 **컴퓨터 관리** 스냅인을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="03e3a-107">From the Office Communications Server 2007 R2 Edge Server, from the **Administrative Tools** group, open the **Computer Management** snap-in.</span></span>

2.  <span data-ttu-id="03e3a-108">콘솔 트리에서 **서비스 및 응용 프로그램**을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e3a-108">In the console tree, expand **Services and Applications**.</span></span>

3.  <span data-ttu-id="03e3a-109">**Office Communications Server 2007 R2**를 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e3a-109">Right-click **Office Communications Server 2007 R2**, and then click **Properties**.</span></span>

4.  <span data-ttu-id="03e3a-110">**내부** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e3a-110">Click the **Internal** tab.</span></span>

5.  <span data-ttu-id="03e3a-111">**서버 추가**에서 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e3a-111">Under **Add Server**, click **Add**.</span></span>

6.  <span data-ttu-id="03e3a-112">**Office Communications Server 추가** 대화 상자에서 적절 한 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e3a-112">In the **Add Office Communications Server** dialog box, enter the appropriate information:</span></span>
    
      - <span data-ttu-id="03e3a-113">각 Lync Server 2013 프런트 엔드 서버 또는 Standard Edition Server 및 Lync Server 2013 풀의 FQDN (정규화 된 도메인 이름)을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e3a-113">Specify the fully qualified domain name (FQDN) of each Lync Server 2013 Front End Server or Standard Edition server, and Lync Server 2013 pool.</span></span>
    
      - <span data-ttu-id="03e3a-114">해당 FQDN으로 다음 홉 컴퓨터를 지정 하는 풀에서 고정 경로를 구성한 경우 Lync Server 2013 디렉터의 FQDN을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e3a-114">Specify the FQDN of the Lync Server 2013 Director if you configured a static route on the pool that specifies the next hop computer by its FQDN.</span></span>

7.  <span data-ttu-id="03e3a-115">각 Lync Server 2013, 프런트 엔드 서버, Standard Edition Server, 풀 및 디렉터에 대 한 항목을 추가한 후 **적용** 을 클릭 한 다음 **확인** 을 클릭 하 여 속성 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="03e3a-115">After you have added an entry for each Lync Server 2013, Front End Server, Standard Edition server, pool, and Director, click **Apply** and then click **OK** to close the Properties page.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

