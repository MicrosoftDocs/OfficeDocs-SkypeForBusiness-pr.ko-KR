---
title: 네트워크 내부 및 외부에서 레거시 인증 방법 끄기 계획
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 이 문서에서는 관리자에게 비즈니스 내부 및 외부에서 사용되는 인증 방법을 보다 제어할 수 있는 cmdlet에 대해 간략하게 설명하고 있습니다. 관리자는 인증 방법을 내부적으로 또는 네트워크 외부에서 설정하거나 해제할 수 있습니다.
ms.openlocfilehash: dca7dca332564442110c626a222f7ed5d138efaf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810032"
---
# <a name="planning-to-turn-off-legacy-authentication-methods-internally-and-externally-to-your-network"></a>네트워크 내부 및 외부에서 레거시 인증 방법을 해제할 계획입니다.

> [!NOTE]
> 이 문서를 읽으면 지원되는 최신 인증 토폴로지, ADAL 및 최신 인증 구성에 대해 이미 알고 있지만 그렇지 않은 경우 시작해야 하는 문서는 다음과 같습니다. 
>  + [https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)
>  + [https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal](https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal)
  
최신 인증은 Two-Factor 인증 또는 인증서 기반 인증과 같은 보다 안전한 인증 방법을 사용하도록 설정하는 것이 아니라 사용자 이름이나 암호 없이도 사용자의 인증을 수행하도록 할 수 있습니다. 매우 간단합니다.

이 문서는 비즈니스용 Skype 서버에 대한 DOS(서비스 거부) 공격에 악용된 구멍을 네트워크에 연결하여 인증에 사용되는 이전 방법을 외부, 내부 또는 둘 다에 해제하는 데 도움이 됩니다. 예를 들어 DOS 공격을 중지하는 좋은 방법은 Windows 통합 인증(NTLM 및 Kerberos 포함)을 해제하는 것입니다. 외부에서 NTLM을 끄고 인증서 기반 인증을 사용하는 경우 암호를 노출로부터 보호하는 데 도움이 됩니다. 이는 NTLM이 암호 자격 증명을 사용하여 사용자를 인증하지만 최신 인증에서 사용하도록 설정된 인증서 기반 인증은 그렇지 않습니다. 즉, DOS 공격을 줄이는 이상적인 한 가지 옵션은 외부에서 NTLM을 차단하고 대신 인증서 기반 인증만 사용하는 것입니다.

시작해보시겠어요?

## <a name="what-would-you-be-changing"></a>어떤 변화가 있을까요? 

이러한 cmdlet은 SIP 및 웹 서비스 액세스 지점에 모두 사용할 수 있습니다. 이러한 두 채널은 서로 다른 액세스 방법을 사용하며, NTLM 및 Kerberos에서 익명 액세스로의 기능을 실행하기는 하지만 비즈니스용 Skype에서 사용하는 모든 표준 방법이 고려되었습니다.

## <a name="how-to-get-the-get--and-set-csauthconfig-cmdlets"></a>Get-and Set-CsAuthConfig cmdlet을 Set-CsAuthConfig 방법

이러한 cmdlet은 Microsoft 비즈니스용 Skype 서버 2015용 2018년 7월 누적 업데이트(6.0.9319.534) 이후만 설치될 예정이면 비즈니스용 Skype 서버에 대해 배포할 수 있는 다양한 토폴로지가 있습니다.

## <a name="topologies"></a>토폴로지

이러한 토폴로지가 이 시나리오에 관련된 지원되는 토폴로지입니다. 예를 들어 메서드 차단에 대한 도움말을 지원으로 이동해야 하는 경우 아래 형식 중 구성이 필요합니다. 

> [!IMPORTANT]
> 아래 표와 설명에서  최신 인증은 __MA로__ 약어되고 *Windows* 통합 인증은 Win으로 약어로 __사용되어 있습니다.__ 미리 알림을 제공한 Windows 통합 인증은 NTLM 및 Kerberos 인증의 두 가지 방법으로 만들 수 있습니다. 테이블을 제대로 읽으면 이 내용을 알아야 합니다.


|       |외부  |내부적으로  |매개 변수  |
|---------|:---------|:---------|---------|
|__유형 1__   |  MA + Win       | MA + Win         |  AllowAllExternallyAndInternally       |
|__유형 2__   |  MA       | MA + Win         | BlockWindowsAuthExternally        |
|__유형 3__   |  MA       | MA        | BlockWindowsAuthExternallyAndInternally        |
|__유형 4__   |  MA       | Win        | BlockWindowsAuthExternallyAndModernAuthInternally    |
|__유형 5__   |  MA + Win       | Win        | BlockModernAuthInternally         |

__유형 1 설명:__ 비즈니스용 Skype 서버에 대해 MA가 켜져 __있는__ 기본 시나리오입니다. 즉, MA를 구성할 때 시작점입니다. 

__유형 2 설명:__ 이 토폴로지에서는 NTLM을 외부적으로 차단하지만 ADAL을 지원하지 않는 클라이언트의 경우 NTLM 또는 Kerberos가 내부적으로 *작동할 수 있습니다.* 클라이언트가 ADAL을 지원하는 경우 내부적으로 MA를 사용하게 됩니다.

__유형 3 설명:__ 이 토폴로지에는 모든 사용자에 대해 MA가 필요합니다. 예를 들어 인증서 기반 인증에서 암호 사용을 해제하는 경우 모든 ADAL 지원 클라이언트가 이 토폴로지에서 작동하며 암호가 활용되지 않습니다.

__유형 4 설명:__ 이 토폴로지는 NTLM을 외부 *및* MA 내부적으로 차단합니다. 이를 통해 *모든* 클라이언트가 내부적으로(ADAL 지원 클라이언트도) 레거시 인증 방법을 사용할 수 있습니다. 

__유형 5 설명:__ *외부에서* 최신 ADAL 클라이언트는 MA를 사용하며 ADAL을 지원하지 않는 클라이언트는 레거시 인증 방법을 사용하게 됩니다. 그러나 *내부적으로 모든*  클라이언트는 레거시 인증(모든 ADAL 지원 클라이언트 포함)을 사용하게 됩니다.

사용 가능한 옵션에서 암호를 보호하는 목표를 쉽게 추적할 수 있습니다. DOS 공격을 방지하기 위해 MA를 외부에서 사용하는 경우(예: 인증서 기반 인증 구성)에 유의하십시오. 최신 클라이언트를 위해 내부적으로 활용하는 경우 비즈니스용 Skype 서버 DOS 공격과 관련하여 향후 네트워크를 증명할 수 있습니다.

## <a name="why-to-use-set-csauthconfig-at-the-global-level"></a>전역 수준에서 Set-CsAuthConfig 사용하는 이유

이 cmdlet은 등록자 및 웹 서비스 역할 둘 다에 대한 `Set-CsAuthConfig` 구성에 영향을 미치게 됩니다.

이 cmdlet은 비즈니스용 Skype 서버의 전역 수준에서 실행됩니다. 풀 *수준에서* 실행할 수 있지만 설치가 복잡해지기 때문에 권장되지 않습니다.  풀 수준에서 이러한 명령을 실행하여 풀에 포함된 모든 역할이 없는 경우(예: 웹 서비스가 없는 경우) 설정은 등록자 역할에만 설정됩니다. 이 경우 웹 서비스는 전역 수준의 설정과 함께 수행됩니다. 이 설정은 특히 의도하지 않은 경우의 행동에 혼동될 수 있습니다.

클라이언트가 한 풀의 등록자 설정과 다른 풀의 웹 서비스 설정을 사용하며 인증 설정이 불일치한 경우 클라이언트에서 로그온하지 못할 수 있습니다.

또한 풀에 역할이 하나만 있는 경우: 
* Set-는 존재하는 역할에 해당하는 설정만 설정합니다. 일부 설정이 설정되지 않은 경우 특별한 경고가 *제공되지* 않습니다. 
* Get-은 존재하는 역할에 해당하는 설정과 존재하지 않는 역할에 대한 전역 설정을 반환합니다.
* 풀에 두 역할이 모두 존재하지 않는다면 Set-및 Get-은 모두 오류 메시지를 반환합니다.
* 두 역할이 모두 풀에 있지만 정책이 풀 수준에서 정의되지 않은 경우 Get-은 오류 메시지를 반환합니다.

이러한 값에 대해 Get-을하고 변경하기 전에 시작 상태를 스크린샷 또는 기록하는 것이 가장 나을 수 있습니다. OneNote에 변경 내용 로그를 보관할 수도 있습니다.

> [!NOTE]
> 
> 참고: CsAuthConfig를 구성한 후 각 Enable-CsComputer 설정을 적용하려면 각 컴퓨터에서 이 설정을 실행해야 합니다.

> [!IMPORTANT]
> Lync Web Access(LWA)를 사용 중이며 외부 액세스에 FBA(양식 기반 액세스)를 사용해야 하는 경우 클라이언트가 익명 액세스로 액세스하여 이러한 시나리오를 지원할 수 있도록 LWA를 다시 구성합니다. 마찬가지로 전화 접속 핀을 사용하는 경우 외부 사용자에 한해 FBA가 차단됩니다. 핀을 변경해야 하는 경우 내부적으로 회사에 로그인해야 합니다.

> [!NOTE]
> 
> BlockWindowsAuthExternally 매개 변수를 사용하여 외부에서 NTLM을 차단하는 경우 SIP 채널에 대한 NTLM도 내부적으로 차단합니다. 그러나 비즈니스용 Skype 및 2010 이후의 Lync 클라이언트는 로그인에 대해 내부적으로 HTTP를 통해 NTLM을 사용하고 SIP를 통해 로그인하기 위해 인증서를 페치하기 때문에 계속 로그인할 수 있습니다. 그러나 2010보다 오래된 클라이언트는 이 상황에서 내부적으로 로그인할 수 없습니다. 따라서 사용자가 보안 기능을 다시 시작할 수 있도록 이러한 응용 프로그램을 업그레이드하는 것을 고려할 수 있습니다.

> [!IMPORTANT] 
> 일부 비즈니스용 Skype 웹 응용 프로그램은 MA를 지원하지 않습니다. 따라서 BlockWindowsAuthExternallyAndInternally 시나리오를 사용하면 이러한 응용 프로그램에 액세스할 수 없습니다. MA 지원이 없는 응용 프로그램은 웹 스케줄러, 전화 접속 페이지, CSCP(비즈니스용 Skype 제어판) 및 응답 그룹 설정 페이지입니다. 

## <a name="links"></a>Links 
- 자세한 PowerShell 정보를 원하세요.
    -  [Get-CsAuthConfig](https://docs.microsoft.com/powershell/module/skype/get-csauthconfig?view=skype-ps)
    -  [Set-CsAuthConfig](https://docs.microsoft.com/powershell/module/skype/set-csauthconfig?view=skype-ps)

- 명령을 사용하는 방법 또는 설치에 필요한 CU에 대한 자세한 방향을 위해 다음을 실행합니다.
    - [Cmdlet 브리핑](https://support.microsoft.com/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication)
    - [비즈니스용 Skype 서버 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015) 업데이트(일반)
    - [2018년 7월](https://support.microsoft.com/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server) 비즈니스용 Skype 서버, 핵심 구성 요소 CU(6.0.9319.534)


 
