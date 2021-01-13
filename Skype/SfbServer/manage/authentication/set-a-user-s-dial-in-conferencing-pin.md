---
title: 비즈니스용 Skype 서버에서 사용자의 전화 접속 회의 PIN 설정
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
ms.assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
description: '요약: 비즈니스용 Skype 서버에 대한 사용자의 전화 접속 회의 PIN을 설정할 수 있습니다.'
ms.openlocfilehash: cd7375519fa9fc161c6414dcf1b9d0fbf6de6ef0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828303"
---
# <a name="set-a-users-dial-in-conferencing-pin-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 사용자의 전화 접속 회의 PIN 설정
 
**요약:** 비즈니스용 Skype 서버에 대한 사용자의 전화 접속 회의 PIN을 설정할 수 있습니다.
  
인증된 사용자로 전화 접속 회의에 참가하려면 AD DS(Active Directory 도메인 서비스) 자격 증명이 있는 비즈니스용 Skype 서버 사용자에게는 개인식별번호(PIN)가 필요합니다. 사용자가 전화 접속 회의 PIN을 잊어버리거나 비즈니스용 Skype 서버를 사용하여 PIN을 설정하지 않은 경우 비즈니스용 Skype 서버 제어판에서 사용자의 PIN을 설정할 수 있습니다. PIN은 자동으로 생성할 수도 있고 수동으로 만들 수도 있습니다.
  
> [!NOTE]
> 최소 길이와 같은 PIN의 특정 특성을 정책으로 구성할 수 있습니다. 글로벌 정책뿐 아니라, 개별 사이트 또는 사용자에 대한 PIN 정책도 구성할 수 있습니다. 
  
### <a name="to-set-a-users-pin"></a>사용자의 PIN을 설정

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
    
    > [!NOTE]
    > PIN이 잠겨 있는 경우에는 PIN 잠금을 해제해야 설정할 수 있습니다. PIN 잠금을 해제하려면 사용자를 클릭하고 **동작** 을 클릭한 후에 **PIN 잠금 해제** 를 클릭합니다. 
  
6. 검색 결과에서 사용자를 클릭하고 **동작** 을 클릭한 후에 **PIN 설정** 을 클릭합니다.
    
7. **PIN 설정** 대화 상자에서 다음 중 하나를 수행합니다.
    
   - 비즈니스용 Skype 서버에서 사용자의 PIN을 생성하도록 허용하려면 유효한 **PIN(기본값)을 자동으로** 생성하도록 선택합니다.
    
   - PIN을 직접 만들려면 **특정 PIN을 수동으로 입력** 을 클릭하고 텍스트 상자를 클릭한 후에 PIN 정책 설정에 지정된 PIN 요구 사항을 충족하는 PIN을 입력합니다.
    
8. **확인** 을 클릭합니다.
    
9. **PIN 설정** 에서 다음 중 하나를 수행합니다. 
    
   - **PIN 표시** 확인란을 선택하여 PIN을 표시한 다음 PIN을 복사하여 조직에서 사용하는 기본 방법을 통해 사용자에게 전달합니다.
    
   - PIN을 전자 메일로 보내려면 **내 전자 메일 응용 프로그램을 열어 새 PIN을 사용자에게 보내기** 를 클릭합니다. Microsoft Office Outlook이 전자 메일 클라이언트인 경우 PIN이 새 전자 메일 메시지에 자동으로 복사됩니다. 다른 전자 메일 클라이언트를 사용하는 경우에는 **PIN 표시** 확인란을 선택하여 PIN을 표시한 다음 전자 메일 메시지에 PIN을 복사합니다.
    
10. **닫기** 를 클릭합니다.
    
## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a>cmdlet을 사용하여 사용자 PIN Windows PowerShell 지정

PIN 번호를 할당할 수도 있는 cmdlet을 사용하여 Set-CsClientPin 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸 또는 비즈니스용 Skype 서버 관리 셸의 원격 세션에서 Windows PowerShell. 원격 서버를 사용하여 비즈니스용 Skype Windows PowerShell 연결하는 데 대한 자세한 내용은 [블로그 문서 "빠른 시작: 원격 PowerShell을 사용하여 Microsoft Lync Server 2010 관리"를](https://go.microsoft.com/fwlink/p/?linkId=255876)참조하세요. 이 프로세스는 비즈니스용 Skype 서버에서 동일합니다. 
  
### <a name="to-auto-assign-a-pin-number-to-a-user"></a>사용자에게 PIN 번호를 자동 할당하는 경우

다음 명령은 Myer라는 사용자에게 PIN 번호를 지정합니다. Pin 매개 변수가 포함되지 않은 경우 비즈니스용 Skype 서버는 PIN 번호를 자동으로 생성하고 할당합니다.
    
  ```PowerShell
  Set-CsClientPin -Identity "Ken Myer" 
  ```

### <a name="to-assign-a-specific-pin-number-to-a-user"></a>사용자에게 특정 PIN 번호를 할당하기 위해

이 명령은 Pin 매개 변수를 사용해서 Ken Myer라는 사용자에게 PIN 번호 121989를 지정합니다.
    
  ```PowerShell
  Set-CsClientPin -Identity "Ken Myer" -Pin 121989
  ```

자세한 내용은 [Set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/set-csclientpin?view=skype-ps) cmdlet에 대한 도움말 항목을 참조하십시오.
  

