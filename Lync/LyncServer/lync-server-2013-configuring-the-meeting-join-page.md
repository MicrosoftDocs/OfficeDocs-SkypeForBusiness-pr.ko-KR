---
title: 'Lync Server 2013: 모임 참가 페이지 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the meeting join page
ms:assetid: 45880423-47f4-49af-b825-cbd8e3fc1046
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204861(v=OCS.15)
ms:contentKeyID: 48184037
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8471b6b897a365763d55edcbd55e4a9bab4a3124
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734638"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-meeting-join-page-in-lync-server-2013"></a><span data-ttu-id="7dcc4-102">Lync Server 2013에서 모임 참가 페이지 구성</span><span class="sxs-lookup"><span data-stu-id="7dcc4-102">Configuring the meeting join page in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7dcc4-103">_**마지막으로 수정한 주제:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="7dcc4-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="7dcc4-104">사용자가 모임 요청에서 모임 링크를 클릭 하면 모임 참가 페이지에서 Lync 2013 클라이언트가 사용자의 컴퓨터에 이미 설치 되어 있는지 여부를 감지 합니다.</span><span class="sxs-lookup"><span data-stu-id="7dcc4-104">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Lync 2013 client is already installed on the user’s computer.</span></span> <span data-ttu-id="7dcc4-105">클라이언트가 이미 설치 된 경우에는 클라이언트가 모임을 열고 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7dcc4-105">If a client is already installed, the client opens and joins the meeting.</span></span> <span data-ttu-id="7dcc4-106">클라이언트가 설치 되어 있지 않으면 기본적으로 2013 버전의 Lync Web App이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="7dcc4-106">If a client is not installed, by default the 2013 version of Lync Web App opens.</span></span>

<span data-ttu-id="7dcc4-107">사용자가 Office Communicator 2007 R2 또는 Lync 2010 수행자와 모임에 참가할 수 있도록 허용 하려면 모임 참가 페이지의 동작을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7dcc4-107">You can modify the behavior of the meeting join page if you want to allow users to join meetings with Office Communicator 2007 R2 or Lync 2010 Attendant.</span></span> <span data-ttu-id="7dcc4-108">이러한 구성 옵션은 Lync Server 2013 제어판에서 제거 되었지만 CsWebServiceConfiguration cmdlet을 사용 하 여 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="7dcc4-108">These configuration options have been removed from the Lync Server 2013 Control Panel, but you configure them by using the Set-CsWebServiceConfiguration cmdlet.</span></span>

### <a name="meeting-join-page-set-cswebserviceconfiguration-parameters"></a><span data-ttu-id="7dcc4-109">모임 참가 페이지 집합-CsWebServiceConfiguration 매개 변수</span><span class="sxs-lookup"><span data-stu-id="7dcc4-109">Meeting Join Page Set-CsWebServiceConfiguration Parameters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7dcc4-110">Set-CsWebServiceConfiguration 매개 변수</span><span class="sxs-lookup"><span data-stu-id="7dcc4-110">Set-CsWebServiceConfiguration Parameter</span></span></th>
<th><span data-ttu-id="7dcc4-111">설명</span><span class="sxs-lookup"><span data-stu-id="7dcc4-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7dcc4-112">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="7dcc4-112">ShowJoinUsingLegacyClientLink</span></span></p></td>
<td><p><span data-ttu-id="7dcc4-113">True로 설정 되 면 Lync 이외의 클라이언트 응용 프로그램을 사용 하 여 모임에 참가 하는 사용자에 게 Office Communicator 2007 R2를 사용 하 여 모임에 참가할 수 있는 기회가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7dcc4-113">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting by using Office Communicator 2007 R2.</span></span> <span data-ttu-id="7dcc4-114">기본값은 False입니다.</span><span class="sxs-lookup"><span data-stu-id="7dcc4-114">The default value is False.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dcc4-115">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="7dcc4-115">ShowAlternateJoinOptionsExpanded</span></span></p></td>
<td><p><span data-ttu-id="7dcc4-116">True로 설정 하면 온라인 회의에 참가 하는 대체 옵션 (예: Office Communicator 2007 R2)이 자동으로 확장 되어 사용자에 게 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7dcc4-116">When set to True then alternate options for joining an online conference (such as Office Communicator 2007 R2) will automatically be expanded and shown to users.</span></span> <span data-ttu-id="7dcc4-117">False (기본값)로 설정 하는 경우 이러한 옵션을 사용할 수 있지만, 사용자는 자동으로 옵션 목록을 표시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7dcc4-117">When set to False (the default value) these options will be available, but the user will have to display the list of options for themselves.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a><span data-ttu-id="7dcc4-118">Lync Server 2013 관리 셸을 사용 하 여 모임 참가 페이지를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="7dcc4-118">To configure the meeting join page by using Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="7dcc4-119">Lync Server 2013 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync Server 2013**, **lync server Management Shell**을 차례로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7dcc4-119">Start the Lync Server 2013 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="7dcc4-120">웹 서비스 구성 설정을 보려면 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7dcc4-120">To view the web service configuration settings, run the following cmdlet:</span></span>
    
        Get-CsWebServiceConfiguration

3.  <span data-ttu-id="7dcc4-121">기본 설정에 따라 매개 변수를 True 또는 False로 설정 하 고 다음 명령을 실행 합니다 (이 cmdlet의 매개 변수에 대 한 자세한 내용은 Lync Server 2013 관리 셸 설명서의 [set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration) 참조).</span><span class="sxs-lookup"><span data-stu-id="7dcc4-121">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see [Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration) in the Lync Server 2013 Management Shell documentation):</span></span>
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7dcc4-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7dcc4-122">See Also</span></span>


[<span data-ttu-id="7dcc4-123">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="7dcc4-123">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

