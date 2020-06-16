---
title: 모임 참가 페이지 구성
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure the meeting join page
ms:assetid: a87319b7-3124-4262-8f9d-18138870ee2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205145(v=OCS.15)
ms:contentKeyID: 48185030
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a63354b9e0b0cf44ed44f53c91061578e01fecb5
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754506"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-meeting-join-page"></a><span data-ttu-id="c36d8-102">모임 참가 페이지 구성</span><span class="sxs-lookup"><span data-stu-id="c36d8-102">Configure the meeting join page</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c36d8-103">_**마지막으로 수정 된 항목:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="c36d8-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="c36d8-104">사용자가 모임 요청에서 모임 링크를 클릭 하면 모임 참가 페이지에서 Lync 2013 클라이언트가 사용자 컴퓨터에 이미 설치 되어 있는지 여부를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="c36d8-104">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Lync 2013 client is already installed on the user’s computer.</span></span> <span data-ttu-id="c36d8-105">클라이언트가 이미 설치되어 있으면 클라이언트가 열리고 모임에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="c36d8-105">If a client is already installed, that client opens and joins the meeting.</span></span> <span data-ttu-id="c36d8-106">클라이언트가 설치 되어 있지 않으면 기본적으로 Microsoft Lync Web App의 2013 버전이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="c36d8-106">If a client is not installed, by default the 2013 version of Microsoft Lync Web App opens.</span></span>

<span data-ttu-id="c36d8-107">사용자가 Office Communicator 2007 R2 또는 Lync 2010 Attendant와 모임에 참가할 수 있도록 허용 하려는 경우에는 모임 참가 페이지의 동작을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c36d8-107">You can modify the behavior of the meeting join page if you want to allow users to join meetings with Office Communicator 2007 R2 or Lync 2010 Attendant.</span></span> <span data-ttu-id="c36d8-108">이러한 구성 옵션은 Lync Server 2013 제어판에서 제거 되었지만 Set-cswebserviceconfiguration cmdlet을 사용 하 여 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c36d8-108">These configuration options have been removed from the Lync Server 2013 Control Panel, but you configure them by using the CsWebServiceConfiguration cmdlet.</span></span>

### <a name="meeting-join-page-cswebserviceconfiguration-parameters"></a><span data-ttu-id="c36d8-109">모임 참가 페이지 CsWebServiceConfiguration 매개 변수</span><span class="sxs-lookup"><span data-stu-id="c36d8-109">Meeting Join Page CsWebServiceConfiguration Parameters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c36d8-110">CsWebServiceConfiguration 매개 변수</span><span class="sxs-lookup"><span data-stu-id="c36d8-110">CsWebServiceConfiguration Parameter</span></span></th>
<th><span data-ttu-id="c36d8-111">설명</span><span class="sxs-lookup"><span data-stu-id="c36d8-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c36d8-112">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="c36d8-112">ShowJoinUsingLegacyClientLink</span></span></p></td>
<td><p><span data-ttu-id="c36d8-113">True로 설정 하면 Lync 이외의 클라이언트 응용 프로그램을 사용 하 여 모임에 참가 하는 사용자에 게 Office Communicator 2007 R2를 사용 하 여 모임에 참가할 수 있는 기회가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c36d8-113">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting by using Office Communicator 2007 R2.</span></span> <span data-ttu-id="c36d8-114">기본값은 False입니다.</span><span class="sxs-lookup"><span data-stu-id="c36d8-114">The default value is False.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c36d8-115">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="c36d8-115">ShowAlternateJoinOptionsExpanded</span></span></p></td>
<td><p><span data-ttu-id="c36d8-116">When set to True then alternate options for joining an online conference (such as Office Communicator 2007 R2) will automatically be expanded and shown to users.</span><span class="sxs-lookup"><span data-stu-id="c36d8-116">When set to True then alternate options for joining an online conference (such as Office Communicator 2007 R2) will automatically be expanded and shown to users.</span></span> <span data-ttu-id="c36d8-117">When set to False (the default value) these options will be available, but the user will have to display the list of options for themselves.</span><span class="sxs-lookup"><span data-stu-id="c36d8-117">When set to False (the default value) these options will be available, but the user will have to display the list of options for themselves.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a><span data-ttu-id="c36d8-118">Lync Server 2013 관리 셸을 사용 하 여 모임 참가 페이지를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="c36d8-118">To configure the meeting join page by using Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="c36d8-119">Lync Server 2013 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **lync server 관리 셸을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c36d8-119">Start the Lync Server 2013 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="c36d8-120">다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c36d8-120">Run the following cmdlet:</span></span>
    
        Get-CsWebServiceConfiguration
    
    <span data-ttu-id="c36d8-121">이 cmdlet는 웹 서비스 구성 설정을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c36d8-121">This cmdlet returns the web service configuration settings.</span></span>

3.  <span data-ttu-id="c36d8-122">기본 설정 (이 cmdlet의 매개 변수에 대 한 자세한 내용은 Lync Server 2013 Management Shell 설명서 참조)에 따라 매개 변수를 True 또는 False로 설정한 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c36d8-122">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see the Lync Server 2013 Management Shell documentation):</span></span>
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

</div>

<span> </span>

</div>

</div>

</div>

