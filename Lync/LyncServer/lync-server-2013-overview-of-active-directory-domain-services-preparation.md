---
title: 'Lync Server 2013: Active Directory 도메인 서비스 준비 개요'
description: 'Lync Server 2013: Active Directory 도메인 서비스 준비 개요'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Active Directory Domain Services preparation
ms:assetid: cdd2a652-6a0d-4728-9950-3fcaa7a80066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398869(v=OCS.15)
ms:contentKeyID: 48185662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18b22e11a73ad7a181e2eaf887b1b49b934d9db5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566844"
---
# <a name="overview-of-active-directory-domain-services-preparation-in-lync-server-2013"></a><span data-ttu-id="6b5ae-103">Lync Server 2013의 Active Directory 도메인 서비스 준비 개요</span><span class="sxs-lookup"><span data-stu-id="6b5ae-103">Overview of Active Directory Domain Services preparation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b5ae-104">_**마지막으로 수정 된 항목:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="6b5ae-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="6b5ae-105">Lync Server 2013 배포에 대 한 Active Directory 도메인 서비스를 준비 하려면 특정 순서에 따라 세 가지 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b5ae-105">To prepare Active Directory Domain Services for your Lync Server 2013 deployment, you must perform three steps in a specific sequence.</span></span>

<span data-ttu-id="6b5ae-106">다음 표에서는 Lync Server 용 AD DS를 준비 하는 데 필요한 단계를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b5ae-106">The following table describes the steps required to prepare AD DS for Lync Server.</span></span>

### <a name="active-directory-preparation-steps"></a><span data-ttu-id="6b5ae-107">Active Directory 준비 단계</span><span class="sxs-lookup"><span data-stu-id="6b5ae-107">Active Directory Preparation Steps</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="6b5ae-108">단계</span><span class="sxs-lookup"><span data-stu-id="6b5ae-108">Step</span></span></th>
<th><span data-ttu-id="6b5ae-109">설명</span><span class="sxs-lookup"><span data-stu-id="6b5ae-109">Description</span></span></th>
<th><span data-ttu-id="6b5ae-110">실행 위치</span><span class="sxs-lookup"><span data-stu-id="6b5ae-110">Where run</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1.</p></td>
<td><p><span data-ttu-id="6b5ae-111"><a href="lync-server-2013-preparing-the-active-directory-schema.md">Lync Server 2013에서 Active Directory 스키마 준비</a></span><span class="sxs-lookup"><span data-stu-id="6b5ae-111"><a href="lync-server-2013-preparing-the-active-directory-schema.md">Preparing the Active Directory schema in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6b5ae-112">Lync Server에서 사용 되는 새 클래스 및 특성을 추가 하 여 Active Directory 스키마를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b5ae-112">Extends the Active Directory schema by adding new classes and attributes that are used by Lync Server.</span></span></p>
<p><span data-ttu-id="6b5ae-113">Lync Server를 배포할 배포의 각 포리스트에서 한 번씩 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b5ae-113">Run once for each forest in your deployment where Lync Server will be deployed.</span></span></p></td>
<td><p><span data-ttu-id="6b5ae-114">Lync Server를 배포할 각 포리스트의 루트 도메인에 있는 스키마 마스터에 대해</span><span class="sxs-lookup"><span data-stu-id="6b5ae-114">Against the schema master in the root domain of each forest where Lync Server will be deployed.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="6b5ae-115">스키마 마스터에 대 한 사용 권한이 있는 경우 루트 도메인에서이 단계를 실행할 필요가 없지만 루트 도메인에 있는 Schema Admins 그룹의 구성원 이어야 하 고 스키마 마스터에서 Enterprise Admins 그룹의 구성원이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b5ae-115">You do not need to run this step in the root domain if you have permissions on the schema master, but you must be a member of the Schema Admins group in the root domain and a member of the Enterprise Admins group on the schema master.</span></span> <span data-ttu-id="6b5ae-116">리소스 포리스트 토폴로지에서는이 단계를 사용자 포리스트에서 사용 하지 않고 리소스 포리스트에서만 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b5ae-116">In a resource forest topology, run this step only in the resource forest, not in any user forests.</span></span> <span data-ttu-id="6b5ae-117">중앙 포리스트 토폴로지에서는 사용자 포리스트가 아닌 중앙 포리스트에서만이 단계를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b5ae-117">In a central forest topology, run this step only in the central forest, not in any user forests.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p>2.</p></td>
<td><p><span data-ttu-id="6b5ae-118"><a href="lync-server-2013-preparing-the-forest.md">Lync Server 2013에 대 한 포리스트 준비</a></span><span class="sxs-lookup"><span data-stu-id="6b5ae-118"><a href="lync-server-2013-preparing-the-forest.md">Preparing the forest for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6b5ae-119">Lync Server에서 사용 하는 전역 설정 및 유니버설 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6b5ae-119">Creates global settings and universal groups that are used by Lync Server.</span></span></p>
<p><span data-ttu-id="6b5ae-120">Lync Server를 배포할 배포의 각 포리스트에서 한 번씩 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b5ae-120">Run once for each forest in your deployment where Lync Server will be deployed.</span></span></p></td>
<td><p><span data-ttu-id="6b5ae-121">Lync Server를 배포할 각 포리스트의 루트 도메인</span><span class="sxs-lookup"><span data-stu-id="6b5ae-121">In the root domain of each forest where Lync Server will be deployed.</span></span> <span data-ttu-id="6b5ae-122">이 단계를 실행 하려면 Enterprise Admins 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b5ae-122">To run this step, you must be a member of the Enterprise Admins group.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="6b5ae-123">리소스 포리스트 토폴로지에서는이 단계를 사용자 포리스트에서 사용 하지 않고 리소스 포리스트에서만 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b5ae-123">In a resource forest topology, run this step only in the resource forest, not in any user forests.</span></span> <span data-ttu-id="6b5ae-124">중앙 포리스트 토폴로지에서는 사용자 포리스트가 아닌 중앙 포리스트에서만이 단계를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b5ae-124">In a central forest topology, run this step only in the central forest, not in any user forests.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p>3.</p></td>
<td><p><span data-ttu-id="6b5ae-125"><a href="lync-server-2013-preparing-domains.md">Lync Server 2013에 대 한 도메인 준비</a></span><span class="sxs-lookup"><span data-stu-id="6b5ae-125"><a href="lync-server-2013-preparing-domains.md">Preparing domains for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6b5ae-126">유니버설 그룹의 구성원에 게 사용할 개체에 대 한 사용 권한을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b5ae-126">Adds permissions on objects to be used by members of universal groups.</span></span></p>
<p><span data-ttu-id="6b5ae-127">사용자 도메인 또는 서버 도메인 별로 한 번씩 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b5ae-127">Run once per user domain or server domain.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="6b5ae-128">Lync Server 2010에서 Lync Server 2013로 마이그레이션하는 경우 배포 마법사에서 도메인 준비가 이미 완료 된 것으로 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b5ae-128">If you are migrating from Lync Server 2010 to Lync Server 2013, the Deployment Wizard may indicate that domain preparation is already complete.</span></span> <span data-ttu-id="6b5ae-129">도메인 준비를 다시 실행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6b5ae-129">You do not need to run domain preparation again.</span></span> <span data-ttu-id="6b5ae-130">사용 권한이 Lync Server 2010에서 Lync Server 2013로 변경 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="6b5ae-130">Permissions were not changed from Lync Server 2010 to Lync Server 2013.</span></span>


</div></td>
<td><p><span data-ttu-id="6b5ae-131">Lync Server를 배포할 각 도메인의 구성원 서버</span><span class="sxs-lookup"><span data-stu-id="6b5ae-131">On a member server in each domain where Lync Server will be deployed.</span></span> <span data-ttu-id="6b5ae-132">이 단계를 실행 하려면 Domain Admins 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b5ae-132">To run this step, you must be a member of the Domain Admins group.</span></span></p></td>
</tr>
</tbody>
</table>


<div id="sectionSection0" class="section">

<span data-ttu-id="6b5ae-133">Lync server 2010와 같은 lync 서버 2013는 Office Communications Server 2007 r 2의 경우 처럼 AD DS 대신 중앙 관리 저장소에 많은 구성 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b5ae-133">Lync Server 2013, like Lync Server 2010, stores much of the configuration information in the Central Management store instead of in AD DS as was the case in Office Communications Server 2007 R2.</span></span> <span data-ttu-id="6b5ae-134">그러나 AD DS에 저장 되는 정보는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6b5ae-134">However, the following information is stored in AD DS:</span></span>

  - <span data-ttu-id="6b5ae-135">**스키마 확장**:</span><span class="sxs-lookup"><span data-stu-id="6b5ae-135">**Schema extensions**:</span></span>
    
      - <span data-ttu-id="6b5ae-136">사용자 개체 확장</span><span class="sxs-lookup"><span data-stu-id="6b5ae-136">User object extensions</span></span>
    
      - <span data-ttu-id="6b5ae-137">이전 버전과의 호환성을 유지 하기 위한 Office Communications Server 2007 R2 클래스에 대 한 확장</span><span class="sxs-lookup"><span data-stu-id="6b5ae-137">Extensions for Office Communications Server 2007 R2 classes to maintain backward compatibility</span></span>

<!-- end list -->

  - <span data-ttu-id="6b5ae-138">**데이터** (Lync Server 확장 스키마 및 기존 스키마 클래스에 저장):</span><span class="sxs-lookup"><span data-stu-id="6b5ae-138">**Data** (stored in Lync Server extended schema and in existing schema classes):</span></span>
    
      - <span data-ttu-id="6b5ae-139">사용자 SIP URI(Uniform Resource Identifier) 및 기타 사용자 설정</span><span class="sxs-lookup"><span data-stu-id="6b5ae-139">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
      - <span data-ttu-id="6b5ae-140">응답 그룹 및 회의 길잡이 등과 같은 응용 프로그램에 대한 대화 상대 개체</span><span class="sxs-lookup"><span data-stu-id="6b5ae-140">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
      - <span data-ttu-id="6b5ae-141">중앙 관리 저장소에 대한 포인터</span><span class="sxs-lookup"><span data-stu-id="6b5ae-141">A pointer to the Central Management store</span></span>
    
      - <span data-ttu-id="6b5ae-142">Kerberos 인증 계정(선택적 컴퓨터 개체)</span><span class="sxs-lookup"><span data-stu-id="6b5ae-142">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="6b5ae-143">Lync Server 2013에서는 RTCUniversalServerAdmins 유니버설 그룹에 대 한 설치 권한을 부여 하 여 설치 및 관리를 위임 하므로 해당 그룹의 구성원이 로컬 서버에서 Lync Server 2013을 설치 하 고 활성화할 수 있습니다 (서버를 토폴로지에 추가 하 고 게시 하 고 사용 하도록 설정한 후).</span><span class="sxs-lookup"><span data-stu-id="6b5ae-143">In Lync Server 2013, you delegate setup and administration by granting setup permissions to the RTCUniversalServerAdmins universal group so that members of that group can install and activate Lync Server 2013 on a local server (after the server has been added to the topology, published, and enabled).</span></span> <span data-ttu-id="6b5ae-144">위임 된 사용자는 Lync Server 2013을 설치 하 고 활성화 하는 컴퓨터의 로컬 관리자 여야 하지만 Domain Admins 그룹의 구성원 일 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6b5ae-144">The delegated users must be local administrators on the computer where they are installing and activating Lync Server 2013, but they do not need to be members of the Domain Admins group.</span></span> <span data-ttu-id="6b5ae-145">또한 지정 된 Ou (조직 구성 단위)에서 개체에 대 한 사용 권한을 부여 하 여 포리스트 준비 중에 만들어지는 유니버설 그룹의 구성원이 Domain Admins 그룹의 구성원이 없어도 해당 개체에 액세스할 수 있도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b5ae-145">You can also grant permissions for objects in specified organizational units (OUs) so that members of the universal groups created during forest preparation can access those objects without being members of the Domain Admins group.</span></span>

<span data-ttu-id="6b5ae-146">Lync Server 2013의 새 배포의 경우 전역 설정을 구성 컨테이너에 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b5ae-146">For new deployments of Lync Server 2013, global settings must be stored in the Configuration container.</span></span> <span data-ttu-id="6b5ae-147">조직이 이전 버전에서 업그레이드 되는 동안 여전히 System 컨테이너에 전역 설정이 있으면 System 컨테이너가 여전히 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b5ae-147">If your organization is upgrading from an earlier version and you still have global settings in the System container, the System container is still supported.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6b5ae-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6b5ae-148">See Also</span></span>


[<span data-ttu-id="6b5ae-149">Lync Server 2013에서 Active Directory 스키마 준비</span><span class="sxs-lookup"><span data-stu-id="6b5ae-149">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
[<span data-ttu-id="6b5ae-150">Lync Server 2013에서 사용 하는 Active Directory 스키마 확장, 클래스 및 특성</span><span class="sxs-lookup"><span data-stu-id="6b5ae-150">Active Directory schema extensions, classes, and attributes used by Lync Server 2013</span></span>](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)  


[<span data-ttu-id="6b5ae-151">Lync Server 2013에 대 한 포리스트 준비</span><span class="sxs-lookup"><span data-stu-id="6b5ae-151">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
[<span data-ttu-id="6b5ae-152">Lync Server 2013에 대 한 도메인 준비</span><span class="sxs-lookup"><span data-stu-id="6b5ae-152">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

