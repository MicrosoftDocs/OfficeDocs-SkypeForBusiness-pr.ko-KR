---
title: 2016에서 SEFAUtil 도구 비즈니스용 Skype
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: 2016에서 SEFAUtil 도구를 비즈니스용 Skype 서버.
ms.openlocfilehash: d4d25a69476aa678f600178b9426db89670289d2
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60837330"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a>2016에서 SEFAUtil 도구 비즈니스용 Skype
 
2016에서 SEFAUtil 도구를 비즈니스용 Skype 서버.
  
그룹 통화 Pickup을 배포하고 관리하려면 SEFAUtil 도구의 비즈니스용 Skype 서버 버전을 사용해야 합니다. 
  
> [!IMPORTANT]
> SEFAUtil 도구를 실행하려면 모든 컴퓨터에 Microsoft UCMA(Unified Communications Managed API) 5 런타임이 설치되어 있어야 합니다. 여기에서 다운로드하세요. [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/download/details.aspx?id=47344). 런타임이 포함된 UCMA 5 SDK는 [UCMA 5.0 SDK](https://www.microsoft.com/download/details.aspx?id=47345)에서 다운로드할 수도 있습니다.
  
배포의 모든 프런트 엔드 풀에서 SEFAUtil 도구를 실행할 수 있습니다. SEFAUtil 도구를 실행하려면 신뢰할 수 있는 응용 프로그램 컴퓨터의 비즈니스용 Skype 배포 마법사에서 1, 2 및 3단계를 실행해야 합니다. SEFAUtil을 사용하려면 인증서뿐만 아니라 로컬 구성 저장소도 필요합니다.
  
> [!NOTE]
> SEFAUtil을 실행하는 방법에 대한 자세한 내용은 블로그 문서["SEFAutil을](/archive/blogs/jenstr/how-to-get-sefautil-running)실행하는 방법" "을 참조하세요. 
  
### <a name="to-deploy-sefautil"></a>SEFAUtil을 배포하기 위해

1. 비즈니스용 Skype 서버 관리 셸이 RTCUniversalServerAdmins 그룹의 구성원으로 설치되거나 설치 권한 위임에 설명된 필요한 사용자 권한으로 컴퓨터에 **로그온합니다.**
    
2. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**
    
3. SEFAUtil 도구는 신뢰할 수 있는 응용 프로그램 풀의 일부인 컴퓨터에서만 실행할 수 있습니다. 필요한 경우 SEFAUtil을 실행할 프런트 엔드 풀에 대해 신뢰할 수 있는 응용 프로그램 풀을 정의합니다. 명령줄에서 다음을 실행합니다.
    
   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > 풀 FQDN: SEFAUtil 응용 프로그램(일반적으로 프런트 엔드 서버 또는 풀)을 호스팅할 서버 또는 비즈니스용 Skype FQDN입니다.
    > 풀 등록자 FQDN: 이 응용 비즈니스용 Skype 프런트 엔드 서버 또는 풀의 FQDN입니다.
    > 풀 사이트: 이 풀이 있는 사이트의 사이트 ID입니다.

4. SEFAUtil 도구를 신뢰할 수 있는 응용 프로그램으로 정의합니다. 명령줄에서 다음을 실행합니다.
    
   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > 필요한 경우 다른 포트를 사용할 수 있습니다. 
  
5. 변경 내용과 함께 토폴로지 사용. 명령줄에서 다음을 실행합니다.
    
   ```powershell
   Enable-CsTopology
   ```

6. 아직 설치하지 않은 경우 이 위치에서 비즈니스용 Skype 서버 버전의 SEFAUtil 도구를 [](https://www.microsoft.com/download/details.aspx?id=52631)다운로드하고 3단계에서 만든 신뢰할 수 있는 응용 프로그램 풀에 설치합니다.
    
7. 다음과 같이 SEFAUtil 도구가 제대로 실행되고 있는지 확인합니다. 
    
    a. 관리자 권한으로 Windows 명령 프롬프트에서 도구를 실행하여 배포에 있는 사용자의 통화 전달 설정을 표시합니다.
    
    b. 사용자의 통화 전달 설정을 표시합니다. 명령줄에서 다음을 실행합니다.
    
   ```console
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

사용자에 대한 전달 설정이 표시됩니다.
