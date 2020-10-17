---
title: 'Lync Server 2013: 인증 된 사용자 권한이 제거 됨'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Authenticated user permissions are removed
ms:assetid: 5fcd70a5-813a-4076-9bb6-5b0d47505038
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398425(v=OCS.15)
ms:contentKeyID: 48184304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8cf9f63fbe5340b3a241fc60b8623f54906dd8cc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515765"
---
# <a name="authenticated-user-permissions-are-removed-in-lync-server-2013"></a><span data-ttu-id="53b0d-102">Lync Server 2013에서 인증 된 사용자 권한이 제거 됨</span><span class="sxs-lookup"><span data-stu-id="53b0d-102">Authenticated user permissions are removed in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53b0d-103">_**마지막으로 수정 된 항목:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="53b0d-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="53b0d-104">잠겨 있는 Active Directory 환경에서는 사용자 및 컴퓨터 개체가 저장되는 OU(조직 구성 단위), 구성 또는 시스템, 사용자를 비롯한 기본 Active Directory 컨테이너에서 인증된 사용자 ACE(액세스 제어 항목)가 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="53b0d-104">In a locked-down Active Directory environment, authenticated user access control entries (ACEs) are removed from the default Active Directory containers, including the Users, Configuration or System, and organizational units (OUs) where User and Computer objects are stored.</span></span> <span data-ttu-id="53b0d-105">인증된 사용자 ACE를 제거하면 Active Directory 정보를 읽을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="53b0d-105">Removing authenticated user ACEs prevents read access to Active Directory information.</span></span> <span data-ttu-id="53b0d-106">그러나 Ace를 제거 하면 이러한 컨테이너에 대 한 읽기 권한이 있어 사용자가 도메인 준비를 실행할 수 있기 때문에 Lync Server 2013에 대 한 문제가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="53b0d-106">However, removing the ACEs creates issues for Lync Server 2013 because it depends on read permissions to these containers to allow users to run domain preparation.</span></span>

<span data-ttu-id="53b0d-p102">이 상황에서 도메인 준비, 서버 활성화 및 풀 만들기를 실행하는 데 필요한 Domain Admins 그룹의 구성원이 기본 컨테이너에 저장된 Active Directory 정보에 대한 읽기 권한을 더 이상 부여할 수 없습니다. 필요한 포리스트 준비 절차가 완료되었는지 확인하려면 포리스트 루트 도메인의 여러 도메인에 대한 읽기 권한을 수동으로 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53b0d-p102">In this situation, membership in the Domain Admins group, which is required to run domain preparation, server activation, and pool creation, no longer grants read access to Active Directory information stored in the default containers. You must manually grant read-access permissions on various containers in the forest root domain to check that the prerequisite forest preparation procedure is complete.</span></span>

<span data-ttu-id="53b0d-109">포리스트 루트 도메인이 아닌 모든 도메인에서 도메인 준비, 서버 활성화 또는 풀 만들기를 활성화하기 위한 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="53b0d-109">To enable a user to run domain preparation, server activation, or pool creation on any non-forest root domain, you have the following options:</span></span>

  - <span data-ttu-id="53b0d-110">엔터프라이즈 관리자 그룹의 구성원 인 계정을 사용 하 여 도메인 준비를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="53b0d-110">Use an account that is a member of the Enterprise Admins group to run domain preparation.</span></span>

  - <span data-ttu-id="53b0d-111">Domain Admins 그룹의 구성원인 계정을 사용하고 포리스트 루트 도메인의 다음 컨테이너에 대한 읽기 권한을 이 계정에 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="53b0d-111">Use an account that is a member of the Domain Admins group and grant this account read-access permissions on each of the following containers in the forest root domain:</span></span>
    
      - <span data-ttu-id="53b0d-112">도메인</span><span class="sxs-lookup"><span data-stu-id="53b0d-112">Domain</span></span>
    
      - <span data-ttu-id="53b0d-113">구성 또는 시스템</span><span class="sxs-lookup"><span data-stu-id="53b0d-113">Configuration or System</span></span>

<span data-ttu-id="53b0d-114">Enterprise Admins 그룹의 구성원인 계정을 사용하여 도메인 준비 작업이나 기타 설치 작업을 실행하지 않으려는 경우 사용할 계정에 포리스트 루트의 관련 컨테이너에 대한 읽기 권한을 명시적으로 부여하십시오.</span><span class="sxs-lookup"><span data-stu-id="53b0d-114">If you do not want to use an account that is a member of the Enterprise Admins group to run domain preparation or other Setup tasks, explicitly grant the account you want to use read access on the relevant containers in the forest root.</span></span>

<div>

## <a name="to-give-users-read-access-permissions-on-containers-in-the-forest-root-domain"></a><span data-ttu-id="53b0d-115">사용자에게 포리스트 루트 도메인의 컨테이너에 대한 읽기 권한을 부여하려면</span><span class="sxs-lookup"><span data-stu-id="53b0d-115">To give users read-access permissions on containers in the forest root domain</span></span>

1.  <span data-ttu-id="53b0d-116">포리스트 루트 도메인에 대한 Domain Admins 그룹의 구성원인 계정으로 포리스트 루트 도메인에 가입된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="53b0d-116">Log on to the computer joined to the forest root domain with an account that is a member of the Domain Admins group for the forest root domain.</span></span>

2.  <span data-ttu-id="53b0d-117">포리스트 루트 도메인에 대해 adsiedit.msc를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="53b0d-117">Run adsiedit.msc for the forest root domain.</span></span>
    
    <span data-ttu-id="53b0d-118">인증된 사용자 ACE가 도메인, 구성 또는 시스템 컨테이너에서 제거된 경우에는 다음 단계를 따라 컨테이너에 대한 읽기 전용 권한을 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53b0d-118">If authenticated user ACEs were removed from the Domain, Configuration, or System container, you must grant read-only permissions to the container, as described in the following steps.</span></span>

3.  <span data-ttu-id="53b0d-119">컨테이너를 마우스 오른쪽 단추로 클릭한 다음 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="53b0d-119">Right-click the container, and then click **Properties**.</span></span>

4.  <span data-ttu-id="53b0d-120">**보안** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="53b0d-120">Click the **Security** tab.</span></span>

5.  <span data-ttu-id="53b0d-121">**고급**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="53b0d-121">Click **Advanced**.</span></span>

6.  <span data-ttu-id="53b0d-122">**사용 권한** 탭에서 **추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="53b0d-122">On the **Permissions** tab, click **Add**.</span></span>

7.  <span data-ttu-id="53b0d-123">다음 형식을 사용 하 여 사용 권한을 받는 사용자 또는 그룹의 이름을 입력 하 `domain\account name` 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="53b0d-123">Type the name of the user or group receiving permissions by using the following format: `domain\account name`, and then click **OK**.</span></span>

8.  <span data-ttu-id="53b0d-124">**개체** 탭의 **적용 대상**에서 **이 개체만**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="53b0d-124">On the **Objects** tab, in **Applies To**, click **This Object Only**.</span></span>

9.  <span data-ttu-id="53b0d-125">**사용 권한**에서 **허용** 열을 클릭하여 **내용 보기**, **모든 속성 읽기** 및 **읽기 권한** 허용 ACE를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="53b0d-125">In **Permissions**, select the following Allow ACEs by clicking the **Allow** column: **List Content**, **Read All Properties**, and **Read Permissions**.</span></span>

10. <span data-ttu-id="53b0d-126">**확인**을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="53b0d-126">Click **OK** twice.</span></span>

11. <span data-ttu-id="53b0d-127">2단계에 나열된 모든 관련 컨테이너에 대해 위의 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="53b0d-127">Repeat these steps for any of the relevant containers listed in Step 2.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

