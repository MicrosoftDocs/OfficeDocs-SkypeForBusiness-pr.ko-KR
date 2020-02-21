---
title: Microsoft Lync Phone Edition 장치의 서비스 품질 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Quality of Service on Microsoft Lync Phone Edition devices
ms:assetid: a6eb2620-a512-4ab6-bdfd-eb76be43bbfe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205137(v=OCS.15)
ms:contentKeyID: 48185004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e154df7c71b32e9f5f1c1440707511bc91c3117
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213115"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-on-microsoft-lync-phone-edition-devices-in-lync-server-2013"></a><span data-ttu-id="daf8b-102">Lync Server 2013에서 Microsoft Lync Phone Edition 장치에 대 한 서비스 품질 구성</span><span class="sxs-lookup"><span data-stu-id="daf8b-102">Configuring Quality of Service on Microsoft Lync Phone Edition devices in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="daf8b-103">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="daf8b-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="daf8b-104">QoS (서비스 품질)는 Iphone와 같은 장치에 대해 기본적으로 사용 하지 않도록 설정 되어 있지만 Lync Phone Edition을 실행 하는 장치에 대해 QoS가 기본적으로 사용 되도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="daf8b-104">Although Quality of Service (QoS) is not enabled by default for devices such as iPhones, QoS is enabled by default for devices running Lync Phone Edition.</span></span> <span data-ttu-id="daf8b-105">이러한 장치는 일반적으로 UC 또는 통합 통신 전화 라고 합니다. 이를 확인 하려면 Lync Server 관리 셸 내에서 다음 Windows PowerShell 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8b-105">(These devices are commonly referred to as UC or Unified Communication phones.) To verify this, run the following Windows PowerShell command from within the Lync Server Management Shell:</span></span>

    Get-CsUCPhoneConfiguration

<span data-ttu-id="daf8b-106">UC 전화 구성 설정을 변경하지 않은 경우 다음과 같은 정보가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="daf8b-106">If you have not made any changes to your UC phone configuration settings then you will get back information that looks like this:</span></span>

    Identity             : Global
    CalendarPollInterval : 00:03:00
    EnforcePhoneLock     : True
    PhoneLockTimeout     : 00:10:00
    MinPhonePinLength    : 6
    SIPSecurityMode      : High
    VoiceDiffServTag     : 40
    Voice8021p           : 0
    LoggingLevel         : Off

<span data-ttu-id="daf8b-107">QoS 용도로는 이러한 속성 중 VoiceDiffServTag 하나만 고려됩니다.</span><span class="sxs-lookup"><span data-stu-id="daf8b-107">For Quality of Service purposes, only one of these properties is of interest: VoiceDiffServTag.</span></span> <span data-ttu-id="daf8b-108">VoiceDiffServTag는 Lync Phone Edition 장치에서 음성 트래픽 emanating에 할당 된 DSCP 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="daf8b-108">The VoiceDiffServTag represents the DSCP value assigned to voice traffic emanating from a Lync Phone Edition device.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="daf8b-109">Voice8021p 매개 변수는 Lync Server 2013에서 더 이상 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="daf8b-109">The Voice8021p parameter is no longer supported in Lync Server 2013.</span></span> <span data-ttu-id="daf8b-110">이 매개 변수는 여전히 Microsoft Lync Server 2010와의 이전 버전과의 호환성을 위해 유효 합니다. 그러나 Lync Server 2013에서 사용 되는 장치에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="daf8b-110">The parameter is still valid for backward compatibility with Microsoft Lync Server 2010; however, it has no effect on devices used with Lync Server 2013.</span></span>



</div>

<span data-ttu-id="daf8b-111">대부분의 네트워크에서 Lync Phone Edition 패킷에 VoiceDiffServTag의 40를 표시 하면 문제가 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="daf8b-111">In most networks, marking Lync Phone Edition packets with a VoiceDiffServTag of 40 should not cause any problems.</span></span> <span data-ttu-id="daf8b-112">그러나 40은 일반적으로 오디오 트래픽에 사용 되는 값이 아닙니다. 대신, 오디오 트래픽은 거의 항상 DSCP 코드 46로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="daf8b-112">However, 40 is not the value typically used for audio traffic; instead, audio traffic is almost always marked with the DSCP code 46.</span></span> <span data-ttu-id="daf8b-113">네트워크 전체에서 일관성을 유지 관리 하기 위해 UC 전화의 VoiceDiffServTag 속성을 46로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daf8b-113">In order to maintain consistency throughout your network, you might want to change the VoiceDiffServTag property of your UC phones to 46.</span></span>

<span data-ttu-id="daf8b-114">이렇게 하려면 Windows PowerShell 또는 Lync Server 제어판을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daf8b-114">To do that, you can use either Windows PowerShell or the Lync Server Control Panel.</span></span> <span data-ttu-id="daf8b-115">Windows PowerShell을 사용 하 여 VoiceDiffServTag 값을 수정 하려면 Lync Server 관리 셸 내에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8b-115">To modify the VoiceDiffServTag value by using Windows PowerShell, run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

<span data-ttu-id="daf8b-p106">위의 명령은 UC 전화 구성 설정의 전역 컬렉션을 수정합니다. 그러나 UC 전화 설정을 사이트 범위에 할당할 수도 있습니다. 사이트 범위에서 UC 전화 구성 설정을 수정하려면 사이트 ID를 지정해야 합니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="daf8b-p106">The preceding command modifies the global collection of UC phone configuration settings. Note, however, that UC phone settings can also be assigned to the site scope. To modify UC phone configuration settings at the site scope, you must specify the site Identity. For example:</span></span>

    Set-CsUCPhoneConfiguration -Identity "site:Redmond" -VoiceDiffServTag 46

<span data-ttu-id="daf8b-120">또한 다음 명령을 사용하여 모든 UC 전화 구성 설정을 동시에 수정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daf8b-120">You can also use the following command to simultaneously modify all your UC phone configuration settings:</span></span>

    Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

<span data-ttu-id="daf8b-121">Lync Server 제어판을 사용 하 여이 변경 작업을 수행 하려면 제어판을 시작 하 고 다음 절차를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8b-121">If you prefer to make this change using Lync Server Control Panel, then start the Control Panel and then complete the following procedure:</span></span>

1.  <span data-ttu-id="daf8b-122">**클라이언트**를 클릭하고 **장치 구성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8b-122">Click **Clients** and then click **Device Configuration**.</span></span>

2.  <span data-ttu-id="daf8b-123">**장치 구성** 탭에서 수정할 설정 컬렉션(예: **전역**)을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8b-123">On the **Device Configuration** tab, double-click the collection of settings you want to modify (for example, **Global**).</span></span>

3.  <span data-ttu-id="daf8b-124">**장치 구성 편집** 대화 상자에서 **음성 QoS(Quality of Service)** 상자의 값을 **46**으로 설정한 다음 **커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8b-124">In the **Edit Device Configuration** dialog box, set the value of the **Voice Quality of Service (QoS)** box to **46** and then click **Commit**.</span></span>

<span data-ttu-id="daf8b-125">여러 컬렉션이 있는 경우 각 UC 전화 설정 컬렉션에 대해 이 프로세스를 반복해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8b-125">If you have multiple collections you will need to repeat this process for each collection of UC phone settings.</span></span> <span data-ttu-id="daf8b-126">Lync Server 제어판에서는 여러 설정 모음을 동시에 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="daf8b-126">Lync Server Control Panel will not allow you to simultaneously modify multiple setting collections.</span></span>

<span data-ttu-id="daf8b-p108">Windows 운영 체제 기반이 아닌 장치(예: iPhone)가 조직에 있는 경우 이러한 장치는 VoiceDiffServTag 설정 변경의 영향을 받지 않습니다. 이러한 장치에서 DSCP 값을 변경하려면 각 장치 유형에 대한 관리 설명서를 참조해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8b-p108">If you have devices that are not based on the Windows operating system (such as iPhones) in your organization these devices will not be affected by changing the VoiceDiffServTag setting. If you want to change DSCP values on those devices you will need to refer to the administration manual for each of your device types.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

