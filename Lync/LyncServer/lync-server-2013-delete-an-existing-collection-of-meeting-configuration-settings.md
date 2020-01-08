---
title: 기존 모임 구성 설정 모음 삭제
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing collection of meeting configuration settings
ms:assetid: 92ff8a91-05c5-4047-a533-5dff12f22299
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688136(v=OCS.15)
ms:contentKeyID: 49733736
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10d564cf8fbcfb8c66df5e84841aae456913f1dc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979974"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-meeting-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="baab4-102">Lync Server 2013에서 모임 구성 설정의 기존 모음 삭제</span><span class="sxs-lookup"><span data-stu-id="baab4-102">Delete an existing collection of meeting configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="baab4-103">_**마지막으로 수정한 주제:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="baab4-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="baab4-104">사이트 또는 사용자 구성을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baab4-104">You can delete a site or user configuration.</span></span> <span data-ttu-id="baab4-105">전역 구성을 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="baab4-105">The global configuration cannot be removed.</span></span> <span data-ttu-id="baab4-106">전역 구성을 삭제 하면 자동으로 기본 값으로 다시 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="baab4-106">If you delete the global configuration, it is automatically reset to the default values.</span></span>

<div>

## <a name="to-delete-a-site-or-user-meeting-configuration"></a><span data-ttu-id="baab4-107">사이트 또는 사용자 모임 구성을 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="baab4-107">To delete a site or user meeting configuration</span></span>

1.  <span data-ttu-id="baab4-108">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="baab4-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="baab4-109">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="baab4-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="baab4-110">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="baab4-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="baab4-111">왼쪽 탐색 모음에서 **회의** 를 클릭 한 다음 **모임 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="baab4-111">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="baab4-112">모임 구성 목록에서 삭제 하려는 사이트 또는 풀 구성을 클릭 하 고 **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="baab4-112">In the list of meeting configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>

</div>

<div>

## <a name="removing-meeting-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="baab4-113">Windows PowerShell Cmdlet을 사용 하 여 모임 구성 설정 제거</span><span class="sxs-lookup"><span data-stu-id="baab4-113">Removing Meeting Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="baab4-114">Windows PowerShell 및 CsMeetingConfiguration cmdlet을 사용 하 여 모임 설정을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baab4-114">Meeting settings can be deleted by using Windows PowerShell and the Remove-CsMeetingConfiguration cmdlet.</span></span> <span data-ttu-id="baab4-115">이 cmdlet은 Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baab4-115">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="baab4-116">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="baab4-116">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-meeting-configuration-settings"></a><span data-ttu-id="baab4-117">지정 된 모임 구성 설정 모음을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="baab4-117">To remove a specified collection of meeting configuration settings</span></span>

  - <span data-ttu-id="baab4-118">이 명령은 Redmond 사이트에 적용 된 모임 구성 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="baab4-118">This command removes the meeting configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsMeetingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-meeting-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="baab4-119">사이트 범위에 적용 된 모든 모임 구성 설정을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="baab4-119">To remove all the meeting configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="baab4-120">이 명령은 사이트 범위에 적용 된 모든 모임 구성 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="baab4-120">This command removes all the meeting configuration settings applied to the site scope:</span></span>
    
        Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration

</div>

<div>

## <a name="to-remove-all-the-meeting-configuration-settings-that-admit-anonymous-users-by-default"></a><span data-ttu-id="baab4-121">익명 사용자를 기본적으로 허용 하는 모든 모임 구성 설정을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="baab4-121">To remove all the meeting configuration settings that admit anonymous users by default</span></span>

  - <span data-ttu-id="baab4-122">이 항목은 익명 사용자가 기본적으로 참석할 수 있도록 허용 하는 설정을 모두 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="baab4-122">And this one removes all the settings that allow anonymous users to be admitted by default:</span></span>
    
        Get-CsMeetingConfiguration | Where-Object {$_.AdmitAnonymousUsersByDefault -eq $True} | Remove-CsMeetingConfiguration

</div>

<span data-ttu-id="baab4-123">자세한 내용은 [제거 CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg412775(v=OCS.15)) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="baab4-123">For more information, see the help topic for the [Remove-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg412775(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

