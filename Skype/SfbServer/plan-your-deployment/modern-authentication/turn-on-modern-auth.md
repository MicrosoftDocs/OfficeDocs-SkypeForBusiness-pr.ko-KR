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
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: ''
description: 이 문서에서는 관리자가 비즈니스 내부 및 외부에서 사용되는 인증 방법을 보다 제어할 수 있는 cmdlet에 대해 간략하게 설명합니다. 관리자는 내부적으로 또는 외부적으로 네트워크에서 인증 방법을 설정하거나 해제할 수 있습니다.
ms.openlocfilehash: 7bad18e79e1595c7dfe4518d73b6dd764e313e22
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58601363"
---
# <a name="planning-to-turn-off-legacy-authentication-methods-internally-and-externally-to-your-network"></a>네트워크 내부 및 외부에서 레거시 인증 방법을 끄기 위한 계획

> [!NOTE]
> 이 문서를 읽으러 가고 있는 경우 지원되는 최신 인증 토폴로지, ADAL 및 최신 인증 구성에 대해 이미 알고 있지만, 그렇지 않은 경우 시작해야 하는 문서는 다음과 같습니다. 
>  + [https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported](./topologies-supported.md)
>  + [https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal](/skypeforbusiness/manage/authentication/use-adal)
  
최신 인증은 Two-Factor 인증 또는 인증서 기반 인증과 같은 보다 안전한 인증 방법을 사용하도록 설정하는 것이 아니라 사용자 이름이나 암호 없이도 사용자의 인증을 수행하도록 할 수 있습니다. 매우 간단합니다.

이 문서는 네트워크에서 인증, 외부, 내부 또는 둘 다에 사용되는 이전 방법을 해제하여 비즈니스용 Skype Server에 대한 DOS(서비스 거부) 공격에 악용된 구멍을 플러그 인하는 데 도움이 됩니다. 예를 들어 DOS 공격을 중지하는 데 도움이 되는 한 가지 좋은 방법은 통합 인증(NTLM 및 Windows 포함)을 해제하는 것입니다. 외부에서 NTLM을 끄고 인증서 기반 인증을 사용하는 경우 암호가 노출되지 않습니다. 이는 NTLM에서 암호 자격 증명을 사용하여 사용자를 인증하지만 최신 인증에서 사용하도록 설정된 인증서 기반 인증은 그렇지 않습니다. 즉, DOS 공격을 줄이는 이상적인 한 가지 옵션은 외부에서 NTLM을 차단하고 대신 인증서 기반 인증만 사용하는 것입니다.

시작해보시겠어요?

## <a name="what-would-you-be-changing"></a>어떤 변화가 있을까요? 

이러한 cmdlet은 SIP 및 웹 서비스 액세스 지점에 모두 사용할 수 있습니다. 이러한 두 채널은 서로 다른 액세스 방법을 사용하며 NTLM 및 Kerberos에서 익명 액세스로의 기능을 실행하기는 하지만, 비즈니스용 Skype 사용하는 모든 표준 메서드를 고려했습니다.

## <a name="how-to-get-the-get--and-set-csauthconfig-cmdlets"></a>Get- 및 cmdlet을 Set-CsAuthConfig 방법

이러한 cmdlet은 Microsoft 비즈니스용 Skype 서버 2015용 2018년 7월 누적 업데이트(6.0.9319.534) 이후만 설치될 예정이면 비즈니스용 Skype 서버에 대해 배포할 수 있는 다양한 토폴로지가 있습니다.

## <a name="topologies"></a>토폴로지

이러한 토폴로지가 이 시나리오에 관련된 지원되는 토폴로지입니다. 예를 들어 방법 차단에 대한 도움말을 위해 지원으로 이동해야 하는 경우 아래 형식 중 구성이 필요합니다. 

> [!IMPORTANT]
> 아래 표와 설명에서  최신 인증은 __MA로__ 약어되고 Windows 통합 인증은 *Win으로* 약식으로 __사용됩니다.__ 미리 Windows 통합 인증은 NTLM 인증과 Kerberos 인증의 두 가지 방법으로 나타남을 예고합니다. 테이블을 제대로 읽으면 이 내용을 알아야 합니다.


|       |외부  |내부적으로  |매개 변수  |
|---------|:---------|:---------|---------|
|__유형 1__   |  MA + Win       | MA + Win         |  AllowAllExternallyAndInternally       |
|__유형 2__   |  MA       | MA + Win         | BlockWindowsAuthExternally        |
|__유형 3__   |  MA       | MA        | BlockWindowsAuthExternallyAndInternally        |
|__유형 4__   |  MA       | Win        | BlockWindowsAuthExternallyAndModernAuthInternally    |
|__유형 5__   |  MA + Win       | Win        | BlockModernAuthInternally         |

__유형 1 설명:__ 이 시나리오는 사용자 지정에  대해 MA가 켜져 있는 비즈니스용 Skype 서버. 즉, MA를 구성할 때 시작점입니다. 

__유형 2 설명:__ 이 토폴로지에서는 외부에서 NTLM을 차단하지만 ADAL을 지원하지 않는 클라이언트의 경우 NTLM 또는 Kerberos가 내부적으로 *작동할 수 있습니다.* 클라이언트가 ADAL을 지원하는 경우 내부적으로 MA를 사용하게 됩니다.

__유형 3 설명:__ 이 토폴로지에는 모든 사용자에 대해 MA가 필요합니다. 예를 들어 인증서 기반 인증에서 암호 사용을 끄는 경우 모든 ADAL 지원 클라이언트가 이 토폴로지에서 작동하며 암호가 활용되지 않습니다.

__유형 4 설명:__ 이 토폴로지가  NTLM을 외부 및 MA 내부적으로 차단합니다. 이를 통해 *모든* 클라이언트가 내부적으로(ADAL 지원 클라이언트도) 레거시 인증 방법을 사용할 수 있습니다. 

__유형 5 설명:__ *외부에서* 최신 ADAL 클라이언트는 MA를 사용하며 ADAL을 지원하지 않는 클라이언트는 레거시 인증 방법을 사용하게 됩니다. 그러나 *내부적으로 모든* *클라이언트는* 레거시 인증(모든 ADAL 지원 클라이언트 포함)을 사용하게 됩니다.

사용 가능한 옵션에서 암호를 보호하는 목표를 쉽게 추적할 수 있습니다. 이상적인 상황은 DOS 공격을 방지하기 위해 외부에서 MA를 사용하는 것입니다(예: 인증서 기반 인증 구성). 최신 클라이언트에 내부적으로 활용하는 경우 DOS 공격과 관련하여 네트워크의 미래를 비즈니스용 Skype 서버 있습니다.

## <a name="why-to-use-set-csauthconfig-at-the-global-level"></a>전역 수준에서 Set-CsAuthConfig 사용하는 이유

이 cmdlet은 등록자 및 웹 서비스 역할 모두에 대한 `Set-CsAuthConfig` 구성에 영향을 미치게 됩니다.

이 cmdlet은 서버의 전역 수준에서 비즈니스용 Skype. 풀 *수준에서* 실행할 수 있지만 설치가 복잡해지기 때문에 권장되지 않습니다.  풀 수준에서 이러한 명령을 실행하여 풀에 포함된 모든 역할이 없는 경우(예: 웹 서비스가 없는 경우) 설정은 등록자 역할에만 설정됩니다. 이 경우 웹 서비스는 전역 수준의 설정으로 수행됩니다. 이 설정은 특히 의도치 않은 경우 수행되는 경우 행동에 혼동을 주게 될 수 있습니다.

클라이언트가 한 풀의 등록자 설정과 다른 풀의 웹 서비스 설정을 사용하며 인증 설정이 불일치 상태인 경우 클라이언트에서 로그온하지 못할 수 있습니다.

또한 풀에 역할이 하나만 있는 경우: 
* Set-는 존재하는 역할에 해당하는 설정만 설정합니다. 일부 설정이 설정되지 않은 경우 특별한 경고가 *제공되지* 않습니다. 
* Get-은 존재하는 역할에 해당하는 설정과 존재하지 않는 역할에 대한 전역 설정을 반환합니다.
* 풀에 두 역할이 모두 존재하지 않는다면 Set- 및 Get은 모두 오류 메시지를 반환합니다.
* 풀에 대해 두 역할이 있지만 정책이 풀 수준에서 정의되지 않은 경우 Get-은 오류 메시지를 반환합니다.

이러한 값에 대해 Get-을하고 변경하기 전에 시작 상태를 스크린샷 또는 기록하는 것이 가장 나을 수 있습니다. 변경 내용 로그를 보관할 수도 OneNote.

> [!NOTE]
> 
> 참고: CsAuthConfig를 구성한 후 각 컴퓨터에서 Enable-CsComputer 실행해야 설정이 적용됩니다.

> [!IMPORTANT]
> Lync Web Access(LWA)를 사용 중이며 외부 액세스에 FBA(양식 기반 액세스)를 사용해야 하는 경우 클라이언트가 이러한 시나리오를 지원하기 위해 익명 액세스로 액세스할 수 있도록 LWA를 다시 구성합니다. 마찬가지로 전화 접속 핀을 사용하는 경우 외부 사용자에 대한 FBA만 차단됩니다. 핀을 변경해야 하는 경우 내부적으로 회사에 로그인해야 합니다.

> [!NOTE]
> 
> BlockWindowsAuthExternally 매개 변수를 사용하여 외부에서 NTLM을 차단하는 경우 SIP 채널에 대한 내부적으로 NTLM도 차단합니다. 그러나 비즈니스용 Skype 및 Lync 클라이언트는 로그인에 대해 내부적으로 HTTP를 통해 NTLM을 사용하여 로그인한 다음 SIP를 통해 로그인하기 위해 인증서를 페치하기 때문에 계속 로그인할 수 있습니다. 그러나 2010보다 오래된 클라이언트는 이 상황에서 내부적으로 로그인할 수 없습니다. 따라서 사용자가 보안 기능을 다시 시작할 수 있도록 이러한 응용 프로그램을 업그레이드하는 것을 고려할 수 있습니다.

> [!IMPORTANT] 
> 일부 비즈니스용 Skype 웹 응용 프로그램은 MA를 지원하지 않습니다. 따라서 BlockWindowsAuthExternallyAndInternally 시나리오를 사용하면 이러한 응용 프로그램에 액세스할 수 없습니다. MA 지원이 없는 응용 프로그램은 웹 스케줄러, 전화 접속 페이지, 비즈니스용 Skype CSCP(제어판) 및 응답 설정 있습니다. 

## <a name="links"></a>링크 
- 자세한 PowerShell 정보를 원하세요.
    -  [Get-CsAuthConfig](/powershell/module/skype/get-csauthconfig?view=skype-ps)
    -  [Set-CsAuthConfig](/powershell/module/skype/set-csauthconfig?view=skype-ps)

- 명령을 사용하는 방법 또는 설치에 필요한 CU에 대한 자세한 내용은 다음을 실행합니다.
    - [Cmdlet 브리핑](https://support.microsoft.com/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication)
    - [비즈니스용 Skype 서버 2015에 대한](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015) 업데이트(일반)
    - [2018년 7월 비즈니스용 Skype 서버, 핵심](https://support.microsoft.com/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server) 구성 요소 CU(6.0.9319.534)


