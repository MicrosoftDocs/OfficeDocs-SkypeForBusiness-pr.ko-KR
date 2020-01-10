---
title: 비즈니스용 Skype 서버에서 SIP 트렁크 구성 설정의 기존 모음 삭제
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
description: '요약: 비즈니스용 Skype 서버 제어판을 사용 하 여 트렁크 구성 설정 모음을 삭제 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 97a0820258a837968b88e6840232829f3ad11d21
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41000998"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="85ecc-103">비즈니스용 Skype 서버에서 SIP 트렁크 구성 설정의 기존 모음 삭제</span><span class="sxs-lookup"><span data-stu-id="85ecc-103">Delete an existing collection of SIP trunk configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="85ecc-104">**요약:** 비즈니스용 Skype 서버 제어판을 사용 하 여 트렁크 구성 설정 모음을 삭제 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="85ecc-104">**Summary:** Learn how to delete a collection of trunk configuration settings by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="85ecc-105">SIP 트렁크 구성 설정은 중재 서버와 PSTN (공개 통신 네트워크) 게이트웨이, IP-공용 분기 교환 (PBX) 또는 서비스 공급자의 SBC (세션 경계 컨트롤러) 간에 관계와 접근 권한 값을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="85ecc-105">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the Public Switched Telephone Network (PSTN) gateway, an IP-Public Branch eXchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="85ecc-106">이러한 설정은 다음을 지정 하는 등의 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="85ecc-106">These settings do such things as specify:</span></span>
  
- <span data-ttu-id="85ecc-107">Trunks에서 미디어 바이패스를 사용 해야 하는지 여부</span><span class="sxs-lookup"><span data-stu-id="85ecc-107">Whether media bypass should be enabled on the trunks.</span></span>
    
- <span data-ttu-id="85ecc-108">RTCP (실시간 전송 제어 프로토콜) 패킷이 전송 되는 조건입니다.</span><span class="sxs-lookup"><span data-stu-id="85ecc-108">The conditions under which Realtime Transport Control Protocol (RTCP) packets are sent.</span></span>
    
- <span data-ttu-id="85ecc-109">각 트렁크에서 보안 실시간 전송 프로토콜 (SRTP) 암호화가 필요한 지 여부</span><span class="sxs-lookup"><span data-stu-id="85ecc-109">Whether or not Secure Realtime Transport Protocol (SRTP) encryption is required on each trunk.</span></span>
    
<span data-ttu-id="85ecc-110">비즈니스용 Skype 서버를 설치 하면 SIP 트렁크 구성 설정의 전역 컬렉션이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85ecc-110">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="85ecc-111">이 전역 설정 모음은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="85ecc-111">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="85ecc-112">그러나 비즈니스용 Skype Server 제어판 또는 [set-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet을 사용 하 여 전역 컬렉션의 속성을 기본값으로 "다시 설정" 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85ecc-112">However, you can use the Skype for Business Server Control Panel or the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="85ecc-113">예를 들어 Enable3pccRefer 속성을 True로 설정한 경우 전역 컬렉션을 다시 설정 하면 Enable3pccRefer 속성은 기본값으로 False로 되돌려집니다.</span><span class="sxs-lookup"><span data-stu-id="85ecc-113">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>
  
<span data-ttu-id="85ecc-114">또한 관리자는 사이트 범위 또는 서비스 범위 (개별 PSTN 게이트웨이의 경우)에서 사용자 지정 트렁크 구성 설정을 만들 수 있습니다. 이러한 사용자 지정 설정은 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85ecc-114">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed.</span></span> <span data-ttu-id="85ecc-115">이러한 사용자 지정 설정을 제거 하는 경우 다음 사항에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="85ecc-115">When removing these custom settings keep the following in mind:</span></span>
  
- <span data-ttu-id="85ecc-116">서비스 범위 설정을 제거 하는 경우 해당 설정에서 관리 하는 SIP 트렁크는 해당 사이트에 적용 된 설정 (있는 경우)에 의해 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85ecc-116">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist.</span></span> <span data-ttu-id="85ecc-117">사이트 설정이 없는 경우 해당 trunks는 트렁크 구성 설정의 전역 컬렉션을 통해 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85ecc-117">If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>
    
- <span data-ttu-id="85ecc-118">사이트 범위 설정을 제거 하면 해당 설정으로 관리 되는 모든 SIP trunks는 트렁크 구성 설정의 전역 컬렉션에서 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85ecc-118">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>
    
### <a name="to-remove-trunk-configuration-settings-with-skype-for-business-server-control-panel"></a><span data-ttu-id="85ecc-119">비즈니스용 Skype Server 제어판에서 트렁크 구성 설정을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="85ecc-119">To remove trunk configuration settings with Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="85ecc-120">비즈니스용 Skype 서버 제어판에서 **음성 라우팅을** 클릭 한 다음 **트렁크 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="85ecc-120">In Skype for Business Server Control Panel, click **Voice Routing** and then click **Trunk Configuration**.</span></span>
    
2. <span data-ttu-id="85ecc-121">**트렁크 구성** 탭에서 삭제할 SIP 트렁크 구성 설정 모음을 선택 하 고 **편집** 을 클릭 한 다음 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="85ecc-121">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit** and then click **Delete**.</span></span> <span data-ttu-id="85ecc-122">동일한 작업에서 여러 컬렉션을 삭제 하려면 삭제할 첫 번째 컬렉션을 클릭 한 다음 Ctrl 키를 누른 채 제거할 추가 모음을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="85ecc-122">To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>
    
3. <span data-ttu-id="85ecc-123">컬렉션에 대 한 State 속성이 **커밋되지**않은 **상태로** 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85ecc-123">The **State** property for the collection will be updated to **Uncommitted**.</span></span> <span data-ttu-id="85ecc-124">변경 내용을 커밋하고 컬렉션을 삭제 하려면 **커밋을** 클릭 한 다음 **모두 커밋을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="85ecc-124">To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>
    
4. <span data-ttu-id="85ecc-125">커밋되지 않은 **음성 구성 설정** 대화 상자에서 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="85ecc-125">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>
    
5. <span data-ttu-id="85ecc-126">**비즈니스용 Skype Server 제어판** 대화 상자에서 **확인을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="85ecc-126">In the **Skype for Business Server Control Panel** dialog box click **OK**.</span></span>
    
6. <span data-ttu-id="85ecc-127">생각이 바뀌어 컬렉션을 삭제 하지 않기로 결정 한 경우에는 **커밋을** 클릭 한 다음 커밋되지 않은 **변경 내용 모두 취소**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="85ecc-127">If you change your mind and decide not to delete the collection, click **Commit** and then click **Cancel All Uncommitted Changes**.</span></span> <span data-ttu-id="85ecc-128">**비즈니스용 Skype 서버 제어판** 대화 상자가 표시 되 면 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="85ecc-128">When the **Skype for Business Server Control Panel** dialog box appears, click **OK**.</span></span>
    
## <a name="removing-trunk-configuration-settings-by-using-skype-for-business-server-management-shell-cmdlets"></a><span data-ttu-id="85ecc-129">비즈니스용 Skype Server Management Shell Cmdlet을 사용 하 여 트렁크 구성 설정 제거</span><span class="sxs-lookup"><span data-stu-id="85ecc-129">Removing Trunk Configuration Settings by Using Skype for Business Server Management Shell Cmdlets</span></span>

<span data-ttu-id="85ecc-130">비즈니스용 Skype Server Management Shell 및 **set-cstrunkconfiguration** cmdlet을 사용 하 여 트렁크 구성 설정을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85ecc-130">You can delete trunk configuration settings by using Skype for Business Server Management Shell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="85ecc-131">비즈니스용 Skype 서버 관리 셸에서 또는 비즈니스용 Skype Server Management Shell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85ecc-131">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Skype for Business Server Management Shell.</span></span>
  
### <a name="to-remove-a-specified-collection-of-settings"></a><span data-ttu-id="85ecc-132">지정 된 설정 모음을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="85ecc-132">To remove a specified collection of settings</span></span>

- <span data-ttu-id="85ecc-133">다음 명령은 Redmond 사이트에 적용 된 트렁크 구성 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="85ecc-133">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>
    
  ```powershell
  Remove-CsTrunkConfiguration -Identity site:Redmond
  ```

### <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a><span data-ttu-id="85ecc-134">사이트 범위에 적용 된 모든 컬렉션을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="85ecc-134">To remove all the collections applied to the site scope</span></span>

- <span data-ttu-id="85ecc-135">이 명령은 서비스 범위에 적용 된 모든 트렁크 구성 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="85ecc-135">This command removes all the trunk configuration settings applied to the service scope:</span></span>
    
  ```powershell
  Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration
  ```

### <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a><span data-ttu-id="85ecc-136">미디어 바이패스를 사용 하도록 설정 된 모든 컬렉션을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="85ecc-136">To remove all the collections where media bypass is enabled</span></span>

- <span data-ttu-id="85ecc-137">다음 명령은 미디어 바이패스를 사용 하도록 설정 된 모든 트렁크 구성 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="85ecc-137">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>
    
  ```powershell
  Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration
  ```

<span data-ttu-id="85ecc-138">자세한 내용은 [제거 set-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="85ecc-138">For more information, see the help topic for the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet.</span></span>
  

