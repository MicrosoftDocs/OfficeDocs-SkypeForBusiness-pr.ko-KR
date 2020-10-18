---
title: 'Lync Server 2013: 기존 CDR 구성 설정 모음 삭제'
description: 'Lync Server 2013: 기존 CDR 구성 설정 컬렉션을 삭제 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of CDR configuration settings
ms:assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688128(v=OCS.15)
ms:contentKeyID: 49733726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e80f6d9e9d878dad258e494095b10c402029932b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572894"
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="b5321-103">Lync Server 2013에서 기존 CDR 구성 설정 모음 삭제</span><span class="sxs-lookup"><span data-stu-id="b5321-103">Delete an existing collection of CDR configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5321-104">_**마지막으로 수정 된 항목:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="b5321-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="b5321-p101">CDR(통화 정보 기록)을 사용하면 피어 투 피어 인스턴트 메시징 세션, VoIP(Voice over Internet Protocol) 전화 통화, 전화 회의 통화 등의 사용 현황을 추적할 수 있습니다. 이러한 사용 내역 데이터에는 누가 누구에게 전화를 걸었는지, 언제 전화를 걸었는지 및 얼마나 오래 통화했는지에 대한 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5321-p101">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>

<span data-ttu-id="b5321-107">Microsoft Lync Server 2013을 설치 하면 CDR 구성 설정의 단일 전역 모음이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="b5321-107">When you install Microsoft Lync Server 2013, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="b5321-108">관리자는 또한 개별 사이트에 적용할 수 있는 사용자 지정 설정 컬렉션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5321-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="b5321-109">사이트 범위에서 구성된 설정은 기본적으로 전역 범위에서 구성된 설정보다 우선 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5321-109">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="b5321-110">사이트 범위 설정을 삭제할 경우 해당 사이트에서 전역 설정을 사용하여 CDR이 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5321-110">If you delete site-scoped settings, then CDR will be managed in that site by using the global settings.</span></span>

<span data-ttu-id="b5321-p103">또한 전역 설정도 "삭제"할 수 있습니다. 하지만 전역 설정이 실제로 제거되지는 않습니다. 대신 해당 컬렉션의 모든 속성이 기본값으로 다시 설정됩니다. 예를 들어, CDR 구성 설정의 컬렉션에서는 기본적으로 삭제를 사용할 수 있도록 설정되어 있습니다. 삭제를 사용하지 않도록 전역 컬렉션을 수정한다고 가정해보겠습니다. 나중에 전역 설정을 삭제하면 모든 속성이 해당 기본값으로 다시 설정됩니다. 따라서 이 경우에는 삭제를 다시 사용할 수 있도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5321-p103">Note that you can also “delete” the global settings. However, the global settings will not actually be removed. Instead, all the properties in that collection will be reset to their default values. For example, by default purging is enabled in a collection of CDR configuration settings. Suppose you modify the global collection so that purging is disabled. If you later delete the global settings, all the properties will be reset to their default values. In this case, that means that purging will once again be enabled.</span></span>

<span data-ttu-id="b5321-118">Lync Server 제어판 또는 [get-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) cmdlet을 사용 하 여 CDR 구성 설정을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5321-118">You can remove CDR configuration settings by using the Lync Server Control Panel or the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) cmdlet.</span></span>

<div>

## <a name="to-remove-cdr-configuration-settings-with-lync-server-control-panel"></a><span data-ttu-id="b5321-119">Lync Server 제어판에서 CDR 구성 설정을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="b5321-119">To remove CDR configuration settings with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="b5321-120">Lync Server 제어판에서 **모니터링 및 보관**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5321-120">In Lync Server Control Panel, click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="b5321-p104">**통화 정보 기록** 탭에서 제거하려는 CDR 설정의 컬렉션을 선택합니다. 여러 컬렉션을 선택하려면 첫 번째 컬렉션을 클릭하고 Ctrl 키를 누른 상태로 추가 컬렉션을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b5321-p104">On the **Call Detail Recording** tab, select the collection (or collections) of CDR settings to be removed. To select multiple collections, click the first collection, hold down the Ctrl key, and click additional collections.</span></span>

3.  <span data-ttu-id="b5321-123">**편집**을 클릭한 다음 **삭제**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b5321-123">Click **Edit**, and then click **Delete**.</span></span>

4.  <span data-ttu-id="b5321-124">Lync Server 제어판 대화 상자에서 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5321-124">In the Lync Server Control Panel dialog box, click **OK**.</span></span>

</div>

<div>

## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b5321-125">Windows PowerShell Cmdlet을 사용 하 여 CDR 구성 설정 제거</span><span class="sxs-lookup"><span data-stu-id="b5321-125">Removing CDR Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b5321-126">Windows PowerShell 및 **get-cscdrconfiguration** cmdlet을 사용 하 여 통화 정보 기록 구성 설정을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5321-126">You can delete call detail recording configuration settings by using Windows PowerShell and the **Remove-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="b5321-127">Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5321-127">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b5321-128">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 하세요.</span><span class="sxs-lookup"><span data-stu-id="b5321-128">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a><span data-ttu-id="b5321-129">CDR 구성 설정의 지정된 컬렉션을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="b5321-129">To remove a specified collection of CDR configuration settings</span></span>

  - <span data-ttu-id="b5321-130">이 명령은 Redmond 사이트에 적용된 CDR 구성 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="b5321-130">This command removes the CDR configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="b5321-131">사이트 범위에 적용 된 모든 CDR 구성 설정을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="b5321-131">To remove all the CDR configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="b5321-132">이 명령은 사이트 범위에 적용된 모든 CDR 구성 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="b5321-132">This command removes all the CDR configuration settings applied to the site scope:</span></span>
    
        Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-that-disable-call-detail-recording"></a><span data-ttu-id="b5321-133">통화 정보 기록을 사용하지 않도록 설정하는 모든 CDR 구성 설정을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="b5321-133">To remove all the CDR configuration settings that disable call detail recording</span></span>

  - <span data-ttu-id="b5321-134">이 명령은 통화 정보 기록이 사용하지 않도록 설정된 모든 CDR 구성 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="b5321-134">This command removes all the CDR configuration settings where Call Detail recording has been disabled:</span></span>
    
        Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration

</div>

<span data-ttu-id="b5321-135">자세한 내용은 [get-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b5321-135">For more information, see the help topic for the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

