---
title: 배치 된 중재 서버를 독립 실행형 중재 서버로 전환 (선택 사항)
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)
ms:assetid: 7c3c2fb4-4ff2-47b1-aab3-0aa91472eadb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205026(v=OCS.15)
ms:contentKeyID: 48184602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ce0228edacba502161c4d44a6a94b38cede6655
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755692"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional"></a><span data-ttu-id="47bd1-102">배치 된 중재 서버를 독립 실행형 중재 서버로 전환 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="47bd1-102">Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47bd1-103">_**마지막으로 수정 된 항목:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="47bd1-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="47bd1-104">단일 사이트 배포를 위해 Standard Edition 서버 또는 프런트 엔드 풀에 배치된 중재 서버를 독립 실행형 중재 서버로 전환하려면 이 절차를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="47bd1-104">Use the procedure that follows to transition your Mediation Server, collocated on your Standard Edition server or Front End pool, to a stand-alone Mediation Server for a single-site deployment.</span></span>

<div>

## <a name="to-transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server"></a><span data-ttu-id="47bd1-105">배치된 중재 서버를 독립 실행형 중재 서버로 전환하려면</span><span class="sxs-lookup"><span data-stu-id="47bd1-105">To transition a collocated Mediation Server to a stand-alone Mediation Server</span></span>

1.  <span data-ttu-id="47bd1-106">토폴로지 작성기에서 기존 토폴로지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="47bd1-106">Open an existing topology from Topology Builder.</span></span>

2.  <span data-ttu-id="47bd1-107">왼쪽 창에서 **중재 풀**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="47bd1-107">In the left pane, navigate to **Mediation pools**.</span></span>

3.  <span data-ttu-id="47bd1-108">**중재 풀**을 마우스 오른쪽 단추로 클릭한 후 **새 중재 서버**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="47bd1-108">Right-click **Mediation pools** and select **New Mediation Server**.</span></span>

4.  <span data-ttu-id="47bd1-109">On the **Define New Mediation Pool** page, provide the FQDN of the new Mediation Server pool.</span><span class="sxs-lookup"><span data-stu-id="47bd1-109">On the **Define New Mediation Pool** page, provide the FQDN of the new Mediation Server pool.</span></span> <span data-ttu-id="47bd1-110">Also, select whether this pool will be a single-server or multiple-server pool, and then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="47bd1-110">Also, select whether this pool will be a single-server or multiple-server pool, and then click **Next**.</span></span>

5.  <span data-ttu-id="47bd1-111">새 중재 서버가 인바운드 호출을 라우팅할 다음 홉 프런트 엔드 서버 풀을 선택한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="47bd1-111">Select the next hop Front End server pool to which the new Mediation Server will route inbound calls, and then click **Next**.</span></span>

6.  <span data-ttu-id="47bd1-112">중재 서버에서 사용할 에지 풀을 선택한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="47bd1-112">Select the Edge pool to be used by the Mediation Server and then click **Next**.</span></span>

7.  <span data-ttu-id="47bd1-113">On the **Specify PSTN gateways** page, associate the previous PSTN gateway with the Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="47bd1-113">On the **Specify PSTN gateways** page, associate the previous PSTN gateway with the Mediation Server.</span></span> <span data-ttu-id="47bd1-114">Select the gateway and then click **Add**.</span><span class="sxs-lookup"><span data-stu-id="47bd1-114">Select the gateway and then click **Add**.</span></span>

8.  <span data-ttu-id="47bd1-115">**마침**을 클릭하여 **새 중재 풀 정의** 마법사를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="47bd1-115">Click **Finish** to close the **Define New Mediation Pool** wizard.</span></span>

9.  <span data-ttu-id="47bd1-116">**토폴로지 작성기**에서 최상위 노드 **Lync Server 2013**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="47bd1-116">From **Topology Builder**, select the top node **Lync Server 2013**.</span></span>

10. <span data-ttu-id="47bd1-117">**동작** 창에서 **토폴로지 게시**를 선택한 후 마법사를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="47bd1-117">From the **Actions** pane, select **Publish Topology** and complete the wizard.</span></span>

11. <span data-ttu-id="47bd1-118">배포 설명서의 [Lync server 2013에서 중재 서버용 파일 설치](lync-server-2013-install-the-files-for-mediation-server.md) 의 단계에 따라 새 중재 서버에 파일을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="47bd1-118">Follow the steps in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) in the Deployment documentation to install the files on the new Mediation Server.</span></span>

12. <span data-ttu-id="47bd1-119">파일이 중재 서버에 설치된 후 토폴로지 작성기로 돌아가고 왼쪽 창에서 해당 풀로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="47bd1-119">After the files are installed on the Mediation Server, return to Topology Builder, and in the left pane navigate to the pool.</span></span>

13. <span data-ttu-id="47bd1-120">풀을 마우스 오른쪽 단추로 클릭한 다음 **속성 편집**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="47bd1-120">Right-click the pool and select **Edit Properties**.</span></span>

14. <span data-ttu-id="47bd1-121">**중재 서버**에서 **배치된 중재 서버 사용됨** 확인란의 선택을 취소한 후 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="47bd1-121">Under **Mediation Server**, clear the check box **Collocated Mediation Server enabled** and then click **OK**.</span></span>

15. <span data-ttu-id="47bd1-122">**토폴로지 작성기**에서 최상위 노드 **Lync Server 2013**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="47bd1-122">From **Topology Builder**, select the top node **Lync Server 2013**.</span></span>

16. <span data-ttu-id="47bd1-123">**동작** 메뉴에서 **토폴로지 게시**를 선택한 후 마법사를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="47bd1-123">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

