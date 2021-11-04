---
title: 사용자당 PIN 정책을 할당합니다비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: d8211c64-0b63-4193-a074-673da7d14287
description: '요약: AV 및 OAuth 인증서를 단계적으로 비즈니스용 Skype 서버.'
ms.openlocfilehash: 2ca870ff500c5a963db17f90262c2f128c847d60
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60750357"
---
# <a name="assign-a-per-user-pin-policy-in-skype-for-business-server"></a>사용자당 PIN 정책을 할당합니다비즈니스용 Skype 서버

**요약:** 단계 AV 및 OAuth 인증서를 비즈니스용 Skype 서버.
  
전화 접속 회의 PIN(개인 식별 번호) 정책은 사용자 계정의 개별 설정 중 하나로, 비즈니스용 Skype 서버 제어판에서 구성할 수 있습니다.
  
하나 이상의 사용자당 PIN 정책을 배포하는 것은 선택 사항입니다. 전역 수준 PIN 정책 또는 사이트 수준 PIN 정책만 배포할 수도 있습니다. 사용자별 정책을 배포하는 경우에는 해당 정책을 사용자, 그룹 또는 연락처 개체에 명시적으로 할당해야 합니다. 특정 사이트 수준 또는 사용자별 정책이 할당되지 않은 경우 전화 접속 회의에 PIN을 사용하는 데 관한 사용자 권한 및 사용 권한은 자동으로 전역 수준 PIN 정책에 정의된 권한으로 기본 설정됩니다.
  
사용자당 PIN 정책을 하나 이상 만든 후 이 항목의 절차에 따라 서버에서 특정 사용자가 만들고 사용하는 PIN에 대해 부과할 제약 조건을 지정하는 정책을 할당합니다.
  
### <a name="to-assign-a-per-user-pin-policy"></a>사용자당 PIN 정책을 할당하기 위해

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다.  
    
3. 왼쪽 탐색 모음에서 **사용자** 를 클릭합니다.
    
4. 다음 방법 중 하나를 통해 사용자를 찾습니다.
    
   - **사용자 검색** 상자에 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 처음 부분을 입력하고 **찾기** 를 클릭합니다.
    
   - 저장된 쿼리가 있는 경우 **쿼리 열기** 아이콘을 클릭하고 **열기** 대화 상자를 통해 쿼리(예: .usf 파일)를 검색한 후에 **찾기** 를 클릭합니다.
    
5. (선택 사항) 추가 검색 조건을 지정하여 결과 범위를 좁힙니다.
    
   a. **필터 추가** 를 클릭합니다.
    
   b. 사용자 속성을 입력하거나 드롭다운 목록의 화살표를 클릭하여 사용자 속성을 선택합니다.
    
   c. **같음** 드롭다운 목록에서 연산자(예: **같음** 또는 **같지 않음**)를 클릭합니다.
    
   d. 선택한 사용자 속성에 따라 검색 결과를 필터링하는 데 사용할 조건을 직접 입력하거나 드롭다운 목록에서 화살표를 클릭하여 입력합니다.
    
    > [!TIP]
    > 쿼리에 검색 절을 더 추가하려면 **필터 추가** 를 클릭합니다. 
  
   e. **찾기** 를 클릭합니다.
    
6. 검색 결과에서 사용자를 클릭하고 **동작** 을 클릭한 후에 **정책 할당** 을 클릭합니다.
    
    > [!TIP]
    > 동일한 사용자당 PIN 정책을 여러 사용자에게 적용하려면 검색 결과에서 여러 사용자를 선택한 다음 작업을 **클릭한** 다음 정책 **할당을 클릭합니다.** 
  
7. 정책 **할당 에서** **PIN 정책** 아래에서 다음 중 하나를 합니다.
    
    > [!NOTE]
    > 정책 할당 대화 상자를 사용하여 구성할 수 있는 정책이 여러 개이기 때문에 대화 상자의 모든 정책에 대해 기본적으로  **\<Keep as is\>** 선택됩니다. 이 설정을 변경하지 않으면 이전에 사용자에게 지정된 정책이 계속 사용됩니다.
  
   - 전역 비즈니스용 Skype 서버 정책 또는 사이트 수준 정책(정의된 경우)을 자동으로 선택하도록 허용합니다.
    
   - PIN 정책 페이지에서 이전에 정의한 사용자당 PIN 정책의 **이름을** 클릭합니다.
    
     > [!TIP]
     > 지정할 정책을 쉽게 결정하려면 정책 이름을 클릭한 후 **보기** 를 클릭하여 정책에 정의된 사용자 권한 및 권한을 확인합니다.
  
8. 작업을 마치면 **확인** 을 클릭합니다.
    
## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a>cmdlet을 Per-User PIN 정책 Windows PowerShell 할당

사용자당 PIN 정책은 **Grant-CsPinPolicy** cmdlet과 Windows PowerShell 할당할 수 있습니다. 비즈니스용 Skype 서버 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다. 원격 연결을 사용하여 원격 Windows PowerShell 연결하는 비즈니스용 Skype 서버 [Microsoft Lync 원격 PowerShell 관리"를 참조합니다.](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/) 프로세스는 동일한 비즈니스용 Skype 서버.
  
### <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a>단일 사용자에게 사용자당 PIN 정책을 할당하는 경우

- 다음 명령은 사용자 Ken Myer에게 사용자당 PIN 정책 RedmondPinPolicy를 할당합니다.
    
  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"
  ```

### <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a>여러 사용자에게 사용자당 PIN 정책을 할당하기 위해

- 다음 명령은 Redmond 시에서 작업하는 모든 사용자에게 사용자당 PIN 정책 RedmondUsersPinPolicy를 할당합니다. 이 명령에 사용되는 LdapFilter 매개 변수에 대한 자세한 내용은 [Get-CsUser를 참조합니다.](/powershell/module/skype/get-csuser?view=skype-ps)
    
  ```PowerShell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"
  ```

### <a name="to-unassign-a-per-user-pin-policy"></a>사용자당 PIN 정책의 위임

- 다음 명령은 이전에 Ken Myer에게 할당된 사용자당 PIN 정책을 할당을 해지합니다. 사용자별 정책을 지정 해제한 후 Ken Myer는 자동으로 글로벌 정책 또는 로컬 사이트 정책(있는 경우)을 사용해서 관리됩니다. 사이트 정책은 글로벌 정책보다 우선 적용됩니다.
    
  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

자세한 내용은 [Grant-CsPinPolicy를 참조합니다.](/powershell/module/skype/grant-cspinpolicy?view=skype-ps)
  
## <a name="see-also"></a>참고 항목

[새 PIN 정책을 비즈니스용 Skype 서버](create-a-new-pin-policy.md)