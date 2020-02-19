---
title: 'Lync Server 2013: 도메인 준비'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing domains
ms:assetid: 8eea541c-5f9d-4afc-92a8-a31d6f742544
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398721(v=OCS.15)
ms:contentKeyID: 48184816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f77c37b1694383284ec80667eba745109814c58
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139139"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-domains-for-lync-server-2013"></a><span data-ttu-id="923ba-102">Lync Server 2013에 대 한 도메인 준비</span><span class="sxs-lookup"><span data-stu-id="923ba-102">Preparing domains for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="923ba-103">_**마지막으로 수정 된 항목:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="923ba-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="923ba-104">도메인 준비는 Lync Server 2013에 대 한 Active Directory 도메인 서비스 준비의 마지막 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="923ba-104">Domain preparation is the final step in preparing Active Directory Domain Services for Lync Server 2013.</span></span> <span data-ttu-id="923ba-105">도메인 준비 단계에서는 호스트에 권한을 부여하고 도메인 내의 사용자를 관리하는 유니버설 그룹에 필요한 ACE(액세스 제어 항목)를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="923ba-105">The domain preparation step adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain.</span></span> <span data-ttu-id="923ba-106">도메인 준비는 도메인 루트와 세 개의 기본 제공 컨테이너인 사용자, 컴퓨터 및 도메인 컨트롤러에 ACE를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="923ba-106">Domain preparation creates ACEs on the domain root and three built-in containers: User, Computers, and Domain Controllers.</span></span>

<span data-ttu-id="923ba-107">Lync Server를 배포 하는 도메인의 모든 컴퓨터에서 도메인 준비를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="923ba-107">You can run domain preparation on any computer in the domain where you are deploying Lync Server.</span></span> <span data-ttu-id="923ba-108">Lync Server 또는 사용자를 호스트 하는 모든 도메인을 준비 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="923ba-108">You must prepare every domain that will host Lync Server or users.</span></span>

<span data-ttu-id="923ba-109">조직에서 권한 상속이 비활성화되어 있거나 인증된 사용자 권한을 비활성화해야 하는 경우 도메인 준비 작업 중에 추가 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="923ba-109">If permissions inheritance is disabled or authenticated user permissions are disabled in your organization, you must perform additional steps during domain preparation.</span></span> <span data-ttu-id="923ba-110">자세한 내용은 [Lync Server 2013에서 잠긴 Active Directory 도메인 서비스 준비](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="923ba-110">For details, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).</span></span>

<span data-ttu-id="923ba-111">조직에서 세 개의 기본 제공 컨테이너(즉, 사용자, 컴퓨터 및 도메인 컨트롤러) 대신에 OU(조직 구성 단위)를 사용하는 경우 OU에 Authenticated Users 그룹에 대한 읽기 권한을 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="923ba-111">If your organization uses organizational units (OU) instead of the three built-in containers (that is, Users, Computers, and Domain Controllers), you must grant read access to the OUs for the Authenticated Users group.</span></span> <span data-ttu-id="923ba-112">컨테이너에 대한 읽기 권한은 도메인을 준비하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="923ba-112">Read access to the containers is required for domain preparation.</span></span> <span data-ttu-id="923ba-113">Authenticated Users 그룹에 OU에 대한 읽기 권한이 없는 경우 각 OU에 읽기 권한을 부여하는 다음 코드 예제와 같이 **Grant-CsOuPermission** cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="923ba-113">If the Authenticated Users group does not have read access to the OU, run the **Grant-CsOuPermission** cmdlet as illustrated in the following code examples to grant read permissions for each OU.</span></span>

   ```PowerShell
    Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU > 
   ```

   ```PowerShell
    Grant-CsOuPermission -ObjectType "user","contact",inetOrgPerson" -OU "ou=Redmond,dc=contoso,dc=net"
   ```

<span data-ttu-id="923ba-114">**부여-CsOuPermission** cmdlet에 대 한 자세한 내용은 Lync Server 관리 셸 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="923ba-114">For details about the **Grant-CsOuPermission** cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div class="">


> [!TIP]  
> <span data-ttu-id="923ba-115">도메인 루트와 사용자, 컴퓨터 및 도메인 컨트롤러 컨테이너에서 만들어진 Ace에 대 한 자세한 내용은 <A href="lync-server-2013-changes-made-by-domain-preparation.md">Lync Server 2013에서 도메인 준비로 인 한 변경 내용을</A>참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="923ba-115">For details about the ACEs created on the domain root and in the Users, Computers, and Domain Controllers containers, see <A href="lync-server-2013-changes-made-by-domain-preparation.md">Changes made by domain preparation in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="923ba-116">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="923ba-116">In This Section</span></span>

  - [<span data-ttu-id="923ba-117">Lync Server 2013에 대 한 도메인 준비 실행</span><span class="sxs-lookup"><span data-stu-id="923ba-117">Running domain preparation for Lync Server 2013</span></span>](lync-server-2013-running-domain-preparation.md)

  - [<span data-ttu-id="923ba-118">Cmdlet을 사용 하 여 Lync Server 2013에 대 한 도메인 준비 되돌리기</span><span class="sxs-lookup"><span data-stu-id="923ba-118">Using cmdlets to reverse domain preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

