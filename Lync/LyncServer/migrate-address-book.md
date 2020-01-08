---
title: 주소록 마이그레이션
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate Address Book
ms:assetid: ac7f0f39-4c6d-4702-8e25-93a73e3d800f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205160(v=OCS.15)
ms:contentKeyID: 48185064
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2293b7ad3e5ac14071bae4d5ecb935c24cfbb335
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980225"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a><span data-ttu-id="5f507-102">주소록 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="5f507-102">Migrate Address Book</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f507-103">_**마지막으로 수정한 주제:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="5f507-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="5f507-104">일반적으로 Lync Server 2010 주소록은 토폴로지의 나머지 부분과 함께 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f507-104">In general, the Lync Server 2010 Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="5f507-105">그러나 Lync Server 2010 환경에서 다음을 사용자 지정 하는 경우 몇 가지 마이그레이션 후 단계를 수행 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f507-105">However, you might need to perform some post-migration steps if you customized the following in your Lync Server 2010 environment:</span></span>

  - <span data-ttu-id="5f507-106">파티션 구성 단위 (OU)를 기준으로 **하** 는 통합 WMI 속성을 설정 하 여 주소록 항목을 그룹화 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f507-106">Set the **PartitionbyOU** WMI property to group Address Book entries by organizational unit (OU).</span></span>

  - <span data-ttu-id="5f507-107">주소록 정규화 규칙을 사용자 지정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5f507-107">Customized the Address Book normalization rules.</span></span>

  - <span data-ttu-id="5f507-108">**UseNormalizationRules** 매개 변수의 기본값을 False로 변경 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5f507-108">Changed the default value for the **UseNormalizationRules** parameter to False.</span></span>

<span data-ttu-id="5f507-109">**그룹화 된 주소록 항목**</span><span class="sxs-lookup"><span data-stu-id="5f507-109">**Grouped Address Book Entries**</span></span>

<span data-ttu-id="5f507-110">각 OU에 대 한 주소록을 만들기 위해 **파티션/사용자** 지정 WMI 속성을 True로 설정 하는 경우, 주소록 항목을 계속 그룹화 하려면 사용자 및 연락처에 **msRTCSIP** Active Directory 특성을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f507-110">If you set the **PartitionbyOU** WMI property to True to create address books for each OU, you need to set the **msRTCSIP-GroupingId** Active Directory attribute on users and contacts if you want to continue grouping address book entries.</span></span> <span data-ttu-id="5f507-111">주소록 항목을 그룹화 하 여 주소록 검색의 범위를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f507-111">You might want to group address book entries to limit the scope of Address Book searches.</span></span> <span data-ttu-id="5f507-112">**MsRTCSIP-GroupingId** 특성을 사용 하려면 그룹화 할 모든 사용자에 대해 동일한 값을 할당 하 여 특성을 채우는 스크립트를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f507-112">To use the **msRTCSIP-GroupingId** attribute, write a script to populate the attribute, assigning the same value for all of the users that you want to group together.</span></span> <span data-ttu-id="5f507-113">예를 들어 OU의 모든 사용자에 대해 단일 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f507-113">For example, assign a single value for all the users in an OU.</span></span>

<span data-ttu-id="5f507-114">**주소록 정규화 규칙**</span><span class="sxs-lookup"><span data-stu-id="5f507-114">**Address Book Normalization Rules**</span></span>

<span data-ttu-id="5f507-115">Lync Server 2010 환경에서 주소록 정규화 규칙을 사용자 지정한 경우 사용자 지정 규칙을 파일럿 풀로 마이그레이션해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f507-115">If you customized Address Book normalization rules in your Lync Server 2010 environment, you must migrate the customized rules to your pilot pool.</span></span> <span data-ttu-id="5f507-116">주소록 정규화 규칙을 사용자 지정 하지 않은 경우에는 주소록 서비스에 대해 마이그레이션할 내용이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5f507-116">If you did not customize Address Book normalization rules, you have nothing to migrate for Address Book service.</span></span> <span data-ttu-id="5f507-117">Lync Server 2013의 기본 정규화 규칙은 Lync Server 2010의 기본 규칙과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f507-117">The default normalization rules for Lync Server 2013 are the same as the default rules for Lync Server 2010.</span></span> <span data-ttu-id="5f507-118">이 섹션의 뒷부분에 나오는 절차에 따라 사용자 지정 정규화 규칙을 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="5f507-118">Follow the procedure later in this section to migrate customized normalization rules.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5f507-119">조직에서 원격 통화 제어를 사용 하 고 주소록 정규화 규칙을 사용자 지정한 경우이 항목의 절차를 수행 해야 원격 통화 제어를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f507-119">If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control.</span></span> <span data-ttu-id="5f507-120">이 절차에서는 RTCUniversalServerAdmins 그룹 또는 해당 권한에 대 한 멤버 자격이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f507-120">The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.</span></span>



</div>

<span data-ttu-id="5f507-121">**UseNormalizationRules를 False로 설정**</span><span class="sxs-lookup"><span data-stu-id="5f507-121">**UseNormalizationRules Set to False**</span></span>

<span data-ttu-id="5f507-122">**UseNormalizationRules** 에 대 한 값을 False로 설정 하 여 사용자가 **UseNormalizationRules** 및 **ignoregenericrules** 를 적용 하지 2013 않고 Active Directory 도메인 서비스에 정의 된 대로 전화 번호를 사용할 수 있도록 설정한 경우에는 "True"로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f507-122">If you set the value for **UseNormalizationRules** to False so that users can use phone numbers as they are defined in Active Directory Domain Services without having Lync Server 2013 apply normalization rules, you need to set the **UseNormalizationRules** and **IgnoreGenericRules** parameters to True.</span></span> <span data-ttu-id="5f507-123">이 섹션의 뒷부분에 나오는 절차에 따라 이러한 매개 변수를 True로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f507-123">Follow the procedure later in this section to set these parameters to True.</span></span>

<div>

## <a name="to-migrate-address-book-customized-normalization-rules"></a><span data-ttu-id="5f507-124">주소록을 사용자 지정 정규화 규칙으로 마이그레이션하려면 다음을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f507-124">To migrate Address Book customized normalization rules</span></span>

1.  <span data-ttu-id="5f507-125">주소록 공유 폴더\_의\_루트\_에\_있는 회사 전화 번호 정규화 규칙 .txt 파일을 찾아 Lync Server 2013의 파일럿 풀에 있는 주소록 공유 폴더의 루트에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f507-125">Find the Company\_Phone\_Number\_Normalization\_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Lync Server 2013 pilot pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5f507-126">예제 주소록 정규화 규칙은 ABS 웹 구성 요소 파일 디렉터리에 설치 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f507-126">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="5f507-127">경로는 <STRONG>$installedDriveLetter: .\ Files\Microsoft Lync Server 2013 \ Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules. t a x,</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="5f507-127">The path is <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</STRONG>.</span></span> <span data-ttu-id="5f507-128">이 파일 &nbsp; <STRONG></STRONG> &nbsp;을 Company_Phone_Number_Normalization_Rules으로 복사 하 여 주소록 공유 폴더의 루트 디렉터리로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f507-128">This file can be copied and renamed as &nbsp;<STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp;to the address book shared folder’s root directory.</span></span> <span data-ttu-id="5f507-129">예를 들어 <STRONG>$serverX</STRONG>&nbsp;에서 공유 되는 주소록은 <STRONG> \\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="5f507-129">For example, the address book shared in <STRONG>$serverX</STRONG>,&nbsp;the path will be similar to: <STRONG>\\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.</span></span>

    
    </div>

2.  <span data-ttu-id="5f507-130">메모장과 같은 텍스트 편집기를 사용 하 여\_회사 전화\_번호\_정규화\_규칙 .txt 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5f507-130">Use a text editor, such as Notepad, to open the Company\_Phone\_Number\_Normalization\_Rules.txt file.</span></span>

3.  <span data-ttu-id="5f507-131">특정 유형의 항목이 Lync Server 2013에서 제대로 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5f507-131">Certain types of entries will not work correctly in Lync Server 2013.</span></span> <span data-ttu-id="5f507-132">이 단계에서 설명 하는 항목 유형에 해당 하는 파일을 살펴보고 필요에 따라 편집한 다음 파일럿 풀의 주소록 공유 폴더에 변경 내용을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f507-132">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>
    
    <span data-ttu-id="5f507-133">필수 공백 또는 문장 부호를 포함 하는 문자열은 정규화 규칙에 입력 된 문자열에서 제거 되므로 정규화 규칙에 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f507-133">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span></span> <span data-ttu-id="5f507-134">필수 공백이 나 문장 부호를 포함 하는 문자열을 사용 하는 경우 문자열을 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f507-134">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span></span> <span data-ttu-id="5f507-135">예를 들어 다음 문자열을 선택 하면 정규화 규칙이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f507-135">For example, the following string would cause the normalization rule to fail:</span></span>
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    <span data-ttu-id="5f507-136">다음 문자열은 정규화 규칙을 실패 시 키 지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5f507-136">The following string would not cause the normalization rule to fail:</span></span>
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<div>

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a><span data-ttu-id="5f507-137">UseNormalizationRules 및 IgnoreGenericRules를 true로 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="5f507-137">To set UseNormalizationRules and IgnoreGenericRules to true</span></span>

1.  <span data-ttu-id="5f507-138">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f507-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="5f507-139">다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f507-139">Do one of the following:</span></span>
    
      - <span data-ttu-id="5f507-140">배포에 Lync Server 2013만 포함 된 경우 전역 수준에서 다음 cmdlet을 실행 하 여 **UseNormalizationRules** 및 **ignoregenericrules** 의 값을 True로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f507-140">If your deployment includes only Lync Server 2013, run the following cmdlet at the global level to change the values for **UseNormalizationRules** and **IgnoreGenericRules** to True:</span></span>
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - <span data-ttu-id="5f507-141">배포에 Lync Server 2013 및 Lync Server 2010 또는 Office Communications Server 2007 R2 조합이 포함 되어 있는 경우 다음 cmdlet을 실행 하 고 토폴로지의 각 Lync Server 2013 풀에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f507-141">If your deployment includes a combination of Lync Server 2013 and Lync Server 2010 or Office Communications Server 2007 R2, run the following cmdlet and assign it to each Lync Server 2013 pool in the topology:</span></span>
        
            New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  <span data-ttu-id="5f507-142">중앙 관리 저장소 복제가 모든 풀에서 발생 하는 것을 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="5f507-142">Wait for Central Management store replication to occur on all pools.</span></span>

4.  <span data-ttu-id="5f507-143">배포에서 콘텐츠를 지우기 위해 전화 정규화 규칙\_파일\_"\_회사\_전화 번호 정규화 규칙. t a x"를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f507-143">Modify the phone normalization rules file, "Company\_Phone\_Number\_Normalization\_Rules.txt", for your deployment to clear the content.</span></span> <span data-ttu-id="5f507-144">파일은 각 Lync Server 2013 풀의 파일 공유에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f507-144">The file is on the file share of each Lync Server 2013 pool.</span></span> <span data-ttu-id="5f507-145">파일이 없는 경우 "\_회사 전화\_번호\_정규화\_규칙. x" 라는 빈 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5f507-145">If the file is not present, then create an empty file named "Company\_Phone\_Number\_Normalization\_Rules.txt".</span></span>

5.  <span data-ttu-id="5f507-146">모든 프런트 엔드 풀이 새 파일을 읽을 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="5f507-146">Wait several minutes for all Front End pools to read the new files.</span></span>

6.  <span data-ttu-id="5f507-147">배포의 각 Lync Server 2013 풀에서 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f507-147">Run the following cmdlet on each Lync Server 2013 pool in your deployment:</span></span>
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

