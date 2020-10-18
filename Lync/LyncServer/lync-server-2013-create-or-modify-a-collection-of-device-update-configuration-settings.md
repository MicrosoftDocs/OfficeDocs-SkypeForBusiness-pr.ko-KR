---
title: 장치 업데이트 구성 설정 모음 만들기 또는 수정
description: 장치 업데이트 구성 설정 모음을 만들거나 수정 합니다.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of Device Update configuration settings
ms:assetid: 3e8ce95f-a8c8-417c-b1f7-0f759a567aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994029(v=OCS.15)
ms:contentKeyID: 51803938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 593a1a0cb0f68254748ee48440cda18c78989780
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578274"
---
# <a name="create-or-modify-a-collection-of-device-update-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="d0b13-103">Lync Server 2013에서 장치 업데이트 구성 설정 모음 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="d0b13-103">Create or modify a collection of Device Update configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0b13-104">_**마지막으로 수정 된 항목:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="d0b13-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="d0b13-105">Windows PowerShell 및 **new-csdeviceupdateconfiguration** cmdlet을 사용 하 고 **new-csdeviceupdateconfiguration** cmdlet을 사용 하 여 수정한 후에는 장치 업데이트 구성 설정을 만들 수 있습니다 (사이트 범위에만 해당).</span><span class="sxs-lookup"><span data-stu-id="d0b13-105">Device update configuration settings can be created (at the site scope only) by using Windows PowerShell and the **New-CsDeviceUpdateConfiguration** cmdlet and modified by using the **Set-CsDeviceUpdateConfiguration** cmdlet.</span></span> <span data-ttu-id="d0b13-106">이러한 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0b13-106">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="d0b13-107">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> 하세요.</span><span class="sxs-lookup"><span data-stu-id="d0b13-107">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="to-create-device-update-configuration-settings-that-use-the-default-values"></a><span data-ttu-id="d0b13-108">기본 값을 사용 하는 장치 업데이트 구성 설정을 만들려면</span><span class="sxs-lookup"><span data-stu-id="d0b13-108">To create device update configuration settings that use the default values</span></span>

  - <span data-ttu-id="d0b13-109">이 명령은 Redmond 사이트에 대 한 새 장치 업데이트 구성 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d0b13-109">This command creates a new set of device update configuration settings for the Redmond site:</span></span>
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond"
    
    <span data-ttu-id="d0b13-110">이전 명령에서 필수 Identity 매개 변수 이외의 매개 변수를 지정 하지 않았으므로 구성 설정의 새 컬렉션은 모든 속성에 대해 기본값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b13-110">Because no parameters other than the mandatory Identity parameter were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-device-update-configuration-settings"></a><span data-ttu-id="d0b13-111">장치 업데이트 구성 설정을 만들 때 단일 속성 값을 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="d0b13-111">To change a single property value when creating device update configuration settings</span></span>

  - <span data-ttu-id="d0b13-112">다른 속성 값을 사용하는 설정을 만들려면 간단히 적합한 매개 변수와 매개 변수 값을 포함하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0b13-112">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="d0b13-113">예를 들어 기본적으로 이전 로그 파일을 21 일 마다 삭제 하는 장치 업데이트 구성 설정 컬렉션을 만들려면 다음과 같은 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b13-113">For example, to create a collection of device update configuration settings that, by default, deletes old log files every 21 days, use a command like this one:</span></span>
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-device-update-configuration-settings"></a><span data-ttu-id="d0b13-114">장치 업데이트 구성 설정을 만들 때 여러 속성 값을 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="d0b13-114">To change multiple property values when creating device update configuration settings</span></span>

  - <span data-ttu-id="d0b13-115">여러 매개 변수를 포함하여 여러 속성 값을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0b13-115">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="d0b13-116">예를 들어이 명령은 로그 정리 간격을 21 일로, 로그 플러시 간격을 30 분으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b13-116">For example, this command sets the log cleanup interval to 21 days and the log flush interval to 30 minutes:</span></span>
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00" -LogFlushInterval "00:30:00"

</div>

<span data-ttu-id="d0b13-117">기존 장치 구성 설정을 수정 하는 방법에 대 한 자세한 내용은 [new-csdeviceupdateconfiguration](https://technet.microsoft.com/library/Gg398320(v=OCS.15)) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d0b13-117">For details about modifying existing device configuration settings, see the Help topic for the [Set-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg398320(v=OCS.15)) cmdlet.</span></span> <span data-ttu-id="d0b13-118">구성 설정 모음을 만드는 방법에 대 한 자세한 내용은 [new-csdeviceupdateconfiguration](https://technet.microsoft.com/library/Gg425761(v=OCS.15)) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d0b13-118">For details about creating collections of configuration settings, see the Help topic for the [New-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425761(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

