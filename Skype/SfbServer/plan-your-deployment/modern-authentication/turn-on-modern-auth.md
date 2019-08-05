---
title: 네트워크를 통해 내부 및 외부적으로 레거시 인증 방법을 해제할 계획
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: ''
description: 이 문서에서는 관리자가 비즈니스 내부 및 외부에서 사용 하는 인증 방법에 대 한 더 많은 제어권을 제공 하는 cmdlet에 대해 간략하게 설명 합니다. 관리자는 내부에서 또는 네트워크에 대 한 인증 방법을 설정 하거나 해제할 수 있습니다.
ms.openlocfilehash: aaee46b04832cc114f895f905c180fe089d7349d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196866"
---
# <a name="planning-to-turn-off-legacy-authentication-methods-internally-and-externally-to-your-network"></a>네트워크의 내부 및 외부에서 레거시 인증 방법을 해제할 계획입니다.

> [!NOTE]
> 이 문서를 읽는 경우에는 이미 지원 되는 최신 인증 토폴로지, ADAL 및 최신 인증 구성에 대해 알고 있어야 하지만, 그렇지 않은 경우에는 다음 문서를 참조 하세요. 
>  + [https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)
>  + [https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal](https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal)
  
최신 인증은 2 단계 인증 또는 인증서 기반 인증 등의 더 안전한 인증 방법을 사용 하는 것이 아니라 사용자 이름 또는 비밀 번호를 필요로 하지 않고 사용자의 인증을 수행할 수 있습니다. 아주 편리한 방법입니다.

이 문서는 비즈니스용 Skype 서버의 DOS (서비스 거부) 공격에 사용 된 네트워크에 대 한 인증, 외부, 내부 또는 두 가지 방법 모두를 해제 하 여 악용 된 구멍을 연결 하는 데 도움을 줍니다. 예를 들어 DOS 공격을 중지 하는 데 도움이 되는 좋은 방법은 NTLM 및 Kerberos가 포함 된 Windows 통합 인증을 해제 하는 것입니다. NTLM을 해제 하 고 인증서 기반 인증을 사용 하면 암호가 노출 되지 않도록 할 수 있습니다. NTLM은 암호 자격 증명을 사용 하 여 사용자를 인증 하기는 하지만 최신 인증을 사용 하도록 설정 된 인증서 기반 인증은 그렇지 않기 때문입니다. 이것은 DOS 공격을 줄이는 데 이상적인 옵션 중 하나는 NTLM을 외부적으로 차단 하 고 대신 인증서 기반 인증만 사용 하는 것입니다.

바로, 시작 해 보세요.

## <a name="what-would-you-be-changing"></a>변경 내용 

이러한 cmdlet은 access의 SIP와 웹 서비스 지점 모두에 대해 작동 합니다. 이러한 두 채널은 서로 다른 access 메서드를 사용 하지만, NTLM 및 Kerberos에서 익명 액세스로 색 범위를 실행 하면 비즈니스용 Skype에서 사용 되는 모든 표준 방법을 고려해 야 합니다.

## <a name="how-to-get-the-get--and-set-csauthconfig-cmdlets"></a>Get 및 Set CsAuthConfig cmdlet을 가져오는 방법

이 cmdlet은 비즈니스용 skype Server 2015에 대 한 7 월 2018 누적 업데이트 (6.0.9319.534) 게시만 설치 되어 있으며,이에 따라 비즈니스용 Skype server에 대해 롤아웃할 수 있는 다양 한 토폴로지가 있습니다.

## <a name="topologies"></a>토폴로지

이 시나리오와 관련 하 여 지원 되는 토폴로지에서는 주의를 두어야 합니다. 예를 들어 메서드 차단에 대 한 도움말 지원으로 이동 해야 하는 경우 아래 형식 중 하나를 구성 해야 합니다. 

> [!IMPORTANT]
> 아래의 표 및 설명에서 *최신 인증은* __MA__ 로 간략 하 고 *Windows 통합 인증은* __Win__으로 간략 한 것입니다. 미리 알림에서 Windows 통합 인증은 NTLM 및 Kerberos 인증 이라는 두 가지 방법으로 이루어집니다. 표를 제대로 읽으려면이를 알아야 합니다.


|       |외부에서  |내부의  |매개 변수  |
|---------|:---------|:---------|---------|
|__종류 1__   |  MA + Win       | MA + Win         |  AllowAllExternallyAndInternally       |
|__종류 2__   |  M       | MA + Win         | BlockWindowsAuthExternally        |
|__3을 입력 합니다.__   |  M       | M        | BlockWindowsAuthExternallyAndInternally        |
|__종류 4__   |  M       | Win        | BlockWindowsAuthExternallyAndModernAuthInternally    |
|__5를 입력 합니다.__   |  MA + Win       | Win        | BlockModernAuthInternally         |

__종류 1 설명:__ 이는 비즈니스용 Skype Server에 대해 MA가 ____ 설정 된 경우의 기본 시나리오입니다. 즉 MA가 구성 되 면이 ** 출발점을 사용할 수 있습니다.

__종류 2 설명:__ 이 토폴로지는 *외부*에서 ntlm을 차단 하지만, *내부적*으로 작동 하도록 NTLM 또는 Kerberos (ADAL을 지원 하지 않는 클라이언트)를 허용 합니다. 클라이언트가 ADAL을 지 원하는 경우에는 MA를 내부적으로 사용 합니다.

__3 설명 입력:__ 이 토폴로지에는 모든 사용자에 대해 MA가 필요 합니다. 이 토폴로지에서는 모든 ADAL 가능 클라이언트가 작동 하 고, 예를 들어 인증서 기반 인증으로 암호 사용을 해제 하는 경우 암호를 활용할 수 없습니다.

__4 형식 설명:__ 이 토폴로지는 내부적으로 NTLM을 *외부* 와 MA로 차단 합니다. 이를 통해 *모든 클라이언트가* 레거시 인증 메서드를 *내부적* 으로 사용할 수 있습니다 (즉, ADAL 가능 클라이언트 라도).

__5 설명 입력:__ *외부*에서 현대적인 adal 클라이언트는 MA를 사용 하 고 ADAL을 지원 하지 않는 클라이언트는 레거시 인증 방법을 사용 합니다. 하지만 *내부적* 으로 *모든 클라이언트가* 레거시 인증 (모든 ADAL 지원 클라이언트 포함)을 사용 합니다.

사용할 수 있는 옵션에서 암호를 보호 하는 목표를 추적 하는 것은 매우 쉽습니다. 가장 좋은 경우는 DOS 공격을 방지 하기 위해 MA (예: 인증서 기반 인증 구성)를 외부적으로 사용 하는 것입니다. 최신 클라이언트를 위해 내부적으로이 기능을 사용할 경우 비즈니스용 Skype Server DOS 공격과 관련 하 여 네트워크를 교정 하는 것도 도움이 됩니다.

## <a name="why-to-use-set-csauthconfig-at-the-global-level"></a>전역 수준에서 Set-CsAuthConfig를 사용 하는 이유

등록자 `Set-CsAuthConfig` 와 웹 서비스 역할에 모두 적용 되는 cmdlet 효과 구성입니다.

이 cmdlet은 비즈니스용 Skype 서버의 전역 수준에서 실행할 수 있도록 고안 되었습니다. 풀 수준에서 실행할 *수* 있지만 설치에 복잡성을 추가 하 게 되므로 *권장 되지* 않습니다. 풀 수준에서 이러한 명령을 실행 하 여 그룹에 포함 된 역할이 모두 없는 경우 (예: 웹 서비스를 사용 하지 않는 경우)에는 등록자 역할에 대해서만 설정이 설정 됩니다. 이 경우 웹 서비스는 전역 수준의 설정을 사용 하 여 수행 되며, 혼동 될 수 있습니다 (특히,이 경우 의도 하지 않은 동작을 수행 하는 경우).

클라이언트가 한 풀의 등록자 설정과 다른 풀의 웹 서비스 설정을 사용 하 고 인증 설정이 일관성이 없는 상태에 있으면 yous 클라이언트에서 로그온 할 수 없는 것일 수 있습니다.

또한 풀에 대해 하나의 역할만 있는 경우: 
* Set-존재 하는 역할에 해당 하는 설정만 설정 합니다. 일부 설정이 설정 *되지* 않았으므로 특별 한 경고가 제공 되지 않습니다. 
* Get-존재 하는 역할에 해당 하는 설정과 존재 하지 않는 역할에 대 한 전역 설정이 반환 됩니다.
* 풀에 대 한 역할이 없는 경우 설정 및 가져오기는 모두 오류 메시지를 반환 합니다.
* 풀에 대해 두 역할이 있지만 정책 풀 수준에서 정의 되지 않은 경우 Get-은 오류 메시지를 반환 합니다.

이러한 값에 대해 Get을 수행 하는 것이 wisest, 변경 하기 전에 스크린샷 또는 시작 상태를 기록 하는 것이 더 나을 수 있습니다. OneNote에서 변경 내용 로그를 유지 하는 것도 고려할 수 있습니다.

> [!NOTE]
> 
> 참고: CsAuthConfig를 구성한 후에는 각 컴퓨터에서 Enable-CsComputer를 실행 하 여 설정을 적용 해야 합니다.

> [!IMPORTANT]
> LWA (Lync Web Access)를 사용 하는 경우 외부 액세스에 대해 FBA (양식 기반 액세스)를 사용 해야 하는 경우 클라이언트가 이러한 시나리오를 지원 하기 위해 익명 액세스를 사용 하 여 액세스할 수 있도록 LWA를 다시 구성 합니다. 마찬가지로 전화 접속 Pin을 사용 하는 경우 외부 사용자만이 FBA를 차단 합니다. Pin을 변경 해야 하는 경우에는 회사에 로그인 하 여 내부적으로이 작업을 수행 해야 합니다.

## <a name="links"></a>링크 
- PowerShell에 대 한 자세한 정보:
    -  [Get-CsAuthConfig](https://docs.microsoft.com/powershell/module/skype/get-csauthconfig?view=skype-ps)
    -  [Set-CsAuthConfig](https://docs.microsoft.com/en-us/powershell/module/skype/set-csauthconfig?view=skype-ps)

- 명령 또는이를 설치 하는 데 필요한 CU (을 사용 하는 방법에 대해 자세히 알아보세요.
    - [Cmdlet 브리핑](https://support.microsoft.com/en-us/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication)
    - [비즈니스용 Skype 서버 2015 업데이트](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015) 전반적
    - [7 월 2018 Skype For Business Server 2015, cu (](https://support.microsoft.com/en-us/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server) (6.0.9319.534)


 
