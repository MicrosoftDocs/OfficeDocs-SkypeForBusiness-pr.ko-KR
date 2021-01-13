---
title: 비즈니스용 Skype 서버에서 사용자 PIN 잠금 또는 잠금 해제
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
description: '요약: 비즈니스용 Skype 서버에 대한 사용자의 전화 접속 회의 PIN을 잠그거나 잠금을 해제합니다.'
ms.openlocfilehash: 73bd9affa159fba4ab35844896b9662eea3e1780
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828368"
---
# <a name="lock-or-unlock-a-user-pin-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 사용자 PIN 잠금 또는 잠금 해제
 
**요약:** 비즈니스용 Skype 서버에 대한 사용자의 전화 접속 회의 PIN을 잠그거나 잠금을 해제합니다.
  
비즈니스용 Skype 서버 제어판의 **사용자** 섹션에서 사용자의 PIN을 잠그거나 잠금을 해제할 수 있습니다.
  
### <a name="to-lock-a-users-pin-in-skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판에서 사용자의 PIN을 잠그기 위해

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2. 브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.  
    
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
    
   f. 사용자를 클릭하고, **작업** 을 클릭한 후 **PIN 잠금** 을 클릭합니다.
    
### <a name="to-unlock-a-users-pin-in-skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판에서 사용자의 PIN 잠금을 해제합니다.

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2. 브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.  
    
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
    
   f. 사용자를 클릭하고 **작업** 을 클릭한 후 **PIN 잠금 해제** 를 클릭합니다.
    
## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a>cmdlet을 사용하여 사용자 WINDOWS POWERSHELL 잠금 해제

cmdlet 및 Windows PowerShell cmdlet을 사용하여 사용자 Lock-CsClientPin 잠금을 Unlock-CsClientPin 있습니다. 이러한 cmdlet은 비즈니스용 Skype 서버 관리 셸 또는 비즈니스용 Skype 서버 관리 셸의 원격 세션에서 Windows PowerShell. 원격 서버를 사용하여 비즈니스용 Skype Windows PowerShell 연결하는 데 대한 자세한 내용은 [블로그 문서 "빠른 시작: 원격 PowerShell을 사용하여 Microsoft Lync Server 2010 관리"를](https://go.microsoft.com/fwlink/p/?linkId=255876)참조하세요. 이 프로세스는 비즈니스용 Skype 서버에서 동일합니다.
  
### <a name="to-lock-a-user-pin"></a>사용자 PIN을 잠그려면

- 사용자의 PIN을 잠그기 위해 Lock-CsClientPin cmdlet을 사용 합니다. 예:
    
  ```PowerShell
  Lock-CsClientPin -Identity "Ken Myer"
  ```

### <a name="to-unlock-a-user-pin"></a>사용자 PIN의 잠금을 해제하려면

- 사용자 PIN의 잠금을 해제하기 위해 Unlock-CsClientPin cmdlet을 사용 합니다. 예제:
    
  ```PowerShell
  Unlock-CsClientPin -Identity "Ken Myer"
  ```

자세한 내용은 [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) 및 [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) cmdlet에 대한 도움말 항목을 참조하십시오.
