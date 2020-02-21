---
title: 'Lync Server 2013: Lync Server에 대해 사용자 계정 추가 및 사용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add and enable user account for Lync Server
ms:assetid: 1edd1c1c-307d-450b-abea-33aaf56bdf13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520961(v=OCS.15)
ms:contentKeyID: 48183578
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 24fe3004f588f50edbcb9428d8bece7a4b20a28a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181401"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-and-enable-user-account-for-lync-server-2013"></a><span data-ttu-id="e30fe-102">Lync Server 2013에 대해 사용자 계정 추가 및 사용</span><span class="sxs-lookup"><span data-stu-id="e30fe-102">Add and enable user account for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e30fe-103">_**마지막으로 수정 된 항목:** 2012-11-02_</span><span class="sxs-lookup"><span data-stu-id="e30fe-103">_**Topic Last Modified:** 2012-11-02_</span></span>

<span data-ttu-id="e30fe-104">Active Directory 사용자 및 컴퓨터에서 사용자 계정을 사용 하도록 설정한 후 Lync server 제어판을 사용 하 여 Active Directory 사용자를 Lync Server에 추가 하 여 새 Lync Server 2013 사용자 계정을 만들고 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e30fe-104">After enabling a user account in Active Directory Users and Computers, you can use Lync Server Control Panel to create and enable new Lync Server 2013 user accounts by adding an Active Directory user to Lync Server.</span></span>

<div>

## <a name="to-add-and-enable-a-new-lync-server-user"></a><span data-ttu-id="e30fe-105">새 Lync Server 사용자를 추가 하 고 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="e30fe-105">To add and enable a new Lync Server user</span></span>

1.  <span data-ttu-id="e30fe-106">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="e30fe-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e30fe-107">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e30fe-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e30fe-108">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e30fe-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e30fe-109">왼쪽 탐색 모음에서 **사용자**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e30fe-109">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="e30fe-110">**사용자 사용**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e30fe-110">Click **Enable users**.</span></span>

5.  <span data-ttu-id="e30fe-111">**새 Lync Server 사용자** 대화 상자에서 **추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e30fe-111">On the **New Lync Server User** dialog, click **Add**.</span></span>

6.  <span data-ttu-id="e30fe-112">**사용자 검색** 상자에 원하는 Active Directory 사용자 계정의 이름, 표시 이름, 성, SAM(보안 계정 관리자) 계정 이름, 전자 메일 주소, UPN(사용자 계정 이름) 또는 전화 번호를 모두 또는 일부분 입력하고 **찾기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e30fe-112">In the **Search users** box, type all or the first portion of the name, display name, first name, last name, Security Accounts Manager (SAM) account name, email address, User Principal Name (UPN), or phone number of the Active Directory user account that you want, and then click **Find**.</span></span>

7.  <span data-ttu-id="e30fe-113">테이블에서 Lync Server에 추가할 계정을 선택 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e30fe-113">In the table, select the account you want to add to Lync Server, and then click **OK**.</span></span>

8.  <span data-ttu-id="e30fe-114">풀에 사용자를 할당하고, 세부 정보를 추가로 지정하고, 원하는 사용자에게 정책을 할당한 후에 **사용**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e30fe-114">Assign the user to a pool, specify any additional details, and assign the policies to the user you want, and then click **Enable**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e30fe-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e30fe-115">See Also</span></span>


[<span data-ttu-id="e30fe-116">Lync Server 2013에 대해 사용자 계정을 사용 하지 않도록 설정 하거나 다시 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="e30fe-116">Disable or re-enable user account for Lync Server 2013</span></span>](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[<span data-ttu-id="e30fe-117">Lync Server 2013에서 사용자 계정 제거</span><span class="sxs-lookup"><span data-stu-id="e30fe-117">Remove a user account from Lync Server 2013</span></span>](lync-server-2013-remove-a-user-account-from-lync-server.md)  


[<span data-ttu-id="e30fe-118">Lync Server 2013에 대 한 사용자 사용 및 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="e30fe-118">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

