---
title: 'Lync Server 2013: 모임에 대해 전화 접속 회의를 사용 하거나 사용 하지 않도록 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable dial-in conferencing for meetings
ms:assetid: 418dcf2d-c8d6-4b2c-b1ab-8723c7ef53e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688036(v=OCS.15)
ms:contentKeyID: 49733627
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa1b18d2d146a56695bc22ea4e6e87e2826c7c8a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137727"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-dial-in-conferencing-for-meetings-in-lync-server-2013"></a><span data-ttu-id="f4575-102">Lync Server 2013에서 모임에 대 한 전화 접속 회의를 사용 하거나 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="f4575-102">Enable or disable dial-in conferencing for meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4575-103">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f4575-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f4575-104">다음 절차에서는 사용자가 전화 접속을 사용해서 모임에 참가하도록 허용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f4575-104">The following procedure describes how to allow user to join a meeting using dial-in.</span></span>

<div>

## <a name="to-enable-or-disable-dial-in-conferencing"></a><span data-ttu-id="f4575-105">전화 접속 회의를 사용 하거나 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="f4575-105">To enable or disable dial-in conferencing</span></span>

1.  <span data-ttu-id="f4575-106">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="f4575-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f4575-107">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f4575-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f4575-108">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f4575-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f4575-109">왼쪽 탐색 모음에서 **회의**를 클릭하고 **회의 정책**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f4575-109">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="f4575-110">회의 정책 목록에서 전화 접속 회의를 사용하도록 설정하려는 정책을 선택하고 **편집**을 클릭한 다음 **세부 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f4575-110">In the list of conferencing policies, select the policy for which you want to enable dial-in conferencing, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="f4575-p102">사용자가 전화 접속을 사용해서 모임에 참가할 수 있도록 허용하려면 **PSTN 전화 접속 회의 사용** 확인란을 선택합니다. 기본적으로 사용자는 PSTN(공중 전화망)을 사용하여 모임에 전화 접속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4575-p102">To allow users to join meeting by dialing in, check the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>

6.  <span data-ttu-id="f4575-113">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f4575-113">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

