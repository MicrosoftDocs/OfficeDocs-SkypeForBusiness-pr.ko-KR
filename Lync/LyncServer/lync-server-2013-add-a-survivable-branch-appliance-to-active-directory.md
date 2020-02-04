---
title: 'Lync Server 2013: Active Directory에 SBA(Survivable Branch Appliance) 추가'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add a Survivable Branch Appliance to Active Directory
ms:assetid: 3e63507c-d60b-40ec-8bbe-586b1d707c3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425906(v=OCS.15)
ms:contentKeyID: 48183938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8712dcb5b68522a8b770aac63c5a37a1a70a669a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735068"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-a-survivable-branch-appliance-to-active-directory-in-lync-server-2013"></a><span data-ttu-id="de833-102">Lync Server 2013에서 Active Directory에 SBA(Survivable Branch Appliance) 추가</span><span class="sxs-lookup"><span data-stu-id="de833-102">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de833-103">_**마지막으로 수정한 주제:** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="de833-103">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="de833-104">Survivable Branch 기기를 배포 하려는 경우 Active Directory 도메인 서비스에 Survivable Branch 기기를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de833-104">If you plan to deploy a Survivable Branch Appliance, you must add the Survivable Branch Appliance to Active Directory Domain Services.</span></span> <span data-ttu-id="de833-105">중앙 사이트에서이 절차를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="de833-105">Perform this procedure at the central site.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="de833-106">Survivable Branch 기기를 배포 하는 경우에만이 절차를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="de833-106">Perform this procedure only if you are deploying a Survivable Branch Appliance.</span></span> <span data-ttu-id="de833-107">Survivable Branch 서버를 배포 하는 경우에는이 작업을 수행 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="de833-107">Do not perform it if you are deploying a Survivable Branch Server.</span></span>



</div>

<div>

## <a name="to-add-an-survivable-branch-appliance-to-active-directory-domain-services"></a><span data-ttu-id="de833-108">Active Directory 도메인 서비스에 Survivable Branch 기기를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="de833-108">To add an Survivable Branch Appliance to Active Directory Domain Services</span></span>

1.  <span data-ttu-id="de833-109">엔터프라이즈 관리자 그룹의 구성원으로 구성원 서버에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="de833-109">Log on to a member server as a member of the Enterprise Admins group.</span></span>

2.  <span data-ttu-id="de833-110">**시작**을 클릭 하 고 **관리 도구**를 클릭 한 다음 **Active Directory 사용자 및 컴퓨터**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="de833-110">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>

3.  <span data-ttu-id="de833-111">**작업** 메뉴에서 **새로 만들기** 를 클릭 한 다음 **컴퓨터**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="de833-111">On the **Actions** menu, click **New** and then click **Computer**.</span></span>

4.  <span data-ttu-id="de833-112">**새 개체-컴퓨터** 대화 상자에서 Survivable Branch 기기 컴퓨터 개체의 이름 (예: BranchOffice1)을 입력 하 고 **변경을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="de833-112">In the **New Object-Computer** dialog box, type in a name for the Survivable Branch Appliance computer object (for example, BranchOffice1), and then click **Change**.</span></span>

5.  <span data-ttu-id="de833-113">**사용자 또는 그룹 선택** 대화 상자에서 RTCUniversalSBATechnicians 그룹을 추가 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="de833-113">In the **Select User or Group** dialog box, add the RTCUniversalSBATechnicians group and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="de833-114">지점 사이트에서 RTCUniversalSBATechnicians 그룹의 구성원은 나중에이 장치를 도메인에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="de833-114">A member of the RTCUniversalSBATechnicians group at the branch site will add this device to the domain later.</span></span>

    
    </div>

6.  <span data-ttu-id="de833-115">**확인** 을 클릭 하 여 Survivable Branch 기기 컴퓨터 개체를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="de833-115">Click **OK** to save the Survivable Branch Appliance computer object.</span></span>

7.  <span data-ttu-id="de833-116">**시작**을 클릭 하 고 **관리 도구**를 클릭 한 다음 **ADSI 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="de833-116">Click **Start**, click **Administrative Tools**, and then click **ADSI Edit**.</span></span>

8.  <span data-ttu-id="de833-117">**ADSI 편집**에서 이전 단계에서 만든 컴퓨터 개체를 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="de833-117">In **ADSI Edit**, right-click the computer object that you created in the previous steps, and then click **Properties**.</span></span>

9.  <span data-ttu-id="de833-118">특성 목록에서 **servicePrincipalName**를 클릭 한 다음 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="de833-118">In the attribute list, click **servicePrincipalName**, and then click **Edit**.</span></span>

10. <span data-ttu-id="de833-119">**추가할 값** \<필드에 HOST/sba fqdn\> 을 입력 합니다. 여기서 \<sba fqdn\> 은 Survivable Branch 기기의 fqdn (정규화 된 도메인 이름)입니다.</span><span class="sxs-lookup"><span data-stu-id="de833-119">In the **Value to add** field, type HOST/\<SBA FQDN\> where \<SBA FQDN\> is the fully qualified domain name (FQDN) of your Survivable Branch Appliance.</span></span> <span data-ttu-id="de833-120">예를 들어 **HOST/BranchOffice1**를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="de833-120">For example, type **HOST/BranchOffice1.contoso.com**.</span></span>

11. <span data-ttu-id="de833-121">**확인** 을 클릭 하 여 **servicePrincipalName** 특성 설정을 저장 한 다음 **확인** 을 클릭 하 여 컴퓨터 개체 속성을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="de833-121">Click **OK** to save the **servicePrincipalName** attribute setting, and then click **OK** to save the computer object properties.</span></span>

12. <span data-ttu-id="de833-122">**Active Directory 사용자 및 컴퓨터**에서 **사용자**를 마우스 오른쪽 단추로 클릭 하 고 **새로 만들기**를 클릭 한 다음 **사용자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="de833-122">In **Active Directory Users and Computers**, right-click **Users**, click **New**, and then click **User**.</span></span>

13. <span data-ttu-id="de833-123">마법사에 정보를 입력 하 여 Survivable Branch 기기 기술자에 대 한 도메인 사용자 계정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="de833-123">Enter information into the wizard to create a domain user account for a Survivable Branch Appliance technician.</span></span>

14. <span data-ttu-id="de833-124">**Active Directory 사용자 및 컴퓨터**에서 **사용자**를 클릭 하 고 사용자 개체를 마우스 오른쪽 단추로 클릭 한 다음 **그룹에 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="de833-124">In **Active Directory Users and Computers**, click **Users**, right-click the user object, and then click **Add to a group**.</span></span>

15. <span data-ttu-id="de833-125">**선택할 개체 이름을 입력**하 고 **RTCUniversalSBATechnicians**을 입력 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="de833-125">In **Enter the object names to select**, type **RTCUniversalSBATechnicians**, and then click **OK**.</span></span>

16. <span data-ttu-id="de833-126">각 지사 사이트 기술자에 대해 12-15 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="de833-126">Repeat Steps 12-15 for each branch site technician.</span></span>

<span data-ttu-id="de833-127">**다음 단계**: [Lync Server 2013에서 토폴로지에 지점 사이트 추가](lync-server-2013-add-branch-sites-to-your-topology.md)</span><span class="sxs-lookup"><span data-stu-id="de833-127">**Next step**: [Add branch sites to your topology in Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

