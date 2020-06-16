---
title: 주소록 마이그레이션
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Address Book
ms:assetid: ac7f0f39-4c6d-4702-8e25-93a73e3d800f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205160(v=OCS.15)
ms:contentKeyID: 48185064
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee0dc4d50fb3b60d4f6a9581d497df11da630122
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757039"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a>주소록 마이그레이션

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-09_

일반적으로 Lync Server 2010 주소록은 토폴로지의 나머지 부분과 함께 마이그레이션됩니다. 그러나 Lync Server 2010 환경에서 다음을 사용자 지정한 경우 몇 가지 마이그레이션 후 단계를 수행 해야 할 수 있습니다.

  - OU(조직 구성 단위)별로 주소록 항목을 그룹화하도록 **PartitionbyOU** WMI 속성 설정

  - 주소록 정규화 규칙을 사용자 지정

  - **UseNormalizationRules** 매개 변수의 기본값을 False로 변경

**그룹화된 주소록 항목**

If you set the **PartitionbyOU** WMI property to True to create address books for each OU, you need to set the **msRTCSIP-GroupingId** Active Directory attribute on users and contacts if you want to continue grouping address book entries. You might want to group address book entries to limit the scope of Address Book searches. To use the **msRTCSIP-GroupingId** attribute, write a script to populate the attribute, assigning the same value for all of the users that you want to group together. For example, assign a single value for all the users in an OU.

**주소록 정규화 규칙**

Lync Server 2010 환경에서 주소록 정규화 규칙을 사용자 지정한 경우 파일럿 풀로 사용자 지정 된 규칙을 마이그레이션해야 합니다. 주소록 정규화 규칙을 사용자 지정하지 않은 경우 주소록 서비스에 대해 마이그레이션할 항목이 없습니다. Lync Server 2013에 대 한 기본 정규화 규칙은 Lync Server 2010의 기본 규칙과 동일 합니다. 사용자 지정된 정규화 규칙을 마이그레이션하려면 이 섹션 뒷부분에 나온 절차를 따르십시오.

<div>


> [!NOTE]  
> If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control. The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.



</div>

**False로 설정된 UseNormalizationRules**

**UseNormalizationRules** 의 값을 False로 설정 하면 사용자가 Lync Server 2013 정규화 규칙을 적용 하지 않고 Active Directory 도메인 서비스에 정의 된 대로 전화 번호를 사용할 수 있도록 **UseNormalizationRules** 및 **Ignoregenericrules** 매개 변수를 True로 설정 해야 합니다. 이러한 매개 변수를 True로 설정하려면 이 섹션 뒷부분에 나온 절차를 따르십시오.

<div>

## <a name="to-migrate-address-book-customized-normalization-rules"></a>사용자 지정된 주소록 정규화 규칙을 마이그레이션하려면

1.  \_ \_ \_ \_ 주소록 공유 폴더의 루트에서 회사 전화 번호 정규화Rules.txt 파일을 찾아 Lync Server 2013 파일럿 풀에 있는 주소록 공유 폴더의 루트에 복사 합니다.
    
    <div>
    

    > [!NOTE]  
    > ABS 웹 구성 요소 파일 디렉터리에 샘플 주소록 정규화 규칙이 설치되어 있습니다. 경로는 <STRONG>$설치 드라이브 문자:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt</STRONG>입니다. 이 파일 &nbsp; <STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp; 을Company_Phone_Number_Normalization_Rules.txt주소록 공유 폴더의 루트 디렉터리에 복사 하 고 이름을 바꿀 수 있습니다. 예를 들어 <STRONG>$serverX</STRONG>에서 공유 되는 주소록의 &nbsp; 경로는 <STRONG> \\ $serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>와 비슷합니다.

    
    </div>

2.  메모장과 같은 텍스트 편집기를 사용 하 여 회사 \_ 전화 \_ 번호 \_ 정규화 \_Rules.txt 파일을 엽니다.

3.  특정 유형의 항목은 Lync Server 2013에서 올바르게 작동 하지 않습니다. 파일에서 이 단계에 설명한 항목 유형을 조사하고, 필요에 따라 편집한 후 변경 내용을 파일럿 풀의 주소록 공유 폴더에 저장합니다.
    
    Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules. If you have strings that include required whitespace or punctuation, you need to modify the strings. For example, the following string would cause the normalization rule to fail:
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    다음 문자열을 사용하면 정규화 규칙이 실패하지 않습니다.
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<div>

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>UseNormalizationRules 및 IgnoreGenericRules를 true로 설정하려면

1.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

2.  다음 중 하나를 수행합니다.
    
      - 배포에 Lync Server 2013만 포함 되는 경우 전역 수준에서 다음 cmdlet을 실행 하 여 **UseNormalizationRules** 및 **ignoregenericrules** 의 값을 True로 변경 합니다.
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - 배포에 Lync Server 2013 및 Lync Server 2010 또는 Office Communications Server 2007 r 2의 조합이 포함 된 경우 다음 cmdlet을 실행 하 여 토폴로지의 각 Lync Server 2013 pool에 할당 합니다.
        
            New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  모든 풀에서 중앙 관리 저장소 복제가 발생할 때까지 기다립니다.

4.  배포에서 콘텐츠를 지우기 위해 전화 정규화 규칙 파일인 "회사 \_ 전화 \_ 번호 \_ 정규화 \_Rules.txt"를 수정 합니다. 파일이 각 Lync Server 2013 풀의 파일 공유에 있습니다. 파일이 없으면 "회사 \_ 전화 \_ 번호 \_ 정규화 \_Rules.txt" 라는 빈 파일을 만듭니다.

5.  모든 프런트 엔드 풀에서 새 파일을 읽을 때까지 몇 분 정도 기다립니다.

6.  배포의 각 Lync Server 2013 풀에서 다음 cmdlet을 실행 합니다.
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

