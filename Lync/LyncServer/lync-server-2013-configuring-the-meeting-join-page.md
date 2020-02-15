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
ms.openlocfilehash: a62ac96688887e9d5ee66f0f0439a73941db3563
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030982"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-meeting-join-page-in-lync-server-2013"></a><span data-ttu-id="47a79-102">Lync Server 2013에서 모임 참가 페이지 구성</span><span class="sxs-lookup"><span data-stu-id="47a79-102">Configuring the meeting join page in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47a79-103">_**마지막으로 수정 된 항목:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="47a79-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="47a79-104">사용자가 모임 요청에서 모임 링크를 클릭 하면 모임 참가 페이지에서 Lync 2013 클라이언트가 사용자 컴퓨터에 이미 설치 되어 있는지 여부를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="47a79-104">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Lync 2013 client is already installed on the user’s computer.</span></span> <span data-ttu-id="47a79-105">클라이언트가 이미 설치된 경우 클라이언트가 열리고 모임에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="47a79-105">If a client is already installed, the client opens and joins the meeting.</span></span> <span data-ttu-id="47a79-106">클라이언트가 설치 되어 있지 않으면 기본적으로 2013 버전의 Lync Web App이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="47a79-106">If a client is not installed, by default the 2013 version of Lync Web App opens.</span></span>

<span data-ttu-id="47a79-107">사용자가 Office Communicator 2007 R2 또는 Lync 2010 Attendant와 모임에 참가할 수 있도록 허용 하려는 경우에는 모임 참가 페이지의 동작을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47a79-107">You can modify the behavior of the meeting join page if you want to allow users to join meetings with Office Communicator 2007 R2 or Lync 2010 Attendant.</span></span> <span data-ttu-id="47a79-108">이러한 구성 옵션은 Lync Server 2013 제어판에서 제거 되었지만 Set-cswebserviceconfiguration cmdlet을 사용 하 여 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="47a79-108">These configuration options have been removed from the Lync Server 2013 Control Panel, but you configure them by using the Set-CsWebServiceConfiguration cmdlet.</span></span>

### <a name="meeting-join-page-set-cswebserviceconfiguration-parameters"></a><span data-ttu-id="47a79-109">모임 참가 페이지 Set-CsWebServiceConfiguration 매개 변수</span><span class="sxs-lookup"><span data-stu-id="47a79-109">Meeting Join Page Set-CsWebServiceConfiguration Parameters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="47a79-110">Set-CsWebServiceConfiguration 매개 변수</span><span class="sxs-lookup"><span data-stu-id="47a79-110">Set-CsWebServiceConfiguration Parameter</span></span></th>
<th><span data-ttu-id="47a79-111">설명</span><span class="sxs-lookup"><span data-stu-id="47a79-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="47a79-112">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="47a79-112">ShowJoinUsingLegacyClientLink</span></span></p></td>
<td><p><span data-ttu-id="47a79-113">True로 설정 하면 Lync 이외의 클라이언트 응용 프로그램을 사용 하 여 모임에 참가 하는 사용자에 게 Office Communicator 2007 R2를 사용 하 여 모임에 참가할 수 있는 기회가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47a79-113">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting by using Office Communicator 2007 R2.</span></span> <span data-ttu-id="47a79-114">기본값은 False입니다.</span><span class="sxs-lookup"><span data-stu-id="47a79-114">The default value is False.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47a79-115">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="47a79-115">ShowAlternateJoinOptionsExpanded</span></span></p></td>
<td><p><span data-ttu-id="47a79-p104">True로 설정하면 Office Communicator 2007 R2 등 온라인 전화 회의 참가를 위한 대체 옵션이 자동으로 확장되어 사용자에게 표시됩니다. 기본값인 False로 설정하면 해당 옵션을 사용할 수는 있지만 사용자가 옵션 목록을 직접 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47a79-p104">When set to True then alternate options for joining an online conference (such as Office Communicator 2007 R2) will automatically be expanded and shown to users. When set to False (the default value) these options will be available, but the user will have to display the list of options for themselves.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a><span data-ttu-id="47a79-118">Lync Server 2013 관리 셸을 사용 하 여 모임 참가 페이지를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="47a79-118">To configure the meeting join page by using Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="47a79-119">Lync Server 2013 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **lync server 관리 셸을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="47a79-119">Start the Lync Server 2013 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="47a79-120">웹 서비스 구성 설정을 보려면 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="47a79-120">To view the web service configuration settings, run the following cmdlet:</span></span>
    
        Get-CsWebServiceConfiguration

3.  <span data-ttu-id="47a79-121">이 cmdlet의 매개 변수에 대 한 자세한 내용은 기본 설정에 따라 매개 변수를 True 또는 False로 설정 하 여 다음 명령을 실행 합니다 (Lync Server 2013 관리 셸 설명서의 [set-cswebserviceconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration) 참조).</span><span class="sxs-lookup"><span data-stu-id="47a79-121">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see [Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration) in the Lync Server 2013 Management Shell documentation):</span></span>
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="47a79-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="47a79-122">See Also</span></span>


[<span data-ttu-id="47a79-123">Set-cswebserviceconfiguration</span><span class="sxs-lookup"><span data-stu-id="47a79-123">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

