---
title: 'Lync Server 2013: Cmdlet을 사용하여 포리스트 준비 되돌리기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using cmdlets to reverse forest preparation
ms:assetid: f48c7eb3-ccb0-48e6-ac79-ab7c7062b9d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413024(v=OCS.15)
ms:contentKeyID: 48185822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b893eb79cb19856572e90bd449b315f0ade803c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744188"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-cmdlets-to-reverse-forest-preparation-for-lync-server-2013"></a><span data-ttu-id="15d93-102">Lync Server 2013에 대해 Cmdlet을 사용하여 포리스트 준비 되돌리기</span><span class="sxs-lookup"><span data-stu-id="15d93-102">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15d93-103">_**마지막으로 수정한 주제:** 2013-06-19_</span><span class="sxs-lookup"><span data-stu-id="15d93-103">_**Topic Last Modified:** 2013-06-19_</span></span>

<span data-ttu-id="15d93-104">포리스트 준비 단계를 반대로 하려면 **Disable-CsAdForest** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d93-104">Use the **Disable-CsAdForest** cmdlet to reverse the forest preparation step.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="15d93-105">이전 버전의 Lync Server도 배포 된 환경에서 <STRONG>Disable-CsAdForest</STRONG> cmdlet을 실행 하는 경우 이전 버전에 대 한 전역 설정도 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="15d93-105">If you run the <STRONG>Disable-CsAdForest</STRONG> cmdlet in an environment where you also have a previous version of Lync Server deployed, the global settings for the previous version will also be deleted.</span></span>



</div>

<div>

## <a name="to-use-cmdlets-to-reverse-forest-preparation"></a><span data-ttu-id="15d93-106">Cmdlet을 사용 하 여 포리스트 준비를 취소 하려면</span><span class="sxs-lookup"><span data-stu-id="15d93-106">To use cmdlets to reverse forest preparation</span></span>

1.  <span data-ttu-id="15d93-107">포리스트 루트 도메인의 Domain Admins 그룹 구성원으로 도메인에 가입한 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d93-107">Log on to a computer that is joined to a domain as a member of the Domain Admins group in the forest root domain.</span></span>

2.  <span data-ttu-id="15d93-108">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d93-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="15d93-109">런</span><span class="sxs-lookup"><span data-stu-id="15d93-109">Run:</span></span>
    
        Disable-CsAdForest [-Force] [-GroupDomain <FQDN of the domain in which universal groups were created>]
    
    <span data-ttu-id="15d93-110">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="15d93-110">For example:</span></span>
    
        Disable-CsAdForest -Force -GroupDomain contoso.net
    
    <span data-ttu-id="15d93-111">Force 매개 변수는 작업을 강제 실행할 것인지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d93-111">The Force parameter specifies whether to force running the task.</span></span> <span data-ttu-id="15d93-112">이 매개 변수가 없으면 포리스트의 한 도메인도 Lync Server 2013에 대해 준비 되어 있는 경우 명령이 실행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="15d93-112">If this parameter is not present, the command will not run if even one domain in the forest is still prepared for Lync Server 2013.</span></span> <span data-ttu-id="15d93-113">Force 매개 변수를 지정 하면 포리스트에 있는 다른 도메인의 상태에 관계 없이 작업이 계속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="15d93-113">If the Force parameter is specified, the action will continue regardless of the state of other domains in the forest.</span></span>
    
    <span data-ttu-id="15d93-114">GroupDomain 매개 변수를 지정 하지 않으면 로컬 도메인이 기본값이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="15d93-114">If you do not specify the GroupDomain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="15d93-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="15d93-115">See Also</span></span>


[<span data-ttu-id="15d93-116">Lync Server 2013에 대한 포리스트 준비 실행</span><span class="sxs-lookup"><span data-stu-id="15d93-116">Running forest preparation for Lync Server 2013</span></span>](lync-server-2013-running-forest-preparation.md)  


[<span data-ttu-id="15d93-117">Lync Server 2013에 대한 포리스트 준비</span><span class="sxs-lookup"><span data-stu-id="15d93-117">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

