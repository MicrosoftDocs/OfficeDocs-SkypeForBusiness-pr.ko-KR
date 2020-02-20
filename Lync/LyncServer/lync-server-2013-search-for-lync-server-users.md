---
title: 'Lync Server 2013: Lync Server 사용자 검색'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Search for Lync Server users
ms:assetid: 3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429701(v=OCS.15)
ms:contentKeyID: 48183871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 665d8bbb0f3409de62565c25dfdb494fd140d636
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144106"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="search-for-lync-server-users-in-lync-server-2013"></a><span data-ttu-id="331f6-102">Lync Server 2013에서 Lync Server 사용자 검색</span><span class="sxs-lookup"><span data-stu-id="331f6-102">Search for Lync Server users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="331f6-103">_**마지막으로 수정 된 항목:** 2014-05-14_</span><span class="sxs-lookup"><span data-stu-id="331f6-103">_**Topic Last Modified:** 2014-05-14_</span></span>

<span data-ttu-id="331f6-104">검색 쿼리의 결과를 사용 하 여 Lync Server 2013에 대 한 사용자를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="331f6-104">You can use the results of a search query to configure users for Lync Server 2013.</span></span> <span data-ttu-id="331f6-105">표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)로 사용자를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="331f6-105">You can search for users by display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="331f6-106">Lync Server 제어판 또는 Active Directory 사용자 및 컴퓨터 스냅인을 사용하여 사용자를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="331f6-106">You can search for users by using the Lync Server Control Panel or the Active Directory Users and Computers snap-in.</span></span> <span data-ttu-id="331f6-107">다음 절차에서는 Lync Server 제어판을 사용 하 여 사용자를 검색 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="331f6-107">The following procedure describes how to use Lync Server Control Panel to search for users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="331f6-108">중앙 포리스트 토폴로지가 있는 환경에서는 사용자의 전자 메일 주소로 사용자를 검색하는 경우 검색 결과가 정확하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="331f6-108">In an environment with a central forest topology, search results might not be accurate when you search for a user by the user’s email address.</span></span> <span data-ttu-id="331f6-109">이러한 경우에는 sip:name과 같은 SIP 주소 접두사를 지정하여 사용자를 검색하거나, 검색 필터를 추가하고 전자 메일 주소의 일부분이 포함된 SIP 주소를 선택하거나, <STRONG>Get-CSUser</STRONG> cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="331f6-109">Instead, you can search for users by specifying a SIP address prefix, for example, sip:name, add a search filter and select a SIP address that contains a partial email address, or use the <STRONG>Get-CSUser</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="to-search-for-one-or-more-users"></a><span data-ttu-id="331f6-110">한 명 이상의 사용자를 검색하려면</span><span class="sxs-lookup"><span data-stu-id="331f6-110">To search for one or more users</span></span>

1.  <span data-ttu-id="331f6-111">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="331f6-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="331f6-112">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="331f6-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="331f6-113">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="331f6-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="331f6-114">왼쪽 탐색 모음에서 **사용자**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="331f6-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="331f6-115">**사용자 검색** 상자에 검색할 사용자 계정의 표시 이름, 이름, 성, SAM 계정 이름, SIP 주소 또는 줄 URI를 모두 입력하거나 첫 부분을 입력하고 **찾기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="331f6-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, SAM account name, SIP address, or line URI of the user account that you want to search for, and then click **Find**.</span></span>

5.  <span data-ttu-id="331f6-116">(선택 사항) 추가 검색 조건을 지정하여 결과 범위를 좁힙니다.</span><span class="sxs-lookup"><span data-stu-id="331f6-116">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="331f6-117">화면 오른쪽 위의 **검색 결과** 위에 있는 확장 화살표 단추를 클릭하고 **필터 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="331f6-117">Click the expand arrow button in the upper-right corner of the screen above **Search results**, and then click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="331f6-118">사용자 속성을 입력하거나 드롭다운 목록의 화살표를 클릭하여 사용자 속성을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="331f6-118">Enter the user property by typing it or clicking the arrow in the drop-down list to select a user property.</span></span>
    
    3.  <span data-ttu-id="331f6-119">**같음** 목록에서 **같음** 또는 **같지 않음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="331f6-119">In the **Equal to** list, click **Equal to** or **Not equal to**.</span></span>
    
    4.  <span data-ttu-id="331f6-120">텍스트 상자에 검색 결과를 필터링하는 데 사용할 검색 조건을 입력하고 **찾기**를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="331f6-120">In the text box, type the search criteria you want to use to filter search results, and then click **Find**.</span></span>

6.  <span data-ttu-id="331f6-p105">**검색 결과** 아래에 검색 결과가 나타납니다. 목록에서 원하는 사용자 또는 모든 사용자를 선택하고 선택한 사용자에 대해 구성 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="331f6-p105">The search results appear under **Search Results**. You can select any or all of the users in the list and perform configuration tasks on the users you select.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="331f6-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="331f6-123">See Also</span></span>


[<span data-ttu-id="331f6-124">Lync Server 2013에 대해 사용 하도록 설정 된 사용자 계정에 대 한 정보 보기</span><span class="sxs-lookup"><span data-stu-id="331f6-124">Viewing information about user accounts enabled for Lync Server 2013</span></span>](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)  
[<span data-ttu-id="331f6-125">Lync Server 2013에 대 한 사용자 사용 및 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="331f6-125">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

