---
title: 'Lync Server 2013: CDR 구성 정보 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View CDR configuration information
ms:assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688096(v=OCS.15)
ms:contentKeyID: 49733695
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: baa03ab1ce52c98746657c0314760c902f295589
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985137"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-cdr-configuration-information-in-lync-server-2013"></a><span data-ttu-id="d8b11-102">Lync Server 2013에서 CDR 구성 정보 보기</span><span class="sxs-lookup"><span data-stu-id="d8b11-102">View CDR configuration information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8b11-103">_**마지막으로 수정한 주제:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="d8b11-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="d8b11-104">CDR (통화 정보 기록)를 사용 하면 피어 투 피어 인스턴트 메시지 세션, VoIP (Voice over 인터넷 프로토콜) 전화 통화, 회의 통화 등의 사용 현황을 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8b11-104">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls.</span></span> <span data-ttu-id="d8b11-105">이 사용 현황 데이터에는 누가 누구에 게, 그들이 통화 되었는지, 그리고 그에 얼마나 오랜 시간에 대 한 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8b11-105">This usage data includes information about who called whom, when they called, and how long they talked.</span></span>

<span data-ttu-id="d8b11-106">Microsoft Lync Server 2013을 설치 하면 사용자를 위해 CDR 구성 설정의 단일 전역 컬렉션이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="d8b11-106">When you install Microsoft Lync Server 2013, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="d8b11-107">또한 관리자는 개별 사이트에 적용할 수 있는 사용자 지정 설정 모음을 만드는 옵션도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8b11-107">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="d8b11-108">Lync Server 제어판 또는 [CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) cmdlet을 사용 하 여 조직에서 사용 중인 CDR 구성 설정을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8b11-108">You can view the CDR configuration settings in use in your organization by using Lync Server Control Panel or the [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) cmdlet.</span></span>

<div>

## <a name="to-view-cdr-configuration-information-by-using-lync-server-control-panel"></a><span data-ttu-id="d8b11-109">Lync Server 제어판을 사용 하 여 CDR 구성 정보를 보려면</span><span class="sxs-lookup"><span data-stu-id="d8b11-109">To view CDR configuration information by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="d8b11-110">Lync Server 제어판에서 **모니터링 및 보관**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b11-110">In Lync Server Control Panel click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="d8b11-111">모든 CDR 구성 설정 목록은 **통화 정보 기록** 탭에 표시 됩니다. 각 설정 컬렉션에 대해 컬렉션 **이름이**표시 됩니다. CDR가 사용 하도록 설정 되었는지 여부 ( **cdr** 속성) ( **CDR 지우기** 속성)를 사용 하 여 제거 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b11-111">A list of all your CDR configuration settings will be displayed in the **Call Detail Recording** tab; for each collection of settings you will see the collection **Name**; whether or not CDR has been enabled (the **CDR** property); and whether or not purging has been enabled (the **CDR purging** property).</span></span> <span data-ttu-id="d8b11-112">컬렉션에 대 한 자세한 정보를 보려면 모음을 두 번 클릭 하거나 해당 모음을 선택 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b11-112">To see detailed information about a collection, double-click the collection, or select the appropriate collection, click **Edit**, and then click **Show Details**.</span></span> <span data-ttu-id="d8b11-113">한 번에 CDR 구성 설정의 단일 컬렉션에 대 한 자세한 정보만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8b11-113">Note that you can only view detailed information for a single collection of CDR configuration settings at a time.</span></span>

</div>

<div>

## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d8b11-114">Windows PowerShell Cmdlet을 사용 하 여 CDR 구성 정보 보기</span><span class="sxs-lookup"><span data-stu-id="d8b11-114">Viewing CDR Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d8b11-115">Windows PowerShell 및 CsCdrConfiguration cmdlet을 사용 하 여 CDR 구성 설정을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8b11-115">You can view CDR configuration settings by using Windows PowerShell and the Get-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="d8b11-116">Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8b11-116">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d8b11-117">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d8b11-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-cdr-configuration-information"></a><span data-ttu-id="d8b11-118">CDR 구성 정보를 보려면</span><span class="sxs-lookup"><span data-stu-id="d8b11-118">To view CDR configuration information</span></span>

  - <span data-ttu-id="d8b11-119">모든 CDR 구성 설정에 대 한 정보를 보려면 Lync Server 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="d8b11-119">To view information about all your CDR configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsCdrConfiguration
    
    <span data-ttu-id="d8b11-120">이는 다음과 같은 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b11-120">That will return information similar to this:</span></span>
    
        Identity               : Global
        EnableCDR              : True
        EnablePurging          : True
        KeepCallDetailForDays  : 90
        KeepErrorReportForDays : 60
        PurgeHourOfDay         : 2

</div>

<span data-ttu-id="d8b11-121">자세한 내용은 Get-help cmdlet에 대 한 도움말 항목 [CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d8b11-121">For more information, see the help topic for the [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

