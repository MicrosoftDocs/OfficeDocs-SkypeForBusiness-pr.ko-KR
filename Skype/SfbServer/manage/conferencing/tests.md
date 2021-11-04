---
title: 전화 접속 회의를 테스트합니다비즈니스용 Skype 서버
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
ms.assetid: f4ccbfd4-6075-466f-b459-20561318803d
description: '요약: 회의에서 전화 접속 회의를 테스트하는 비즈니스용 Skype 서버.'
ms.openlocfilehash: 0a2a612b242a83c5e1d98525f040bf96c4e69ca8
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60773628"
---
# <a name="test-dial-in-conferencing-in-skype-for-business-server"></a>전화 접속 회의를 테스트합니다비즈니스용 Skype 서버
 
**요약:** 전화 접속 회의를 테스트하는 방법을 비즈니스용 Skype 서버.
  
전화 접속 회의 구성의 최종 확인 작업으로 액세스 번호에서 사용되지 않은 전화 접속 회의 지역이 포함된 다이얼 플랜 및 전화 접속 회의 지역이 할당되지 않은 액세스 번호를 검색할 수 있습니다. 또한 전화 접속 회의가 웹 설정 전화 접속 액세스 번호가 제대로 작동하고 있는지 확인해야 합니다.
  
## <a name="find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a>액세스 번호에서 사용되지 않는 전화 접속 회의 지역이 있는 다이얼 플랜 찾기

1. RTCUniversalServerAdmins 그룹의 구성원이나 Cs-ServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온합니다.
    
2. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**
    
3. 명령 프롬프트에서 다음을 실행합니다.
    
   ```PowerShell
   Get-CsDialinConferencingAccessNumber -EmptyRegion
   ```

    이 cmdlet은 액세스 번호에서 사용되지 않은 전화 접속 회의 지역이 포함된 모든 다이얼 플랜을 반환합니다.
    
자세한 내용은 [Get-CsDialInConferencingAccessNumber를 참조하십시오.](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)
  
## <a name="find-access-numbers-without-assigned-regions"></a>할당된 지역이 없는 액세스 번호 찾기

1. RTCUniversalServerAdmins 그룹의 구성원이나 Cs-ServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온합니다.
    
2. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**
    
3. 명령 프롬프트에서 다음을 실행합니다.
    
   ```PowerShell
   Get-CsDialinConferencingAccessNumber -Region NULL
   ```

    이 cmdlet은 지역과 연관되지 않은 모든 전화 접속 회의 액세스 번호를 반환합니다.
    
자세한 내용은 [Get-CsDialInConferencingAccessNumber를 참조하십시오.](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)
  
## <a name="test-webpage-and-access-numbers"></a>웹 페이지 테스트 및 액세스 번호

전화 접속 회의 설정 웹 페이지와 전화 접속 액세스 번호가 올바르게 작동하는지 확인하려면 다음을 수행해야 합니다.
  
- 단순 URL에 로그인하여 전화 접속 회의 설정 웹 페이지를 테스트합니다.
    
- 이 항목 뒷부분에 나와 있는 스크립트를 실행하여 특정 풀에 대해 액세스 번호가 올바르게 작동하는지 테스트합니다. 이 스크립트는 액세스 번호에 대한 호출을 시뮬레이트합니다. 이 스크립트를 사용하려면 특정 풀에서 호스팅되는 단일 UC(통합 통신) 클라이언트의 SIP 주소 및 자격 증명이 필요합니다.
    
### <a name="to-test-access-numbers-for-a-specific-pool"></a>특정 풀에 대한 액세스 번호를 테스트하려면

1. RTCUniversalServerAdmins 그룹의 구성원이나 Cs-ServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온합니다.
    
2. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**
    
3. 명령 프롬프트에서 다음을 실행합니다.
    
   ```PowerShell
   $credentials = Get-Credential
   User name:  testuser1@contoso.com
   Password:  ********
   Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
   ```

    결과 보고서에는 성공 또는 실패와 특정 진단 정보가 표시됩니다. -Verbose 플래그는 발견된 액세스 번호 수와 해당 번호에 대한 세부 정보에 대한 자세한 정보를 제공합니다.
    
자세한 내용은 [Test-CsDialInConferencing을 참조하십시오.](/powershell/module/skype/test-csdialinconferencing?view=skype-ps)
