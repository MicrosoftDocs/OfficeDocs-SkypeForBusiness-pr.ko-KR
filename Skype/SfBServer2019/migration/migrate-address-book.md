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
description: 일반적으로 주소 책은 나머지 토폴로지와 함께 마이그레이션됩니다. 그러나 레거시 환경에서 다음을 사용자 지정한 경우 몇 가지 마이그레이션 후 단계를 수행해야 할 수 있습니다.
ms.openlocfilehash: 6d2ccf0d38814d149495518a71f888f0c2999d24
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752840"
---
# <a name="migrate-address-book"></a>주소록 마이그레이션

일반적으로 주소 책은 나머지 토폴로지와 함께 마이그레이션됩니다. 그러나 레거시 환경에서 다음을 사용자 지정한 경우 몇 가지 마이그레이션 후 단계를 수행해야 할 수 있습니다. 

- 주소록 정규화 규칙을 사용자 지정

- **UseNormalizationRules** 매개 변수의 기본값을 False로 변경 


 **주소록 정규화 규칙**

레거시 환경에서 주소부 정규화 규칙을 사용자 지정한 경우 사용자 지정된 규칙을 파일럿 풀로 마이그레이션해야 합니다. 주소록 정규화 규칙을 사용자 지정하지 않은 경우 주소록 서비스에 대해 마이그레이션할 항목이 없습니다. 비즈니스용 Skype 서버 2019의 기본 정규화 규칙은 레거시 설치에 대한 기본 규칙과 동일합니다. 사용자 지정된 정규화 규칙을 마이그레이션하려면 이 섹션 뒷부분에 나온 절차를 따르십시오.

> [!NOTE]
> 조직에서 원격 통화 제어를 사용하고 사용자가 주소록 정규화 규칙을 사용자 지정한 경우 원격 통화 제어를 사용하기 전에 이 항목의 절차를 수행해야 합니다. 이 절차를 수행하려면 RTCUniversalServerAdmins 그룹의 구성원이거나 이와 동등한 권한이 있어야 합니다. 

 **False로 설정된 UseNormalizationRules**

비즈니스용 Skype 서버 2019에서 정규화 규칙을 적용하지 않고도 사용자가 Active Directory 도메인 서비스에 정의된 전화 번호를 사용할 수 있도록 **UseNormalizationRules의** 값을 False로 설정하는 경우 **UseNormalizationRules** 및 **IgnoreGenericRules** 매개 변수를 True로 설정해야 합니다. 이러한 매개 변수를 True로 설정하려면 이 섹션 뒷부분에 나온 절차를 따르십시오. 

## <a name="to-migrate-address-book-customized-normalization-rules"></a>사용자 지정된 주소록 정규화 규칙을 마이그레이션하려면

1. 주소 Company_Phone_Number_Normalization_Rules.txt 폴더의 루트에서 Company_Phone_Number_Normalization_Rules.txt 파일을 찾아서 비즈니스용 Skype 서버 2019 파일럿 풀의 주소 책 공유 폴더 루트에 복사합니다.

    > [!NOTE]
    > ABS 웹 구성 요소 파일 디렉터리에 샘플 주소록 정규화 규칙이 설치되어 있습니다. 경로는 **$installedDriveLetter:\Program Files\Microsoft Skype for Business Server 2019\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt.** 이 파일은 주소Company_Phone_Number_Normalization_Rules.txt폴더의 루트  디렉터리에 복사하여 이름을 바일 수 있습니다. 예를 들어 주소 $serverX 경로는 $serverX **\\ \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles와** 유사합니다. 

2. 메모장과 같은 텍스트 편집기를 사용하여 Company_Phone_Number_Normalization_Rules.txt 파일을 엽니다.

3. 특정 유형의 항목은 비즈니스용 Skype 서버 2019에서 제대로 작동하지 않습니다. 파일에서 이 단계에 설명한 항목 유형을 조사하고, 필요에 따라 편집한 후 변경 내용을 파일럿 풀의 주소록 공유 폴더에 저장합니다.

    공백 또는 문장 부호가 포함된 문자열의 경우 정규화 규칙에 입력할 때 이러한 문자가 제거되기 때문에 이러한 문자열을 사용하면 정규화 규칙이 실패할 수 있습니다. 공백 또는 문장 부호가 필요한 문자열의 경우 문자열을 수정해야 합니다. 예를 들어 다음 문자열을 사용하면 정규화 규칙이 실패합니다.

   ```console
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    다음 문자열을 사용하면 정규화 규칙이 실패하지 않습니다.

   ```console
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>UseNormalizationRules 및 IgnoreGenericRules를 true로 설정하려면

1. 비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** **Microsoft 비즈니스용 Skype 서버 2019,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**

2. 다음 중 하나를 수행합니다.

   - 배포에 비즈니스용 Skype 서버 2019만 포함되어 있는 경우 전역 수준에서 다음 cmdlet을 실행하여 **UseNormalizationRules** 및 **IgnoreGenericRules의** 값을 True로 변경합니다. 

   ```PowerShell
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - 배포에 비즈니스용 Skype 서버 2019와 레거시 설치가 조합된 경우 다음 cmdlet을 실행하여 토폴로지의 각 비즈니스용 Skype 서버 2019 풀에 할당합니다.

   ```PowerShell
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. 모든 풀에서 중앙 관리 저장소 복제가 발생할 때까지 기다렸다가

4. 배포의 전화 정규화 규칙 파일 "Company_Phone_Number_Normalization_Rules.txt"에 들어 있는 내용을 삭제하여 이 파일을 수정합니다. 파일은 각 비즈니스용 Skype 서버 2019 풀의 파일 공유에 있습니다. 이 파일이 없는 경우 "Company_Phone_Number_Normalization_Rules.txt"라는 이름의 비어 있는 파일을 만듭니다.

5. 모든 프런트 엔드 풀에서 새 파일을 읽을 때까지 몇 분 정도 기다립니다.

6. 배포의 각 비즈니스용 Skype 서버 2019 풀에서 다음 cmdlet을 실행합니다.

   ```PowerShell
   Update-CsAddressBook
   ```


