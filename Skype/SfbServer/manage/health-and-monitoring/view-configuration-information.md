---
title: 비즈니스용 Skype 서버에서 CDR 구성 정보 보기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
description: '요약: 비즈니스용 Skype 서버에서 CDR (통화 정보 기록)를 사용 하는 방법에 대해 알아보세요.'
ms.openlocfilehash: 976f61ac98cb02a0cd69750a581bfa5190156ff7
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991683"
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server"></a><span data-ttu-id="2f08f-103">비즈니스용 Skype 서버에서 CDR 구성 정보 보기</span><span class="sxs-lookup"><span data-stu-id="2f08f-103">View CDR configuration information in Skype for Business Server</span></span>
 
<span data-ttu-id="2f08f-104">**요약:** 비즈니스용 Skype 서버에서 CDR (통화 정보 기록)를 사용 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="2f08f-104">**Summary:** Learn how to use Call Detail Recording (CDR) in Skype for Business Server.</span></span>
  
<span data-ttu-id="2f08f-105">CDR (통화 정보 기록)를 사용 하면 피어 투 피어 인스턴트 메시지 세션, VoIP (Voice over 인터넷 프로토콜) 전화 통화, 회의 통화 등의 사용 현황을 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f08f-105">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls.</span></span> <span data-ttu-id="2f08f-106">이 사용 현황 데이터에는 누가 누구에 게, 그들이 통화 되었는지, 그리고 그에 얼마나 오랜 시간에 대 한 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f08f-106">This usage data includes information about who called whom, when they called, and how long they talked.</span></span>
  
<span data-ttu-id="2f08f-107">비즈니스용 Skype 서버를 설치 하면 사용자를 위해 CDR 구성 설정의 단일 전역 컬렉션이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="2f08f-107">When you install Skype for Business Server, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="2f08f-108">또한 관리자는 개별 사이트에 적용할 수 있는 사용자 지정 설정 모음을 만드는 옵션도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f08f-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="2f08f-109">비즈니스용 Skype Server 제어판 또는 [CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet을 사용 하 여 조직에서 사용 중인 CDR 구성 설정을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f08f-109">You can view the CDR configuration settings in use in your organization by using Skype for Business Server Control Panel or the [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="2f08f-110">비즈니스용 Skype Server 제어판을 사용 하 여 CDR 구성 정보를 보려면</span><span class="sxs-lookup"><span data-stu-id="2f08f-110">To view CDR configuration information by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="2f08f-111">비즈니스용 Skype 서버 제어판에서 **모니터링 및 보관**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f08f-111">In Skype for Business Server Control Panel click **Monitoring and Archiving**.</span></span>
    
2. <span data-ttu-id="2f08f-112">모든 CDR 구성 설정 목록은 **통화 정보 기록** 탭에 표시 됩니다. 각 설정 컬렉션에 대해 컬렉션 **이름이**표시 됩니다. CDR가 사용 하도록 설정 되었는지 여부 ( **cdr** 속성) ( **CDR 지우기** 속성)를 사용 하 여 제거 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f08f-112">A list of all your CDR configuration settings will be displayed in the **Call Detail Recording** tab; for each collection of settings you will see the collection **Name**; whether or not CDR has been enabled (the **CDR** property); and whether or not purging has been enabled (the **CDR purging** property).</span></span> <span data-ttu-id="2f08f-113">컬렉션에 대 한 자세한 정보를 보려면 모음을 두 번 클릭 하거나 해당 모음을 선택 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f08f-113">To see detailed information about a collection, double-click the collection, or select the appropriate collection, click **Edit**, and then click **Show Details**.</span></span> <span data-ttu-id="2f08f-114">한 번에 CDR 구성 설정의 단일 컬렉션에 대 한 자세한 정보만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f08f-114">Note that you can only view detailed information for a single collection of CDR configuration settings at a time.</span></span>
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2f08f-115">Windows PowerShell cmdlet을 사용 하 여 CDR 구성 정보 보기</span><span class="sxs-lookup"><span data-stu-id="2f08f-115">Viewing CDR configuration information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="2f08f-116">Windows PowerShell 및 CsCdrConfiguration cmdlet을 사용 하 여 CDR 구성 설정을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f08f-116">You can view CDR configuration settings by using Windows PowerShell and the Get-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="2f08f-117">이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f08f-117">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="2f08f-118">원격 Windows PowerShell을 사용 하 여 비즈니스용 Skype Server에 연결 하는 방법에 대 한 자세한 내용은 블로그 문서 ["빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"](https://go.microsoft.com/fwlink/p/?linkId=255876)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2f08f-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="2f08f-119">이 프로세스는 비즈니스용 Skype 서버에서 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f08f-119">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-cdr-configuration-information"></a><span data-ttu-id="2f08f-120">CDR 구성 정보를 보려면</span><span class="sxs-lookup"><span data-stu-id="2f08f-120">To view CDR configuration information</span></span>

- <span data-ttu-id="2f08f-121">모든 CDR 구성 설정에 대 한 정보를 보려면 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="2f08f-121">To view information about all your CDR configuration settings, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```PowerShell
  Get-CsCdrConfiguration
  ```

    <span data-ttu-id="2f08f-122">이는 다음과 같은 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f08f-122">That will return information similar to this:</span></span>
    
<pre>
Identity               : Global
EnableCDR              : True
EnablePurging          : True
KeepCallDetailForDays  : 90
KeepErrorReportForDays : 60
PurgeHourOfDay         : 2
</pre>

<span data-ttu-id="2f08f-123">자세한 내용은 Get-help cmdlet에 대 한 도움말 항목 [CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2f08f-123">For more information, see the help topic for the [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  

