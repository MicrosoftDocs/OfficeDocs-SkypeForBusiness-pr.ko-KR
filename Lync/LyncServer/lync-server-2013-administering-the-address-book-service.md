---
title: 'Lync Server 2013: 주소록 서비스 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Administering the Address Book Service
ms:assetid: 801e4243-9670-4477-aa2f-88b61ecf5351
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429711(v=OCS.15)
ms:contentKeyID: 48184649
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8acf59a898f8da14b9c5c4151728206cc501ceaf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985385"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administering-the-address-book-service-in-lync-server-2013"></a><span data-ttu-id="86643-102">Lync Server에서 주소록 서비스 관리 2013</span><span class="sxs-lookup"><span data-stu-id="86643-102">Administering the Address Book Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86643-103">_**마지막으로 수정한 주제:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="86643-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="86643-104">Lync Server, Enterprise Edition 또는 Standard Edition Server 배포의 일부로 주소록 서비스는 기본적으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86643-104">As a part of the deployment of Lync Server, Enterprise Edition or Standard Edition server, the Address Book Service is installed by default.</span></span> <span data-ttu-id="86643-105">주소록 서비스에 사용 되는 데이터베이스 (RTCab –)는 SQL Server (Enterprise Edition의 경우 백 엔드 SQL Server, collocated SQL Server의 경우)에 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86643-105">The database used by the Address Book Service – RTCab – is created on the SQL Server (for Enterprise Edition, this is the back-end SQL Server; for Standard Edition server, the collocated SQL Server).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="86643-106"><STRONG>Adsi 편집</STRONG> 을 사용 하 여 Active Directory 도메인 서비스 개체 특성을 편집 하는 방법에 대 한 자세한 내용은 <A href="http://go.microsoft.com/fwlink/?linkid=330427">adsi 편집</A>을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="86643-106">For information about using <STRONG>ADSI Edit</STRONG> to edit Active Directory Domain Services object attributes, see <A href="http://go.microsoft.com/fwlink/?linkid=330427">ADSI Edit</A>.</span></span> <span data-ttu-id="86643-107">특정 주소록 서비스에 대 한 리소스 키트의 도구에 대 한 자세한 내용은 <A href="http://go.microsoft.com/fwlink/?linkid=330429">Microsoft Lync Server 2013 리소스 키트 도구</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="86643-107">For information about a tool in the Resource Kit specifically for the Address Book service, see <A href="http://go.microsoft.com/fwlink/?linkid=330429">Microsoft Lync Server 2013 Resource Kit Tools</A>.</span></span>



</div>

<div>

## <a name="address-book-server-phone-number-normalization"></a><span data-ttu-id="86643-108">주소록 서버 전화 번호 정규화</span><span class="sxs-lookup"><span data-stu-id="86643-108">Address Book Server Phone Number Normalization</span></span>

<span data-ttu-id="86643-109">Lync Server에는 표준화 된 RFC 3966/E-164 휴대폰 번호가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="86643-109">Lync Server requires standardized RFC 3966/E.164 phone numbers.</span></span> <span data-ttu-id="86643-110">형식이 지정 되지 않거나 일관성을 해제 한 전화 번호를 사용 하기 위해 Lync Server는 정규화 규칙에 전달 하기 전에 전화 번호를 전처리 하기 위해 주소록 서버에 의존 합니다.</span><span class="sxs-lookup"><span data-stu-id="86643-110">To use phone numbers that are unstructured or inconsistently formatted, Lync Server relies on the Address Book Server to preprocess phone numbers before they are handed off to the normalization rules.</span></span> <span data-ttu-id="86643-111">주소록에서 전화 번호를 사용 하 고 정규화 규칙을 적용 한 경우, Lync Phone Edition과 Lync Mobile 등의 클라이언트에서 이러한 정규화 된 숫자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86643-111">When a phone number is used from the address book and the normalization rule is applied, clients, such as Lync Phone Edition and Lync Mobile, can use these normalized numbers.</span></span>

<span data-ttu-id="86643-112">이전 버전에서 사용한 정규화 규칙이 일부 조정 없이 제대로 작동 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86643-112">The normalization rules that were used in previous versions may not work properly without some adjustments.</span></span> <span data-ttu-id="86643-113">정규화 규칙 전에 공백 및 비 필수 문자를 제거 했으므로 regex 식이 제거 된 대시 또는 다른 문자를 구체적으로 찾는 경우에는 정규화 규칙이 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86643-113">Because the white space and non-mandatory characters are removed prior to the normalization rules, if your regex expression is specifically looking for a dash or other character that was removed, your normalization rule might fail.</span></span> <span data-ttu-id="86643-114">정규화 규칙을 검토 하 여 이러한 비 필수 문자를 찾지 못하거나 규칙이 예상 되는 위치에 문자가 표시 되지 않는 경우에도 메시지가 정상적으로 실패 하 고 계속할 수 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86643-114">You should review your normalization rules to ensure that either they are not looking for these non-mandatory characters, or that the rule can fail gracefully and continue in the event that the character is not present where the rule anticipates it will be.</span></span>

</div>

<div>

## <a name="user-replicator-and-address-book-server"></a><span data-ttu-id="86643-115">사용자 복제기 및 주소록 서버</span><span class="sxs-lookup"><span data-stu-id="86643-115">User Replicator and Address Book Server</span></span>

<span data-ttu-id="86643-116">주소록 서버는 사용자 복제기에서 제공 하는 데이터를 사용 하 여 GAL (전체 주소 목록)에서 처음 얻은 정보를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="86643-116">The Address Book Server uses data provided by User Replicator to update the information that it initially obtains from the global address list (GAL).</span></span> <span data-ttu-id="86643-117">사용자 복제기는 각 사용자, 연락처 및 그룹의 Active Directory 도메인 서비스 특성을 데이터베이스의 AbUserEntry 테이블에 기록 하 고 주소록 서버는 데이터베이스의 사용자 데이터를 주소록 서버 파일 저장소의 파일에 동기화 하 고 주소록 데이터베이스 RTCab.</span><span class="sxs-lookup"><span data-stu-id="86643-117">User Replicator writes the Active Directory Domain Services attributes for each user, contact, and group into the AbUserEntry table in the database and the Address Book Server syncs the user data from the database into files in the Address Book Server file store and into the Address Book database RTCab.</span></span> <span data-ttu-id="86643-118">AbUserEntry 테이블에 대 한 스키마는 **Userguid** 와 **UserData**라는 두 개의 열을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="86643-118">The schema for the AbUserEntry table uses two columns, **UserGuid** and **UserData**.</span></span> <span data-ttu-id="86643-119">**Userguid** 는 인덱스 열로, Active Directory 개체의 16 바이트 GUID를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="86643-119">**UserGuid** is the index column and contains the 16-byte GUID of the Active Directory object.</span></span> <span data-ttu-id="86643-120">**UserData** 는 해당 연락처에 대해 앞에서 언급 한 모든 Active Directory 도메인 서비스 특성을 포함 하는 image 열입니다.</span><span class="sxs-lookup"><span data-stu-id="86643-120">**UserData** is an image column which contains all of the previously mentioned Active Directory Domain Services attributes for that contact.</span></span>

<span data-ttu-id="86643-121">사용자 복제기는 AbUserEntry 테이블과 동일한 SQL Server 기반 인스턴스에 있는 구성 테이블을 읽어 쓰려는 Active Directory 특성을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="86643-121">User Replicator determines which Active Directory attributes to write by reading a configuration table located in the same SQL Server-based instance as the AbUserEntry table.</span></span> <span data-ttu-id="86643-122">AbAttribute 테이블에는 **ID**, **이름**, **플래그**, **Enable**의 세 열이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86643-122">The AbAttribute table contains three columns, **ID**, **Name**, **Flags**, and **Enable**.</span></span> <span data-ttu-id="86643-123">이 테이블은 데이터베이스 설정 중에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="86643-123">The table is created during database setup.</span></span> <span data-ttu-id="86643-124">AbAttribute 테이블이 비어 있는 경우 사용자 복제기는 AbUserEntry 테이블 처리 논리를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="86643-124">If the AbAttribute table is empty, User Replicator skips its AbUserEntry table processing logic.</span></span> <span data-ttu-id="86643-125">주소록 서버 특성은 동적 이며, 주소록 서버가 활성화 되 면 주소록 서버에서 처음으로 작성 하는 AbAttribute 테이블에서 검색 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86643-125">Address Book Server attributes are dynamic and are retrieved from the AbAttribute table, which is initially written by the Address Book Server when the Address Book Server is activated.</span></span>

<span data-ttu-id="86643-126">주소록 서버 활성화에서 다음 표에 표시 된 값으로 AbAttribute 테이블을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="86643-126">Address Book Server activation populates the AbAttribute table with the values shown in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="86643-127">I</span><span class="sxs-lookup"><span data-stu-id="86643-127">ID</span></span></th>
<th><span data-ttu-id="86643-128">이름</span><span class="sxs-lookup"><span data-stu-id="86643-128">Name</span></span></th>
<th><span data-ttu-id="86643-129">플래그</span><span class="sxs-lookup"><span data-stu-id="86643-129">Flags</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86643-130">1</span><span class="sxs-lookup"><span data-stu-id="86643-130">1</span></span></p></td>
<td><p><span data-ttu-id="86643-131">givenName</span><span class="sxs-lookup"><span data-stu-id="86643-131">givenName</span></span></p></td>
<td><p><span data-ttu-id="86643-132">0x01400000</span><span class="sxs-lookup"><span data-stu-id="86643-132">0x01400000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86643-133">2</span><span class="sxs-lookup"><span data-stu-id="86643-133">2</span></span></p></td>
<td><p><span data-ttu-id="86643-134">만들려면</span><span class="sxs-lookup"><span data-stu-id="86643-134">Sn</span></span></p></td>
<td><p><span data-ttu-id="86643-135">0x02400000</span><span class="sxs-lookup"><span data-stu-id="86643-135">0x02400000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86643-136">3</span><span class="sxs-lookup"><span data-stu-id="86643-136">3</span></span></p></td>
<td><p><span data-ttu-id="86643-137">이름</span><span class="sxs-lookup"><span data-stu-id="86643-137">displayName</span></span></p></td>
<td><p><span data-ttu-id="86643-138">0x03420000</span><span class="sxs-lookup"><span data-stu-id="86643-138">0x03420000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86643-139">4(tcp/ipv4)</span><span class="sxs-lookup"><span data-stu-id="86643-139">4</span></span></p></td>
<td><p><span data-ttu-id="86643-140">타이틀이</span><span class="sxs-lookup"><span data-stu-id="86643-140">Title</span></span></p></td>
<td><p><span data-ttu-id="86643-141">0x04000000</span><span class="sxs-lookup"><span data-stu-id="86643-141">0x04000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86643-142">5mb</span><span class="sxs-lookup"><span data-stu-id="86643-142">5</span></span></p></td>
<td><p><span data-ttu-id="86643-143">mailNickname</span><span class="sxs-lookup"><span data-stu-id="86643-143">mailNickname</span></span></p></td>
<td><p><span data-ttu-id="86643-144">0x05400000</span><span class="sxs-lookup"><span data-stu-id="86643-144">0x05400000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86643-145">26</span><span class="sxs-lookup"><span data-stu-id="86643-145">6</span></span></p></td>
<td><p><span data-ttu-id="86643-146">회사별로</span><span class="sxs-lookup"><span data-stu-id="86643-146">Company</span></span></p></td>
<td><p><span data-ttu-id="86643-147">0x06000000</span><span class="sxs-lookup"><span data-stu-id="86643-147">0x06000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86643-148">7</span><span class="sxs-lookup"><span data-stu-id="86643-148">7</span></span></p></td>
<td><p><span data-ttu-id="86643-149">physicalDeliveryOfficeName</span><span class="sxs-lookup"><span data-stu-id="86643-149">physicalDeliveryOfficeName</span></span></p></td>
<td><p><span data-ttu-id="86643-150">0x07000000</span><span class="sxs-lookup"><span data-stu-id="86643-150">0x07000000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86643-151">20cm(8</span><span class="sxs-lookup"><span data-stu-id="86643-151">8</span></span></p></td>
<td><p><span data-ttu-id="86643-152">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="86643-152">msRTCSIP-PrimaryUserAddress</span></span></p></td>
<td><p><span data-ttu-id="86643-153">0x08520C00</span><span class="sxs-lookup"><span data-stu-id="86643-153">0x08520C00</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86643-154">되었는지</span><span class="sxs-lookup"><span data-stu-id="86643-154">9</span></span></p></td>
<td><p><span data-ttu-id="86643-155">telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="86643-155">telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="86643-156">0x09022800</span><span class="sxs-lookup"><span data-stu-id="86643-156">0x09022800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86643-157">1천만</span><span class="sxs-lookup"><span data-stu-id="86643-157">10</span></span></p></td>
<td><p><span data-ttu-id="86643-158">homePhone</span><span class="sxs-lookup"><span data-stu-id="86643-158">homePhone</span></span></p></td>
<td><p><span data-ttu-id="86643-159">0x0A302800</span><span class="sxs-lookup"><span data-stu-id="86643-159">0x0A302800</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86643-160">mb</span><span class="sxs-lookup"><span data-stu-id="86643-160">11</span></span></p></td>
<td><p><span data-ttu-id="86643-161">모바일</span><span class="sxs-lookup"><span data-stu-id="86643-161">Mobile</span></span></p></td>
<td><p><span data-ttu-id="86643-162">0x0B622800</span><span class="sxs-lookup"><span data-stu-id="86643-162">0x0B622800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86643-163">까지</span><span class="sxs-lookup"><span data-stu-id="86643-163">12</span></span></p></td>
<td><p><span data-ttu-id="86643-164">기타 전화</span><span class="sxs-lookup"><span data-stu-id="86643-164">otherTelephone</span></span></p></td>
<td><p><span data-ttu-id="86643-165">0x0C302000</span><span class="sxs-lookup"><span data-stu-id="86643-165">0x0C302000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86643-166">일자</span><span class="sxs-lookup"><span data-stu-id="86643-166">13</span></span></p></td>
<td><p><span data-ttu-id="86643-167">ipPhone</span><span class="sxs-lookup"><span data-stu-id="86643-167">ipPhone</span></span></p></td>
<td><p><span data-ttu-id="86643-168">0x0D302000</span><span class="sxs-lookup"><span data-stu-id="86643-168">0x0D302000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86643-169">13</span><span class="sxs-lookup"><span data-stu-id="86643-169">14</span></span></p></td>
<td><p><span data-ttu-id="86643-170">편집</span><span class="sxs-lookup"><span data-stu-id="86643-170">Mail</span></span></p></td>
<td><p><span data-ttu-id="86643-171">0x0E500000</span><span class="sxs-lookup"><span data-stu-id="86643-171">0x0E500000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86643-172">~</span><span class="sxs-lookup"><span data-stu-id="86643-172">15</span></span></p></td>
<td><p><span data-ttu-id="86643-173">groupType</span><span class="sxs-lookup"><span data-stu-id="86643-173">groupType</span></span></p></td>
<td><p><span data-ttu-id="86643-174">0x0F010800</span><span class="sxs-lookup"><span data-stu-id="86643-174">0x0F010800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86643-175">16</span><span class="sxs-lookup"><span data-stu-id="86643-175">16</span></span></p></td>
<td><p><span data-ttu-id="86643-176">부서</span><span class="sxs-lookup"><span data-stu-id="86643-176">Department</span></span></p></td>
<td><p><span data-ttu-id="86643-177">0x10000000</span><span class="sxs-lookup"><span data-stu-id="86643-177">0x10000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86643-178">17@@</span><span class="sxs-lookup"><span data-stu-id="86643-178">17</span></span></p></td>
<td><p><span data-ttu-id="86643-179">설명</span><span class="sxs-lookup"><span data-stu-id="86643-179">Description</span></span></p></td>
<td><p><span data-ttu-id="86643-180">0x11000100</span><span class="sxs-lookup"><span data-stu-id="86643-180">0x11000100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86643-181">awg</span><span class="sxs-lookup"><span data-stu-id="86643-181">18</span></span></p></td>
<td><p><span data-ttu-id="86643-182">관리자로</span><span class="sxs-lookup"><span data-stu-id="86643-182">Manager</span></span></p></td>
<td><p><span data-ttu-id="86643-183">0x12040001</span><span class="sxs-lookup"><span data-stu-id="86643-183">0x12040001</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86643-184">인치</span><span class="sxs-lookup"><span data-stu-id="86643-184">19</span></span></p></td>
<td><p><span data-ttu-id="86643-185">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="86643-185">proxyAddress</span></span></p></td>
<td><p><span data-ttu-id="86643-186">0x00500 105</span><span class="sxs-lookup"><span data-stu-id="86643-186">0x00500105</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86643-187">명</span><span class="sxs-lookup"><span data-stu-id="86643-187">20</span></span></p></td>
<td><p><span data-ttu-id="86643-188">msExchHideFromAddressLists</span><span class="sxs-lookup"><span data-stu-id="86643-188">msExchHideFromAddressLists</span></span></p></td>
<td><p><span data-ttu-id="86643-189">0xFF000003</span><span class="sxs-lookup"><span data-stu-id="86643-189">0xFF000003</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86643-190">99</span><span class="sxs-lookup"><span data-stu-id="86643-190">99</span></span></p></td>
<td><p><span data-ttu-id="86643-191">Id</span><span class="sxs-lookup"><span data-stu-id="86643-191">entryID</span></span></p></td>
<td><p><span data-ttu-id="86643-192">0x99000000</span><span class="sxs-lookup"><span data-stu-id="86643-192">0x99000000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="86643-193">**ID** 열의 숫자는 고유 해야 하며 다시 사용해 서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86643-193">The numbers in the **ID** column must be unique and should never be reused.</span></span> <span data-ttu-id="86643-194">또한 256 아래의 ID 값을 유지 하면 주소록 서버에서 작성 한 출력 파일에 공간을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86643-194">Also, keeping the ID values under 256 saves space in the output files written by the Address Book Server.</span></span> <span data-ttu-id="86643-195">그러나 최대 ID 값은 65535입니다.</span><span class="sxs-lookup"><span data-stu-id="86643-195">However, the maximum ID value is 65535.</span></span> <span data-ttu-id="86643-196">**이름** 열은 사용자 복제기에서 각 연락처에 대 한 AbUserEntry 테이블에 입력 해야 하는 Active Directory 특성 이름에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="86643-196">The **Name** column corresponds to the Active Directory attribute name that User Replicator should put in the AbUserEntry table for each contact.</span></span> <span data-ttu-id="86643-197">**Flags** 열의 값은 특성의 형식을 정의 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86643-197">The value in the **Flags** column is used to define the type of attribute.</span></span> <span data-ttu-id="86643-198">다음과 같은 유형의 주소록 서버 특성은 **Flags** 열에서 값의 하위 바이트로 표시 되는 사용자 복제기에 의해 인식 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86643-198">The following types of Address Book Server attributes are recognized by User Replicator, indicated by the low byte of the value in the **Flags** column.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="86643-199">특성</span><span class="sxs-lookup"><span data-stu-id="86643-199">Attribute</span></span></th>
<th><span data-ttu-id="86643-200">설명</span><span class="sxs-lookup"><span data-stu-id="86643-200">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86643-201">0</span><span class="sxs-lookup"><span data-stu-id="86643-201">0x0</span></span></p></td>
<td><p><span data-ttu-id="86643-202">문자열 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="86643-202">A string attribute.</span></span> <span data-ttu-id="86643-203">사용자 복제기는 AbUserEntry 테이블에 저장 하기 전에이 형식을 u t f-8로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="86643-203">User Replicator converts this type to UTF-8 before storing it in the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86643-204">이면</span><span class="sxs-lookup"><span data-stu-id="86643-204">0x1</span></span></p></td>
<td><p><span data-ttu-id="86643-205">이진 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="86643-205">A binary attribute.</span></span> <span data-ttu-id="86643-206">사용자 복제기는 변환 하지 않고 blob에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="86643-206">User Replicator stores this in the blob without any conversion.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86643-207">0x2</span><span class="sxs-lookup"><span data-stu-id="86643-207">0x2</span></span></p></td>
<td><p><span data-ttu-id="86643-208">String 특성 이지만 특성 값이 tel: &quot;&quot;로 시작 하는 경우에만 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86643-208">A string attribute, but is included only if the attribute value begins with &quot;tel:&quot;.</span></span> <span data-ttu-id="86643-209">이는 주로 여러 개의 값을 갖는 문자열 특성, 특히 <strong>proxyAddresses</strong>에 대 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="86643-209">This is primarily for multi-valued string attributes, specifically <strong>proxyAddresses</strong>.</span></span> <span data-ttu-id="86643-210">이 경우 주소록 서버는 tel: &quot;&quot;로 시작 되는 <strong>proxyAddresses</strong> 항목에만 관심이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86643-210">In this case, Address Book Server is interested only in <strong>proxyAddresses</strong> entries that begin with &quot;tel:&quot;.</span></span> <span data-ttu-id="86643-211">따라서 공간을 절약 하기 위해 사용자 복제기는 tel: &quot;&quot;로 시작 하는 항목만 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="86643-211">Therefore, in the interest of saving space, User Replicator stores only the entries that begin with &quot;tel:&quot;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86643-212">한다면</span><span class="sxs-lookup"><span data-stu-id="86643-212">0x3</span></span></p></td>
<td><p><span data-ttu-id="86643-213">TRUE 이면 사용자 복제기가 AbUserEntry 테이블에이 연락처를 포함 하지 않도록 하는 부울 문자열 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="86643-213">A Boolean string attribute, which if TRUE causes User Replicator to not include this contact in the AbUserEntry table.</span></span> <span data-ttu-id="86643-214">FALSE 인 경우 사용자 복제기는 AbUserEntry 테이블에이 연락처에 대 한 특성을 포함 하지만,이 플래그를 사용 하 여 특정 특성이 아닌 경우에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="86643-214">If FALSE, it causes User Replicator to include the attributes for this contact in the AbUserEntry table, but not the particular attribute with this flag.</span></span> <span data-ttu-id="86643-215">이는 주로 <strong>msExchHideFromAddressLists</strong> 특성에 대 한 다른 특별 사례 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="86643-215">This is another special case type that is primarily for the <strong>msExchHideFromAddressLists</strong> attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86643-216">0x4</span><span class="sxs-lookup"><span data-stu-id="86643-216">0x4</span></span></p></td>
<td><p><span data-ttu-id="86643-217">문자열 특성 이지만 특성 값 &quot;이 smtp:&quot; 로 시작 하는 경우에만 포함 되며 기호를 &quot; @ &quot; 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="86643-217">A string attribute, but is included only if the attribute value begins with &quot;smtp:&quot; and includes the &quot;@&quot; symbol.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86643-218">0x5</span><span class="sxs-lookup"><span data-stu-id="86643-218">0x5</span></span></p></td>
<td><p><span data-ttu-id="86643-219">String 특성 이지만 특성 값 &quot;이 tel:&quot; 또는 &quot;smtp:&quot; 로 시작 하 고 기호를 &quot; @ &quot; 포함 하는 경우에만 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86643-219">A string attribute, but is included only if the attribute value begins with either &quot;tel:&quot; or &quot;smtp:&quot; and includes the &quot;@&quot; symbol.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86643-220">0x100</span><span class="sxs-lookup"><span data-stu-id="86643-220">0x100</span></span></p></td>
<td><p><span data-ttu-id="86643-221">설정 된 경우 각 연락처에 대해 두 번 이상 표시할 수 있는 다중 값 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="86643-221">If set, this is a multi-valued attribute that can appear more than once for each contact.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86643-222">0x400</span><span class="sxs-lookup"><span data-stu-id="86643-222">0x400</span></span></p></td>
<td><p><span data-ttu-id="86643-223">설정 되 면 연락처에 대 한 전자 메일 사용자 계정 이름 특성을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="86643-223">If set, this identifies the email user account name attribute for a contact.</span></span> <span data-ttu-id="86643-224">주소록 서버는이 플래그를 사용 하 여 전화 정규화 이벤트 로그 항목에 표시할 특성 값을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="86643-224">Address Book Server uses this flag to identify which attribute value to show in the phone normalization event log entry.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86643-225">0x800</span><span class="sxs-lookup"><span data-stu-id="86643-225">0x800</span></span></p></td>
<td><p><span data-ttu-id="86643-226">Set 인 경우 연락처에 대 한 필수 특성을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="86643-226">If set, this identifies a required attribute for a contact.</span></span> <span data-ttu-id="86643-227">Active Directory에이 특성에 대 한 값이 있는 경우에만 주소록 서버에는 AbUserEntry 테이블의 사용자가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86643-227">Address Book Server includes a user in the AbUserEntry table only if there is a value for this attribute in Active Directory.</span></span> <span data-ttu-id="86643-228">필수 특성을 두 개 이상 사용 하는 경우에는 사용자에 게 AbUserEntry 테이블에 포함할 값이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86643-228">If there is more than one required attribute, only one of them is required to have a value to include the user in the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86643-229">0x1000</span><span class="sxs-lookup"><span data-stu-id="86643-229">0x1000</span></span></p></td>
<td><p><span data-ttu-id="86643-230">설정 하는 경우 주소록 서버는 항상이 특성의 값을 정규화 합니다.</span><span class="sxs-lookup"><span data-stu-id="86643-230">If set, Address Book Server always normalizes the value of this attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86643-231">0x2000</span><span class="sxs-lookup"><span data-stu-id="86643-231">0x2000</span></span></p></td>
<td><p><span data-ttu-id="86643-232">설정 하는 경우, <strong>UseNormalizationRules</strong> CMS 설정이 FALSE 인 경우 주소록 서버는 <strong>proxyAddresses</strong>에서 정규화 된 번호를 사용 합니다. 그렇지 않으면 플래그 비트가 0x1000 경우와 동일 하 게 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="86643-232">If set, Address Book Server uses the normalized number from <strong>proxyAddresses</strong>, if the <strong>UseNormalizationRules</strong> CMS setting is FALSE; otherwise it behaves the same as when the flag bit is 0x1000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86643-233">0x4000</span><span class="sxs-lookup"><span data-stu-id="86643-233">0x4000</span></span></p></td>
<td><p><span data-ttu-id="86643-234">설정 하는 경우 주소록 서버는 지정 된 특성에 대해이 값이 있는 AbUserEntry 테이블의 개체를 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="86643-234">If set, Address Book Server does not include objects in the AbUserEntry table that have this value for the specified attribute.</span></span> <span data-ttu-id="86643-235">예를 들어 <strong>msRTCSIP-PrimaryUserAddress</strong> 특성에이 플래그 비트가 설정 되어 있으면이 특성이 있는 연락처가 데이터베이스에 기록 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="86643-235">For example, if the <strong>msRTCSIP-PrimaryUserAddress</strong> attribute has this flag bit set, then contacts that have this attribute are not written to the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86643-236">0x8000</span><span class="sxs-lookup"><span data-stu-id="86643-236">0x8000</span></span></p></td>
<td><p><span data-ttu-id="86643-237">설정 하는 경우 주소록 서버는 지정 된 특성에 대해이 값이 없는 AbUserEntry 테이블의 개체를 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="86643-237">If set, Address Book Server does not include objects in the AbUserEntry table that do not have this value for the specified attribute.</span></span> <span data-ttu-id="86643-238">개체에 0x4000 및 0x8000 플래그 비트가 모두 설정 된 경우에는 플래그 비트 값이 0x4000로 설정 된 특성이 우선권을 가지 며 해당 개체가 AbUserEntry 테이블에서 제외 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86643-238">If both the 0x4000 and 0x8000 flag bits are set on an object, the attribute with the flag bit value set to 0x4000 takes precedence, and the object is excluded from the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86643-239">0x10000</span><span class="sxs-lookup"><span data-stu-id="86643-239">0x10000</span></span></p></td>
<td><p><span data-ttu-id="86643-240">Set 인 경우이는 그룹 개체를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="86643-240">If set, this represents a group object.</span></span> <span data-ttu-id="86643-241">사용자 복제기는이 플래그 비트를 사용 하 여 현재 상태가 그룹을 나타내는 <strong>groupType</strong> 특성이 있는 연락처를 포함 합니다 (예: 메일 목록 또는 보안 그룹).</span><span class="sxs-lookup"><span data-stu-id="86643-241">User Replicator uses this flag bit to include contacts with the <strong>groupType</strong> attribute whose presence indicates a group (for example, a distribution list or security group).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86643-242">0x20000</span><span class="sxs-lookup"><span data-stu-id="86643-242">0x20000</span></span></p></td>
<td><p><span data-ttu-id="86643-243">설정 하는 경우 사용자 복제기는이 플래그 비트를 사용 하 여 디바이스 관련 주소록 서버 파일 (즉, 확장명이 dabs 인 파일)에이 특성을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="86643-243">If set, User Replicator uses this flag bit to include this attribute in device-specific Address Book Server files (that is, files with a .dabs extension).</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="86643-244">이전 버전의 Lync Server에서 Active Directory에 변경 내용을 적용 하는 경우 관리자는 **업데이트 CSUserDatabase** 및 **update – CSAddressBook** Windows PowerShell cmdlet을 실행 하 여 Lync Server 사용자 데이터베이스와 rtcab 데이터베이스에 대 한 변경 내용을 즉시 유지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86643-244">In previous versions of Lync Server, when applying a change to Active Directory, the administrator would be required to run **Update -CSUserDatabase** and **Update –CSAddressBook** Windows PowerShell cmdlets to persist the change to the Lync Server user database and RTCab database immediately.</span></span> <span data-ttu-id="86643-245">Lync Server 2013에서 Lync Server 사용자 복제기는 Active Directory에서 변경 된 내용을 선택 하 고 구성 된 간격을 기준으로 Lync Server 사용자 데이터베이스를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="86643-245">In Lync Server 2013, Lync Server User Replicator will pick up the changes from Active Directory and update the Lync Server user database based on a configured interval.</span></span> <span data-ttu-id="86643-246">또한 Lync Server 사용자 복제기는 관리자가 CSAddressBook를 실행 하지 않아도 RTCab 데이터베이스에 대 한 변경 내용을 빠르게 전파 합니다.</span><span class="sxs-lookup"><span data-stu-id="86643-246">Lync Server User Replicator will also propagate the changes to the RTCab database quickly without the administrator having to run Update-CSAddressBook.</span></span> <span data-ttu-id="86643-247">주소록 웹 쿼리를 사용 하도록 설정 하면 변경 내용이 Lync 클라이언트에의 한 검색 결과에 반영 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86643-247">If Address Book Web query is enabled, then the changes will be reflected in search results by Lync clients.</span></span> <span data-ttu-id="86643-248">주소록 파일 다운로드를 사용 하는 경우 관리자는 업데이트 CSAddressBook 실행 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86643-248">Administrators will only need to run Update -CSAddressBook if the Address Book file download is enabled.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="86643-249">기본적으로 Lync Server 사용자 복제기는 5 분 마다 자동으로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86643-249">By default Lync Server User Replicator runs automatically every 5 minutes.</span></span> <span data-ttu-id="86643-250">Set-CSUserReplicatorConfiguration-ReplicationCycleInterval &lt; &gt;를 사용 하 여이 간격을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86643-250">You can configure this interval by using Set -CSUserReplicatorConfiguration -ReplicationCycleInterval &lt;&gt;.</span></span>



</div>

</div>

<div>

## <a name="filtering-the-address-book"></a><span data-ttu-id="86643-251">주소록 필터링</span><span class="sxs-lookup"><span data-stu-id="86643-251">Filtering the Address Book</span></span>

<span data-ttu-id="86643-252">주소록 서버 파일에 채워진 사용자는 AbAttribute 테이블에 나열 된 특정 Active Directory 도메인 서비스 특성을 기준으로 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86643-252">The users populated in the Address Book Server files can be controlled based on certain Active Directory Domain Services attributes listed in the AbAttribute table.</span></span> <span data-ttu-id="86643-253">필터링에 사용 되는 이러한 특성 중 하나는 **msExchangeHideFromAddressBook** 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="86643-253">One such attribute used for filtering is the **msExchangeHideFromAddressBook** attribute.</span></span> <span data-ttu-id="86643-254">Exchange 스키마에서 추가한 사용자 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="86643-254">This is a user attribute added by the Exchange schema.</span></span> <span data-ttu-id="86643-255">이 특성의 값이 TRUE 인 경우 Exchange Server는이 특성을 사용 하 여 Outlook GAL (전체 주소 목록)에서 연락처를 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="86643-255">If the value of this attribute is TRUE, Exchange Server uses this attribute to hide the contact from the Outlook Global Address List (GAL).</span></span> <span data-ttu-id="86643-256">마찬가지로,이 특성의 값이 TRUE 이면 사용자 복제기는 AbUserEntry 테이블에 해당 사용자를 포함 하지 않으며이 사용자는 주소록 서버 파일에 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="86643-256">Similarly, if the value of this attribute is TRUE, User Replicator does not include that user in the AbUserEntry table and this user will not be in the Address Book Server files.</span></span>

<span data-ttu-id="86643-257">일부 플래그 비트를 사용 하 여 주소록 서버 특성에서 사용할 필터를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86643-257">You can use some flag bits to define a filter to use on Address Book Server attributes.</span></span> <span data-ttu-id="86643-258">예를 들어 특정 플래그 비트가 있으면 특성을 include 특성 또는 exclude 특성으로 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86643-258">For example, the presence of certain flag bits can identify an attribute as an include attribute or an exclude attribute.</span></span> <span data-ttu-id="86643-259">사용자 복제기에서는 exclude 특성이 포함 된 연락처를 필터링 하 고 include 특성이 포함 되지 않은 항목을 필터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="86643-259">User Replicator filters out contacts that contain an exclude attribute and filters out contains that do not contain an include attribute.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="86643-260">주소록 필터링에 대 한 자세한 내용은 <A href="https://technet.microsoft.com/en-us/library/gg415643(v=ocs.15)">Lync server 2013의 주소록 서버 cmdlet</A>을 참조 하 고 <A href="http://go.microsoft.com/fwlink/?linkid=330430">Lync 2013 주소록 필터링</A></span><span class="sxs-lookup"><span data-stu-id="86643-260">For more information about filtering the Address Book, see <A href="https://technet.microsoft.com/en-us/library/gg415643(v=ocs.15)">Address Book Server cmdlets in Lync Server 2013</A>, and <A href="http://go.microsoft.com/fwlink/?linkid=330430">Filter Lync 2013 address book</A></span></span>



</div>

<span data-ttu-id="86643-261">현재 세 가지 다른 필터가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86643-261">Currently, there are three different filters.</span></span> <span data-ttu-id="86643-262">다음 표에는 이러한 필터가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86643-262">The following table lists these filters.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="86643-263">특성</span><span class="sxs-lookup"><span data-stu-id="86643-263">Attribute</span></span></th>
<th><span data-ttu-id="86643-264">설명</span><span class="sxs-lookup"><span data-stu-id="86643-264">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86643-265">0x800</span><span class="sxs-lookup"><span data-stu-id="86643-265">0x800</span></span></p></td>
<td><p><span data-ttu-id="86643-266">Set 인 경우 연락처에 대 한 필수 특성을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="86643-266">If set, this identifies a required attribute for a contact.</span></span> <span data-ttu-id="86643-267">사용자 복제기는이 플래그 비트를 사용 하 여 하나 이상의 필수 특성이 포함 되지 않은 연락처를 필터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="86643-267">User Replicator uses this flag bit to filter out contacts that do not contain at least one required attribute.</span></span> <span data-ttu-id="86643-268">OuPathId은 항상 설정 되는 필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="86643-268">The OuPathId is a required attribute, which is always set.</span></span> <span data-ttu-id="86643-269">따라서 다른 필수 특성 중 하나 이상을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86643-269">So at least one of other required attributes should be set.</span></span> <span data-ttu-id="86643-270">그렇지 않으면 연락처 (즉, 필수 특성의 값이 OuPathId)가 여전히 데이터베이스에 쓰여지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="86643-270">Otherwise, contact (that is, with value of required attribute OuPathId) will still not be written to database.</span></span> <span data-ttu-id="86643-271">예를 들어 <strong>telephoneNumber</strong> 및 <strong>homePhone</strong> 이 필수 특성으로 정의 된 경우 이러한 특성 중 하나 이상에 해당 하는 연락처만 데이터베이스에 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86643-271">For example, if <strong>telephoneNumber</strong> and <strong>homePhone</strong> are defined as required attributes, only the contacts that have at least one of these attributes are written to the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86643-272">0x4000</span><span class="sxs-lookup"><span data-stu-id="86643-272">0x4000</span></span></p></td>
<td><p><span data-ttu-id="86643-273">Set 인 경우 exclude 특성을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="86643-273">If set, this identifies an exclude attribute.</span></span> <span data-ttu-id="86643-274">사용자 복제기는이 플래그 비트를 사용 하 여이 특성을 포함 하는 연락처를 필터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="86643-274">User Replicator uses this flag bit to filter out contacts that contain this attribute.</span></span> <span data-ttu-id="86643-275">예를 들어 <strong>msRTCSIP-PrimaryUserAddress</strong> 가 exclude 특성으로 정의 된 경우이 특성을 가진 연락처는 데이터베이스에 기록 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="86643-275">For example, if <strong>msRTCSIP-PrimaryUserAddress</strong> is defined as an exclude attribute, contacts that have this attribute are not written to the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86643-276">0x8000</span><span class="sxs-lookup"><span data-stu-id="86643-276">0x8000</span></span></p></td>
<td><p><span data-ttu-id="86643-277">Set 인 경우 include 특성을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="86643-277">If set, this identifies an include attribute.</span></span> <span data-ttu-id="86643-278">사용자 복제기는이 플래그 비트를 사용 하 여이 특성을 포함 하지 않는 연락처를 필터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="86643-278">User Replicator uses this flag bit to filter out contacts that do not contain this attribute.</span></span> <span data-ttu-id="86643-279">예를 들어 <strong>msRTCSIP-PrimaryUserAddress</strong> 가 include 특성으로 정의 되 면이 특성이 있는 연락처만 데이터베이스에 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86643-279">For example, if <strong>msRTCSIP-PrimaryUserAddress</strong> is defined as an include attribute, only the contacts that have this attribute are written to the database.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="86643-280">0x4000 (exclude 특성) 및 0x8000 (include 특성) 플래그 비트가 설정 된 경우 0x4000 비트는 0x8000 비트를 재정의 하 고 연락처가 제외 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86643-280">If both the 0x4000 (exclude attribute) and 0x8000 (include attribute) flag bits are set, the 0x4000 bit overrides the 0x8000 bit and the contact is excluded.</span></span>



</div>

<span data-ttu-id="86643-281">특정 사용자만 포함 하도록 주소록을 필터링 할 수 있지만, 항목을 제한 하더라도 필터링 된 사용자에 게 연락 하거나 현재 상태를 확인 하는 다른 사용자의 권한은 제한 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="86643-281">Although you can filter the Address Book to include only certain users, limiting entries does not limit other users' ability to contact the filtered users or to see their presence status.</span></span> <span data-ttu-id="86643-282">사용자의 전체 로그인 이름을 입력 하 여 사용자가 언제 든 지 인스턴트 메시지를 찾거나 수동으로 보내거나 주소록에 없는 사용자에 게 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86643-282">Users can always find, manually send instant messages, or manually initiate calls to users not in the Address Book by entering a user's complete sign-in name.</span></span> <span data-ttu-id="86643-283">또한 Outlook 에서도 사용자의 연락처 정보를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86643-283">Also, contact information for a user could also be found in Outlook.</span></span>

<span data-ttu-id="86643-284">주소록 파일에 전체 연락처 레코드를 포함 하는 동안에는 Lync Server를 사용 하 여 세션 초기화를 위해 구성 되지 않은 사용자와 전자 메일, 전화 또는 엔터프라이즈 음성 통화 (서버에서 Enterprise Voice를 사용 하는 경우)를 시작할 수 있습니다. 프로토콜 (SIP)의 경우, 일부 조직에서는 SIP 지원 사용자만 주소록 서버 항목에 포함 하는 것을 선호 합니다.</span><span class="sxs-lookup"><span data-stu-id="86643-284">While having full contact records in the Address Book files enables you to use Lync Server to initiate email, telephone, or Enterprise Voice calls (that is, if Enterprise Voice is enabled on the server) with users that are not configured for Session Initiation Protocol (SIP), some organizations prefer to include only SIP-enabled users in their Address Book Server entries.</span></span> <span data-ttu-id="86643-285">**MailNickname**, **telephoneNumber**, **homePhone**, **mobile**등 필수 특성의 **Flags** 열에서 0x800 Bit를 지워 SIP 사용 가능 사용자만 포함 하도록 주소록을 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86643-285">You can filter the Address Book to include only SIP-enabled users by clearing the 0x800 bit in the **Flags** column of the following required attributes: **mailNickname**, **telephoneNumber**, **homePhone**, and **mobile**.</span></span> <span data-ttu-id="86643-286">**MsRTCSIP-PrimaryUserAddress** 특성의 **Flags** 열에 0x8000 (include 특성)을 설정 하 여 주소록을 필터링 하 여 SIP 사용 가능 사용자만 포함 하도록 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86643-286">You can also filter the Address Book to include only SIP-enabled users by setting the 0x8000 (include attribute) in the **Flags** column of the **msRTCSIP-PrimaryUserAddress** attribute.</span></span> <span data-ttu-id="86643-287">또한 주소록 파일에서 서비스 계정을 제외 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86643-287">This also helps to exclude service accounts from the Address Book files.</span></span>

<span data-ttu-id="86643-288">AbAttribute 테이블을 수정한 후에는 cmdlet **업데이트-CsUserDatabase** 명령을 실행 하 여 AbUserEntry 테이블에서 데이터를 새로 고칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86643-288">After you modify the AbAttribute table, you can refresh the data in the AbUserEntry table by running the cmdlet **Update-CsUserDatabase** command.</span></span> <span data-ttu-id="86643-289">UR 복제가 완료 되 면 cmdlet **UpdateCsAddressBook** 명령을 수동으로 실행 하 여 주소록 서버 파일 저장소에서 파일을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86643-289">After UR replication completes, you can update the file in the Address Book Server file store by manually running the cmdlet **UpdateCsAddressBook** command.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="86643-290">주소록 서버를 배치 하는 프런트 엔드 서버는 관리적으로 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="86643-290">The Front End Server that the Address Book Server is placed is not administratively configurable.</span></span> <span data-ttu-id="86643-291">배포 중에 하나 (일반적으로 첫 번째 프런트 엔드 서버를 배포 하는 경우)가 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86643-291">One is chosen during deployment—typically, the first Front End Server deployed.</span></span> <span data-ttu-id="86643-292">실패 한 경우 주소록 서비스는 다른 프런트 엔드 서버로 이동 하 고 관리 주의가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="86643-292">In the event of failure, the Address Book Service will move to another Front End Server, and requires no administrative attention.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="86643-293">다중 포리스트 배포 또는 상위/하위 배포 (Lync 서버로 이동 하기 전에 인프라 통합)에서 인프라를 통합 하거나 수정 하는 경우 주소록 서비스 다운로드 및 주소록 웹 쿼리가 일부 사용자에 게 실패 하는 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86643-293">If you have consolidated or otherwise modified your infrastructure from a multi-forest deployment or a parent/child deployment (such as consolidating your infrastructure before moving to Lync Server), you may find that the Address Book service download and the Address Book Web Query fails for some users.</span></span> <span data-ttu-id="86643-294">여러 도메인 또는 포리스트가 있는 배포의 경우 <STRONG>MsRTCSIP-OriginatorSid</STRONG> 특성이 문제를 발생 하는 사용자 개체에 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="86643-294">When in a deployment that had multiple domains or forests, the attribute <STRONG>MsRTCSIP-OriginatorSid</STRONG> is populated on the user objects that are exhibiting the issue.</span></span> <span data-ttu-id="86643-295">이 문제를 해결 하려면 이러한 개체에 대해 <STRONG>MsRTCSIP-OriginatorSid</STRONG> 특성을 NULL로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86643-295">The <STRONG>MsRTCSIP-OriginatorSid</STRONG> attribute must be set to NULL on these objects to resolve the issue.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

