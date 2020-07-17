---
title: 주소록 마이그레이션
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 일반적으로 주소록은 토폴로지의 나머지 부분과 함께 마이그레이션됩니다. 그러나 레거시 환경에서 다음을 사용자 지정한 경우에는 일부 마이그레이션 후 단계를 수행 해야 할 수 있습니다.
ms.openlocfilehash: 6d2ccf0d38814d149495518a71f888f0c2999d24
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752840"
---
# <a name="migrate-address-book"></a><span data-ttu-id="b90e3-104">주소록 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="b90e3-104">Migrate Address Book</span></span>

<span data-ttu-id="b90e3-105">일반적으로 주소록은 토폴로지의 나머지 부분과 함께 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="b90e3-105">In general, the Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="b90e3-106">그러나 레거시 환경에서 다음을 사용자 지정한 경우에는 일부 마이그레이션 후 단계를 수행 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b90e3-106">However, you might need to perform some post-migration steps if you customized the following in your legacy environment:</span></span> 

- <span data-ttu-id="b90e3-107">주소록 정규화 규칙을 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="b90e3-107">Customized the Address Book normalization rules.</span></span>

- <span data-ttu-id="b90e3-108">**UseNormalizationRules** 매개 변수의 기본값을 False로 변경</span><span class="sxs-lookup"><span data-stu-id="b90e3-108">Changed the default value for the **UseNormalizationRules** parameter to False.</span></span> 


 <span data-ttu-id="b90e3-109">**주소록 정규화 규칙**</span><span class="sxs-lookup"><span data-stu-id="b90e3-109">**Address Book Normalization Rules**</span></span>

<span data-ttu-id="b90e3-110">레거시 환경에서 주소록 정규화 규칙을 사용자 지정한 경우에는 파일럿 풀로 사용자 지정 된 규칙을 마이그레이션해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b90e3-110">If you customized Address Book normalization rules in your legacy environment, you must migrate the customized rules to your pilot pool.</span></span> <span data-ttu-id="b90e3-111">주소록 정규화 규칙을 사용자 지정하지 않은 경우 주소록 서비스에 대해 마이그레이션할 항목이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b90e3-111">If you did not customize Address Book normalization rules, you have nothing to migrate for Address Book service.</span></span> <span data-ttu-id="b90e3-112">비즈니스용 Skype 서버 2019에 대 한 기본 정규화 규칙은 레거시 설치의 기본 규칙과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="b90e3-112">The default normalization rules for Skype for Business Server 2019 are the same as the default rules for the legacy install.</span></span> <span data-ttu-id="b90e3-113">사용자 지정된 정규화 규칙을 마이그레이션하려면 이 섹션 뒷부분에 나온 절차를 따르십시오.</span><span class="sxs-lookup"><span data-stu-id="b90e3-113">Follow the procedure later in this section to migrate customized normalization rules.</span></span>

> [!NOTE]
> <span data-ttu-id="b90e3-p104">조직에서 원격 통화 제어를 사용하고 사용자가 주소록 정규화 규칙을 사용자 지정한 경우 원격 통화 제어를 사용하기 전에 이 항목의 절차를 수행해야 합니다. 이 절차를 수행하려면 RTCUniversalServerAdmins 그룹의 구성원이거나 이와 동등한 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b90e3-p104">If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control. The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.</span></span> 

 <span data-ttu-id="b90e3-116">**False로 설정된 UseNormalizationRules**</span><span class="sxs-lookup"><span data-stu-id="b90e3-116">**UseNormalizationRules Set to False**</span></span>

<span data-ttu-id="b90e3-117">**UseNormalizationRules** 의 값을 False로 설정 하 여 사용자가 비즈니스용 Skype 서버 2019에서 정규화 규칙을 적용 하지 않고 Active Directory 도메인 서비스에 정의 된 대로 전화 번호를 사용할 수 있도록 하려면 **UseNormalizationRules** 및 **Ignoregenericrules** 매개 변수를 True로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b90e3-117">If you set the value for **UseNormalizationRules** to False so that users can use phone numbers as they are defined in Active Directory Domain Services without having Skype for Business Server 2019 apply normalization rules, you need to set the **UseNormalizationRules** and **IgnoreGenericRules** parameters to True.</span></span> <span data-ttu-id="b90e3-118">이러한 매개 변수를 True로 설정하려면 이 섹션 뒷부분에 나온 절차를 따르십시오.</span><span class="sxs-lookup"><span data-stu-id="b90e3-118">Follow the procedure later in this section to set these parameters to True.</span></span> 

## <a name="to-migrate-address-book-customized-normalization-rules"></a><span data-ttu-id="b90e3-119">사용자 지정된 주소록 정규화 규칙을 마이그레이션하려면</span><span class="sxs-lookup"><span data-stu-id="b90e3-119">To migrate Address Book customized normalization rules</span></span>

1. <span data-ttu-id="b90e3-120">주소록 공유 폴더의 루트에서 Company_Phone_Number_Normalization_Rules.txt 파일을 찾아 비즈니스용 Skype 서버 2019의 파일럿 풀에 있는 주소록 공유 폴더의 루트에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="b90e3-120">Find the Company_Phone_Number_Normalization_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Skype for Business Server 2019 pilot pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b90e3-121">ABS 웹 구성 요소 파일 디렉터리에 샘플 주소록 정규화 규칙이 설치되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b90e3-121">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="b90e3-122">경로는 **$installedDriveLetter: 웹 \ Files\Microsoft 비즈니스용 Skype 서버 2019 \ Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**입니다.</span><span class="sxs-lookup"><span data-stu-id="b90e3-122">The path is **$installedDriveLetter:\Program Files\Microsoft Skype for Business Server 2019\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**.</span></span> <span data-ttu-id="b90e3-123">이 파일을 **Company_Phone_Number_Normalization_Rules.txt** 주소록 공유 폴더의 루트 디렉터리에 복사 하 고 이름을 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b90e3-123">This file can be copied and renamed as **Company_Phone_Number_Normalization_Rules.txt** to the address book shared folder's root directory.</span></span> <span data-ttu-id="b90e3-124">예를 들어 **$serverX**에서 공유 되는 주소록의 경로는 \*\* \\ $serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles\*\*와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="b90e3-124">For example, the address book shared in **$serverX**, the path will be similar to: **\\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**.</span></span> 

2. <span data-ttu-id="b90e3-125">메모장과 같은 텍스트 편집기를 사용하여 Company_Phone_Number_Normalization_Rules.txt 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b90e3-125">Use a text editor, such as Notepad, to open the Company_Phone_Number_Normalization_Rules.txt file.</span></span>

3. <span data-ttu-id="b90e3-126">특정 유형의 항목이 비즈니스용 Skype 서버 2019에서 올바르게 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b90e3-126">Certain types of entries will not work correctly in Skype for Business Server 2019.</span></span> <span data-ttu-id="b90e3-127">파일에서 이 단계에 설명한 항목 유형을 조사하고, 필요에 따라 편집한 후 변경 내용을 파일럿 풀의 주소록 공유 폴더에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="b90e3-127">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>

    <span data-ttu-id="b90e3-p108">공백 또는 문장 부호가 포함된 문자열의 경우 정규화 규칙에 입력할 때 이러한 문자가 제거되기 때문에 이러한 문자열을 사용하면 정규화 규칙이 실패할 수 있습니다. 공백 또는 문장 부호가 필요한 문자열의 경우 문자열을 수정해야 합니다. 예를 들어 다음 문자열을 사용하면 정규화 규칙이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="b90e3-p108">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules. If you have strings that include required whitespace or punctuation, you need to modify the strings. For example, the following string would cause the normalization rule to fail:</span></span>

   ```console
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    <span data-ttu-id="b90e3-131">다음 문자열을 사용하면 정규화 규칙이 실패하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b90e3-131">The following string would not cause the normalization rule to fail:</span></span>

   ```console
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a><span data-ttu-id="b90e3-132">UseNormalizationRules 및 IgnoreGenericRules를 true로 설정하려면</span><span class="sxs-lookup"><span data-stu-id="b90e3-132">To set UseNormalizationRules and IgnoreGenericRules to true</span></span>

1. <span data-ttu-id="b90e3-133">비즈니스용 Skype 서버 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft 비즈니스용 skype 서버 2019**을 차례로 클릭 한 다음 **비즈니스용 skype 서버 관리 셸을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b90e3-133">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="b90e3-134">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b90e3-134">Do one of the following:</span></span>

   - <span data-ttu-id="b90e3-135">배포에 비즈니스용 Skype 서버 2019만 포함 되는 경우 전역 수준에서 다음 cmdlet을 실행 하 여 **UseNormalizationRules** 및 **ignoregenericrules** 의 값을 True로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="b90e3-135">If your deployment includes only Skype for Business Server 2019, run the following cmdlet at the global level to change the values for **UseNormalizationRules** and **IgnoreGenericRules** to True:</span></span> 

   ```PowerShell
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - <span data-ttu-id="b90e3-136">배포에 비즈니스용 Skype 서버 2019와 레거시 설치가 함께 포함 되어 있는 경우 다음 cmdlet을 실행 하 여 토폴로지의 각 비즈니스용 Skype 서버 2019 풀에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b90e3-136">If your deployment includes a combination of Skype for Business Server 2019 and a legacy install, run the following cmdlet and assign it to each Skype for Business Server 2019 pool in the topology:</span></span>

   ```PowerShell
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. <span data-ttu-id="b90e3-137">모든 풀에서 중앙 관리 저장소 복제가 발생할 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="b90e3-137">Wait for Central Management store replication to occur on all pools.</span></span>

4. <span data-ttu-id="b90e3-138">배포의 전화 정규화 규칙 파일 "Company_Phone_Number_Normalization_Rules.txt"에 들어 있는 내용을 삭제하여 이 파일을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="b90e3-138">Modify the phone normalization rules file, "Company_Phone_Number_Normalization_Rules.txt", for your deployment to clear the content.</span></span> <span data-ttu-id="b90e3-139">파일이 각 비즈니스용 Skype 서버 2019 풀의 파일 공유에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b90e3-139">The file is on the file share of each Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="b90e3-140">이 파일이 없는 경우 "Company_Phone_Number_Normalization_Rules.txt"라는 이름의 비어 있는 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b90e3-140">If the file is not present, then create an empty file named "Company_Phone_Number_Normalization_Rules.txt".</span></span>

5. <span data-ttu-id="b90e3-141">모든 프런트 엔드 풀에서 새 파일을 읽을 때까지 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="b90e3-141">Wait several minutes for all Front End pools to read the new files.</span></span>

6. <span data-ttu-id="b90e3-142">배포의 각 비즈니스용 Skype 서버 2019 풀에서 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b90e3-142">Run the following cmdlet on each Skype for Business Server 2019 pool in your deployment:</span></span>

   ```PowerShell
   Update-CsAddressBook
   ```


