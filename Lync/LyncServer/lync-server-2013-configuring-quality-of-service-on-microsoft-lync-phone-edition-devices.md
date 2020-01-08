---
title: Microsoft Lync Phone Edition 장치에서 서비스 품질 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Quality of Service on Microsoft Lync Phone Edition devices
ms:assetid: a6eb2620-a512-4ab6-bdfd-eb76be43bbfe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205137(v=OCS.15)
ms:contentKeyID: 48185004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9f7f96e90aa07da193f9ffb714fc3437ba46cd8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983535"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-on-microsoft-lync-phone-edition-devices-in-lync-server-2013"></a><span data-ttu-id="83576-102">Lync Server 2013에서 Microsoft Lync Phone Edition 장치에 대 한 서비스 품질 구성</span><span class="sxs-lookup"><span data-stu-id="83576-102">Configuring Quality of Service on Microsoft Lync Phone Edition devices in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83576-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="83576-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="83576-104">QoS (서비스 품질)는 Iphone와 같은 디바이스에 대해 기본적으로 사용 되지 않지만, Lync Phone Edition을 실행 하는 디바이스에 대해 기본적으로 QoS를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83576-104">Although Quality of Service (QoS) is not enabled by default for devices such as iPhones, QoS is enabled by default for devices running Lync Phone Edition.</span></span> <span data-ttu-id="83576-105">(이러한 장치는 일반적으로 UC 또는 통합 통신 전화 라고 합니다.) 이를 확인 하려면 Lync Server Management Shell 내에서 다음 Windows PowerShell 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="83576-105">(These devices are commonly referred to as UC or Unified Communication phones.) To verify this, run the following Windows PowerShell command from within the Lync Server Management Shell:</span></span>

    Get-CsUCPhoneConfiguration

<span data-ttu-id="83576-106">UC 전화 구성 설정을 변경 하지 않은 경우에는 다음과 같은 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83576-106">If you have not made any changes to your UC phone configuration settings then you will get back information that looks like this:</span></span>

    Identity             : Global
    CalendarPollInterval : 00:03:00
    EnforcePhoneLock     : True
    PhoneLockTimeout     : 00:10:00
    MinPhonePinLength    : 6
    SIPSecurityMode      : High
    VoiceDiffServTag     : 40
    Voice8021p           : 0
    LoggingLevel         : Off

<span data-ttu-id="83576-107">서비스 품질을 위해 다음 속성 중 하나에만 관심이 있습니다. VoiceDiffServTag.</span><span class="sxs-lookup"><span data-stu-id="83576-107">For Quality of Service purposes, only one of these properties is of interest: VoiceDiffServTag.</span></span> <span data-ttu-id="83576-108">VoiceDiffServTag는 Lync Phone Edition 장치에서 음성 트래픽 emanating에 할당 된 DSCP 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="83576-108">The VoiceDiffServTag represents the DSCP value assigned to voice traffic emanating from a Lync Phone Edition device.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="83576-109">Voice8021p 매개 변수는 Lync Server 2013에서 더 이상 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83576-109">The Voice8021p parameter is no longer supported in Lync Server 2013.</span></span> <span data-ttu-id="83576-110">이 매개 변수는 여전히 Microsoft Lync Server 2010의 이전 버전과의 호환성을 위해 유효 합니다. 그러나 Lync Server 2013에 사용 되는 장치에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83576-110">The parameter is still valid for backward compatibility with Microsoft Lync Server 2010; however, it has no effect on devices used with Lync Server 2013.</span></span>



</div>

<span data-ttu-id="83576-111">대부분의 네트워크에서 40의 VoiceDiffServTag으로 Lync Phone Edition 패킷을 표시 하면 문제가 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83576-111">In most networks, marking Lync Phone Edition packets with a VoiceDiffServTag of 40 should not cause any problems.</span></span> <span data-ttu-id="83576-112">그러나 40는 일반적으로 오디오 트래픽에 사용 되는 값이 아닙니다. 대신 오디오 트래픽은 거의 항상 DSCP 코드 46으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83576-112">However, 40 is not the value typically used for audio traffic; instead, audio traffic is almost always marked with the DSCP code 46.</span></span> <span data-ttu-id="83576-113">네트워크 전체에서 일관성을 유지 하기 위해 UC 휴대폰의 VoiceDiffServTag 속성을 46으로 변경 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="83576-113">In order to maintain consistency throughout your network, you might want to change the VoiceDiffServTag property of your UC phones to 46.</span></span>

<span data-ttu-id="83576-114">이렇게 하려면 Windows PowerShell 또는 Lync Server 제어판을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83576-114">To do that, you can use either Windows PowerShell or the Lync Server Control Panel.</span></span> <span data-ttu-id="83576-115">Windows PowerShell을 사용 하 여 VoiceDiffServTag 값을 수정 하려면 Lync Server Management Shell 내에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="83576-115">To modify the VoiceDiffServTag value by using Windows PowerShell, run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

<span data-ttu-id="83576-116">앞의 명령은 UC 전화 구성 설정의 전역 컬렉션을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="83576-116">The preceding command modifies the global collection of UC phone configuration settings.</span></span> <span data-ttu-id="83576-117">그러나 통합 커뮤니케이션 설정은 사이트 범위에 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83576-117">Note, however, that UC phone settings can also be assigned to the site scope.</span></span> <span data-ttu-id="83576-118">사이트 범위에서 UC 전화 구성 설정을 수정 하려면 사이트 Id를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83576-118">To modify UC phone configuration settings at the site scope, you must specify the site Identity.</span></span> <span data-ttu-id="83576-119">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="83576-119">For example:</span></span>

    Set-CsUCPhoneConfiguration -Identity "site:Redmond" -VoiceDiffServTag 46

<span data-ttu-id="83576-120">다음 명령을 사용 하 여 모든 UC 전화 구성 설정을 동시에 수정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83576-120">You can also use the following command to simultaneously modify all your UC phone configuration settings:</span></span>

    Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

<span data-ttu-id="83576-121">Lync Server 제어판을 사용 하 여이 변경 작업을 수행 하려면 제어판을 시작 하 고 다음 절차를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="83576-121">If you prefer to make this change using Lync Server Control Panel, then start the Control Panel and then complete the following procedure:</span></span>

1.  <span data-ttu-id="83576-122">**클라이언트** 를 클릭 한 다음 **장치 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83576-122">Click **Clients** and then click **Device Configuration**.</span></span>

2.  <span data-ttu-id="83576-123">**장치 구성** 탭에서 수정 하려는 설정 모음을 두 번 클릭 합니다 (예: **전역**).</span><span class="sxs-lookup"><span data-stu-id="83576-123">On the **Device Configuration** tab, double-click the collection of settings you want to modify (for example, **Global**).</span></span>

3.  <span data-ttu-id="83576-124">**장치 구성 편집** 대화 상자에서 **Voice QoS (서비스 품질)** 상자의 값을 **46** 로 설정한 다음 **커밋을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83576-124">In the **Edit Device Configuration** dialog box, set the value of the **Voice Quality of Service (QoS)** box to **46** and then click **Commit**.</span></span>

<span data-ttu-id="83576-125">여러 컬렉션이 있는 경우 UC 전화 설정의 각 컬렉션에 대해이 프로세스를 반복 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83576-125">If you have multiple collections you will need to repeat this process for each collection of UC phone settings.</span></span> <span data-ttu-id="83576-126">Lync Server 제어판을 사용 하 여 여러 설정 모음을 동시에 수정할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="83576-126">Lync Server Control Panel will not allow you to simultaneously modify multiple setting collections.</span></span>

<span data-ttu-id="83576-127">조직의 Windows 운영 체제 (예: Iphone)를 기반으로 하지 않는 장치를 사용 하는 경우에는 VoiceDiffServTag 설정을 변경 해도 이러한 장치가 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83576-127">If you have devices that are not based on the Windows operating system (such as iPhones) in your organization these devices will not be affected by changing the VoiceDiffServTag setting.</span></span> <span data-ttu-id="83576-128">이러한 장치에서 DSCP 값을 변경 하려는 경우 각 디바이스 유형에 대 한 관리 매뉴얼을 참조 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83576-128">If you want to change DSCP values on those devices you will need to refer to the administration manual for each of your device types.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

