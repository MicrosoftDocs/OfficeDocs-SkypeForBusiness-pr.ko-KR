---
title: 'Lync Server 2013: Active Directory 도메인 서비스 준비 개요'
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
ms.openlocfilehash: 4590a3aff21683b12d22a1253522d6c49f626957
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153308"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-active-directory-domain-services-preparation-in-lync-server-2013"></a><span data-ttu-id="b3fd8-102">Lync Server 2013의 Active Directory 도메인 서비스 준비 개요</span><span class="sxs-lookup"><span data-stu-id="b3fd8-102">Overview of Active Directory Domain Services preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3fd8-103">_**마지막으로 수정 된 항목:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="b3fd8-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="b3fd8-104">Lync Server 2013 배포에 대 한 Active Directory 도메인 서비스를 준비 하려면 특정 순서에 따라 세 가지 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd8-104">To prepare Active Directory Domain Services for your Lync Server 2013 deployment, you must perform three steps in a specific sequence.</span></span>

<span data-ttu-id="b3fd8-105">다음 표에서는 Lync Server 용 AD DS를 준비 하는 데 필요한 단계를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd8-105">The following table describes the steps required to prepare AD DS for Lync Server.</span></span>

### <a name="active-directory-preparation-steps"></a><span data-ttu-id="b3fd8-106">Active Directory 준비 단계</span><span class="sxs-lookup"><span data-stu-id="b3fd8-106">Active Directory Preparation Steps</span></span>

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
<th><span data-ttu-id="b3fd8-107">단계</span><span class="sxs-lookup"><span data-stu-id="b3fd8-107">Step</span></span></th>
<th><span data-ttu-id="b3fd8-108">설명</span><span class="sxs-lookup"><span data-stu-id="b3fd8-108">Description</span></span></th>
<th><span data-ttu-id="b3fd8-109">실행 위치</span><span class="sxs-lookup"><span data-stu-id="b3fd8-109">Where run</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1.</p></td>
<td><p><span data-ttu-id="b3fd8-110"><a href="lync-server-2013-preparing-the-active-directory-schema.md">Lync Server 2013에서 Active Directory 스키마 준비</a></span><span class="sxs-lookup"><span data-stu-id="b3fd8-110"><a href="lync-server-2013-preparing-the-active-directory-schema.md">Preparing the Active Directory schema in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b3fd8-111">Lync Server에서 사용 되는 새 클래스 및 특성을 추가 하 여 Active Directory 스키마를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd8-111">Extends the Active Directory schema by adding new classes and attributes that are used by Lync Server.</span></span></p>
<p><span data-ttu-id="b3fd8-112">Lync Server를 배포할 배포의 각 포리스트에서 한 번씩 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd8-112">Run once for each forest in your deployment where Lync Server will be deployed.</span></span></p></td>
<td><p><span data-ttu-id="b3fd8-113">Lync Server를 배포할 각 포리스트의 루트 도메인에 있는 스키마 마스터에 대해</span><span class="sxs-lookup"><span data-stu-id="b3fd8-113">Against the schema master in the root domain of each forest where Lync Server will be deployed.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="b3fd8-114">스키마 마스터에 대 한 사용 권한이 있는 경우 루트 도메인에서이 단계를 실행할 필요가 없지만 루트 도메인에 있는 Schema Admins 그룹의 구성원 이어야 하 고 스키마 마스터에서 Enterprise Admins 그룹의 구성원이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd8-114">You do not need to run this step in the root domain if you have permissions on the schema master, but you must be a member of the Schema Admins group in the root domain and a member of the Enterprise Admins group on the schema master.</span></span> <span data-ttu-id="b3fd8-115">리소스 포리스트 토폴로지에서는이 단계를 사용자 포리스트에서 사용 하지 않고 리소스 포리스트에서만 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd8-115">In a resource forest topology, run this step only in the resource forest, not in any user forests.</span></span> <span data-ttu-id="b3fd8-116">중앙 포리스트 토폴로지에서는 사용자 포리스트가 아닌 중앙 포리스트에서만이 단계를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd8-116">In a central forest topology, run this step only in the central forest, not in any user forests.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p>2.</p></td>
<td><p><span data-ttu-id="b3fd8-117"><a href="lync-server-2013-preparing-the-forest.md">Lync Server 2013에 대 한 포리스트 준비</a></span><span class="sxs-lookup"><span data-stu-id="b3fd8-117"><a href="lync-server-2013-preparing-the-forest.md">Preparing the forest for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b3fd8-118">Lync Server에서 사용 하는 전역 설정 및 유니버설 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd8-118">Creates global settings and universal groups that are used by Lync Server.</span></span></p>
<p><span data-ttu-id="b3fd8-119">Lync Server를 배포할 배포의 각 포리스트에서 한 번씩 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd8-119">Run once for each forest in your deployment where Lync Server will be deployed.</span></span></p></td>
<td><p><span data-ttu-id="b3fd8-120">Lync Server를 배포할 각 포리스트의 루트 도메인</span><span class="sxs-lookup"><span data-stu-id="b3fd8-120">In the root domain of each forest where Lync Server will be deployed.</span></span> <span data-ttu-id="b3fd8-121">이 단계를 실행 하려면 Enterprise Admins 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd8-121">To run this step, you must be a member of the Enterprise Admins group.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="b3fd8-122">리소스 포리스트 토폴로지에서는이 단계를 사용자 포리스트에서 사용 하지 않고 리소스 포리스트에서만 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd8-122">In a resource forest topology, run this step only in the resource forest, not in any user forests.</span></span> <span data-ttu-id="b3fd8-123">중앙 포리스트 토폴로지에서는 사용자 포리스트가 아닌 중앙 포리스트에서만이 단계를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd8-123">In a central forest topology, run this step only in the central forest, not in any user forests.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p>3.</p></td>
<td><p><span data-ttu-id="b3fd8-124"><a href="lync-server-2013-preparing-domains.md">Lync Server 2013에 대 한 도메인 준비</a></span><span class="sxs-lookup"><span data-stu-id="b3fd8-124"><a href="lync-server-2013-preparing-domains.md">Preparing domains for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b3fd8-125">유니버설 그룹의 구성원에 게 사용할 개체에 대 한 사용 권한을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd8-125">Adds permissions on objects to be used by members of universal groups.</span></span></p>
<p><span data-ttu-id="b3fd8-126">사용자 도메인 또는 서버 도메인 별로 한 번씩 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd8-126">Run once per user domain or server domain.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="b3fd8-127">Lync Server 2010에서 Lync Server 2013로 마이그레이션하는 경우 배포 마법사에서 도메인 준비가 이미 완료 된 것으로 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd8-127">If you are migrating from Lync Server 2010 to Lync Server 2013, the Deployment Wizard may indicate that domain preparation is already complete.</span></span> <span data-ttu-id="b3fd8-128">도메인 준비를 다시 실행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd8-128">You do not need to run domain preparation again.</span></span> <span data-ttu-id="b3fd8-129">사용 권한이 Lync Server 2010에서 Lync Server 2013로 변경 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd8-129">Permissions were not changed from Lync Server 2010 to Lync Server 2013.</span></span>


</div></td>
<td><p><span data-ttu-id="b3fd8-130">Lync Server를 배포할 각 도메인의 구성원 서버</span><span class="sxs-lookup"><span data-stu-id="b3fd8-130">On a member server in each domain where Lync Server will be deployed.</span></span> <span data-ttu-id="b3fd8-131">이 단계를 실행 하려면 Domain Admins 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd8-131">To run this step, you must be a member of the Domain Admins group.</span></span></p></td>
</tr>
</tbody>
</table>


<div id="sectionSection0" class="section">

<span data-ttu-id="b3fd8-132">Lync server 2010와 같은 lync 서버 2013는 Office Communications Server 2007 r 2의 경우 처럼 AD DS 대신 중앙 관리 저장소에 많은 구성 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd8-132">Lync Server 2013, like Lync Server 2010, stores much of the configuration information in the Central Management store instead of in AD DS as was the case in Office Communications Server 2007 R2.</span></span> <span data-ttu-id="b3fd8-133">그러나 AD DS에 저장 되는 정보는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd8-133">However, the following information is stored in AD DS:</span></span>

  - <span data-ttu-id="b3fd8-134">**스키마 확장**:</span><span class="sxs-lookup"><span data-stu-id="b3fd8-134">**Schema extensions**:</span></span>
    
      - <span data-ttu-id="b3fd8-135">사용자 개체 확장</span><span class="sxs-lookup"><span data-stu-id="b3fd8-135">User object extensions</span></span>
    
      - <span data-ttu-id="b3fd8-136">이전 버전과의 호환성을 유지 하기 위한 Office Communications Server 2007 R2 클래스에 대 한 확장</span><span class="sxs-lookup"><span data-stu-id="b3fd8-136">Extensions for Office Communications Server 2007 R2 classes to maintain backward compatibility</span></span>

<!-- end list -->

  - <span data-ttu-id="b3fd8-137">**데이터** (Lync Server 확장 스키마 및 기존 스키마 클래스에 저장):</span><span class="sxs-lookup"><span data-stu-id="b3fd8-137">**Data** (stored in Lync Server extended schema and in existing schema classes):</span></span>
    
      - <span data-ttu-id="b3fd8-138">사용자 SIP URI(Uniform Resource Identifier) 및 기타 사용자 설정</span><span class="sxs-lookup"><span data-stu-id="b3fd8-138">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
      - <span data-ttu-id="b3fd8-139">응답 그룹 및 회의 길잡이 등과 같은 응용 프로그램에 대한 대화 상대 개체</span><span class="sxs-lookup"><span data-stu-id="b3fd8-139">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
      - <span data-ttu-id="b3fd8-140">중앙 관리 저장소에 대한 포인터</span><span class="sxs-lookup"><span data-stu-id="b3fd8-140">A pointer to the Central Management store</span></span>
    
      - <span data-ttu-id="b3fd8-141">Kerberos 인증 계정(선택적 컴퓨터 개체)</span><span class="sxs-lookup"><span data-stu-id="b3fd8-141">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="b3fd8-142">Lync Server 2013에서는 RTCUniversalServerAdmins 유니버설 그룹에 대 한 설치 권한을 부여 하 여 설치 및 관리를 위임 하므로 해당 그룹의 구성원이 로컬 서버에서 Lync Server 2013을 설치 하 고 활성화할 수 있습니다 (서버를 토폴로지, 게시 됨 및 사용 가능)</span><span class="sxs-lookup"><span data-stu-id="b3fd8-142">In Lync Server 2013, you delegate setup and administration by granting setup permissions to the RTCUniversalServerAdmins universal group so that members of that group can install and activate Lync Server 2013 on a local server (after the server has been added to the topology, published, and enabled).</span></span> <span data-ttu-id="b3fd8-143">위임 된 사용자는 Lync Server 2013을 설치 하 고 활성화 하는 컴퓨터의 로컬 관리자 여야 하지만 Domain Admins 그룹의 구성원 일 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd8-143">The delegated users must be local administrators on the computer where they are installing and activating Lync Server 2013, but they do not need to be members of the Domain Admins group.</span></span> <span data-ttu-id="b3fd8-144">또한 지정 된 Ou (조직 구성 단위)에서 개체에 대 한 사용 권한을 부여 하 여 포리스트 준비 중에 만들어지는 유니버설 그룹의 구성원이 Domain Admins 그룹의 구성원이 없어도 해당 개체에 액세스할 수 있도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd8-144">You can also grant permissions for objects in specified organizational units (OUs) so that members of the universal groups created during forest preparation can access those objects without being members of the Domain Admins group.</span></span>

<span data-ttu-id="b3fd8-145">Lync Server 2013의 새 배포의 경우 전역 설정을 구성 컨테이너에 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd8-145">For new deployments of Lync Server 2013, global settings must be stored in the Configuration container.</span></span> <span data-ttu-id="b3fd8-146">조직이 이전 버전에서 업그레이드 되는 동안 여전히 System 컨테이너에 전역 설정이 있으면 System 컨테이너가 여전히 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3fd8-146">If your organization is upgrading from an earlier version and you still have global settings in the System container, the System container is still supported.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b3fd8-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b3fd8-147">See Also</span></span>


[<span data-ttu-id="b3fd8-148">Lync Server 2013에서 Active Directory 스키마 준비</span><span class="sxs-lookup"><span data-stu-id="b3fd8-148">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
[<span data-ttu-id="b3fd8-149">Lync Server 2013에서 사용 하는 Active Directory 스키마 확장, 클래스 및 특성</span><span class="sxs-lookup"><span data-stu-id="b3fd8-149">Active Directory schema extensions, classes, and attributes used by Lync Server 2013</span></span>](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)  


[<span data-ttu-id="b3fd8-150">Lync Server 2013에 대 한 포리스트 준비</span><span class="sxs-lookup"><span data-stu-id="b3fd8-150">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
[<span data-ttu-id="b3fd8-151">Lync Server 2013에 대 한 도메인 준비</span><span class="sxs-lookup"><span data-stu-id="b3fd8-151">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

