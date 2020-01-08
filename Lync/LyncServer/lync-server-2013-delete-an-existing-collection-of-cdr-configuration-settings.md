---
title: 'Lync Server 2013: 기존 CDR 구성 설정 모음 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing collection of CDR configuration settings
ms:assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688128(v=OCS.15)
ms:contentKeyID: 49733726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28d15f224d7e3aa4b43b20925a4efd4007a0c6c3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983587"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="23e4f-102">Lync Server 2013에서 기존 CDR 구성 설정 모음 삭제</span><span class="sxs-lookup"><span data-stu-id="23e4f-102">Delete an existing collection of CDR configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23e4f-103">_**마지막으로 수정한 주제:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="23e4f-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="23e4f-104">CDR (통화 정보 기록)를 사용 하면 피어 투 피어 인스턴트 메시지 세션, VoIP (Voice over 인터넷 프로토콜) 전화 통화, 회의 통화 등의 사용 현황을 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23e4f-104">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls.</span></span> <span data-ttu-id="23e4f-105">이 사용 현황 데이터에는 누가 누구에 게, 그들이 통화 되었는지, 그리고 그에 얼마나 오랜 시간에 대 한 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23e4f-105">This usage data includes information about who called whom, when they called, and how long they talked.</span></span>

<span data-ttu-id="23e4f-106">Microsoft Lync Server 2013을 설치 하면 사용자를 위해 CDR 구성 설정의 단일 전역 컬렉션이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="23e4f-106">When you install Microsoft Lync Server 2013, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="23e4f-107">또한 관리자는 개별 사이트에 적용할 수 있는 사용자 지정 설정 모음을 만드는 옵션도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23e4f-107">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="23e4f-108">사이트 범위에서 구성 된 설정은 전역 범위에서 구성 된 설정 보다 우선 하므로 디자인에 따라 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23e4f-108">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="23e4f-109">사이트 범위 설정을 삭제 하는 경우에는 전역 설정을 사용 하 여 해당 사이트에서 CDR가 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23e4f-109">If you delete site-scoped settings, then CDR will be managed in that site by using the global settings.</span></span>

<span data-ttu-id="23e4f-110">전역 설정을 "삭제" 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23e4f-110">Note that you can also “delete” the global settings.</span></span> <span data-ttu-id="23e4f-111">그러나 전역 설정은 실제로 제거 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="23e4f-111">However, the global settings will not actually be removed.</span></span> <span data-ttu-id="23e4f-112">대신 해당 컬렉션의 모든 속성이 기본값으로 다시 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23e4f-112">Instead, all the properties in that collection will be reset to their default values.</span></span> <span data-ttu-id="23e4f-113">예를 들어, CDR 구성 설정 컬렉션에서 기본적으로 제거를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23e4f-113">For example, by default purging is enabled in a collection of CDR configuration settings.</span></span> <span data-ttu-id="23e4f-114">제거를 사용할 수 없도록 전역 컬렉션을 수정 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="23e4f-114">Suppose you modify the global collection so that purging is disabled.</span></span> <span data-ttu-id="23e4f-115">나중에 전역 설정을 삭제 하면 모든 속성이 기본값으로 다시 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23e4f-115">If you later delete the global settings, all the properties will be reset to their default values.</span></span> <span data-ttu-id="23e4f-116">이 경우 제거를 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23e4f-116">In this case, that means that purging will once again be enabled.</span></span>

<span data-ttu-id="23e4f-117">Lync Server 제어판 또는 [CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) cmdlet을 사용 하 여 CDR 구성 설정을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23e4f-117">You can remove CDR configuration settings by using the Lync Server Control Panel or the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) cmdlet.</span></span>

<div>

## <a name="to-remove-cdr-configuration-settings-with-lync-server-control-panel"></a><span data-ttu-id="23e4f-118">Lync Server 제어판에서 CDR 구성 설정을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="23e4f-118">To remove CDR configuration settings with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="23e4f-119">Lync Server 제어판에서 **모니터링 및 보관**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="23e4f-119">In Lync Server Control Panel, click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="23e4f-120">**통화 정보 기록** 탭에서 제거할 CDR 설정 모음 (또는 컬렉션)을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="23e4f-120">On the **Call Detail Recording** tab, select the collection (or collections) of CDR settings to be removed.</span></span> <span data-ttu-id="23e4f-121">여러 컬렉션을 선택 하려면 첫 번째 컬렉션을 클릭 하 고 Ctrl 키를 누른 상태에서 추가 모음을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="23e4f-121">To select multiple collections, click the first collection, hold down the Ctrl key, and click additional collections.</span></span>

3.  <span data-ttu-id="23e4f-122">**편집**을 클릭 한 다음 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="23e4f-122">Click **Edit**, and then click **Delete**.</span></span>

4.  <span data-ttu-id="23e4f-123">Lync Server 제어판 대화 상자에서 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="23e4f-123">In the Lync Server Control Panel dialog box, click **OK**.</span></span>

</div>

<div>

## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="23e4f-124">Windows PowerShell Cmdlet을 사용 하 여 CDR 구성 설정 제거</span><span class="sxs-lookup"><span data-stu-id="23e4f-124">Removing CDR Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="23e4f-125">Windows PowerShell 및 **CsCdrConfiguration** cmdlet을 사용 하 여 통화 정보 기록 구성 설정을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23e4f-125">You can delete call detail recording configuration settings by using Windows PowerShell and the **Remove-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="23e4f-126">Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23e4f-126">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="23e4f-127">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="23e4f-127">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a><span data-ttu-id="23e4f-128">지정 된 CDR 구성 설정 모음을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="23e4f-128">To remove a specified collection of CDR configuration settings</span></span>

  - <span data-ttu-id="23e4f-129">이 명령은 Redmond 사이트에 적용 된 CDR 구성 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="23e4f-129">This command removes the CDR configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="23e4f-130">사이트 범위에 적용 된 모든 CDR 구성 설정을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="23e4f-130">To remove all the CDR configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="23e4f-131">이 명령은 사이트 범위에 적용 된 모든 CDR 구성 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="23e4f-131">This command removes all the CDR configuration settings applied to the site scope:</span></span>
    
        Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-that-disable-call-detail-recording"></a><span data-ttu-id="23e4f-132">통화 정보 기록을 사용 하지 않도록 설정 하는 모든 CDR 구성 설정을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="23e4f-132">To remove all the CDR configuration settings that disable call detail recording</span></span>

  - <span data-ttu-id="23e4f-133">이 명령은 통화 세부 기록이 비활성화 된 모든 CDR 구성 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="23e4f-133">This command removes all the CDR configuration settings where Call Detail recording has been disabled:</span></span>
    
        Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration

</div>

<span data-ttu-id="23e4f-134">자세한 내용은 [제거 CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="23e4f-134">For more information, see the help topic for the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

