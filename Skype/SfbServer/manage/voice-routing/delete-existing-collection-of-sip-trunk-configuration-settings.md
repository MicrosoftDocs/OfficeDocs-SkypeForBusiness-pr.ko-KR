---
title: 비즈니스용 Skype 서버에서 SIP 트렁크 구성 설정의 기존 컬렉션 삭제
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'SIP 트렁크 구성 설정은 중재 서버 및 PSTN(공중 전화망) 게이트웨이, IP-PBX(Public Branch Exchange) 또는 서비스 공급자의 SBC(세션 경계 컨트롤러) 사이의 관계 및 기능을 정의합니다. '
ms.openlocfilehash: f8e7e3576640e4c560cd620349f5c3afdaf541cd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816328"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="e7234-103">비즈니스용 Skype 서버에서 SIP 트렁크 구성 설정의 기존 컬렉션 삭제</span><span class="sxs-lookup"><span data-stu-id="e7234-103">Delete an existing collection of SIP trunk configuration settings in Skype for Business Server</span></span>

<span data-ttu-id="e7234-p101">SIP 트렁크 구성 설정은 중재 서버 및 PSTN(공중 전화망) 게이트웨이, IP-PBX(Public Branch Exchange) 또는 서비스 공급자의 SBC(세션 경계 컨트롤러) 사이의 관계 및 기능을 정의합니다. 이러한 설정은 지정할 경우 다음과 같은 기능을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e7234-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

- <span data-ttu-id="e7234-106">트렁크에 미디어 우회를 설정할지 여부</span><span class="sxs-lookup"><span data-stu-id="e7234-106">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="e7234-107">RTCP(Real-time Transport Control Protocol) 패킷이 전송되는 조건</span><span class="sxs-lookup"><span data-stu-id="e7234-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="e7234-108">SRTP(Secure Real-time Protocol) 암호화가 각 트렁크에 필요한지 여부</span><span class="sxs-lookup"><span data-stu-id="e7234-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="e7234-109">비즈니스용 Skype 서버를 설치하면 전역 SIP 트렁크 구성 설정 컬렉션이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="e7234-109">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="e7234-110">이 전역 설정 컬렉션은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e7234-110">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="e7234-111">그러나 비즈니스용 Skype 서버Control 패널 또는 [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet을 사용하여 전역 컬렉션의 속성을 기본값으로 "다시 설정"할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7234-111">However, you can use the Skype for Business ServerControl Panel or the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="e7234-112">예를 들어 Enable3pccRefer 속성을 True로 설정한 경우 전역 컬렉션을 다시 설정하면 Enable3pccRefer 속성이 기본값인 False로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="e7234-112">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>

<span data-ttu-id="e7234-p103">관리자는 개별 PSTN 게이트웨이에 대해 사이트 범위 또는 서비스 범위에서 사용자 지정 트렁크 구성 설정을 만들 수도 있습니다. 이러한 사용자 지정 설정은 제거할 수 있습니다. 이와 같은 사용자 지정 설정을 제거할 때는 다음 사항에 유의하십시오.</span><span class="sxs-lookup"><span data-stu-id="e7234-p103">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed. When removing these custom settings keep the following in mind:</span></span>

- <span data-ttu-id="e7234-p104">서비스 범위 설정을 제거하면 해당 설정에 의해 관리되는 SIP 트렁크는 사이트에 적용되는 설정(있는 경우)에 의해 관리됩니다. 사이트 설정이 없으면 트렁크는 트렁크 구성 설정의 전역 컬렉션에 의해 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7234-p104">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist. If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>
- <span data-ttu-id="e7234-117">사이트 범위 설정을 제거하면 해당 설정에 의해 관리되는 SIP 트렁크는 트렁크 구성 설정의 전역 컬렉션에 의해 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7234-117">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>

<span data-ttu-id="e7234-118">**비즈니스용 Skype 서버 제어판을 사용하여 트렁크 구성 설정을 제거하려면**</span><span class="sxs-lookup"><span data-stu-id="e7234-118">**To remove trunk configuration settings with the Skype for Business Server Control Panel**</span></span> 

1. <span data-ttu-id="e7234-119">비즈니스용 Skype 서버 제어판에서 음성 라우팅을 클릭한 다음 **트렁크 구성을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="e7234-119">In the Skype for Business Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>
2. <span data-ttu-id="e7234-120">**트렁크** 구성 탭에서 삭제할 SIP 트렁크 구성 설정 컬렉션을 선택하고 **편집을** 클릭한 다음 삭제를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="e7234-120">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit**, and then click **Delete**.</span></span> <span data-ttu-id="e7234-121">같은 작업에서 여러 컬렉션을 삭제하려면 삭제할 첫 번째 컬렉션을 클릭하고 Ctrl 키를 누른 상태로 제거할 추가 컬렉션을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e7234-121">To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>
3. <span data-ttu-id="e7234-p106">컬렉션의 **상태** 속성은 **커밋되지 않음** 으로 업데이트됩니다. 변경 내용을 커밋하고 컬렉션을 삭제하려면 **커밋** 을 클릭한 후 **모두 커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e7234-p106">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>
4. <span data-ttu-id="e7234-124">**커밋되지 않은 음성 구성 설정** 대화 상자에서 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e7234-124">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>
5. <span data-ttu-id="e7234-125">비즈니스용 **Skype 서버 제어판** 대화 상자에서 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="e7234-125">In the **Skype for Business Server Control Panel** dialog box, click **OK**.</span></span>
6. <span data-ttu-id="e7234-126">마음이 바뀌어 컬렉션을 삭제하지 않을 경우 커밋을 클릭한 다음 커밋되지 않은 모든 변경 내용 **취소를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="e7234-126">If you change your mind and decide not to delete the collection, click **Commit**, and then click **Cancel All Uncommitted Changes**.</span></span> <span data-ttu-id="e7234-127">비즈니스용 **Skype 서버 제어판** 대화 상자가 나타나면 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="e7234-127">When the **Skype for Business Server Control Panel** dialog box appears, click **OK**.</span></span>

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e7234-128">cmdlet을 사용하여 트렁크 구성 Windows PowerShell 제거</span><span class="sxs-lookup"><span data-stu-id="e7234-128">Removing trunk configuration settings by using Windows PowerShell cmdlets</span></span>


<span data-ttu-id="e7234-129">트렁크 구성 설정은 **Remove-CsTrunkConfiguration** cmdlet과 Windows PowerShell 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7234-129">You can delete trunk configuration settings by using Windows PowerShell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="e7234-130">이 cmdlet은 비즈니스용 Skype 서버 관리 셸 또는 비즈니스용 Skype 서버 관리 셸의 원격 세션에서 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e7234-130">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

<span data-ttu-id="e7234-131">**지정한 설정 컬렉션을 제거하려면**</span><span class="sxs-lookup"><span data-stu-id="e7234-131">**To remove a specified collection of settings**</span></span>

<span data-ttu-id="e7234-132">다음 명령은 Redmond 사이트에 적용된 트렁크 구성 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="e7234-132">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>

`Remove-CsTrunkConfiguration -Identity site:Redmond`

<span data-ttu-id="e7234-133">**사이트 범위에 적용된 모든 컬렉션을 제거하려면**</span><span class="sxs-lookup"><span data-stu-id="e7234-133">**To remove all the collections applied to the site scope**</span></span>

<span data-ttu-id="e7234-134">다음 명령은 서비스 범위에 적용된 모든 트렁크 구성 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="e7234-134">This command removes all the trunk configuration settings applied to the service scope:</span></span>

`Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration`

<span data-ttu-id="e7234-135">**미디어 우회가 사용하도록 설정된 모든 컬렉션을 제거하려면**</span><span class="sxs-lookup"><span data-stu-id="e7234-135">**To remove all the collections where media bypass is enabled**</span></span>

<span data-ttu-id="e7234-136">다음 명령은 미디어 바이패스가 사용하도록 설정된 모든 트렁크 구성 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="e7234-136">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>

`Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration`

<span data-ttu-id="e7234-137">자세한 내용은 [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet에 대한 도움말 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e7234-137">For more information, see the help topic for the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet.</span></span>
