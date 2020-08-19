---
title: 네트워크 내부 및 외부적으로 레거시 인증 방법 해제 계획
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: ''
description: 이 문서에서는 관리자가 비즈니스 내부 및 외부에서 사용 되는 인증 방법에 대 한 더 많은 제어 권한을 제공 하는 cmdlet을 소개 합니다. 관리자는 내부에서 또는 네트워크 외부에서 인증 방법을 설정/해제할 수 있습니다.
ms.openlocfilehash: e2f9a8c9c8576c07de3158fb2446cb3cb89bac72
ms.sourcegitcommit: aae3eeb4dedd825ab176abe7e1aff9463c88799b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2020
ms.locfileid: "46797456"
---
# <a name="planning-to-turn-off-legacy-authentication-methods-internally-and-externally-to-your-network"></a>네트워크에서 내부적으로 또는 외부적으로 레거시 인증 방법을 해제할 계획입니다.

> [!NOTE]
> 이 문서를 읽으면 지원 되는 최신 인증 토폴로지, ADAL 및 최신 인증 구성에 대해 알고 있어야 하지만, 그렇지 않은 경우에는 다음과 같은 문서를 시작 해야 합니다. 
>  + [https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)
>  + [https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal](https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal)
  
최신 인증은 두 가지 보안 인증 방법 (예를 들어, 인증서 기반 인증)을 사용 하는 것이 아니라 사용자 이름 또는 암호를 입력 하지 않아도 자신의 인증을 수행할 수 있습니다. 매우 편리 합니다.

이 문서는 비즈니스용 Skype 서버의 DOS (서비스 거부) 공격에 사용 된 이전 방법, 외부, 내부 또는 두 가지 모두를 네트워크에 연결 하는 기능을 해제 하는 방식으로 악용 되는 정보를 플러그 인으로 전달 하는 데 도움이 됩니다. 예를 들어 DOS 공격을 중지 하는 데 도움이 되는 좋은 방법은 Windows 통합 인증 (NTLM 및 Kerberos 포함)을 해제 하는 것입니다. NTLM을 해제 하 고 인증서 기반 인증을 사용 하면 암호 노출을 보호할 수 있습니다. NTLM은 암호 자격 증명을 사용 하 여 사용자를 인증 하지만 인증서 기반 인증은 최신 인증을 통해 사용 하도록 설정 되기 때문입니다. 즉, DOS 공격을 줄이기 위한 이상적인 옵션 중 하나는 NTLM을 외부적으로 차단 하 고 대신 인증서 기반 인증만 사용 하는 것입니다.

바로 시작 해 보겠습니다.

## <a name="what-would-you-be-changing"></a>무엇이 변경 됩니까? 

이러한 cmdlet은 SIP 및 웹 서비스 액세스 지점에서 모두 작동 합니다. 이러한 두 채널은 서로 다른 액세스 방법을 사용 하지만 NTLM 및 Kerberos에서 익명 액세스로 영역을 실행 하는 경우 비즈니스용 Skype에서 사용 되는 모든 표준 방법을 고려해 야 합니다.

## <a name="how-to-get-the-get--and-set-csauthconfig-cmdlets"></a>Get 및 Set-CsAuthConfig cmdlet을 가져오는 방법

이러한 cmdlet은 Microsoft 비즈니스용 Skype 서버 2015에 대 한 7 월 2018 누적 업데이트 (6.0.9319.534)로만 설치 되며 비즈니스용 Skype 서버에 대해 롤아웃할 수 있는 다양 한 토폴로지가 있습니다.

## <a name="topologies"></a>기술

이 시나리오와 관련 하 여 지원 되는 토폴로지를 고려해 야 합니다. 예를 들어 메서드를 차단 하는 방법에 대 한 지원으로 이동 해야 하는 경우 아래 형식 중 하나를 구성 해야 합니다. 

> [!IMPORTANT]
> 아래의 표 및 설명에서 *최신 인증은* __MA__ 로, *Windows 통합 인증은* __Win__으로 축약 됩니다. 미리 알림으로 Windows 통합 인증은 NTLM 및 Kerberos 인증의 두 가지 방법으로 구성 됩니다. 테이블을 제대로 읽으려면이를 확인 해야 합니다.


|       |있거나  |내부적인  |매개 변수  |
|---------|:---------|:---------|---------|
|__유형 1__   |  MA + Win       | MA + Win         |  AllowAllExternallyAndInternally       |
|__유형 2__   |  MA       | MA + Win         | BlockWindowsAuthExternally        |
|__유형 3__   |  MA       | MA        | BlockWindowsAuthExternallyAndInternally        |
|__유형 4__   |  MA       | Nm-win        | BlockWindowsAuthExternallyAndModernAuthInternally    |
|__유형 5__   |  MA + Win       | Nm-win        | BlockModernAuthInternally         |

__유형 1 설명:__ 비즈니스용 Skype 서버 __에 대해 MA가 설정 된__ 경우 이것이 기본 시나리오입니다. 즉 MA가 구성 되 면이 *출발점* 을 기준으로 합니다.

__형식 2 설명:__ 이 토폴로지는 *외부*에서 ntlm을 차단 하지만, ADAL을 지원 하지 않는 클라이언트의 경우에는 Ntlm 또는 Kerberos를 사용 하 여 *내부적*으로 작업할 수 있습니다. 클라이언트에서 ADAL을 지 원하는 경우에는 MA를 내부적으로 사용 합니다.

__3 설명 형식:__ 이 토폴로지에서는 모든 사용자에 대해 MA가 필요 합니다. 모든 ADAL 지원 클라이언트는이 토폴로지에서 작동 하며, 예를 들어 인증서 기반 인증을 통해 암호를 사용 하지 않도록 설정 하는 등의 경우 암호가 활용 되지 않습니다.

__4 설명 유형:__ 이 토폴로지는 내부적 *으로 NTLM을* 차단 합니다. 이를 통해 *모든 클라이언트가* 레거시 인증 방법 (ADAL 가능 클라이언트 라도)을 *내부적* 으로 사용할 수 있습니다.

__5 입력 설명:__ *외부*에서 최신 ADAL 클라이언트는 MA를 사용 하며, adal을 지원 하지 않는 클라이언트는 레거시 인증 방법을 사용 합니다. 그러나 *내부적* 으로는 *모든 클라이언트* 에서 레거시 인증 (모든 ADAL 지원 클라이언트 포함)을 사용 합니다.

사용 가능한 옵션에서 암호를 보호 하는 목표를 쉽게 추적할 수 있는 것은 매우 쉽습니다. 이 경우에는 DOS 공격을 방지 하기 위해 MA 외부적 (예: 인증서 기반 인증 구성)을 사용 하는 것이 이상적입니다. 최신 클라이언트에 대해 내부적으로이 기능을 사용 하는 경우 비즈니스용 Skype 서버 DOS 공격과 관련 하 여 네트워크를 교정 해야 할 수도 있습니다.

## <a name="why-to-use-set-csauthconfig-at-the-global-level"></a>전역 수준에서 CsAuthConfig를 사용 하는 이유

`Set-CsAuthConfig`등록자 및 웹 서비스 역할 둘 다에 대 한 cmdlet 효과 구성

이 cmdlet은 비즈니스용 Skype 서버의 전역 수준에서 실행 되는 것을 의미 합니다. 풀 수준에서 실행할 *수* 는 있지만 설치가 복잡해 짐에 따라 *권장 되지* 않습니다. 풀 수준에서 이러한 명령을 실행 하 여 풀에 포함 된 역할이 모두 없는 경우 (예: 웹 서비스가 없는 경우) 설정은 등록자 역할에 대해서만 설정 됩니다. 이 경우 웹 서비스는 전역 수준의 설정을 사용 하 여 수행 되며, 이러한 동작은 혼란을 야기할 수 있습니다 (특히이 작업을 수행 하는 경우).

클라이언트가 한 풀의 등록자 설정을 사용 하 고 다른 풀의 웹 서비스 설정과 일치 하지 않는 상태 이면 yous 클라이언트에서 로그온 하지 못할 수 있습니다.

또한 풀에 대해 역할이 하나만 있는 경우: 
* 설정 됨-존재 하는 역할에 해당 하는 설정만 설정 합니다. 일부 설정은 설정 *되지* 않았으므로 특별 한 경고는 제공 되지 않습니다. 
* Get-존재 하는 역할에 해당 하는 설정과 존재 하지 않는 역할에 대 한 전역 설정을 반환 합니다.
* 풀에 대 한 역할이 없는 경우 설정 및 Get은 모두 오류 메시지를 반환 합니다.
* 풀에 대해 두 역할이 모두 있고 정책이 풀 수준에서 정의 되지 않은 경우 Get은 오류 메시지를 반환 합니다.

이러한 값에 대해 Get-wisest를 수행 하 고, 변경 작업을 수행 하기 전에 스크린샷 또는 시작 상태를 기록 하는 것이 좋습니다. 또한 OneNote에서 변경 내용 로그를 유지 하는 것이 좋습니다.

> [!NOTE]
> 
> 참고: CsAuthConfig를 구성한 후에는 각 컴퓨터에서 사용 하도록 설정 된 컴퓨터에서 CsComputer를 실행 해야 설정이 적용 됩니다.

> [!IMPORTANT]
> LWA (Lync Web Access)를 사용 하는 경우 외부 액세스를 위해 FBA (양식 기반 액세스)를 사용 해야 하는 경우 클라이언트에서 이러한 시나리오를 지원 하기 위해 익명 액세스를 통해 액세스할 수 있도록 LWA를 다시 구성 합니다. 마찬가지로 전화 접속 Pin을 사용 하는 경우에는 외부 사용자에 대해서만 FBA가 차단 됩니다. Pin을 변경 해야 하는 경우에는 회사에 로그인 하 여 내부적으로이 작업을 수행 해야 합니다.

> [!NOTE]
> 
> BlockWindowsAuthExternally 매개 변수를 사용 하 여 외부에서 NTLM을 차단 하는 경우에는 SIP 채널에 대해서도 내부적으로 NTLM을 차단 합니다. 그러나 비즈니스용 Skype 및 Lync 클라이언트가 2010 보다 최신인 경우 로그인에 대해 내부적으로 NTLM HTTP를 사용 하 고 SIP를 통해 로그인 할 인증서를 페치 (fetch) 할 수 있습니다. 그러나 2010 보다 오래 된 클라이언트는 이러한 상황에서 내부적으로 로그인 할 수 없으며, 사용자가 보안 기능을 다시 시작할 수 있도록 이러한 응용 프로그램의 업그레이드를 고려해 야 할 수 있습니다.

> [!IMPORTANT] 
> 비즈니스용 Skype 웹 응용 프로그램 중 일부는 MA를 지원 하지 않습니다. 따라서 BlockWindowsAuthExternallyAndInternally 시나리오를 사용 하 여 이러한 응용 프로그램에 액세스할 수 없게 됩니다. MA가 지원 되지 않는 응용 프로그램은 웹 스케줄러, 전화 접속 페이지, CSCP (비즈니스용 Skype 제어판) 및 응답 그룹 설정 페이지입니다. 

## <a name="links"></a>Links 
- PowerShell에 대 한 자세한 정보:
    -  [Get-CsAuthConfig](https://docs.microsoft.com/powershell/module/skype/get-csauthconfig?view=skype-ps)
    -  [Set-CsAuthConfig](https://docs.microsoft.com/powershell/module/skype/set-csauthconfig?view=skype-ps)

- 명령 또는 명령을 설치 하는 데 필요한 CU를 사용 하는 방법에 대 한 자세한 지침을 설명 합니다.
    - [Cmdlet 브리핑](https://support.microsoft.com/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication)
    - [비즈니스용 Skype 서버 2015에 대 한 업데이트](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015) (일반)
    - [7 월 2018 비즈니스용 Skype 서버 2015, 핵심 구성 요소 CU](https://support.microsoft.com/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server) (6.0.9319.534)


 
