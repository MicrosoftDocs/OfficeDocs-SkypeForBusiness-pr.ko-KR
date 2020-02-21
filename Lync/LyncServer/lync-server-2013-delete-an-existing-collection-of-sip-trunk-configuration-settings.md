---
title: SIP 트렁크 구성 설정의 기존 컬렉션 삭제
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of SIP trunk configuration settings
ms:assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688024(v=OCS.15)
ms:contentKeyID: 49733614
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f80192db366f5a691724078ba8f8c6948b3472f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202684"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="d2a5c-102">Lync Server 2013에서 SIP 트렁크 구성 설정의 기존 컬렉션 삭제</span><span class="sxs-lookup"><span data-stu-id="d2a5c-102">Delete an existing collection of SIP trunk configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2a5c-103">_**마지막으로 수정 된 항목:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="d2a5c-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="d2a5c-p101">SIP 트렁크 구성 설정은 중재 서버 및 PSTN(공중 전화망) 게이트웨이, IP-PBX(Public Branch Exchange) 또는 서비스 공급자의 SBC(세션 경계 컨트롤러) 사이의 관계 및 기능을 정의합니다. 이러한 설정은 지정할 경우 다음과 같은 기능을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a5c-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

  - <span data-ttu-id="d2a5c-106">트렁크에 미디어 우회를 설정할지 여부</span><span class="sxs-lookup"><span data-stu-id="d2a5c-106">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="d2a5c-107">RTCP(Real-time Transport Control Protocol) 패킷이 전송되는 조건</span><span class="sxs-lookup"><span data-stu-id="d2a5c-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="d2a5c-108">SRTP(Secure Real-time Protocol) 암호화가 각 트렁크에 필요한지 여부</span><span class="sxs-lookup"><span data-stu-id="d2a5c-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="d2a5c-109">Microsoft Lync Server 2013을 설치 하면 SIP 트렁크 구성 설정의 전역 모음이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="d2a5c-109">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="d2a5c-110">이 전역 설정 컬렉션은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a5c-110">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="d2a5c-111">그러나 Lync Server 제어판 또는 [get-cstrunkconfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15)) cmdlet을 사용 하 여 전역 컬렉션의 속성을 기본값으로 "다시 설정" 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a5c-111">However, you can use the Lync Server Control Panel or the [Remove-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15)) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="d2a5c-112">예를 들어 Enable3pccRefer 속성을 True로 설정한 경우 전역 컬렉션을 다시 설정하면 Enable3pccRefer 속성이 기본값인 False로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="d2a5c-112">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>

<span data-ttu-id="d2a5c-p103">관리자는 개별 PSTN 게이트웨이에 대해 사이트 범위 또는 서비스 범위에서 사용자 지정 트렁크 구성 설정을 만들 수도 있습니다. 이러한 사용자 지정 설정은 제거할 수 있습니다. 이와 같은 사용자 지정 설정을 제거할 때는 다음 사항에 유의하십시오.</span><span class="sxs-lookup"><span data-stu-id="d2a5c-p103">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed. When removing these custom settings keep the following in mind:</span></span>

  - <span data-ttu-id="d2a5c-p104">서비스 범위 설정을 제거하면 해당 설정에 의해 관리되는 SIP 트렁크는 사이트에 적용되는 설정(있는 경우)에 의해 관리됩니다. 사이트 설정이 없으면 트렁크는 트렁크 구성 설정의 전역 컬렉션에 의해 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a5c-p104">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist. If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>

  - <span data-ttu-id="d2a5c-117">사이트 범위 설정을 제거하면 해당 설정에 의해 관리되는 SIP 트렁크는 트렁크 구성 설정의 전역 컬렉션에 의해 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a5c-117">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>

<div>

## <a name="to-remove-trunk-configuration-settings-with-lync-server-control-panel"></a><span data-ttu-id="d2a5c-118">Lync Server 제어판을 사용 하 여 트렁크 구성 설정을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="d2a5c-118">To remove trunk configuration settings with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="d2a5c-119">Lync Server 제어판에서 **음성 라우팅을** 클릭 한 다음 **트렁크 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a5c-119">In Lync Server Control Panel, click **Voice Routing** and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="d2a5c-p105">**트렁크 구성** 탭에서 삭제할 SIP 트렁크 구성 설정 컬렉션을 선택하고 **편집**, **삭제**를 차례로 클릭합니다. 같은 작업에서 여러 컬렉션을 삭제하려면 삭제할 첫 번째 컬렉션을 클릭하고 Ctrl 키를 누른 상태로 제거할 추가 컬렉션을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a5c-p105">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit** and then click **Delete**. To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>

3.  <span data-ttu-id="d2a5c-p106">컬렉션의 **상태** 속성이 **커밋되지 않음**으로 업데이트됩니다. 변경 내용을 커밋하고 컬렉션을 삭제하려면 **커밋**, **모두 커밋**을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a5c-p106">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>

4.  <span data-ttu-id="d2a5c-124">**커밋되지 않은 음성 구성 설정** 대화 상자에서 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a5c-124">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>

5.  <span data-ttu-id="d2a5c-125">**Microsoft Lync Server 2013 제어판** 대화 상자에서 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a5c-125">In the **Microsoft Lync Server 2013 Control Panel** dialog box click **OK**.</span></span>

6.  <span data-ttu-id="d2a5c-p107">컬렉션을 삭제하지 않으려는 경우 **커밋**을 클릭한 다음 **커밋되지 않은 모든 변경 내용 취소**를 클릭합니다. **Microsoft Lync Server 2013 제어판** 대화 상자가 나타나면 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a5c-p107">If you change your mind and decide not to delete the collection, click **Commit** and then click **Cancel All Uncommitted Changes**. When the **Microsoft Lync Server 2013 Control Panel** dialog box appears, click **OK**.</span></span>

</div>

<div>

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d2a5c-128">Windows PowerShell Cmdlet을 사용 하 여 트렁크 구성 설정 제거</span><span class="sxs-lookup"><span data-stu-id="d2a5c-128">Removing Trunk Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d2a5c-129">Windows PowerShell 및 **get-cstrunkconfiguration** cmdlet을 사용 하 여 트렁크 구성 설정을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a5c-129">You can delete trunk configuration settings by using Windows PowerShell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="d2a5c-130">Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a5c-130">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d2a5c-131">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d2a5c-131">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-settings"></a><span data-ttu-id="d2a5c-132">지정 된 설정 컬렉션을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="d2a5c-132">To remove a specified collection of settings</span></span>

  - <span data-ttu-id="d2a5c-133">다음 명령은 Redmond 사이트에 적용된 트렁크 구성 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a5c-133">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsTrunkConfiguration -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a><span data-ttu-id="d2a5c-134">사이트 범위에 적용 된 모든 컬렉션을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="d2a5c-134">To remove all the collections applied to the site scope</span></span>

  - <span data-ttu-id="d2a5c-135">다음 명령은 서비스 범위에 적용된 모든 트렁크 구성 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a5c-135">This command removes all the trunk configuration settings applied to the service scope:</span></span>
    
        Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration

</div>

<div>

## <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a><span data-ttu-id="d2a5c-136">미디어 바이패스가 사용 하도록 설정 된 모든 컬렉션을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="d2a5c-136">To remove all the collections where media bypass is enabled</span></span>

  - <span data-ttu-id="d2a5c-137">다음 명령은 미디어 바이패스가 사용하도록 설정된 모든 트렁크 구성 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a5c-137">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>
    
        Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration

</div>

<span data-ttu-id="d2a5c-138">자세한 내용은 [get-cstrunkconfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15)) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d2a5c-138">For more information, see the help topic for the [Remove-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

