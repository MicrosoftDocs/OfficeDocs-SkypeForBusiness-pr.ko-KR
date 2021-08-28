---
title: 모임 참가 페이지 구성
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: End User
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 사용자가 모임 요청에서 모임 링크를 클릭하면 모임 참가 페이지에서 사용자 컴퓨터에 이미 설치된 클라이언트를 검색합니다. 클라이언트가 이미 설치되어 있으면 클라이언트가 열리고 모임에 참가합니다. 클라이언트가 설치되어 있지 않은 경우 기본적으로 Web App이 열립니다.
ms.openlocfilehash: 8cba2a6ea0bc54eae6c30265c21d33d01ec951c0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58617114"
---
# <a name="configure-the-meeting-join-page"></a>모임 참가 페이지 구성

사용자가 모임 요청에서 모임 링크를 클릭하면 모임 참가 페이지에서 사용자 컴퓨터에 이미 설치된 클라이언트를 검색합니다. 클라이언트가 이미 설치되어 있으면 클라이언트가 열리고 모임에 참가합니다. 클라이언트가 설치되어 있지 않은 경우 기본적으로 Web App이 열립니다.
  
사용자가 모임에 참가하도록 허용하려는 경우 모임 참가 페이지의 동작을 수정할 수 있습니다. 이러한 구성 옵션은 제어판에서 제거했지만 CsWebServiceConfiguration cmdlet을 사용하여 구성합니다.
  
**모임 참가 페이지 CsWebServiceConfiguration 매개 변수**

|**CsWebServiceConfiguration 매개 변수**|**설명**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |True로 설정하면 Lync가 다른 클라이언트 응용 프로그램을 사용하여 모임에 참가하는 사용자에게 모임에 참가할 수 있는 기회가 부여됩니다. 기본값은 False입니다.  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |True로 설정하면 온라인 회의에 참가하기 위한 대체 옵션이 자동으로 확장되어 사용자에게 표시됩니다. False(기본값)로 설정하면 이러한 옵션을 사용할 수 있지만 사용자가 직접 옵션 목록을 표시해야 합니다.  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a>2019 관리 셸을 사용하여 모임 참가 비즈니스용 Skype 서버 구성

1. 비즈니스용 Skype 서버 2019 관리 셸 시작: **시작,** 모든 프로그램, Microsoft 비즈니스용 Skype 서버 **2019를** 클릭한 다음 비즈니스용 Skype 서버 **관리 셸을 클릭합니다.** 
    
2. 다음 cmdlet을 실행합니다. 
    
   ```PowerShell
   Get-CsWebServiceConfiguration
   ```

    이 cmdlet는 웹 서비스 구성 설정을 반환합니다.
    
3. 기본 설정에 따라 매개 변수를 True 또는 False로 설정하여 다음 명령을 [실행합니다(이](../../SfbServer/manage/management-shell.md) cmdlet의 매개 변수에 대한 자세한 내용은 비즈니스용 Skype 서버 관리 셸 설명서 참조).
    
   ```PowerShell
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


