---
title: 비즈니스용 Skype 서버에서 사용자 PIN 정보 보기
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
ms.assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
description: '요약: 비즈니스용 Skype 서버에서 사용자 PIN 정보를 볼 수 있습니다.'
ms.openlocfilehash: c016e6edf258f63166b930be833542bf9e730f15
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099224"
---
# <a name="view-user-pin-information-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 사용자 PIN 정보 보기
 
**요약:** 비즈니스용 Skype 서버에서 사용자 PIN 정보를 볼 수 있습니다.
  
인증된 사용자로 전화 접속 회의에 참가하려면 AD DS(Active Directory 도메인 서비스) 자격 증명이 있는 비즈니스용 Skype 서버 사용자에게는 개인식별번호(PIN)가 필요합니다. 비즈니스용 Skype 서버 제어판에서 사용자의 PIN 정보를 볼 수 있습니다.
  
> [!NOTE]
> PIN이 설정되었는지 여부 또는 PIN이 마지막으로 변경된 시간 등의 PIN 상태 정보를 볼 수 있지만 PIN 상태로 조회해서 현재 PIN을 볼 수는 없습니다. 사용자가 PIN을 분실한 경우 비즈니스용 Skype 서버에서 사용자의 전화 접속 회의 PIN 설정의 절차에 따라 PIN을 다시 설정할 [수 있습니다.](set-a-user-s-dial-in-conferencing-pin.md)
  
### <a name="to-view-a-users-pin-in-skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판에서 사용자의 PIN을 표시

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
  
6. 검색 결과에서 사용자를 클릭하고 **동작** 을 클릭한 후에 **PIN 상태 보기** 를 클릭합니다.
    
## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a>cmdlet을 사용하여 사용자 PIN Windows PowerShell 보기

Get-CsClientPinInfo cmdlet을 사용하여 사용자 PIN 정보를 볼 수 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸 또는 비즈니스용 Skype 서버 관리 셸에서 실행할 수 Windows PowerShell. 원격 Windows PowerShell 사용하여 비즈니스용 Skype 서버에 연결하는 데 대한 자세한 내용은 [블로그 문서 "빠른 시작: 원격 PowerShell을 사용하여 Microsoft Lync Server 2010 관리"를 참조하세요.](https://go.microsoft.com/fwlink/p/?linkId=255876) 이 프로세스는 비즈니스용 Skype 서버에서 동일합니다.
  
### <a name="to-view-user-pin-information"></a>사용자 PIN 정보를 보려면

사용자에 대한 PIN 정보를 보기 위해 비즈니스용 Skype 서버 관리 셸에 다음과 비슷한 명령을 입력한 다음 Enter를 눌러야 합니다.
    
  ```PowerShell
  Get-CsClientPinInfo -Identity "Ken Myer"
  ```

그러면 다음과 같은 정보가 반환됩니다.

<pre>
Identity          : sip:kenmyer@litwareinc.com
IsPinSet          : False
IsLockedOut       : False
LastPinChangeTime : 9/25/2012 1:35:03 PM
PinExpirationTime :
</pre>

자세한 내용은 [Get-CsConferenceDisclaimer](/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) cmdlet에 대한 도움말 항목을 참조하십시오.
  
## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버에서 사용자의 전화 접속 회의 PIN 설정](set-a-user-s-dial-in-conferencing-pin.md)
  
[비즈니스용 Skype 서버에서 사용자 PIN 잠금 또는 잠금 해제](lock-or-unlock-a-user-pin.md)