---
title: 주소록 마이그레이션
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 일반적으로 주소록은 토폴로지의 나머지 부분과 함께 마이그레이션됩니다. 그러나 레거시 환경에서 다음을 사용자 지정 하는 경우 몇 가지 마이그레이션 후 단계를 수행 해야 할 수 있습니다.
ms.openlocfilehash: 4263ae5bff60859cc9606a3683a3a03b0d2d4c35
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197803"
---
# <a name="migrate-address-book"></a><span data-ttu-id="1ef07-104">주소록 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="1ef07-104">Migrate Address Book</span></span>

<span data-ttu-id="1ef07-105">일반적으로 주소록은 토폴로지의 나머지 부분과 함께 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ef07-105">In general, the Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="1ef07-106">그러나 레거시 환경에서 다음을 사용자 지정 하는 경우 몇 가지 마이그레이션 후 단계를 수행 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ef07-106">However, you might need to perform some post-migration steps if you customized the following in your legacy environment:</span></span> 

- <span data-ttu-id="1ef07-107">주소록 정규화 규칙을 사용자 지정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1ef07-107">Customized the Address Book normalization rules.</span></span>

- <span data-ttu-id="1ef07-108">**UseNormalizationRules** 매개 변수의 기본값을 False로 변경 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1ef07-108">Changed the default value for the **UseNormalizationRules** parameter to False.</span></span> 


 <span data-ttu-id="1ef07-109">**주소록 정규화 규칙**</span><span class="sxs-lookup"><span data-stu-id="1ef07-109">**Address Book Normalization Rules**</span></span>

<span data-ttu-id="1ef07-110">레거시 환경에서 주소록 정규화 규칙을 사용자 지정한 경우에는 사용자 지정 규칙을 파일럿 풀로 마이그레이션해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ef07-110">If you customized Address Book normalization rules in your legacy environment, you must migrate the customized rules to your pilot pool.</span></span> <span data-ttu-id="1ef07-111">주소록 정규화 규칙을 사용자 지정 하지 않은 경우에는 주소록 서비스에 대해 마이그레이션할 내용이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1ef07-111">If you did not customize Address Book normalization rules, you have nothing to migrate for Address Book service.</span></span> <span data-ttu-id="1ef07-112">비즈니스용 Skype 서버 2019의 기본 정규화 규칙은 레거시 설치에 대 한 기본 규칙과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ef07-112">The default normalization rules for Skype for Business Server 2019 are the same as the default rules for the legacy install.</span></span> <span data-ttu-id="1ef07-113">이 섹션의 뒷부분에 나오는 절차에 따라 사용자 지정 정규화 규칙을 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="1ef07-113">Follow the procedure later in this section to migrate customized normalization rules.</span></span>

> [!NOTE]
> <span data-ttu-id="1ef07-114">조직에서 원격 통화 제어를 사용 하 고 주소록 정규화 규칙을 사용자 지정한 경우이 항목의 절차를 수행 해야 원격 통화 제어를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ef07-114">If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control.</span></span> <span data-ttu-id="1ef07-115">이 절차에서는 RTCUniversalServerAdmins 그룹 또는 해당 권한에 대 한 멤버 자격이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ef07-115">The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.</span></span> 

 <span data-ttu-id="1ef07-116">**UseNormalizationRules를 False로 설정**</span><span class="sxs-lookup"><span data-stu-id="1ef07-116">**UseNormalizationRules Set to False**</span></span>

<span data-ttu-id="1ef07-117">**UseNormalizationRules** 의 값을 False로 설정 하 여 비즈니스용 Skype Server 2019에서 정규화 규칙을 적용 하지 않고 사용자가 전화 번호를 Active Directory 도메인 서비스에 정의한 대로 사용할 수 있도록 하려면 다음을 설정 해야 합니다 **. UseNormalizationRules** 및 **Ignoregenericrules** 매개 변수를 True로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ef07-117">If you set the value for **UseNormalizationRules** to False so that users can use phone numbers as they are defined in Active Directory Domain Services without having Skype for Business Server 2019 apply normalization rules, you need to set the **UseNormalizationRules** and **IgnoreGenericRules** parameters to True.</span></span> <span data-ttu-id="1ef07-118">이 섹션의 뒷부분에 나오는 절차에 따라 이러한 매개 변수를 True로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ef07-118">Follow the procedure later in this section to set these parameters to True.</span></span> 

## <a name="to-migrate-address-book-customized-normalization-rules"></a><span data-ttu-id="1ef07-119">주소록을 사용자 지정 정규화 규칙으로 마이그레이션하려면 다음을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ef07-119">To migrate Address Book customized normalization rules</span></span>

1. <span data-ttu-id="1ef07-120">주소록 공유 폴더의 루트에 있는 Company_Phone_Number_Normalization_Rules 파일을 찾아 비즈니스용 Skype Server 2019의 파일럿 풀에 있는 주소록 공유 폴더의 루트에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ef07-120">Find the Company_Phone_Number_Normalization_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Skype for Business Server 2019 pilot pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1ef07-121">예제 주소록 정규화 규칙은 ABS 웹 구성 요소 파일 디렉터리에 설치 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ef07-121">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="1ef07-122">경로는 $installedDriveLetter입니다. Components\Address: s e t e **-비즈니스용 Files\Microsoft Server 2019 \ Web Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.**</span><span class="sxs-lookup"><span data-stu-id="1ef07-122">The path is **$installedDriveLetter:\Program Files\Microsoft Skype for Business Server 2019\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**.</span></span> <span data-ttu-id="1ef07-123">이 파일을 **Company_Phone_Number_Normalization_Rules** 로 복사 하 고 이름을 변경 하 여 주소록 공유 폴더의 루트 디렉터리로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ef07-123">This file can be copied and renamed as **Company_Phone_Number_Normalization_Rules.txt** to the address book shared folder's root directory.</span></span> <span data-ttu-id="1ef07-124">예를 들어 **$serverX**에서 공유 되는 주소록은 \*\* \\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles\*\*와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="1ef07-124">For example, the address book shared in **$serverX**, the path will be similar to: **\\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**.</span></span> 

2. <span data-ttu-id="1ef07-125">메모장과 같은 텍스트 편집기를 사용 하 여 Company_Phone_Number_Normalization_Rules 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1ef07-125">Use a text editor, such as Notepad, to open the Company_Phone_Number_Normalization_Rules.txt file.</span></span>

3. <span data-ttu-id="1ef07-126">특정 유형의 항목이 비즈니스용 Skype 서버 2019에서 제대로 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1ef07-126">Certain types of entries will not work correctly in Skype for Business Server 2019.</span></span> <span data-ttu-id="1ef07-127">이 단계에서 설명 하는 항목 유형에 해당 하는 파일을 살펴보고 필요에 따라 편집한 다음 파일럿 풀의 주소록 공유 폴더에 변경 내용을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ef07-127">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>

    <span data-ttu-id="1ef07-128">필수 공백 또는 문장 부호를 포함 하는 문자열은 정규화 규칙에 입력 된 문자열에서 제거 되므로 정규화 규칙에 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ef07-128">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span></span> <span data-ttu-id="1ef07-129">필수 공백이 나 문장 부호를 포함 하는 문자열을 사용 하는 경우 문자열을 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ef07-129">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span></span> <span data-ttu-id="1ef07-130">예를 들어 다음 문자열을 선택 하면 정규화 규칙이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ef07-130">For example, the following string would cause the normalization rule to fail:</span></span>

   ```
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    <span data-ttu-id="1ef07-131">다음 문자열은 정규화 규칙을 실패 시 키 지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1ef07-131">The following string would not cause the normalization rule to fail:</span></span>

   ```
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a><span data-ttu-id="1ef07-132">UseNormalizationRules 및 IgnoreGenericRules를 true로 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="1ef07-132">To set UseNormalizationRules and IgnoreGenericRules to true</span></span>

1. <span data-ttu-id="1ef07-133">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **Microsoft 비즈니스용 skype 서버 2019**을 차례로 클릭 한 다음 비즈니스용 **skype server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ef07-133">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="1ef07-134">다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ef07-134">Do one of the following:</span></span>

   - <span data-ttu-id="1ef07-135">배포에 비즈니스용 Skype 서버 2019만 포함 된 경우 전역 수준에서 다음 cmdlet을 실행 하 여 **UseNormalizationRules** 및 **ignoregenericrules** 의 값을 True로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ef07-135">If your deployment includes only Skype for Business Server 2019, run the following cmdlet at the global level to change the values for **UseNormalizationRules** and **IgnoreGenericRules** to True:</span></span> 

   ```
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - <span data-ttu-id="1ef07-136">배포에 비즈니스용 Skype 서버 2019와 레거시 설치의 조합이 포함 되어 있는 경우 다음 cmdlet을 실행 하 고 토폴로지의 각 비즈니스용 Skype Server 2019 풀에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ef07-136">If your deployment includes a combination of Skype for Business Server 2019 and a legacy install, run the following cmdlet and assign it to each Skype for Business Server 2019 pool in the topology:</span></span>

   ```
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. <span data-ttu-id="1ef07-137">중앙 관리 저장소 복제가 모든 풀에서 발생 하는 것을 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="1ef07-137">Wait for Central Management store replication to occur on all pools.</span></span>

4. <span data-ttu-id="1ef07-138">배포에 대 한 전화 정규화 규칙 파일 "Company_Phone_Number_Normalization_Rules"를 수정 하 여 콘텐츠를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="1ef07-138">Modify the phone normalization rules file, "Company_Phone_Number_Normalization_Rules.txt", for your deployment to clear the content.</span></span> <span data-ttu-id="1ef07-139">파일은 각 비즈니스용 Skype Server 2019 풀의 파일 공유에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ef07-139">The file is on the file share of each Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="1ef07-140">파일이 없는 경우 "Company_Phone_Number_Normalization_Rules" 라는 빈 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1ef07-140">If the file is not present, then create an empty file named "Company_Phone_Number_Normalization_Rules.txt".</span></span>

5. <span data-ttu-id="1ef07-141">모든 프런트 엔드 풀이 새 파일을 읽을 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="1ef07-141">Wait several minutes for all Front End pools to read the new files.</span></span>

6. <span data-ttu-id="1ef07-142">배포의 각 비즈니스용 Skype Server 2019 풀에서 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ef07-142">Run the following cmdlet on each Skype for Business Server 2019 pool in your deployment:</span></span>

   ```
   Update-CsAddressBook
   ```


