---
title: 비즈니스용 Skype 서버에서 SIP 트렁크 구성 설정의 기존 모음 삭제
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'SIP 트렁크 구성 설정은 중재 서버와 PSTN (공개 통신 네트워크) 게이트웨이, IP-공용 분기 교환 (PBX) 또는 서비스 공급자의 SBC (세션 경계 컨트롤러) 간에 관계와 접근 권한 값을 정의 합니다. '
ms.openlocfilehash: 55636cc34df4b05ccdd4b9035ef3aa4bb169e9a0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187026"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="54b30-103">비즈니스용 Skype 서버에서 SIP 트렁크 구성 설정의 기존 모음 삭제</span><span class="sxs-lookup"><span data-stu-id="54b30-103">Delete an existing collection of SIP trunk configuration settings in Skype for Business Server</span></span>

<span data-ttu-id="54b30-104">SIP 트렁크 구성 설정은 중재 서버와 PSTN (공개 통신 네트워크) 게이트웨이, IP-공용 분기 교환 (PBX) 또는 서비스 공급자의 SBC (세션 경계 컨트롤러) 간에 관계와 접근 권한 값을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="54b30-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="54b30-105">이러한 설정은 다음을 지정 하는 등의 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="54b30-105">These settings do such things as specify:</span></span>

- <span data-ttu-id="54b30-106">Trunks에서 미디어 바이패스를 사용 해야 하는지 여부</span><span class="sxs-lookup"><span data-stu-id="54b30-106">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="54b30-107">RTCP (실시간 전송 제어 프로토콜) 패킷이 전송 되는 조건입니다.</span><span class="sxs-lookup"><span data-stu-id="54b30-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="54b30-108">각 트렁크에서 보안 실시간 프로토콜 (SRTP) 암호화가 필요한 지 여부</span><span class="sxs-lookup"><span data-stu-id="54b30-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="54b30-109">비즈니스용 Skype 서버를 설치 하면 SIP 트렁크 구성 설정의 전역 컬렉션이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54b30-109">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="54b30-110">이 전역 설정 모음은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="54b30-110">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="54b30-111">그러나 비즈니스용 Skype ServerControl 패널 또는 [set-cstrunkconfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet을 사용 하 여 전역 컬렉션의 속성을 기본값으로 "다시 설정" 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54b30-111">However, you can use the Skype for Business ServerControl Panel or the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="54b30-112">예를 들어 Enable3pccRefer 속성을 True로 설정한 경우 전역 컬렉션을 다시 설정 하면 Enable3pccRefer 속성은 기본값으로 False로 되돌려집니다.</span><span class="sxs-lookup"><span data-stu-id="54b30-112">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>

<span data-ttu-id="54b30-113">또한 관리자는 사이트 범위 또는 서비스 범위 (개별 PSTN 게이트웨이의 경우)에서 사용자 지정 트렁크 구성 설정을 만들 수 있습니다. 이러한 사용자 지정 설정은 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54b30-113">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed.</span></span> <span data-ttu-id="54b30-114">이러한 사용자 지정 설정을 제거 하는 경우 다음 사항에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="54b30-114">When removing these custom settings keep the following in mind:</span></span>

- <span data-ttu-id="54b30-115">서비스 범위 설정을 제거 하는 경우 해당 설정에서 관리 하는 SIP 트렁크는 해당 사이트에 적용 된 설정 (있는 경우)에 의해 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54b30-115">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist.</span></span> <span data-ttu-id="54b30-116">사이트 설정이 없는 경우 해당 trunks는 트렁크 구성 설정의 전역 컬렉션을 통해 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54b30-116">If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>
- <span data-ttu-id="54b30-117">사이트 범위 설정을 제거 하면 해당 설정으로 관리 되는 모든 SIP trunks는 트렁크 구성 설정의 전역 컬렉션에서 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54b30-117">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>

<span data-ttu-id="54b30-118">**비즈니스용 Skype 서버 제어판에서 트렁크 구성 설정을 제거 하려면**</span><span class="sxs-lookup"><span data-stu-id="54b30-118">**To remove trunk configuration settings with the Skype for Business Server Control Panel**</span></span> 

1. <span data-ttu-id="54b30-119">비즈니스용 Skype Server 제어판에서 **음성 라우팅을**클릭 한 다음 **트렁크 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="54b30-119">In the Skype for Business Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>
2. <span data-ttu-id="54b30-120">**트렁크 구성** 탭에서 삭제할 SIP 트렁크 구성 설정 모음을 선택 하 고 **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="54b30-120">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit**, and then click **Delete**.</span></span> <span data-ttu-id="54b30-121">동일한 작업에서 여러 컬렉션을 삭제 하려면 삭제할 첫 번째 컬렉션을 클릭 한 다음 Ctrl 키를 누른 채 제거할 추가 모음을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="54b30-121">To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>
3. <span data-ttu-id="54b30-122">컬렉션에 대 한 State 속성이 **커밋되지**않은 **상태로** 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54b30-122">The **State** property for the collection will be updated to **Uncommitted**.</span></span> <span data-ttu-id="54b30-123">변경 내용을 커밋하고 컬렉션을 삭제 하려면 **커밋을** 클릭 한 다음 **모두 커밋을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="54b30-123">To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>
4. <span data-ttu-id="54b30-124">커밋되지 않은 **음성 구성 설정** 대화 상자에서 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="54b30-124">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>
5. <span data-ttu-id="54b30-125">**비즈니스용 Skype Server 제어판** 대화 상자에서 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="54b30-125">In the **Skype for Business Server Control Panel** dialog box, click **OK**.</span></span>
6. <span data-ttu-id="54b30-126">생각이 바뀌어 컬렉션을 삭제 하지 않기로 결정 한 경우에는 **커밋을**클릭 한 다음 **커밋되지 않은 변경 내용 모두 취소**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="54b30-126">If you change your mind and decide not to delete the collection, click **Commit**, and then click **Cancel All Uncommitted Changes**.</span></span> <span data-ttu-id="54b30-127">**비즈니스용 Skype 서버 제어판** 대화 상자가 표시 되 면 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="54b30-127">When the **Skype for Business Server Control Panel** dialog box appears, click **OK**.</span></span>

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="54b30-128">Windows PowerShell cmdlet을 사용 하 여 트렁크 구성 설정 제거</span><span class="sxs-lookup"><span data-stu-id="54b30-128">Removing trunk configuration settings by using Windows PowerShell cmdlets</span></span>


<span data-ttu-id="54b30-129">Windows PowerShell 및 **set-cstrunkconfiguration** cmdlet을 사용 하 여 트렁크 구성 설정을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54b30-129">You can delete trunk configuration settings by using Windows PowerShell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="54b30-130">이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54b30-130">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

<span data-ttu-id="54b30-131">**지정 된 설정 모음을 제거 하려면**</span><span class="sxs-lookup"><span data-stu-id="54b30-131">**To remove a specified collection of settings**</span></span>

<span data-ttu-id="54b30-132">다음 명령은 Redmond 사이트에 적용 된 트렁크 구성 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="54b30-132">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>

`Remove-CsTrunkConfiguration -Identity site:Redmond`

<span data-ttu-id="54b30-133">**사이트 범위에 적용 된 모든 컬렉션을 제거 하려면**</span><span class="sxs-lookup"><span data-stu-id="54b30-133">**To remove all the collections applied to the site scope**</span></span>

<span data-ttu-id="54b30-134">이 명령은 서비스 범위에 적용 된 모든 트렁크 구성 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="54b30-134">This command removes all the trunk configuration settings applied to the service scope:</span></span>

`Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration`

<span data-ttu-id="54b30-135">**미디어 바이패스를 사용 하도록 설정 된 모든 컬렉션을 제거 하려면**</span><span class="sxs-lookup"><span data-stu-id="54b30-135">**To remove all the collections where media bypass is enabled**</span></span>

<span data-ttu-id="54b30-136">다음 명령은 미디어 바이패스를 사용 하도록 설정 된 모든 트렁크 구성 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="54b30-136">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>

`Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration`

<span data-ttu-id="54b30-137">자세한 내용은 [제거 set-cstrunkconfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="54b30-137">For more information, see the help topic for the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet.</span></span>
