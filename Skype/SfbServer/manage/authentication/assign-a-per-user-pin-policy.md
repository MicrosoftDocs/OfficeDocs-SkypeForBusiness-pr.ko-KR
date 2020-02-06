---
title: 비즈니스용 Skype 서버에서 사용자 단위 PIN 정책 할당
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d8211c64-0b63-4193-a074-673da7d14287
description: '요약: 비즈니스용 Skype 서버용으로 AV 및 OAuth 인증서를 준비 합니다.'
ms.openlocfilehash: b7c353090f9eef3d2d2fbd0e6f8884121458f2f0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818870"
---
# <a name="assign-a-per-user-pin-policy-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 사용자 단위 PIN 정책 할당

**요약:** 비즈니스용 Skype 서버용으로 AV 및 OAuth 인증서를 준비 합니다.
  
전화 접속 회의 개인 식별 번호 (PIN) 정책은 비즈니스용 Skype 서버 제어판에서 구성할 수 있는 사용자 계정의 개별 설정 중 하나입니다.
  
사용자 단위 PIN 정책은 하나 이상 배포 하는 것이 선택 사항입니다. 전역 수준 PIN 정책 또는 사이트 수준 PIN 정책만 배포할 수도 있습니다. 사용자별 정책을 배포 하는 경우 사용자, 그룹 또는 연락처 개체에 명시적으로 할당 해야 합니다. 특정 사이트 수준 또는 사용자별 정책이 할당 되지 않은 경우 전화 접속 회의의 핀 사용에 대 한 사용자 권한 및 사용 권한은 자동으로 전역 수준 PIN 정책에 정의 된 것과 관련 됩니다.
  
하나 이상의 사용자 단위 PIN 정책을 만든 후에는이 항목의 절차를 사용 하 여 서버가 특정 사용자가 만들고 사용 하는 핀에 대해 설정할 제약 조건을 지정 하는 정책을 할당 합니다.
  
### <a name="to-assign-a-per-user-pin-policy"></a>사용자 단위 PIN 정책을 할당 하려면

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.
    
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.  
    
3. 왼쪽 탐색 모음에서 **사용자**를 클릭 합니다.
    
4. 사용자를 찾으려면 다음 방법 중 하나를 사용 합니다.
    
   - 사용자 **검색** 상자에 표시 이름, 이름, 성, SAM (보안 계정 관리자) 계정 이름, SIP 주소 또는 사용자 계정의 URI (Uniform resource identifier) 중 첫 번째 부분을 입력 한 다음 **찾기를**클릭 합니다.
    
   - 저장 된 쿼리가 있는 경우 **쿼리 열기** 아이콘을 클릭 하 고 **열기** 대화 상자를 사용 하 여 쿼리 (usf 파일)를 검색 한 다음 **찾기를**클릭 합니다.
    
5. ) 추가 검색 조건을 지정 하 여 결과의 범위를 좁힙니다.
    
   에서. **필터 추가**를 클릭 합니다.
    
   b. 사용자 속성을 입력 하거나 드롭다운 목록에서 화살표를 클릭 하 여 속성을 선택 하 여 입력 합니다.
    
   c. 다음과 같이 **같음** 드롭다운 목록에서 연산자 (예: **같음** 또는 **같지 않음**)를 클릭 합니다.
    
   a. 선택한 사용자 속성에 따라 검색 결과를 입력 하거나 드롭다운 목록에서 화살표를 클릭 하 여 필터링 하는 데 사용할 조건을 입력 합니다.
    
    > [!TIP]
    > 쿼리에 추가 검색 절을 추가 하려면 **필터 추가**를 클릭 합니다. 
  
   z.e.n.works. **찾기를**클릭 합니다.
    
6. 검색 결과에서 사용자를 클릭 하 고 **작업**을 클릭 한 다음 **정책 할당**을 클릭 합니다.
    
    > [!TIP]
    > 동일한 사용자별 PIN 정책을 여러 사용자에 게 적용 하려면 검색 결과에서 여러 사용자를 선택한 다음 **작업**을 클릭 하 고 **정책 할당**을 클릭 합니다. 
  
7. **지정 정책**에서 **핀 정책**아래에서 다음 중 하나를 수행 합니다.
    
    > [!NOTE]
    > **정책 할당** 대화 상자를 ** \<\> ** 사용 하 여 구성할 수 있는 정책이 여러 개 있기 때문에 대화 상자에 있는 모든 정책에 대해 다음으로 유지 옵션이 기본적으로 선택 되어 있습니다. 이전에이 설정을 변경 하지 않고 사용자에 게 할당 된 정책을 계속 사용 합니다.
  
   - 비즈니스용 Skype 서버에서 전역 수준 정책이 자동으로 선택 되도록 허용 하거나 정의 된 경우 사이트 수준 정책
    
   - 이전에 **PIN 정책** 페이지에 정의한 사용자 단위 PIN 정책의 이름을 클릭 합니다.
    
     > [!TIP]
     > 할당 하려는 정책을 결정할 수 있도록 정책 이름을 클릭 한 후 **보기** 를 클릭 하 여 정책에 정의 된 사용자 권한 및 사용 권한을 확인 합니다.
  
8. 완료 되 면 **확인**을 클릭 합니다.
    
## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 사용자 단위 PIN 정책 할당

Windows PowerShell 및 **CsPinPolicy** cmdlet을 사용 하 여 사용자 단위 PIN 정책을 할당할 수 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 비즈니스용 Skype Server에 연결 하는 방법에 대 한 자세한 내용은 블로그 문서 ["빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"](https://go.microsoft.com/fwlink/p/?linkId=255876)를 참조 하세요. 이 프로세스는 비즈니스용 Skype 서버에서 동일 합니다.
  
### <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a>단일 사용자에 게 사용자 단위 PIN 정책을 할당 하려면 다음을 사용 합니다.

- 다음 명령을 사용 하 여 사용자 단위 핀 정책 RedmondPinPolicy: 진구 Myer에 할당 합니다.
    
  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"
  ```

### <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a>사용자 단위 PIN 정책을 여러 사용자에 게 할당 하려면

- 다음 명령을 사용 하 여 사용자 단위 핀 정책 RedmondUsersPinPolicy을 Redmond의 구/군/시로 근무 하는 모든 사용자에 게 할당 합니다. 이 명령에 사용 되는 LdapFilter 매개 변수에 대 한 자세한 내용은 [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)를 참조 하세요.
    
  ```PowerShell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"
  ```

### <a name="to-unassign-a-per-user-pin-policy"></a>사용자 단위 PIN 정책의 할당을 취소 하려면

- 다음 명령은: 진구 Myer에 이전에 할당 된 사용자 단위 PIN 정책을 할당 해제 합니다. 사용자별 정책에 할당 되지 않은 경우: 진구 Myer는 전역 정책을 사용 하 여 자동으로 관리 되거나 있는 경우 해당 로컬 사이트 정책이 됩니다. 사이트 정책이 전역 정책 보다 우선 합니다.
    
  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

자세한 내용은 [허용-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps)을 참조 하세요.
  
## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버에서 새 PIN 정책 만들기](create-a-new-pin-policy.md)
