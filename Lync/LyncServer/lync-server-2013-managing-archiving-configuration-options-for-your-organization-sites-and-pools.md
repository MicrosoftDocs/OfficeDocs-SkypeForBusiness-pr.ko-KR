---
title: 'Lync Server 2013: 조직, 사이트 및 풀에 대 한 보관 구성 옵션 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing Archiving configuration options for your organization, sites, and pools
ms:assetid: 377a6f80-5f2b-4bc1-b507-e930a461fb1d
ms:mtpsurl: https://technet.microsoft.com/library/JJ204802(v=OCS.15)
ms:contentKeyID: 48183830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d27ea110c345be8963c5b3be3fa8b761e1b3727
ms.sourcegitcommit: 0119af282f53f49c4ab6e01c3319d01bc6fdad2c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2020
ms.locfileid: "41111722"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-archiving-configuration-options-in-lync-server-2013-for-your-organization-sites-and-pools"></a><span data-ttu-id="5a8af-102">조직, 사이트 및 풀에 대 한 Lync Server 2013의 보관 구성 옵션 관리</span><span class="sxs-lookup"><span data-stu-id="5a8af-102">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a8af-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="5a8af-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="5a8af-104">Lync Server 2013 제어판에서 보관 구성을 사용 하 여 보관을 구현 하는 방법을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a8af-104">In Lync Server 2013 Control Panel, you use Archiving configurations to specify how archiving is implemented.</span></span> <span data-ttu-id="5a8af-105">여기에는 다음과 같은 보관 구성이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a8af-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="5a8af-106">Lync Server 2013을 배포할 때 기본적으로 만들어지는 전역 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="5a8af-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="5a8af-107">특정 사이트 또는 풀에 대해 보관을 구현 하는 방법을 지정 하기 위해 만들고 사용할 수 있는 선택적 사이트 수준 및 풀 수준 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="5a8af-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="5a8af-108">보관을 배포할 때 초기에 보관 구성을 설정 했지만 배포 후 구성을 변경, 추가 및 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a8af-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="5a8af-109">Lync Server 2013 제어판에서 **보관 및 모니터링** 그룹의 **보관 구성** 페이지를 사용 하 여 전역 수준, 사이트 수준 및 풀 수준에서 구성을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a8af-109">In Lync Server 2013 Control Panel, you can use the **Archiving Configuration** page of the **Archiving and Monitoring** group to manage configurations at the global level, site level, and pool level.</span></span> <span data-ttu-id="5a8af-110">지정할 수 있는 옵션 및 보관 구성의 계층 구조를 비롯 하 여 보관 구성이 구현 되는 방법에 대 한 자세한 내용은 계획 문서, 배포 설명서 또는 운영 설명서의 [Lync Server 2013에서 보관을 작동 하는 방법을](lync-server-2013-how-archiving-works.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5a8af-110">For details about how Archiving configurations are implemented, including which options you can specify, and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5a8af-111">보관을 사용 하려면 보관 정책을 구성 하 여 Lync Server 2013에 있는 모든 사용자에 대해 내부 통신, 외부 통신 또는 둘 다에 대해 보관을 사용할지 여부를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a8af-111">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for all users homed on Lync Server 2013.</span></span> <span data-ttu-id="5a8af-112">기본적으로 내부 또는 외부 통신에 대해 보관을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5a8af-112">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="5a8af-113">Microsoft Exchange 통합을 사용 하는 경우 exchange 2013에 속한 모든 사용자 (사서함이 원본 위치 유지에 배치 된 경우)에 대 한 보관을 지원 하도록 Exchange 2013를 설정 하 고 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a8af-113">If you use Microsoft Exchange integration, you must enable and configure Exchange 2013 to support archiving for all users homed on Exchange 2013 who have had their mailboxes put on In-Place Hold.</span></span><BR><span data-ttu-id="5a8af-114">보관을 사용 하도록 설정 하기 전에이 섹션에서 설명 하는 대로 배포에 적절 한 보관 구성을 지정 하 고 필요에 따라 특정 사이트 및 풀에 대해 해당 하는 경우를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a8af-114">Prior to enabling Archiving, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="5a8af-115">보관을 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 배포 설명서의 <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Lync Server 2013에서 보관 정책 구성 및 할당</A> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5a8af-115">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="5a8af-116">**Windows PowerShell cmdlet을 사용 하 여 구성 정보 보관을 보려면**</span><span class="sxs-lookup"><span data-stu-id="5a8af-116">**To view archiving configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="5a8af-117">Windows PowerShell 및 **CsArchivingConfiguration** cmdlet을 사용 하 여 보관 구성 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a8af-117">You can view Archiving configuration information by using Windows PowerShell and the **Get-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="5a8af-118">Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a8af-118">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="5a8af-119">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5a8af-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="5a8af-120">Lync Server 관리 셸에서 다음 명령을 사용 하 여 모든 보관 구성 설정에 대 한 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a8af-120">In the Lync Server Management Shell, use the following command to view information about all of your archiving configuration settings:</span></span>
    
        Get-CsArchivingConfiguration

<div>

## <a name="in-this-section"></a><span data-ttu-id="5a8af-121">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="5a8af-121">In This Section</span></span>

  - [<span data-ttu-id="5a8af-122">Lync Server 2013에서 보관 구성을 만들어 특정 사이트 또는 풀에 대 한 보관 관리</span><span class="sxs-lookup"><span data-stu-id="5a8af-122">Creating an Archiving configuration in Lync Server 2013 to manage Archiving for specific sites or pools</span></span>](lync-server-2013-creating-an-archiving-configuration-to-manage-archiving-for-specific-sites-or-pools.md)

  - [<span data-ttu-id="5a8af-123">Lync Server 2013에서 IM 또는 회의 세션 보관 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="5a8af-123">Enabling or disabling Archiving of IM or conferencing sessions in Lync Server 2013</span></span>](lync-server-2013-enabling-or-disabling-archiving-of-im-or-conferencing-sessions.md)

  - [<span data-ttu-id="5a8af-124">Lync Server 2013에서 보관 된 데이터 제거 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="5a8af-124">Enabling or disabling the purging of archived data in Lync Server 2013</span></span>](lync-server-2013-enabling-or-disabling-the-purging-of-archived-data.md)

  - [<span data-ttu-id="5a8af-125">보관에 실패 한 경우 Lync Server 2013에서 IM 및 웹 회의 세션을 차단 하거나 허용 하기 위해 중요 모드를 사용 하거나 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="5a8af-125">Enabling or disabling critical mode in Lync Server 2013 to block or allow IM and web conferencing sessions if Archiving fails</span></span>](lync-server-2013-enable-disable-critical-mode.md)

  - [<span data-ttu-id="5a8af-126">Lync Server 2013에서 페더레이션 파트너에게 보관 고지 사항 보내기를 사용하거나 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="5a8af-126">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [<span data-ttu-id="5a8af-127">Exchange 저장소와 함께 Lync Server 2013의 통합 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="5a8af-127">Enabling or disabling integration of Lync Server 2013 with Exchange storage</span></span>](lync-server-2013-enabling-or-disabling-integration-with-exchange-storage.md)

  - [<span data-ttu-id="5a8af-128">Lync Server 2013에서 보관 구성 삭제</span><span class="sxs-lookup"><span data-stu-id="5a8af-128">Deleting an Archiving configuration in Lync Server 2013</span></span>](lync-server-2013-deleting-an-archiving-configuration.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5a8af-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5a8af-129">See Also</span></span>


[<span data-ttu-id="5a8af-130">Lync Server 2013 보관 관리</span><span class="sxs-lookup"><span data-stu-id="5a8af-130">Managing Lync Server 2013 Archiving</span></span>](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

