---
title: 'Lync Server 2013: 주소록 서비스 관리'
description: 'Lync Server 2013: 주소록 서비스 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administering the Address Book Service
ms:assetid: 801e4243-9670-4477-aa2f-88b61ecf5351
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429711(v=OCS.15)
ms:contentKeyID: 48184649
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86d549b06b5c6ac1c450edf9e7edb0b902ef9adf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553004"
---
# <a name="administering-the-address-book-service-in-lync-server-2013"></a><span data-ttu-id="70f7b-103">Lync Server 2013에서 주소록 서비스 관리</span><span class="sxs-lookup"><span data-stu-id="70f7b-103">Administering the Address Book Service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70f7b-104">_**마지막으로 수정 된 항목:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="70f7b-104">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="70f7b-105">Lync Server, Enterprise Edition 또는 Standard Edition Server 배포의 일환으로 주소록 서비스가 기본적으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-105">As a part of the deployment of Lync Server, Enterprise Edition or Standard Edition server, the Address Book Service is installed by default.</span></span> <span data-ttu-id="70f7b-106">주소록 서비스에서 사용 되는 데이터베이스 (RTCab)는 SQL Server (Enterprise Edition의 경우에는 백 엔드 SQL Server 인 Standard Edition server의 경우 배치 된 SQL Server)에서 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-106">The database used by the Address Book Service – RTCab – is created on the SQL Server (for Enterprise Edition, this is the back-end SQL Server; for Standard Edition server, the collocated SQL Server).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="70f7b-107"><STRONG>Adsi 편집</STRONG> 을 사용 하 여 Active Directory 도메인 서비스 개체 특성을 편집 하는 방법에 대 한 자세한 내용은 <A href="https://go.microsoft.com/fwlink/?linkid=330427">adsi 편집</A>을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="70f7b-107">For information about using <STRONG>ADSI Edit</STRONG> to edit Active Directory Domain Services object attributes, see <A href="https://go.microsoft.com/fwlink/?linkid=330427">ADSI Edit</A>.</span></span> <span data-ttu-id="70f7b-108">주소록 서비스에 대 한 리소스 키트의 도구에 대 한 자세한 내용은 <A href="https://go.microsoft.com/fwlink/?linkid=330429">Microsoft Lync Server 2013 Resource Kit Tools</A>를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="70f7b-108">For information about a tool in the Resource Kit specifically for the Address Book service, see <A href="https://go.microsoft.com/fwlink/?linkid=330429">Microsoft Lync Server 2013 Resource Kit Tools</A>.</span></span>



</div>

<div>

## <a name="address-book-server-phone-number-normalization"></a><span data-ttu-id="70f7b-109">주소록 서버 전화 번호 정규화</span><span class="sxs-lookup"><span data-stu-id="70f7b-109">Address Book Server Phone Number Normalization</span></span>

<span data-ttu-id="70f7b-110">Lync Server에는 표준화 된 RFC 3966/E. 164 휴대폰 번호가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-110">Lync Server requires standardized RFC 3966/E.164 phone numbers.</span></span> <span data-ttu-id="70f7b-111">형식이 지정 되지 않거나 일관성 없는 전화 번호를 사용 하기 위해 Lync Server는 주소록 서버에 의존 하 여 정규화 규칙으로 전달 되기 전에 전화 번호를 전처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-111">To use phone numbers that are unstructured or inconsistently formatted, Lync Server relies on the Address Book Server to preprocess phone numbers before they are handed off to the normalization rules.</span></span> <span data-ttu-id="70f7b-112">주소록에서 전화 번호를 사용 하 고 정규화 규칙을 적용 하면 Lync Phone Edition과 Lync Mobile과 같은 클라이언트에서 이러한 정규화 된 번호를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-112">When a phone number is used from the address book and the normalization rule is applied, clients, such as Lync Phone Edition and Lync Mobile, can use these normalized numbers.</span></span>

<span data-ttu-id="70f7b-p104">이전 버전에서 사용된 정규화 규칙을 적용하려면 일부 설정을 조정해야 합니다. 공백 및 필수가 아닌 문자는 정규화 규칙이 적용되기 전에 제거되기 때문에 regex 식에서 특별히 대시 또는 제거된 다른 문자를 찾는 경우 정규화 규칙이 실패할 수 있습니다. 정규화 규칙을 검토하여 이러한 필수가 아닌 문자를 찾지 않는지 또는 규칙에서 예상하는 곳에 문자가 없는 경우 규칙이 정상적으로 실패하고 계속 적용될 수 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-p104">The normalization rules that were used in previous versions may not work properly without some adjustments. Because the white space and non-mandatory characters are removed prior to the normalization rules, if your regex expression is specifically looking for a dash or other character that was removed, your normalization rule might fail. You should review your normalization rules to ensure that either they are not looking for these non-mandatory characters, or that the rule can fail gracefully and continue in the event that the character is not present where the rule anticipates it will be.</span></span>

</div>

<div>

## <a name="user-replicator-and-address-book-server"></a><span data-ttu-id="70f7b-116">User Replicator와 주소록 서버</span><span class="sxs-lookup"><span data-stu-id="70f7b-116">User Replicator and Address Book Server</span></span>

<span data-ttu-id="70f7b-117">주소록 서버는 사용자 복제기에서 제공 하는 데이터를 사용 하 여 처음에 GAL (전체 주소 목록)에서 가져온 정보를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-117">The Address Book Server uses data provided by User Replicator to update the information that it initially obtains from the global address list (GAL).</span></span> <span data-ttu-id="70f7b-118">사용자 복제기는 각 사용자, 연락처 및 그룹에 대 한 Active Directory 도메인 서비스 특성을 데이터베이스의 AbUserEntry 테이블에 쓰고 주소록 서버는 데이터베이스의 사용자 데이터를 주소록 서버 파일 저장소의 파일과 주소록 데이터베이스 RTCab에 동기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-118">User Replicator writes the Active Directory Domain Services attributes for each user, contact, and group into the AbUserEntry table in the database and the Address Book Server syncs the user data from the database into files in the Address Book Server file store and into the Address Book database RTCab.</span></span> <span data-ttu-id="70f7b-119">AbUserEntry 테이블에 대 한 스키마는 **Userguid** 및 **UserData**라는 두 개의 열을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-119">The schema for the AbUserEntry table uses two columns, **UserGuid** and **UserData**.</span></span> <span data-ttu-id="70f7b-120">**Userguid** 는 인덱스 열로, Active Directory 개체의 16 바이트 GUID를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-120">**UserGuid** is the index column and contains the 16-byte GUID of the Active Directory object.</span></span> <span data-ttu-id="70f7b-121">**UserData** 는 해당 연락처에 대해 앞에서 설명한 모든 Active Directory 도메인 서비스 특성을 포함 하는 이미지 열입니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-121">**UserData** is an image column which contains all of the previously mentioned Active Directory Domain Services attributes for that contact.</span></span>

<span data-ttu-id="70f7b-122">사용자 복제기는 AbUserEntry 테이블과 같은 SQL Server 기반 인스턴스에 있는 구성 테이블을 읽어 작성할 Active Directory 특성을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-122">User Replicator determines which Active Directory attributes to write by reading a configuration table located in the same SQL Server-based instance as the AbUserEntry table.</span></span> <span data-ttu-id="70f7b-123">AbAttribute 테이블에는 **ID**, **이름**, **플래그** 및 **사용**이라는 세 개의 열이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-123">The AbAttribute table contains three columns, **ID**, **Name**, **Flags**, and **Enable**.</span></span> <span data-ttu-id="70f7b-124">이 테이블은 데이터베이스 설정 중에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-124">The table is created during database setup.</span></span> <span data-ttu-id="70f7b-125">AbAttribute 테이블이 비어 있는 경우 User Replicator는 해당 AbUserEntry 테이블 처리 논리를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-125">If the AbAttribute table is empty, User Replicator skips its AbUserEntry table processing logic.</span></span> <span data-ttu-id="70f7b-126">주소록 서버 특성은 동적이며 주소록 서버가 활성화될 때 주소록 서버에서 처음으로 작성한 AbAttribute 테이블에서 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-126">Address Book Server attributes are dynamic and are retrieved from the AbAttribute table, which is initially written by the Address Book Server when the Address Book Server is activated.</span></span>

<span data-ttu-id="70f7b-127">주소록 서버 활성화 AbAttribute 테이블에 다음 표에 나와 있는 값을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-127">Address Book Server activation populates the AbAttribute table with the values shown in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="70f7b-128">ID</span><span class="sxs-lookup"><span data-stu-id="70f7b-128">ID</span></span></th>
<th><span data-ttu-id="70f7b-129">이름</span><span class="sxs-lookup"><span data-stu-id="70f7b-129">Name</span></span></th>
<th><span data-ttu-id="70f7b-130">부호가</span><span class="sxs-lookup"><span data-stu-id="70f7b-130">Flags</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="70f7b-131">1 </span><span class="sxs-lookup"><span data-stu-id="70f7b-131">1</span></span></p></td>
<td><p><span data-ttu-id="70f7b-132">givenName</span><span class="sxs-lookup"><span data-stu-id="70f7b-132">givenName</span></span></p></td>
<td><p><span data-ttu-id="70f7b-133">0x01400000</span><span class="sxs-lookup"><span data-stu-id="70f7b-133">0x01400000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70f7b-134">2</span><span class="sxs-lookup"><span data-stu-id="70f7b-134">2</span></span></p></td>
<td><p><span data-ttu-id="70f7b-135">Sn</span><span class="sxs-lookup"><span data-stu-id="70f7b-135">Sn</span></span></p></td>
<td><p><span data-ttu-id="70f7b-136">0x02400000</span><span class="sxs-lookup"><span data-stu-id="70f7b-136">0x02400000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70f7b-137">3(sp3)</span><span class="sxs-lookup"><span data-stu-id="70f7b-137">3</span></span></p></td>
<td><p><span data-ttu-id="70f7b-138">displayName</span><span class="sxs-lookup"><span data-stu-id="70f7b-138">displayName</span></span></p></td>
<td><p><span data-ttu-id="70f7b-139">0x03420000</span><span class="sxs-lookup"><span data-stu-id="70f7b-139">0x03420000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70f7b-140">4 </span><span class="sxs-lookup"><span data-stu-id="70f7b-140">4</span></span></p></td>
<td><p><span data-ttu-id="70f7b-141">제목</span><span class="sxs-lookup"><span data-stu-id="70f7b-141">Title</span></span></p></td>
<td><p><span data-ttu-id="70f7b-142">0x04000000</span><span class="sxs-lookup"><span data-stu-id="70f7b-142">0x04000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70f7b-143">5 </span><span class="sxs-lookup"><span data-stu-id="70f7b-143">5</span></span></p></td>
<td><p><span data-ttu-id="70f7b-144">mailNickname</span><span class="sxs-lookup"><span data-stu-id="70f7b-144">mailNickname</span></span></p></td>
<td><p><span data-ttu-id="70f7b-145">0x05400000</span><span class="sxs-lookup"><span data-stu-id="70f7b-145">0x05400000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70f7b-146">6 </span><span class="sxs-lookup"><span data-stu-id="70f7b-146">6</span></span></p></td>
<td><p><span data-ttu-id="70f7b-147">Company</span><span class="sxs-lookup"><span data-stu-id="70f7b-147">Company</span></span></p></td>
<td><p><span data-ttu-id="70f7b-148">0x06000000</span><span class="sxs-lookup"><span data-stu-id="70f7b-148">0x06000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70f7b-149">7 </span><span class="sxs-lookup"><span data-stu-id="70f7b-149">7</span></span></p></td>
<td><p><span data-ttu-id="70f7b-150">physicalDeliveryOfficeName</span><span class="sxs-lookup"><span data-stu-id="70f7b-150">physicalDeliveryOfficeName</span></span></p></td>
<td><p><span data-ttu-id="70f7b-151">0x07000000</span><span class="sxs-lookup"><span data-stu-id="70f7b-151">0x07000000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70f7b-152">8 </span><span class="sxs-lookup"><span data-stu-id="70f7b-152">8</span></span></p></td>
<td><p><span data-ttu-id="70f7b-153">Msrtcsip-gateways-Msrtcsip-primaryuseraddress</span><span class="sxs-lookup"><span data-stu-id="70f7b-153">msRTCSIP-PrimaryUserAddress</span></span></p></td>
<td><p><span data-ttu-id="70f7b-154">0x08520C00</span><span class="sxs-lookup"><span data-stu-id="70f7b-154">0x08520C00</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70f7b-155">9 </span><span class="sxs-lookup"><span data-stu-id="70f7b-155">9</span></span></p></td>
<td><p><span data-ttu-id="70f7b-156">telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="70f7b-156">telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="70f7b-157">0x09022800</span><span class="sxs-lookup"><span data-stu-id="70f7b-157">0x09022800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70f7b-158">10  </span><span class="sxs-lookup"><span data-stu-id="70f7b-158">10</span></span></p></td>
<td><p><span data-ttu-id="70f7b-159">homePhone</span><span class="sxs-lookup"><span data-stu-id="70f7b-159">homePhone</span></span></p></td>
<td><p><span data-ttu-id="70f7b-160">0x0A302800</span><span class="sxs-lookup"><span data-stu-id="70f7b-160">0x0A302800</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70f7b-161">11 </span><span class="sxs-lookup"><span data-stu-id="70f7b-161">11</span></span></p></td>
<td><p><span data-ttu-id="70f7b-162">Mobile</span><span class="sxs-lookup"><span data-stu-id="70f7b-162">Mobile</span></span></p></td>
<td><p><span data-ttu-id="70f7b-163">0x0B622800</span><span class="sxs-lookup"><span data-stu-id="70f7b-163">0x0B622800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70f7b-164">12 </span><span class="sxs-lookup"><span data-stu-id="70f7b-164">12</span></span></p></td>
<td><p><span data-ttu-id="70f7b-165">otherTelephone</span><span class="sxs-lookup"><span data-stu-id="70f7b-165">otherTelephone</span></span></p></td>
<td><p><span data-ttu-id="70f7b-166">0x0C302000</span><span class="sxs-lookup"><span data-stu-id="70f7b-166">0x0C302000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70f7b-167">13 </span><span class="sxs-lookup"><span data-stu-id="70f7b-167">13</span></span></p></td>
<td><p><span data-ttu-id="70f7b-168">ipPhone</span><span class="sxs-lookup"><span data-stu-id="70f7b-168">ipPhone</span></span></p></td>
<td><p><span data-ttu-id="70f7b-169">0x0D302000</span><span class="sxs-lookup"><span data-stu-id="70f7b-169">0x0D302000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70f7b-170">14 </span><span class="sxs-lookup"><span data-stu-id="70f7b-170">14</span></span></p></td>
<td><p><span data-ttu-id="70f7b-171">메일로</span><span class="sxs-lookup"><span data-stu-id="70f7b-171">Mail</span></span></p></td>
<td><p><span data-ttu-id="70f7b-172">0x0E500000</span><span class="sxs-lookup"><span data-stu-id="70f7b-172">0x0E500000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70f7b-173">15 </span><span class="sxs-lookup"><span data-stu-id="70f7b-173">15</span></span></p></td>
<td><p><span data-ttu-id="70f7b-174">groupType</span><span class="sxs-lookup"><span data-stu-id="70f7b-174">groupType</span></span></p></td>
<td><p><span data-ttu-id="70f7b-175">0x0F010800</span><span class="sxs-lookup"><span data-stu-id="70f7b-175">0x0F010800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70f7b-176">16 </span><span class="sxs-lookup"><span data-stu-id="70f7b-176">16</span></span></p></td>
<td><p><span data-ttu-id="70f7b-177">부서</span><span class="sxs-lookup"><span data-stu-id="70f7b-177">Department</span></span></p></td>
<td><p><span data-ttu-id="70f7b-178">0x10000000</span><span class="sxs-lookup"><span data-stu-id="70f7b-178">0x10000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70f7b-179">17 </span><span class="sxs-lookup"><span data-stu-id="70f7b-179">17</span></span></p></td>
<td><p><span data-ttu-id="70f7b-180">설명</span><span class="sxs-lookup"><span data-stu-id="70f7b-180">Description</span></span></p></td>
<td><p><span data-ttu-id="70f7b-181">0x11000100</span><span class="sxs-lookup"><span data-stu-id="70f7b-181">0x11000100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70f7b-182">18 </span><span class="sxs-lookup"><span data-stu-id="70f7b-182">18</span></span></p></td>
<td><p><span data-ttu-id="70f7b-183">관리자</span><span class="sxs-lookup"><span data-stu-id="70f7b-183">Manager</span></span></p></td>
<td><p><span data-ttu-id="70f7b-184">0x12040001</span><span class="sxs-lookup"><span data-stu-id="70f7b-184">0x12040001</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70f7b-185">인치</span><span class="sxs-lookup"><span data-stu-id="70f7b-185">19</span></span></p></td>
<td><p><span data-ttu-id="70f7b-186">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="70f7b-186">proxyAddress</span></span></p></td>
<td><p><span data-ttu-id="70f7b-187">0x00500105</span><span class="sxs-lookup"><span data-stu-id="70f7b-187">0x00500105</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70f7b-188">20cm(8</span><span class="sxs-lookup"><span data-stu-id="70f7b-188">20</span></span></p></td>
<td><p><span data-ttu-id="70f7b-189">msExchHideFromAddressLists</span><span class="sxs-lookup"><span data-stu-id="70f7b-189">msExchHideFromAddressLists</span></span></p></td>
<td><p><span data-ttu-id="70f7b-190">0xFF000003</span><span class="sxs-lookup"><span data-stu-id="70f7b-190">0xFF000003</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70f7b-191">99</span><span class="sxs-lookup"><span data-stu-id="70f7b-191">99</span></span></p></td>
<td><p><span data-ttu-id="70f7b-192">entryID</span><span class="sxs-lookup"><span data-stu-id="70f7b-192">entryID</span></span></p></td>
<td><p><span data-ttu-id="70f7b-193">0x99000000</span><span class="sxs-lookup"><span data-stu-id="70f7b-193">0x99000000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="70f7b-194">**ID** 열의 숫자는 고유해야 하며 재사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-194">The numbers in the **ID** column must be unique and should never be reused.</span></span> <span data-ttu-id="70f7b-195">또한 ID 값을 256 미만으로 유지하면 주소록 서버에서 작성하는 출력 파일의 공간이 절약됩니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-195">Also, keeping the ID values under 256 saves space in the output files written by the Address Book Server.</span></span> <span data-ttu-id="70f7b-196">그러나 최대 ID 값은 65535입니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-196">However, the maximum ID value is 65535.</span></span> <span data-ttu-id="70f7b-197">**이름** 열은 사용자 복제기가 각 연락처에 대해 AbUserEntry 테이블에 저장 해야 하는 Active Directory 특성 이름에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-197">The **Name** column corresponds to the Active Directory attribute name that User Replicator should put in the AbUserEntry table for each contact.</span></span> <span data-ttu-id="70f7b-198">**플래그** 열의 값은 특성 유형을 정의하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-198">The value in the **Flags** column is used to define the type of attribute.</span></span> <span data-ttu-id="70f7b-199">User Replicator에서 인식되는 주소록 서버 특성의 유형은 다음과 같으며, **플래그** 열 값의 낮은 바이트로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-199">The following types of Address Book Server attributes are recognized by User Replicator, indicated by the low byte of the value in the **Flags** column.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="70f7b-200">특성</span><span class="sxs-lookup"><span data-stu-id="70f7b-200">Attribute</span></span></th>
<th><span data-ttu-id="70f7b-201">설명</span><span class="sxs-lookup"><span data-stu-id="70f7b-201">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="70f7b-202">0</span><span class="sxs-lookup"><span data-stu-id="70f7b-202">0x0</span></span></p></td>
<td><p><span data-ttu-id="70f7b-p108">문자열 특성입니다. User Replicator는 이 유형을 AbUserEntry 테이블에 저장하기 전에 UTF-8로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-p108">A string attribute. User Replicator converts this type to UTF-8 before storing it in the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70f7b-205">이면</span><span class="sxs-lookup"><span data-stu-id="70f7b-205">0x1</span></span></p></td>
<td><p><span data-ttu-id="70f7b-p109">이진 특성입니다. User Replicator는 이 유형을 변환하지 않고 blob에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-p109">A binary attribute. User Replicator stores this in the blob without any conversion.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70f7b-208">0x2</span><span class="sxs-lookup"><span data-stu-id="70f7b-208">0x2</span></span></p></td>
<td><p><span data-ttu-id="70f7b-209">특성 값이 tel:로 시작 하는 경우에만 포함 되는 string 특성입니다 &quot; &quot; .</span><span class="sxs-lookup"><span data-stu-id="70f7b-209">A string attribute, but is included only if the attribute value begins with &quot;tel:&quot;.</span></span> <span data-ttu-id="70f7b-210">주로 다중값 문자열 특성(특히 <strong>proxyAddresses</strong>)에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-210">This is primarily for multi-valued string attributes, specifically <strong>proxyAddresses</strong>.</span></span> <span data-ttu-id="70f7b-211">이 경우 주소록 서버는 tel:로 시작 하는 <strong>proxyAddresses</strong> 항목에만 관심이 &quot; &quot; 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-211">In this case, Address Book Server is interested only in <strong>proxyAddresses</strong> entries that begin with &quot;tel:&quot;.</span></span> <span data-ttu-id="70f7b-212">따라서 공간을 절약 하기 위해 사용자 복제기는 tel:로 시작 하는 항목만 저장 합니다 &quot; &quot; .</span><span class="sxs-lookup"><span data-stu-id="70f7b-212">Therefore, in the interest of saving space, User Replicator stores only the entries that begin with &quot;tel:&quot;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70f7b-213">0x3</span><span class="sxs-lookup"><span data-stu-id="70f7b-213">0x3</span></span></p></td>
<td><p><span data-ttu-id="70f7b-p111">부울 문자열 특성입니다. TRUE로 설정하면 User Replicator가 AbUserEntry 테이블에 해당 연락처를 포함하지 않고, FALSE로 설정하면 User Replicator가 AbUserEntry 테이블에 해당 연락처의 특성을 포함합니다(이 플래그가 있는 특정 특성은 제외). 이는 주로 <strong>msExchHideFromAddressLists</strong> 특성에 사용되는 또 다른 특별한 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-p111">A Boolean string attribute, which if TRUE causes User Replicator to not include this contact in the AbUserEntry table. If FALSE, it causes User Replicator to include the attributes for this contact in the AbUserEntry table, but not the particular attribute with this flag. This is another special case type that is primarily for the <strong>msExchHideFromAddressLists</strong> attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70f7b-217">0x4</span><span class="sxs-lookup"><span data-stu-id="70f7b-217">0x4</span></span></p></td>
<td><p><span data-ttu-id="70f7b-218">특성 값이 &quot; smtp:로 시작 &quot; 하 고 기호를 포함 하는 경우에만 포함 되는 문자열 특성입니다 &quot; @ &quot; .</span><span class="sxs-lookup"><span data-stu-id="70f7b-218">A string attribute, but is included only if the attribute value begins with &quot;smtp:&quot; and includes the &quot;@&quot; symbol.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70f7b-219">0x5</span><span class="sxs-lookup"><span data-stu-id="70f7b-219">0x5</span></span></p></td>
<td><p><span data-ttu-id="70f7b-220">특성 값이 &quot; tel: &quot; 또는 &quot; smtp:로 시작 &quot; 하 고 기호를 포함 &quot; @ &quot; 하는 경우에만 포함 되는 문자열 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-220">A string attribute, but is included only if the attribute value begins with either &quot;tel:&quot; or &quot;smtp:&quot; and includes the &quot;@&quot; symbol.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70f7b-221">0x100</span><span class="sxs-lookup"><span data-stu-id="70f7b-221">0x100</span></span></p></td>
<td><p><span data-ttu-id="70f7b-222">이 유형은 설정된 경우 각 연락처에 대해 두 번 이상 표시될 수 있는 다중값 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-222">If set, this is a multi-valued attribute that can appear more than once for each contact.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70f7b-223">0x400</span><span class="sxs-lookup"><span data-stu-id="70f7b-223">0x400</span></span></p></td>
<td><p><span data-ttu-id="70f7b-p112">이 유형은 설정된 경우 연락처의 전자 메일 사용자 계정 이름 특성을 나타냅니다. 주소록 서버는 이 플래그를 사용하여 전화 정규화 이벤트 로그 항목에 표시할 특성 값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-p112">If set, this identifies the email user account name attribute for a contact. Address Book Server uses this flag to identify which attribute value to show in the phone normalization event log entry.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70f7b-226">0x800</span><span class="sxs-lookup"><span data-stu-id="70f7b-226">0x800</span></span></p></td>
<td><p><span data-ttu-id="70f7b-p113">이 유형은 설정된 경우 연락처의 필수 특성을 나타냅니다. 주소록 서버는 Active Directory에 이 특성에 대한 값이 있는 경우에만 AbUserEntry 테이블에 사용자를 포함합니다. 둘 이상의 필수 특성이 있는 경우 둘 중 하나의 값만 있으면 AbUserEntry 테이블에 사용자를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-p113">If set, this identifies a required attribute for a contact. Address Book Server includes a user in the AbUserEntry table only if there is a value for this attribute in Active Directory. If there is more than one required attribute, only one of them is required to have a value to include the user in the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70f7b-230">0x1000</span><span class="sxs-lookup"><span data-stu-id="70f7b-230">0x1000</span></span></p></td>
<td><p><span data-ttu-id="70f7b-231">이 유형이 설정된 경우 주소록 서버에서 이 특성 값을 항상 정규화합니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-231">If set, Address Book Server always normalizes the value of this attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70f7b-232">0x2000</span><span class="sxs-lookup"><span data-stu-id="70f7b-232">0x2000</span></span></p></td>
<td><p><span data-ttu-id="70f7b-233">이 유형이 설정된 경우 주소록 서버에서 <strong>proxyAddresses</strong>의 정규화된 번호를 사용합니다. 단, <strong>UseNormalizationRules</strong> CMS 설정이 FALSE로 설정되어 있어야 하며, 그렇지 않은 경우 플래그 비트가 0x1000인 경우와 동일하게 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-233">If set, Address Book Server uses the normalized number from <strong>proxyAddresses</strong>, if the <strong>UseNormalizationRules</strong> CMS setting is FALSE; otherwise it behaves the same as when the flag bit is 0x1000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70f7b-234">0x4000</span><span class="sxs-lookup"><span data-stu-id="70f7b-234">0x4000</span></span></p></td>
<td><p><span data-ttu-id="70f7b-p114">이 유형이 설정된 경우 주소록 서버에서 지정된 특성에 대해 이 값을 가진 개체를 AbUserEntry 테이블에 포함하지 않습니다. 예를 들어 <strong>msRTCSIP-PrimaryUserAddress</strong> 특성에 이 플래그 비트가 설정된 경우 이 특성을 가진 연락처가 데이터베이스에 기록되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-p114">If set, Address Book Server does not include objects in the AbUserEntry table that have this value for the specified attribute. For example, if the <strong>msRTCSIP-PrimaryUserAddress</strong> attribute has this flag bit set, then contacts that have this attribute are not written to the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70f7b-237">0x8000</span><span class="sxs-lookup"><span data-stu-id="70f7b-237">0x8000</span></span></p></td>
<td><p><span data-ttu-id="70f7b-p115">이 유형이 설정된 경우 주소록 서버에서 지정된 특성에 대해 이 값을 가지지 않은 개체를 AbUserEntry 테이블에 포함하지 않습니다. 하나의 개체에 0x4000 및 0x8000 플래그 비트가 둘 다 설정된 경우에는 플래그 비트 값이 0x4000으로 설정된 특성이 우선적으로 적용되므로 개체가 AbUserEntry 테이블에서 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-p115">If set, Address Book Server does not include objects in the AbUserEntry table that do not have this value for the specified attribute. If both the 0x4000 and 0x8000 flag bits are set on an object, the attribute with the flag bit value set to 0x4000 takes precedence, and the object is excluded from the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70f7b-240">0x10000</span><span class="sxs-lookup"><span data-stu-id="70f7b-240">0x10000</span></span></p></td>
<td><p><span data-ttu-id="70f7b-p116">이 유형은 설정된 경우 그룹 개체를 나타냅니다. User Replicator는 이 플래그 비트를 사용하여 현재 상태가 그룹(예: 메일 그룹 또는 보안 그룹)을 나타내는 <strong>groupType</strong> 특성을 가진 연락처를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-p116">If set, this represents a group object. User Replicator uses this flag bit to include contacts with the <strong>groupType</strong> attribute whose presence indicates a group (for example, a distribution list or security group).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70f7b-243">0x20000</span><span class="sxs-lookup"><span data-stu-id="70f7b-243">0x20000</span></span></p></td>
<td><p><span data-ttu-id="70f7b-244">이 유형이 설정된 경우 User Replicator는 이 플래그 비트를 사용하여 장치별 주소록 서버 파일(즉, 확장명이 .dabs인 파일)에 이 특성을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-244">If set, User Replicator uses this flag bit to include this attribute in device-specific Address Book Server files (that is, files with a .dabs extension).</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="70f7b-245">이전 버전의 Lync Server에서 Active Directory에 변경 내용을 적용 하는 경우 관리자는 **Update-csaddressbook** Windows PowerShell cmdlet을 **실행 하** 여 Lync Server 사용자 데이터베이스 및 rtcab 데이터베이스에 대 한 변경 내용을 즉시 유지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-245">In previous versions of Lync Server, when applying a change to Active Directory, the administrator would be required to run **Update -CSUserDatabase** and **Update –CSAddressBook** Windows PowerShell cmdlets to persist the change to the Lync Server user database and RTCab database immediately.</span></span> <span data-ttu-id="70f7b-246">Lync Server 2013에서는 Lync Server 사용자 복제기가 Active Directory에서 변경 된 내용을 선택 하 고 구성 된 간격에 따라 Lync Server 사용자 데이터베이스를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-246">In Lync Server 2013, Lync Server User Replicator will pick up the changes from Active Directory and update the Lync Server user database based on a configured interval.</span></span> <span data-ttu-id="70f7b-247">또한 Lync Server 사용자 복제기는 관리자가 Update-csaddressbook를 실행 하지 않고 RTCab 데이터베이스에 대 한 변경 내용을 빠르게 전파 합니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-247">Lync Server User Replicator will also propagate the changes to the RTCab database quickly without the administrator having to run Update-CSAddressBook.</span></span> <span data-ttu-id="70f7b-248">주소록 웹 쿼리가 설정된 경우, 변경 내용이 Lync 클라이언트의 검색 결과에 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-248">If Address Book Web query is enabled, then the changes will be reflected in search results by Lync clients.</span></span> <span data-ttu-id="70f7b-249">주소록 파일 다운로드가 설정된 경우 관리자는 Update -CSAddressBook만 실행하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-249">Administrators will only need to run Update -CSAddressBook if the Address Book file download is enabled.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="70f7b-250">기본적으로 Lync Server 사용자 복제기는 5 분 마다 자동으로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-250">By default Lync Server User Replicator runs automatically every 5 minutes.</span></span> <span data-ttu-id="70f7b-251">Get-csuserreplicatorconfiguration-ReplicationCycleInterval을 사용 하 여이 간격을 구성할 수 있습니다 &lt; &gt; .</span><span class="sxs-lookup"><span data-stu-id="70f7b-251">You can configure this interval by using Set -CSUserReplicatorConfiguration -ReplicationCycleInterval &lt;&gt;.</span></span>



</div>

</div>

<div>

## <a name="filtering-the-address-book"></a><span data-ttu-id="70f7b-252">주소록 필터링</span><span class="sxs-lookup"><span data-stu-id="70f7b-252">Filtering the Address Book</span></span>

<span data-ttu-id="70f7b-253">주소록 서버 파일에 입력 한 사용자는 AbAttribute 테이블에 나열 된 특정 Active Directory 도메인 서비스 특성을 기반으로 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-253">The users populated in the Address Book Server files can be controlled based on certain Active Directory Domain Services attributes listed in the AbAttribute table.</span></span> <span data-ttu-id="70f7b-254">필터링에 사용 되는 이러한 특성 중 하나는 **msExchangeHideFromAddressBook** 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-254">One such attribute used for filtering is the **msExchangeHideFromAddressBook** attribute.</span></span> <span data-ttu-id="70f7b-255">Exchange 스키마에서 추가 하는 사용자 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-255">This is a user attribute added by the Exchange schema.</span></span> <span data-ttu-id="70f7b-256">이 특성의 값이 TRUE 인 경우 Exchange Server에서는이 특성을 사용 하 여 Outlook GAL (전체 주소 목록)에서 연락처를 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-256">If the value of this attribute is TRUE, Exchange Server uses this attribute to hide the contact from the Outlook Global Address List (GAL).</span></span> <span data-ttu-id="70f7b-257">마찬가지로이 특성의 값이 TRUE 인 경우 사용자 복제기는 AbUserEntry 테이블에 해당 사용자를 포함 하지 않으며이 사용자는 주소록 서버 파일에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-257">Similarly, if the value of this attribute is TRUE, User Replicator does not include that user in the AbUserEntry table and this user will not be in the Address Book Server files.</span></span>

<span data-ttu-id="70f7b-p120">일부 플래그 비트를 사용하여 주소록 서버 특성에 대해 사용할 필터를 정의할 수 있습니다. 예를 들어 특정 플래그 비트를 표시하여 특성을 포함 특성 또는 제외 특성으로 구분할 수 있습니다. User Replicator는 제외 특성이 포함된 연락처와 포함 특성이 포함되지 않은 연락처를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-p120">You can use some flag bits to define a filter to use on Address Book Server attributes. For example, the presence of certain flag bits can identify an attribute as an include attribute or an exclude attribute. User Replicator filters out contacts that contain an exclude attribute and filters out contains that do not contain an include attribute.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="70f7b-261">주소록 필터링에 대 한 자세한 내용은 <A href="https://technet.microsoft.com/library/gg415643(v=ocs.15)">Lync server 2013의 주소록 서버 cmdlet</A>및 <A href="https://go.microsoft.com/fwlink/?linkid=330430">필터 lync 2013 주소록</A> 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="70f7b-261">For more information about filtering the Address Book, see <A href="https://technet.microsoft.com/library/gg415643(v=ocs.15)">Address Book Server cmdlets in Lync Server 2013</A>, and <A href="https://go.microsoft.com/fwlink/?linkid=330430">Filter Lync 2013 address book</A></span></span>



</div>

<span data-ttu-id="70f7b-p121">현재 세 가지 필터가 있으며, 아래 표에 이러한 필터가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-p121">Currently, there are three different filters. The following table lists these filters.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="70f7b-264">특성</span><span class="sxs-lookup"><span data-stu-id="70f7b-264">Attribute</span></span></th>
<th><span data-ttu-id="70f7b-265">설명</span><span class="sxs-lookup"><span data-stu-id="70f7b-265">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="70f7b-266">0x800</span><span class="sxs-lookup"><span data-stu-id="70f7b-266">0x800</span></span></p></td>
<td><p><span data-ttu-id="70f7b-p122">이 유형은 설정된 경우 연락처의 필수 특성을 나타냅니다. User Replicator는 이 플래그 비트를 사용하여 하나 이상의 필수 특성이 포함되지 않은 연락처를 필터링합니다. OuPathId는 필수 특성이므로 항상 설정됩니다. 따라서 다른 필수 특성 중 하나 이상이 설정되어 있어야 합니다. 그렇지 않으면 연락처(즉, OuPathId 필수 특성 값이 있는 연락처)가 데이터베이스에 기록되지 않습니다. 예를 들어 <strong>telephoneNumber</strong> 및 <strong>homePhone</strong>이 필수 특성으로 정의된 경우 이러한 특성 중 하나 이상이 있는 연락처만 데이터베이스에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-p122">If set, this identifies a required attribute for a contact. User Replicator uses this flag bit to filter out contacts that do not contain at least one required attribute. The OuPathId is a required attribute, which is always set. So at least one of other required attributes should be set. Otherwise, contact (that is, with value of required attribute OuPathId) will still not be written to database. For example, if <strong>telephoneNumber</strong> and <strong>homePhone</strong> are defined as required attributes, only the contacts that have at least one of these attributes are written to the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70f7b-273">0x4000</span><span class="sxs-lookup"><span data-stu-id="70f7b-273">0x4000</span></span></p></td>
<td><p><span data-ttu-id="70f7b-p123">이 유형은 설정된 경우 제외 특성을 나타냅니다. User Replicator는 이 플래그 비트를 사용하여 이 특성이 포함된 연락처를 필터링합니다. 예를 들어 <strong>msRTCSIP-PrimaryUserAddress</strong>가 제외 특성으로 정의된 경우 이 특성을 가진 연락처가 데이터베이스에 기록되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-p123">If set, this identifies an exclude attribute. User Replicator uses this flag bit to filter out contacts that contain this attribute. For example, if <strong>msRTCSIP-PrimaryUserAddress</strong> is defined as an exclude attribute, contacts that have this attribute are not written to the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70f7b-277">0x8000</span><span class="sxs-lookup"><span data-stu-id="70f7b-277">0x8000</span></span></p></td>
<td><p><span data-ttu-id="70f7b-p124">이 유형은 설정된 경우 포함 특성을 나타냅니다. User Replicator는 이 플래그 비트를 사용하여 이 특성이 포함되지 않은 연락처를 필터링합니다. 예를 들어 <strong>msRTCSIP-PrimaryUserAddress</strong>가 포함 특성으로 정의된 경우 이 특성을 가진 연락처만 데이터베이스에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-p124">If set, this identifies an include attribute. User Replicator uses this flag bit to filter out contacts that do not contain this attribute. For example, if <strong>msRTCSIP-PrimaryUserAddress</strong> is defined as an include attribute, only the contacts that have this attribute are written to the database.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="70f7b-281">0x4000(제외 특성) 및 0x8000(포함 특성) 플래그 비트가 둘 다 설정된 경우에는 0x4000 비트가 0x8000 비트에 우선하므로 연락처가 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-281">If both the 0x4000 (exclude attribute) and 0x8000 (include attribute) flag bits are set, the 0x4000 bit overrides the 0x8000 bit and the contact is excluded.</span></span>



</div>

<span data-ttu-id="70f7b-p125">특정 사용자만 포함하도록 주소록을 필터링할 수 있지만 항목을 제한하면 다른 사용자가 필터링된 사용자에게 연결하거나 필터링된 사용자의 현재 상태를 볼 수 있는 기능이 제한됩니다. 사용자는 언제든지 전체 로그인 이름을 입력하여 주소록에 없는 사용자를 찾거나 수동으로 인스턴트 메시지를 보내거나 수동으로 전화를 걸 수 있습니다. 또한 사용자의 연락처 정보는 Outlook에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-p125">Although you can filter the Address Book to include only certain users, limiting entries does not limit other users' ability to contact the filtered users or to see their presence status. Users can always find, manually send instant messages, or manually initiate calls to users not in the Address Book by entering a user's complete sign-in name. Also, contact information for a user could also be found in Outlook.</span></span>

<span data-ttu-id="70f7b-285">주소록 파일에 전체 연락처 레코드를 포함 하는 경우 SIP (Session initiate Protocol)에 대해 구성 되지 않은 사용자와 함께 Lync Server를 사용 하 여 전자 메일, 전화 또는 엔터프라이즈 음성 통화를 시작할 수 있습니다 (즉, 서버에서 Enterprise Voice를 사용 하는 경우) 일부 조직에서는 SIP 사용 가능 사용자만 주소록 서버 항목에 추가 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-285">While having full contact records in the Address Book files enables you to use Lync Server to initiate email, telephone, or Enterprise Voice calls (that is, if Enterprise Voice is enabled on the server) with users that are not configured for Session Initiation Protocol (SIP), some organizations prefer to include only SIP-enabled users in their Address Book Server entries.</span></span> <span data-ttu-id="70f7b-286">**MailNickname**, **telephoneNumber**, **homePhone**및 **mobile**과 같은 필수 특성의 **Flags** 열에서 0x800 비트를 지워 SIP 사용 가능 사용자만 포함 하도록 주소록을 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-286">You can filter the Address Book to include only SIP-enabled users by clearing the 0x800 bit in the **Flags** column of the following required attributes: **mailNickname**, **telephoneNumber**, **homePhone**, and **mobile**.</span></span> <span data-ttu-id="70f7b-287">**Msrtcsip-gateways-msrtcsip-primaryuseraddress** 특성의 **Flags** 열에 0x8000 (include 특성)을 설정 하 여 주소록을 필터링 하 여 SIP 사용 가능 사용자만 포함 하도록 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-287">You can also filter the Address Book to include only SIP-enabled users by setting the 0x8000 (include attribute) in the **Flags** column of the **msRTCSIP-PrimaryUserAddress** attribute.</span></span> <span data-ttu-id="70f7b-288">또한 주소록 파일에서 서비스 계정을 제외 하는 데에도 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-288">This also helps to exclude service accounts from the Address Book files.</span></span>

<span data-ttu-id="70f7b-289">AbAttribute 테이블을 수정한 후 **Update-CsUserDatabase** cmdlet 명령을 실행하여 AbUserEntry 테이블의 데이터를 새로 고칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-289">After you modify the AbAttribute table, you can refresh the data in the AbUserEntry table by running the cmdlet **Update-CsUserDatabase** command.</span></span> <span data-ttu-id="70f7b-290">UR 복제가 완료되면 **UpdateCsAddressBook** 명령을 수동으로 실행하여 주소록 서버 파일 저장소의 파일을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-290">After UR replication completes, you can update the file in the Address Book Server file store by manually running the cmdlet **UpdateCsAddressBook** command.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="70f7b-291">주소록 서버를 넣은 프런트 엔드 서버는 관리적으로 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-291">The Front End Server that the Address Book Server is placed is not administratively configurable.</span></span> <span data-ttu-id="70f7b-292">배포 중에, 즉 첫 번째 프런트 엔드 서버를 배포 하는 중에 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-292">One is chosen during deployment—typically, the first Front End Server deployed.</span></span> <span data-ttu-id="70f7b-293">오류가 발생 하는 경우 주소록 서비스는 다른 프런트 엔드 서버로 이동 되며, 관리 주의가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-293">In the event of failure, the Address Book Service will move to another Front End Server, and requires no administrative attention.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="70f7b-294">다중 포리스트 배포 또는 상위/하위 배포 (예: Lync Server로 이동 하기 전에 인프라 통합)에서 인프라를 통합 하거나 수정한 경우에는 주소록 서비스 다운로드 및 주소록 웹 쿼리가 일부 사용자에 대해 실패 하는 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-294">If you have consolidated or otherwise modified your infrastructure from a multi-forest deployment or a parent/child deployment (such as consolidating your infrastructure before moving to Lync Server), you may find that the Address Book service download and the Address Book Web Query fails for some users.</span></span> <span data-ttu-id="70f7b-295">여러 도메인 또는 포리스트가 포함된 배포에서는 <STRONG>MsRTCSIP-OriginatorSid</STRONG> 특성이 채워진 사용자 개체에서 문제가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-295">When in a deployment that had multiple domains or forests, the attribute <STRONG>MsRTCSIP-OriginatorSid</STRONG> is populated on the user objects that are exhibiting the issue.</span></span> <span data-ttu-id="70f7b-296">문제를 해결하려면 이러한 개체에 대한 <STRONG>MsRTCSIP-OriginatorSid</STRONG> 특성을 NULL로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70f7b-296">The <STRONG>MsRTCSIP-OriginatorSid</STRONG> attribute must be set to NULL on these objects to resolve the issue.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

