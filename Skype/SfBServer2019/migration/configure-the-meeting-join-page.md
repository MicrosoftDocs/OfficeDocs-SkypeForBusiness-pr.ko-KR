---
title: 모임 참가 페이지 구성
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: End User
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 사용자가 모임 요청에서 모임 링크를 클릭 하면 모임 참가 페이지에서 사용자 컴퓨터에 이미 설치 되어 있는 클라이언트를 감지 합니다. 클라이언트가 이미 설치 되어 있는 경우 해당 클라이언트에서 모임에 참가 하 고 참석 합니다. 클라이언트가 설치 되어 있지 않으면 기본적으로 웹 앱이 열립니다.
ms.openlocfilehash: 5c9e6653783d90411e0f701b5d3395c569d8bdff
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40989563"
---
# <a name="configure-the-meeting-join-page"></a>모임 참가 페이지 구성

사용자가 모임 요청에서 모임 링크를 클릭 하면 모임 참가 페이지에서 사용자 컴퓨터에 이미 설치 되어 있는 클라이언트를 감지 합니다. 클라이언트가 이미 설치 되어 있는 경우 해당 클라이언트에서 모임에 참가 하 고 참석 합니다. 클라이언트가 설치 되어 있지 않으면 기본적으로 웹 앱이 열립니다.
  
사용자가 모임에 참가할 수 있도록 하려면 모임 참가 페이지의 동작을 수정할 수 있습니다. 이러한 구성 옵션은 제어판에서 제거 되었지만 CsWebServiceConfiguration cmdlet을 사용 하 여 구성 합니다.
  
**모임 참가 페이지 CsWebServiceConfiguration 매개 변수**

|**CsWebServiceConfiguration 매개 변수**|**설명**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |True로 설정 하면 Lync 이외의 클라이언트 응용 프로그램을 사용 하 여 모임에 참가 하는 사용자에 게 모임에 참가할 수 있는 기회가 제공 됩니다. 기본값은 False입니다.  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |이를 True로 설정 하면 온라인 회의에 참가 하는 대체 옵션이 자동으로 확장 되어 사용자에 게 표시 됩니다. False (기본값)로 설정 하는 경우 이러한 옵션을 사용할 수 있지만, 사용자는 자신의 옵션 목록을 표시 해야 합니다.  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a>비즈니스용 Skype Server 2019 관리 셸을 사용 하 여 모임 참가 페이지를 구성 하려면

1. 비즈니스용 Skype 서버 2019 관리 셸을 **시작 하 고,** **모든 프로그램**을 클릭 하 고, **Microsoft 비즈니스용 skype server 2019**을 클릭 한 다음 비즈니스용 **skype server Management Shell**을 클릭 합니다.
    
2. 다음 cmdlet을 실행 합니다. 
    
   ```PowerShell
   Get-CsWebServiceConfiguration
   ```

    이 cmdlet은 웹 서비스 구성 설정을 반환 합니다.
    
3. 기본 설정에 따라 매개 변수를 True 또는 False로 설정 하 고 다음 명령을 실행 합니다 (이 cmdlet의 매개 변수에 대 한 자세한 내용은 [비즈니스용 Skype 서버 관리 셸](../../SfbServer/manage/management-shell.md) 설명서 참조).
    
   ```PowerShell
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


