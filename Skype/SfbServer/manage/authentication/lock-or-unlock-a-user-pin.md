---
title: 비즈니스용 Skype 서버에서 사용자 PIN 잠금 또는 잠금 해제
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
ms.assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
description: '요약: 비즈니스용 Skype 서버용 사용자의 전화 접속 회의 PIN을 잠그거나 잠금 해제 합니다.'
ms.openlocfilehash: e9a5e59497a4cb771d0b20cef55b09b26817216d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818790"
---
# <a name="lock-or-unlock-a-user-pin-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 사용자 PIN 잠금 또는 잠금 해제
 
**요약:** 비즈니스용 Skype 서버에서 사용자의 전화 접속 회의 PIN을 잠그거나 잠금 해제 합니다.
  
비즈니스용 Skype Server 제어판의 **사용자** 섹션에서 사용자의 PIN을 잠그거나 잠금을 해제할 수 있습니다.
  
### <a name="to-lock-a-users-pin-in-skype-for-business-server-control-panel"></a>비즈니스용 Skype Server 제어판에서 사용자의 PIN을 잠그려면

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
    
   f. 사용자를 클릭 하 고 **동작**을 클릭 한 다음 **핀**고정을 클릭 합니다.
    
### <a name="to-unlock-a-users-pin-in-skype-for-business-server-control-panel"></a>비즈니스용 Skype Server 제어판에서 사용자의 PIN 잠금 해제

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
    
   f. 사용자를 클릭 하 고 **작업**을 클릭 한 다음 **PIN 잠금 해제**를 클릭 합니다.
    
## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 사용자 Pin 잠금 및 잠금 해제

Windows PowerShell 및 잠금-csclientpin cmdlet을 사용 하 여 사용자 Pin을 잠그고 잠금을 해제할 수 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 비즈니스용 Skype Server에 연결 하는 방법에 대 한 자세한 내용은 블로그 문서 ["빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"](https://go.microsoft.com/fwlink/p/?linkId=255876)를 참조 하세요. 이 프로세스는 비즈니스용 Skype 서버에서 동일 합니다.
  
### <a name="to-lock-a-user-pin"></a>사용자 PIN을 잠그려면

- 사용자의 PIN을 잠그려면 Lock-CsClientPin cmdlet을 사용 합니다. 예를 들면 다음과 같습니다.
    
  ```PowerShell
  Lock-CsClientPin -Identity "Ken Myer"
  ```

### <a name="to-unlock-a-user-pin"></a>사용자 PIN의 잠금을 해제 하려면

- 사용자 PIN의 잠금을 해제 하려면 잠금 해제-CsClientPin cmdlet을 사용 합니다. 예를 들면 다음과 같습니다.
    
  ```PowerShell
  Unlock-CsClientPin -Identity "Ken Myer"
  ```

자세한 내용은 [잠금 csclientpin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) 및 [잠금 해제-csclientpin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) cmdlet에 대 한 도움말 항목을 참조 하세요.
