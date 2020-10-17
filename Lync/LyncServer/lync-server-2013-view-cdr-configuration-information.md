---
title: 'Lync Server 2013: CDR 구성 정보 보기'
description: 'Lync Server 2013: CDR 구성 정보를 확인 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View CDR configuration information
ms:assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688096(v=OCS.15)
ms:contentKeyID: 49733695
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 687ee05701c022e1d7ecfe2cd8be5190949c51d0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551314"
---
# <a name="view-cdr-configuration-information-in-lync-server-2013"></a><span data-ttu-id="e0844-103">Lync Server 2013에서 CDR 구성 정보 보기</span><span class="sxs-lookup"><span data-stu-id="e0844-103">View CDR configuration information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0844-104">_**마지막으로 수정 된 항목:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="e0844-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="e0844-p101">CDR(통화 정보 기록)을 사용하면 피어 투 피어 인스턴트 메시징 세션, VoIP(Voice over Internet Protocol) 전화 통화, 전화 회의 통화 등의 사용 현황을 추적할 수 있습니다. 이러한 사용 내역 데이터에는 누가 누구에게 전화를 걸었는지, 언제 전화를 걸었는지 및 얼마나 오래 통화했는지에 대한 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0844-p101">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>

<span data-ttu-id="e0844-107">Microsoft Lync Server 2013을 설치 하면 CDR 구성 설정의 단일 전역 모음이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="e0844-107">When you install Microsoft Lync Server 2013, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="e0844-108">관리자는 또한 개별 사이트에 적용할 수 있는 사용자 지정 설정 컬렉션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0844-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="e0844-109">Lync Server 제어판 또는 [get-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) cmdlet을 사용 하 여 조직에서 사용 중인 CDR 구성 설정을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0844-109">You can view the CDR configuration settings in use in your organization by using Lync Server Control Panel or the [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) cmdlet.</span></span>

<div>

## <a name="to-view-cdr-configuration-information-by-using-lync-server-control-panel"></a><span data-ttu-id="e0844-110">Lync Server 제어판을 사용 하 여 CDR 구성 정보를 보려면</span><span class="sxs-lookup"><span data-stu-id="e0844-110">To view CDR configuration information by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="e0844-111">Lync Server 제어판에서 **모니터링 및 보관**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0844-111">In Lync Server Control Panel click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="e0844-p103">모든 CDR 구성 설정에 대한 목록은 **통화 정보 기록** 탭에 표시됩니다. 설정의 각 컬렉션에 대해 컬렉션 **이름**이 표시되고, CDR이 설정되었는지 여부(**CDR** 속성), 삭제가 설정되었는지 여부(**CDR 삭제** 속성)가 표시됩니다. 컬렉션에 대한 자세한 내용을 보려면 해당 컬렉션을 두 번 클릭하거나 적합한 컬렉션을 선택하고, **편집**을 클릭한 후 **세부 정보 표시**를 클릭합니다. CDR 구성 설정은 한 번에 하나의 단일 컬렉션에 대한 자세한 정보만 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0844-p103">A list of all your CDR configuration settings will be displayed in the **Call Detail Recording** tab; for each collection of settings you will see the collection **Name**; whether or not CDR has been enabled (the **CDR** property); and whether or not purging has been enabled (the **CDR purging** property). To see detailed information about a collection, double-click the collection, or select the appropriate collection, click **Edit**, and then click **Show Details**. Note that you can only view detailed information for a single collection of CDR configuration settings at a time.</span></span>

</div>

<div>

## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e0844-115">Windows PowerShell Cmdlet을 사용 하 여 CDR 구성 정보 보기</span><span class="sxs-lookup"><span data-stu-id="e0844-115">Viewing CDR Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e0844-116">Windows PowerShell 및 Get-CsCdrConfiguration cmdlet을 사용 하 여 CDR 구성 설정을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0844-116">You can view CDR configuration settings by using Windows PowerShell and the Get-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="e0844-117">Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0844-117">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e0844-118">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 하세요.</span><span class="sxs-lookup"><span data-stu-id="e0844-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-cdr-configuration-information"></a><span data-ttu-id="e0844-119">CDR 구성 정보를 보려면</span><span class="sxs-lookup"><span data-stu-id="e0844-119">To view CDR configuration information</span></span>

  - <span data-ttu-id="e0844-120">모든 CDR 구성 설정에 대 한 정보를 보려면 Lync Server 관리 셸에서 다음 명령을 입력 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="e0844-120">To view information about all your CDR configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsCdrConfiguration
    
    <span data-ttu-id="e0844-121">그러면 다음과 같은 정보가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0844-121">That will return information similar to this:</span></span>
    
        Identity               : Global
        EnableCDR              : True
        EnablePurging          : True
        KeepCallDetailForDays  : 90
        KeepErrorReportForDays : 60
        PurgeHourOfDay         : 2

</div>

<span data-ttu-id="e0844-122">자세한 내용은 [get-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e0844-122">For more information, see the help topic for the [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

