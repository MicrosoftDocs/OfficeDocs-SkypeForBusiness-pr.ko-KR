---
title: 기존 SIP 트렁크 구성 설정 모음 삭제
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing collection of SIP trunk configuration settings
ms:assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688024(v=OCS.15)
ms:contentKeyID: 49733614
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b896d53760184d15b02afed14b8a9c0d660f96b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983974"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="aeba9-102">Lync Server 2013에서 기존 SIP 트렁크 구성 설정 모음 삭제</span><span class="sxs-lookup"><span data-stu-id="aeba9-102">Delete an existing collection of SIP trunk configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aeba9-103">_**마지막으로 수정한 주제:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="aeba9-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="aeba9-104">SIP 트렁크 구성 설정은 중재 서버와 PSTN (공개 통신 네트워크) 게이트웨이, IP-공용 분기 교환 (PBX) 또는 서비스 공급자의 SBC (세션 경계 컨트롤러) 간에 관계와 접근 권한 값을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeba9-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="aeba9-105">이러한 설정은 다음을 지정 하는 등의 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeba9-105">These settings do such things as specify:</span></span>

  - <span data-ttu-id="aeba9-106">Trunks에서 미디어 바이패스를 사용 해야 하는지 여부</span><span class="sxs-lookup"><span data-stu-id="aeba9-106">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="aeba9-107">RTCP (실시간 전송 제어 프로토콜) 패킷이 전송 되는 조건입니다.</span><span class="sxs-lookup"><span data-stu-id="aeba9-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="aeba9-108">각 트렁크에서 보안 실시간 프로토콜 (SRTP) 암호화가 필요한 지 여부</span><span class="sxs-lookup"><span data-stu-id="aeba9-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="aeba9-109">Microsoft Lync Server 2013을 설치할 때 SIP 트렁크 구성 설정의 전역 컬렉션이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aeba9-109">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="aeba9-110">이 전역 설정 모음은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aeba9-110">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="aeba9-111">그러나 Lync Server 제어판 또는 [set-cstrunkconfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15)) cmdlet을 사용 하 여 전역 컬렉션의 속성을 기본값으로 "다시 설정" 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aeba9-111">However, you can use the Lync Server Control Panel or the [Remove-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15)) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="aeba9-112">예를 들어 Enable3pccRefer 속성을 True로 설정한 경우 전역 컬렉션을 다시 설정 하면 Enable3pccRefer 속성은 기본값으로 False로 되돌려집니다.</span><span class="sxs-lookup"><span data-stu-id="aeba9-112">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>

<span data-ttu-id="aeba9-113">또한 관리자는 사이트 범위 또는 서비스 범위 (개별 PSTN 게이트웨이의 경우)에서 사용자 지정 트렁크 구성 설정을 만들 수 있습니다. 이러한 사용자 지정 설정은 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aeba9-113">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed.</span></span> <span data-ttu-id="aeba9-114">이러한 사용자 지정 설정을 제거 하는 경우 다음 사항에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="aeba9-114">When removing these custom settings keep the following in mind:</span></span>

  - <span data-ttu-id="aeba9-115">서비스 범위 설정을 제거 하는 경우 해당 설정에서 관리 하는 SIP 트렁크는 해당 사이트에 적용 된 설정 (있는 경우)에 의해 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aeba9-115">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist.</span></span> <span data-ttu-id="aeba9-116">사이트 설정이 없는 경우 해당 trunks는 트렁크 구성 설정의 전역 컬렉션을 통해 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aeba9-116">If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>

  - <span data-ttu-id="aeba9-117">사이트 범위 설정을 제거 하면 해당 설정으로 관리 되는 모든 SIP trunks는 트렁크 구성 설정의 전역 컬렉션에서 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aeba9-117">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>

<div>

## <a name="to-remove-trunk-configuration-settings-with-lync-server-control-panel"></a><span data-ttu-id="aeba9-118">Lync Server 제어판에서 트렁크 구성 설정을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="aeba9-118">To remove trunk configuration settings with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="aeba9-119">Lync Server 제어판에서 **음성 라우팅을** 클릭 한 다음 **트렁크 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeba9-119">In Lync Server Control Panel, click **Voice Routing** and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="aeba9-120">**트렁크 구성** 탭에서 삭제할 SIP 트렁크 구성 설정 모음을 선택 하 고 **편집** 을 클릭 한 다음 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeba9-120">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit** and then click **Delete**.</span></span> <span data-ttu-id="aeba9-121">동일한 작업에서 여러 컬렉션을 삭제 하려면 삭제할 첫 번째 컬렉션을 클릭 한 다음 Ctrl 키를 누른 채 제거할 추가 모음을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeba9-121">To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>

3.  <span data-ttu-id="aeba9-122">컬렉션에 대 한 State 속성이 **커밋되지**않은 **상태로** 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aeba9-122">The **State** property for the collection will be updated to **Uncommitted**.</span></span> <span data-ttu-id="aeba9-123">변경 내용을 커밋하고 컬렉션을 삭제 하려면 **커밋을** 클릭 한 다음 **모두 커밋을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeba9-123">To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>

4.  <span data-ttu-id="aeba9-124">커밋되지 않은 **음성 구성 설정** 대화 상자에서 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeba9-124">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>

5.  <span data-ttu-id="aeba9-125">**Microsoft Lync Server 2013 제어판** 대화 상자에서 **확인을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeba9-125">In the **Microsoft Lync Server 2013 Control Panel** dialog box click **OK**.</span></span>

6.  <span data-ttu-id="aeba9-126">생각이 바뀌어 컬렉션을 삭제 하지 않기로 결정 한 경우에는 **커밋을** 클릭 한 다음 커밋되지 않은 **변경 내용 모두 취소**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeba9-126">If you change your mind and decide not to delete the collection, click **Commit** and then click **Cancel All Uncommitted Changes**.</span></span> <span data-ttu-id="aeba9-127">**Microsoft Lync Server 2013 제어판** 대화 상자가 표시 되 면 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeba9-127">When the **Microsoft Lync Server 2013 Control Panel** dialog box appears, click **OK**.</span></span>

</div>

<div>

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="aeba9-128">Windows PowerShell Cmdlet을 사용 하 여 트렁크 구성 설정 제거</span><span class="sxs-lookup"><span data-stu-id="aeba9-128">Removing Trunk Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="aeba9-129">Windows PowerShell 및 **set-cstrunkconfiguration** cmdlet을 사용 하 여 트렁크 구성 설정을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aeba9-129">You can delete trunk configuration settings by using Windows PowerShell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="aeba9-130">Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aeba9-130">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="aeba9-131">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="aeba9-131">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-settings"></a><span data-ttu-id="aeba9-132">지정 된 설정 모음을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="aeba9-132">To remove a specified collection of settings</span></span>

  - <span data-ttu-id="aeba9-133">다음 명령은 Redmond 사이트에 적용 된 트렁크 구성 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeba9-133">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsTrunkConfiguration -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a><span data-ttu-id="aeba9-134">사이트 범위에 적용 된 모든 컬렉션을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="aeba9-134">To remove all the collections applied to the site scope</span></span>

  - <span data-ttu-id="aeba9-135">이 명령은 서비스 범위에 적용 된 모든 트렁크 구성 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeba9-135">This command removes all the trunk configuration settings applied to the service scope:</span></span>
    
        Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration

</div>

<div>

## <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a><span data-ttu-id="aeba9-136">미디어 바이패스를 사용 하도록 설정 된 모든 컬렉션을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="aeba9-136">To remove all the collections where media bypass is enabled</span></span>

  - <span data-ttu-id="aeba9-137">다음 명령은 미디어 바이패스를 사용 하도록 설정 된 모든 트렁크 구성 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeba9-137">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>
    
        Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration

</div>

<span data-ttu-id="aeba9-138">자세한 내용은 [제거 set-cstrunkconfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15)) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="aeba9-138">For more information, see the help topic for the [Remove-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

