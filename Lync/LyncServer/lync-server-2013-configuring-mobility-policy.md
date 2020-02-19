---
title: 'Lync Server 2013: 모바일 정책 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring mobility policy
ms:assetid: 595536e0-9bb3-49a3-8d13-1a77351ebc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690018(v=OCS.15)
ms:contentKeyID: 48184204
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82ca5fbd079f428edf48ef3f0c28bd3677a5acde
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134754"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-policy-in-lync-server-2013"></a><span data-ttu-id="54fab-102">Lync Server 2013에서 모바일 정책 구성</span><span class="sxs-lookup"><span data-stu-id="54fab-102">Configuring mobility policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54fab-103">_**마지막으로 수정 된 항목:** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="54fab-103">_**Topic Last Modified:** 2013-02-13_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="54fab-104">Lync Server 2013에서는 모바일 기능을 사용할 수 있는 사람, 직장, VoIP (voice over IP) 또는 비디오를 통해 전화를 거는 방법 및 VoIP 또는 비디오에 대해 WiFi가 필요한 지를 결정 하는 모바일 정책을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="54fab-104">Lync Server 2013 provides mobility policies that determine who can use mobility features, Call via Work, voice over IP (VoIP) or video, and whether WiFi will be required for either VoIP or video.</span></span> <span data-ttu-id="54fab-105">업무를 통한 통화 기능을 사용 하면 모바일 사용자가 휴대폰 번호 대신 회사 전화 번호를 사용 하 여 휴대폰에서 전화를 걸고 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54fab-105">The Call via Work feature enables a mobile user to make and receive calls on a mobile phone by using a work phone number instead of the mobile phone number.</span></span> <span data-ttu-id="54fab-106">이 기능은 전화 건 사람이 발신자의 휴대폰 번호를 확인 하 여 아웃 바운드 통화 요금을 피할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="54fab-106">This feature prevents the called party from seeing the caller's mobile phone number and enables a user to avoid outbound calling charges.</span></span> <span data-ttu-id="54fab-107">VoIP 및 동영상을 구성 하면 사용자가 VoIP 통화 및 비디오를 수신 하 고 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54fab-107">Configuring VoIP and video makes it possible for users to receive and make VoIP calls and video.</span></span> <span data-ttu-id="54fab-108">WiFi 사용 설정 사용자의 장치에서 셀룰러 데이터 네트워크를 통해 WiFi 네트워크를 사용 해야 하는 경우를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="54fab-108">Settings for WiFi usage define if a user’s device will be required to use a WiFi network over a cellular data network.</span></span>

<span data-ttu-id="54fab-109">기본적으로는 mobility, Work를 통한 통화 및 VoIP 및 비디오 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54fab-109">By default, mobility, Call via Work, and the VoIP and video features are enabled.</span></span> <span data-ttu-id="54fab-110">VoIp 및 비디오용으로 WiFi를 요구 하는 설정을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="54fab-110">The settings to require WiFi for VoIp and video are disabled.</span></span> <span data-ttu-id="54fab-111">관리자는 cmdlet을 실행하여 이러한 기능에 액세스할 수 있는 사용자를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54fab-111">Administrators can determine who has access to these features by running a cmdlet.</span></span> <span data-ttu-id="54fab-112">옵션을 전역적으로 해제할 수도 있고 사이트나 사용자별로 해제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54fab-112">You can turn options off globally, by site, or by user.</span></span>

<span data-ttu-id="54fab-113">모바일 기능과 회사번호로 전화 기능을 사용하려면 사용자는 다음 필수 구성 요소를 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54fab-113">To be able to use mobility features and Call via Work, users must meet the following prerequisites:</span></span>

  - <span data-ttu-id="54fab-114">Lync Server 2013에 대해 사용자를 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54fab-114">Users must be enabled for Lync Server 2013.</span></span>

  - <span data-ttu-id="54fab-115">사용자가 Enterprise Voice를 사용할 수 있도록 설정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54fab-115">Users must be enabled for Enterprise Voice.</span></span>

  - <span data-ttu-id="54fab-116">**EnableMobility** 옵션이 True로 설정된 모바일 정책이 사용자에게 지정되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54fab-116">Users must be assigned a mobility policy that has the **EnableMobility** option set to True.</span></span>

<span data-ttu-id="54fab-117">회사번호로 전화 기능을 사용하려는 사용자는 다음의 두 선행 조건을 추가로 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54fab-117">For users to be able to use Call via Work, they must meet the following two additional prerequisites:</span></span>

  - <span data-ttu-id="54fab-118">**동시 전화 신호 울림 사용** 옵션이 선택된 음성 정책이 사용자에게 지정되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54fab-118">Users must be assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>

  - <span data-ttu-id="54fab-119">**EnableOutsideVoice** 옵션이 True로 설정된 모바일 정책이 사용자에게 지정되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54fab-119">Users must be assigned a mobility policy that has the **EnableOutsideVoice** option set to True.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="54fab-120">Enterprise Voice를 사용 하도록 설정 하지 않은 사용자는 모바일 장치를 사용 하 여 Lync for Lync (Voice over IP) 통화를 수행 하거나, 해당 사용자에 게 음성 정책에 대 한 적절 한 옵션을 할당 하는 경우 모바일 장치에서 링크를 클릭 하 여 연결을 통해 회의에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54fab-120">Users who are not enabled for Enterprise Voice can use their mobile devices to make Lync to Lync Voice over IP (VoIP) calls, or can join conferences by using the Click to Join link on their mobile devices, if you assign those users the appropriate options for voice policy.</span></span> <span data-ttu-id="54fab-121">자세한 내용은 <A href="lync-server-2013-defining-your-mobility-requirements.md">Lync Server 2013에 대 한 모바일 기능 요구 사항 정의</A>를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="54fab-121">For details, see <A href="lync-server-2013-defining-your-mobility-requirements.md">Defining your mobility requirements for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="54fab-122">Lync Server 2013에 대해 사용자를 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 [Disable or enable user account For Lync server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="54fab-122">For details about enabling users for Lync Server 2013, see [Disable or re-enable user account for Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span></span> <span data-ttu-id="54fab-123">Enterprise Voice를 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 사용자에 게 Enterprise Voice 사용을 허용](lync-server-2013-enable-users-for-enterprise-voice.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="54fab-123">For details about enabling users for Enterprise Voice, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span> <span data-ttu-id="54fab-124">음성 정책 옵션을 설정 하는 방법에 대 한 자세한 내용은 [Modify a voice policy 및 CONFIGURE PSTN usage records In Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="54fab-124">For details about setting voice policy options, see [Modify a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md).</span></span>

<div>

## <a name="to-modify-global-mobility-policy"></a><span data-ttu-id="54fab-125">전역 모바일 정책을 수정하려면</span><span class="sxs-lookup"><span data-stu-id="54fab-125">To modify global mobility policy</span></span>

1.  <span data-ttu-id="54fab-126">Lync Server 관리 셸 및 Ocscore CsAdministrator 역할의 구성원으로 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="54fab-126">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="54fab-127">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="54fab-127">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="54fab-p105">명령줄에 다음을 입력하여 모바일 기능 및 회사번호로 전화 기능에 대한 액세스를 전역적으로 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="54fab-p105">Turn off access to mobility and Call via Work globally. At the command line, type:</span></span>
    
        Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="54fab-p106">모바일 기능 액세스는 해제하지 않고 회사번호로 전화 기능만 해제할 수는 있지만, 회사번호로 전화 기능은 해제하지 않고 모바일 기능만 해제할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="54fab-p106">You can turn off Call via Work without turning off access to mobility. However, you cannot turn off mobility without also turning off Call via Work.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-mobility-policy-by-site"></a><span data-ttu-id="54fab-132">사이트별로 모바일 정책을 수정하려면</span><span class="sxs-lookup"><span data-stu-id="54fab-132">To modify mobility policy by site</span></span>

1.  <span data-ttu-id="54fab-133">Lync Server 관리 셸 및 Ocscore CsAdministrator 역할의 구성원으로 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="54fab-133">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="54fab-134">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="54fab-134">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="54fab-135">사이트 수준 정책을 만들고 VoIP 및 비디오를 끈 다음 사이트 별로 ip 오디오 및 IP 비디오용으로 WiFi를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="54fab-135">Create a site-level policy, and turn off VoIP and video, and enable Require WiFi for IP Audio and for IP Video by site.</span></span> <span data-ttu-id="54fab-136">명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="54fab-136">At the command line, type:</span></span>
    
        New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $False -RequireWiFiForIPAudio $True -RequireWiFiForIPVideo $True

</div>

<div>

## <a name="to-modify-mobility-policy-by-user"></a><span data-ttu-id="54fab-137">사용자별로 모바일 정책을 수정하려면</span><span class="sxs-lookup"><span data-stu-id="54fab-137">To modify mobility policy by user</span></span>

1.  <span data-ttu-id="54fab-138">Lync Server 관리 셸 및 Ocscore CsAdministrator 역할의 구성원으로 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="54fab-138">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="54fab-139">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="54fab-139">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="54fab-p108">명령줄에 다음을 입력하여 사용자 수준 모바일 정책을 만들고 모바일 기능 및 회사번호로 전화 기능을 사용자별로 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="54fab-p108">Create user level mobility policies and turn off mobility and Call via Work by user. At the command line, type:</span></span>
    
        New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
    
    <span data-ttu-id="54fab-p109">모바일 기능 액세스는 해제하지 않고 회사번호로 전화 기능만 해제할 수는 있지만, 회사번호로 전화 기능은 해제하지 않고 모바일 기능만 해제할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="54fab-p109">You can turn off Call via Work without turning off access to mobility. However, you cannot turn off mobility without also turning off Call via Work.</span></span>
    
    <span data-ttu-id="54fab-144">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="54fab-144">For example:</span></span>
    
        New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity -MobileUser1@contoso.com -PolicyName Tag:disableOutsideVoice

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="54fab-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="54fab-145">See Also</span></span>


[<span data-ttu-id="54fab-146">Lync Server 2013에 대해 사용자 계정을 사용 하지 않도록 설정 하거나 다시 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="54fab-146">Disable or re-enable user account for Lync Server 2013</span></span>](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[<span data-ttu-id="54fab-147">Lync Server 2013에서 Enterprise Voice를 사용할 수 있도록 사용자 설정</span><span class="sxs-lookup"><span data-stu-id="54fab-147">Enable users for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-enterprise-voice.md)  
[<span data-ttu-id="54fab-148">Lync Server 2013에서 음성 정책 수정 및 PSTN 사용 레코드 구성</span><span class="sxs-lookup"><span data-stu-id="54fab-148">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  


[<span data-ttu-id="54fab-149">Lync Server 2013에 대 한 모바일 기능 요구 사항 정의</span><span class="sxs-lookup"><span data-stu-id="54fab-149">Defining your mobility requirements for Lync Server 2013</span></span>](lync-server-2013-defining-your-mobility-requirements.md)  


[<span data-ttu-id="54fab-150">Get-csmobilitypolicy</span><span class="sxs-lookup"><span data-stu-id="54fab-150">New-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)  
[<span data-ttu-id="54fab-151">Get-csmobilitypolicy</span><span class="sxs-lookup"><span data-stu-id="54fab-151">Set-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy)  
[<span data-ttu-id="54fab-152">Get-csmobilitypolicy</span><span class="sxs-lookup"><span data-stu-id="54fab-152">Get-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy)  
[<span data-ttu-id="54fab-153">Get-csmobilitypolicy</span><span class="sxs-lookup"><span data-stu-id="54fab-153">Grant-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy)  
[<span data-ttu-id="54fab-154">Get-csmobilitypolicy을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="54fab-154">Remove-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

