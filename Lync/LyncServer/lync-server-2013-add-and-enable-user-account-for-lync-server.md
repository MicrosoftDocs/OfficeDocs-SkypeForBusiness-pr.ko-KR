---
title: 'Lync Server 2013: Lync Server에 대 한 사용자 계정 추가 및 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add and enable user account for Lync Server
ms:assetid: 1edd1c1c-307d-450b-abea-33aaf56bdf13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520961(v=OCS.15)
ms:contentKeyID: 48183578
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fc52e76d480e323669b88c1ee461eeccf9aef38
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980678"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-and-enable-user-account-for-lync-server-2013"></a><span data-ttu-id="8dcaa-102">Lync Server 2013에 대 한 사용자 계정 추가 및 설정</span><span class="sxs-lookup"><span data-stu-id="8dcaa-102">Add and enable user account for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8dcaa-103">_**마지막으로 수정한 주제:** 2012-11-02_</span><span class="sxs-lookup"><span data-stu-id="8dcaa-103">_**Topic Last Modified:** 2012-11-02_</span></span>

<span data-ttu-id="8dcaa-104">Active Directory 사용자 및 컴퓨터에서 사용자 계정을 사용 하도록 설정한 후 Lync server 제어판을 사용 하 여 lync server에 Active Directory 사용자를 추가 하 여 새 Lync Server 2013 사용자 계정을 만들고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dcaa-104">After enabling a user account in Active Directory Users and Computers, you can use Lync Server Control Panel to create and enable new Lync Server 2013 user accounts by adding an Active Directory user to Lync Server.</span></span>

<div>

## <a name="to-add-and-enable-a-new-lync-server-user"></a><span data-ttu-id="8dcaa-105">새 Lync Server 사용자를 추가 하 고 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="8dcaa-105">To add and enable a new Lync Server user</span></span>

1.  <span data-ttu-id="8dcaa-106">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dcaa-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8dcaa-107">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8dcaa-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8dcaa-108">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8dcaa-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8dcaa-109">왼쪽 탐색 모음에서 **사용자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dcaa-109">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="8dcaa-110">**사용자 사용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dcaa-110">Click **Enable users**.</span></span>

5.  <span data-ttu-id="8dcaa-111">**새 Lync Server 사용자** 대화 상자에서 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dcaa-111">On the **New Lync Server User** dialog, click **Add**.</span></span>

6.  <span data-ttu-id="8dcaa-112">**사용자 검색** 상자에 이름, 표시 이름, 이름, 성, 보안 계정 관리자 (SAM) 계정 이름, 전자 메일 주소, UPN (사용자 이름) 또는 원하는 Active Directory 사용자 계정의 전화 번호 중 첫 번째 부분을 입력 한 다음 **찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dcaa-112">In the **Search users** box, type all or the first portion of the name, display name, first name, last name, Security Accounts Manager (SAM) account name, email address, User Principal Name (UPN), or phone number of the Active Directory user account that you want, and then click **Find**.</span></span>

7.  <span data-ttu-id="8dcaa-113">표에서 Lync Server에 추가 하려는 계정을 선택한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dcaa-113">In the table, select the account you want to add to Lync Server, and then click **OK**.</span></span>

8.  <span data-ttu-id="8dcaa-114">풀에 사용자를 할당 하 고, 추가 세부 정보를 지정 하 고, 정책을 원하는 사용자에 게 할당 한 다음 **사용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dcaa-114">Assign the user to a pool, specify any additional details, and assign the policies to the user you want, and then click **Enable**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8dcaa-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8dcaa-115">See Also</span></span>


[<span data-ttu-id="8dcaa-116">Lync Server 2013의 사용자 계정을 사용 하지 않도록 설정 하거나 다시 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="8dcaa-116">Disable or re-enable user account for Lync Server 2013</span></span>](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[<span data-ttu-id="8dcaa-117">Lync Server 2013에서 사용자 계정 제거</span><span class="sxs-lookup"><span data-stu-id="8dcaa-117">Remove a user account from Lync Server 2013</span></span>](lync-server-2013-remove-a-user-account-from-lync-server.md)  


[<span data-ttu-id="8dcaa-118">Lync Server 2013에 대 한 사용자 설정 및 해제</span><span class="sxs-lookup"><span data-stu-id="8dcaa-118">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

