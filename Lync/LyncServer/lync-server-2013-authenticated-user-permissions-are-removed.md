---
title: 'Lync Server 2013: 인증된 사용자 권한이 제거됨'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Authenticated user permissions are removed
ms:assetid: 5fcd70a5-813a-4076-9bb6-5b0d47505038
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398425(v=OCS.15)
ms:contentKeyID: 48184304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d5e14b8129f771093ed9facb09d047ac7c36d32
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979143"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="authenticated-user-permissions-are-removed-in-lync-server-2013"></a><span data-ttu-id="77e61-102">Lync Server 2013에서 인증된 사용자 권한이 제거됨</span><span class="sxs-lookup"><span data-stu-id="77e61-102">Authenticated user permissions are removed in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77e61-103">_**마지막으로 수정한 주제:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="77e61-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="77e61-104">잠겨진 Active Directory 환경에서 인증 된 Ace (사용자 액세스 제어 항목)는 사용자 및 컴퓨터의 사용자, 구성 또는 시스템, 조직 구성 단위 (Ou) 등의 기본 Active Directory 컨테이너에서 제거 됩니다. 개체가 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="77e61-104">In a locked-down Active Directory environment, authenticated user access control entries (ACEs) are removed from the default Active Directory containers, including the Users, Configuration or System, and organizational units (OUs) where User and Computer objects are stored.</span></span> <span data-ttu-id="77e61-105">인증 된 사용자 Ace를 제거 하면 Active Directory 정보에 대 한 읽기 액세스가 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="77e61-105">Removing authenticated user ACEs prevents read access to Active Directory information.</span></span> <span data-ttu-id="77e61-106">그러나 Ace를 제거 하면 사용자가 도메인 준비를 실행할 수 있도록 하기 위해 이러한 컨테이너에 대 한 읽기 권한에 따라 Lync 서버 2013에 대 한 문제가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="77e61-106">However, removing the ACEs creates issues for Lync Server 2013 because it depends on read permissions to these containers to allow users to run domain preparation.</span></span>

<span data-ttu-id="77e61-107">이 경우 도메인 준비, 서버 활성화, 풀 만들기를 실행 하는 데 필요한 Domain Admins 그룹의 구성원은 더 이상 기본 컨테이너에 저장 된 Active Directory 정보에 대 한 읽기 권한을 부여 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="77e61-107">In this situation, membership in the Domain Admins group, which is required to run domain preparation, server activation, and pool creation, no longer grants read access to Active Directory information stored in the default containers.</span></span> <span data-ttu-id="77e61-108">필수 구성 요소 포리스트 준비 절차가 완료 되었는지 확인 하려면 포리스트 루트 도메인의 다양 한 컨테이너에 대 한 읽기 액세스 권한을 수동으로 부여 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77e61-108">You must manually grant read-access permissions on various containers in the forest root domain to check that the prerequisite forest preparation procedure is complete.</span></span>

<span data-ttu-id="77e61-109">사용자가 포리스트 이외의 루트 도메인에서 도메인 준비, 서버 활성화 또는 풀 만들기를 실행할 수 있도록 설정 하려면 다음 옵션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="77e61-109">To enable a user to run domain preparation, server activation, or pool creation on any non-forest root domain, you have the following options:</span></span>

  - <span data-ttu-id="77e61-110">엔터프라이즈 관리자 그룹의 구성원 인 계정을 사용 하 여 도메인 준비를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="77e61-110">Use an account that is a member of the Enterprise Admins group to run domain preparation.</span></span>

  - <span data-ttu-id="77e61-111">도메인 관리자 그룹의 구성원 인 계정을 사용 하 고 포리스트 루트 도메인의 다음 컨테이너 각각에 대해이 계정에 대 한 읽기 액세스 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="77e61-111">Use an account that is a member of the Domain Admins group and grant this account read-access permissions on each of the following containers in the forest root domain:</span></span>
    
      - <span data-ttu-id="77e61-112">도메인이</span><span class="sxs-lookup"><span data-stu-id="77e61-112">Domain</span></span>
    
      - <span data-ttu-id="77e61-113">구성 또는 시스템</span><span class="sxs-lookup"><span data-stu-id="77e61-113">Configuration or System</span></span>

<span data-ttu-id="77e61-114">엔터프라이즈 관리자 그룹의 구성원 인 계정을 사용 하 여 도메인 준비 나 기타 설치 작업을 실행 하지 않으려는 경우에는 포리스트 루트의 관련 컨테이너에 대 한 읽기 권한을 사용 하도록 계정을 명시적으로 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="77e61-114">If you do not want to use an account that is a member of the Enterprise Admins group to run domain preparation or other Setup tasks, explicitly grant the account you want to use read access on the relevant containers in the forest root.</span></span>

<div>

## <a name="to-give-users-read-access-permissions-on-containers-in-the-forest-root-domain"></a><span data-ttu-id="77e61-115">사용자에 게 포리스트 루트 도메인의 컨테이너에 대 한 읽기 액세스 권한을 부여 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="77e61-115">To give users read-access permissions on containers in the forest root domain</span></span>

1.  <span data-ttu-id="77e61-116">포리스트 루트 도메인에 대 한 Domain Admins 그룹의 구성원 인 계정을 사용 하 여 포리스트 루트 도메인에 연결 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="77e61-116">Log on to the computer joined to the forest root domain with an account that is a member of the Domain Admins group for the forest root domain.</span></span>

2.  <span data-ttu-id="77e61-117">포리스트 루트 도메인에 대해 adsiedit를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="77e61-117">Run adsiedit.msc for the forest root domain.</span></span>
    
    <span data-ttu-id="77e61-118">인증 된 사용자 Ace가 도메인, 구성 또는 시스템 컨테이너에서 제거 되 면 다음 단계에 설명 된 대로 컨테이너에 읽기 전용 권한을 부여 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77e61-118">If authenticated user ACEs were removed from the Domain, Configuration, or System container, you must grant read-only permissions to the container, as described in the following steps.</span></span>

3.  <span data-ttu-id="77e61-119">컨테이너를 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="77e61-119">Right-click the container, and then click **Properties**.</span></span>

4.  <span data-ttu-id="77e61-120">**보안** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="77e61-120">Click the **Security** tab.</span></span>

5.  <span data-ttu-id="77e61-121">**고급**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="77e61-121">Click **Advanced**.</span></span>

6.  <span data-ttu-id="77e61-122">**사용 권한** 탭에서 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="77e61-122">On the **Permissions** tab, click **Add**.</span></span>

7.  <span data-ttu-id="77e61-123">다음 형식으로 권한을 받는 사용자 또는 그룹의 이름을 입력 하 고 `domain\account name` **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="77e61-123">Type the name of the user or group receiving permissions by using the following format: `domain\account name`, and then click **OK**.</span></span>

8.  <span data-ttu-id="77e61-124">**개체** 탭의 **적용 대상**에서 **해당 개체만**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="77e61-124">On the **Objects** tab, in **Applies To**, click **This Object Only**.</span></span>

9.  <span data-ttu-id="77e61-125">**사용 권한**에서 **허용** 열: **콘텐츠 목록**, **모든 속성 읽기**, **권한 읽기**를 차례로 클릭 하 여 다음 ace 허용을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="77e61-125">In **Permissions**, select the following Allow ACEs by clicking the **Allow** column: **List Content**, **Read All Properties**, and **Read Permissions**.</span></span>

10. <span data-ttu-id="77e61-126">**확인을** 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="77e61-126">Click **OK** twice.</span></span>

11. <span data-ttu-id="77e61-127">2 단계에 나열 된 관련 컨테이너에 대해이 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="77e61-127">Repeat these steps for any of the relevant containers listed in Step 2.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

