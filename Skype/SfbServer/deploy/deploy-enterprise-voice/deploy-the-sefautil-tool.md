---
title: 비즈니스용 Skype에서 SEFAUtil 도구 배포
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: 비즈니스용 Skype 서버에서 SEFAUtil 도구 배포
ms.openlocfilehash: e36448652f245d1c81a00cc206b6e8047a8f9d28
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001888"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a>비즈니스용 Skype에서 SEFAUtil 도구 배포
 
비즈니스용 Skype 서버에서 SEFAUtil 도구 배포
  
그룹 통화 픽업을 배포 하 고 관리 하려면 비즈니스용 Skype 서버 버전의 SEFAUtil 도구를 사용 해야 합니다. 
  
> [!IMPORTANT]
> Microsoft 통합 커뮤니케이션 관리 API (c) SEFAUtil 도구를 실행할 컴퓨터에는 5 개의 런타임을 설치 해야 합니다. [통합 커뮤니케이션 관리 API 5.0 런타임을](https://www.microsoft.com/en-us/download/details.aspx?id=47344)여기에 다운로드 하세요. 또한 런타임, 그리고 여기에 포함 된 참조 ( [5.0 sdk](https://www.microsoft.com/en-us/download/details.aspx?id=47345))를 비롯 하 여 함께 다운로드 하는 sdk를 다운로드할 수 있습니다.
  
배포의 모든 프런트 엔드 풀에서 SEFAUtil 도구를 실행할 수 있습니다. SEFAUtil 도구를 실행 하려면 신뢰할 수 있는 응용 프로그램 컴퓨터의 비즈니스용 Skype 배포 마법사에서 1, 2, 3 단계를 실행 해야 합니다. SEFAUtil에는 로컬 구성 저장소가 있어야 하 고 인증서도 필요 합니다.
  
> [!NOTE]
> SEFAUtil를 실행 하는 방법에 대 한 자세한 내용은 블로그 문서, "[실행 중인 SEFAUtil를 가져오는 방법](https://go.microsoft.com/fwlink/?LinkId=278940)"을 참조 하세요. 
  
### <a name="to-deploy-sefautil"></a>SEFAUtil 배포

1. 비즈니스용 Skype 서버 관리 셸이 설치 되어 있는 컴퓨터에 RTCUniversalServerAdmins 그룹의 구성원 또는 **대리인 설정 권한에**설명 된 대로 필요한 사용자 권한으로 로그온 합니다.
    
2. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.
    
3. SEFAUtil 도구는 신뢰할 수 있는 응용 프로그램 풀의 일부인 컴퓨터 에서만 실행 됩니다. 필요한 경우 SEFAUtil를 실행할 계획의 프런트 엔드 풀에 대해 신뢰할 수 있는 응용 프로그램 풀을 정의 합니다. 명령줄에서 다음을 실행 합니다.
    
   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > 풀 FQDN: SEFAUtil 응용 프로그램을 호스트할 서버 또는 풀의 FQDN입니다 (일반적으로 비즈니스용 Skype 프런트 엔드 서버 또는 풀).
    > 풀 등록자 FQDN:이 응용 프로그램 풀과 연결 된 비즈니스용 Skype 프런트 엔드 서버 또는 풀의 FQDN입니다.
    > 풀 사이트:이 풀이 속한 사이트의 사이트 ID입니다.

4. SEFAUtil 도구를 신뢰할 수 있는 응용 프로그램으로 정의 합니다. 명령줄에서 다음을 실행 합니다.
    
   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > 필요한 경우 다른 포트를 사용할 수 있습니다. 
  
5. 변경 내용이 포함 된 토폴로지를 사용 하도록 설정 합니다. 명령줄에서 다음을 실행 합니다.
    
   ```powershell
   Enable-CsTopology
   ```

6. 아직 없는 경우 비즈니스용 Skype Server 버전을 [이 위치](https://www.microsoft.com/en-us/download/details.aspx?id=52631)에서 다운로드 하 여 3 단계에서 만든 신뢰 된 응용 프로그램 풀에 설치 합니다.
    
7. 다음과 같이 SEFAUtil 도구가 올바르게 실행 되 고 있는지 확인 합니다. 
    
    에서. Windows 명령 프롬프트에서 관리자 권한으로 도구를 실행 하 여 배포에 있는 사용자의 착신 전환 설정을 표시 합니다.
    
    b. 사용자의 착신 전환 설정을 표시 합니다. 명령줄에서 다음을 실행 합니다.
    
   ```console
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

사용자의 착신 전환 설정이 표시 됩니다.
    

