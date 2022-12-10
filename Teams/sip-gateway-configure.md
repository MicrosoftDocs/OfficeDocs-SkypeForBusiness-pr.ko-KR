---
title: SIP 게이트웨이 구성
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/8/2022
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: SIP 게이트웨이를 구성하는 방법을 알아봅니다.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: c93aec7cb65cdd40c05a540b51a3da8ba268c7e9
ms.sourcegitcommit: feb9b7d10e38f5a629ee9202b5aaec5beef4de9b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2022
ms.locfileid: "69343296"
---
# <a name="configure-sip-gateway"></a>SIP 게이트웨이 구성

이 문서에서는 조직에서 Microsoft Teams와 호환되는 SIP 디바이스를 사용할 수 있도록 SIP 게이트웨이를 구성하는 방법을 설명합니다. 조직에 대해 SIP Gateway가 수행할 수 있는 작업과 조직에 필요한 하드웨어, 소프트웨어 및 라이선스를 알아보려면 [SIP 게이트웨이 계획을](sip-gateway-plan.md) 참조하세요.

SIP 게이트웨이를 구성하려면 다음을 수행합니다.

- **SIP 디바이스를 공장 기본 설정으로 다시 설정합니다.** 사용자 또는 조직의 사용자는 SIP 게이트웨이와 함께 사용되는 각 SIP 디바이스를 공장 기본 설정으로 다시 설정해야 합니다. 이 작업을 수행하는 방법을 알아보려면 제조업체의 지침을 참조하세요.

- **방화벽을 열어 365 및 Teams를 Microsoft.** Office 365 [URL 및 IP 주소 범위에](/microsoft-365/enterprise/urls-and-ip-address-ranges) 설명된 대로 네트워크의 방화벽을 열어 365 및 Teams 트래픽을 Microsoft. 방화벽 규칙은 아웃바운드 트래픽에만 필요합니다.

- **SIP 디바이스가 프록시 뒤에 있지 않은지 확인합니다.** http/s 트래픽이 회사 http/s 프록시를 우회하는지 확인합니다.

- **UDP 포트를 엽니다.** IP 범위 52.112.0.0/14 및 52.122.0.0/15의 경우 49152~53247 범위에서 UDP 포트를 엽니다.

- **TCP 포트를 엽니다.** IP 범위 52.112.0.0/14 및 52.122.0.0/15에 대한 TCP 포트 5061을 엽니다.

- **다음 https 엔드포인트(IP 주소 및 URL)를 엽니다.**

  - 13.75.175.145
  - 52.189.219.201
  - 51.124.34.164
  - 13.74.250.91
  - 13.83.55.36
  - 23.96.103.40
  - https://blobsdgapac.blob.core.windows.net
  - https://blobsdgemea.blob.core.windows.net
  - https://blobsdgnoam.blob.core.windows.net
  - https://httpblobsdgapac.blob.core.windows.net
  - https://httpblobsdgemea.blob.core.windows.net
  - https://httpblobsdgnoam.blob.core.windows.net


다음 섹션에서는 SIP 게이트웨이를 구성하기 위해 관리자 권한으로 수행해야 하는 작업을 설명합니다.

- [조직에 SIP 게이트웨이를 사용할 수 있는지 확인합니다](#verify-that-sip-gateway-is-available-for-your-organization).

- [조직의 사용자에 대해 SIP 게이트웨이를 사용하도록 설정합니다](#enable-sip-gateway-for-the-users-in-your-organization).

- [SIP 게이트웨이 프로비저닝 서버 URL을 설정합니다](#set-the-sip-gateway-provisioning-server-url).

이 문서에서는 다음 방법도 설명합니다.

- [편의를 위해 개별적으로 또는 일괄 처리로 SIP 디바이스를 등록합니다](#provision-and-enroll-sip-devices-as-common-area-phones).  

- [SIP 디바이스를 보고 모니터링합니다.](#view-and-monitor-sip-devices)

- [다국어 사용자 인터페이스에 대한 지원을 사용하도록 설정합니다.](#set-a-sip-devices-ui-language)

## <a name="verify-that-sip-gateway-is-available-for-your-organization"></a>조직에 SIP 게이트웨이를 사용할 수 있는지 확인합니다.

1. [Teams 관리 센터에 로그인합니다](https://admin.teams.microsoft.com/).

2. 왼쪽에서 **Teams 디바이스** 를 선택하고 **SIP 디바이스** 탭이 표시되는지 확인합니다. 이 경우 조직에 대해 SIP 게이트웨이 서비스가 사용하도록 설정됩니다.

## <a name="enable-sip-gateway-for-the-users-in-your-organization"></a>조직의 사용자에 대해 SIP 게이트웨이 사용

Teams 관리 센터를 사용하거나 PowerShell cmdlet을 사용하는 두 가지 방법 중 하나로 조직에 SIP 게이트웨이를 사용하도록 설정할 수 있습니다.

### <a name="by-using-teams-admin-center"></a>Teams 관리 센터 사용

Teams 관리 센터에서 SIP 게이트웨이를 사용하도록 설정하려면 다음 단계를 수행합니다.

1. [Teams 관리 센터로](https://admin.teams.microsoft.com/) 이동

2. 왼쪽의 **음성** 아래에서 **통화 정책을** 선택합니다.

3. **정책 관리** 의 오른쪽에서 사용자에게 할당된 적절한 통화 정책을 선택하거나 필요한 경우 새 통화 정책을 만들고 필요한 사용자에게 할당합니다.

4. **정책 관리를** 선택하고 정책을 선택한 다음 **편집** 을 선택합니다.

5. **호출에 사용할 수 있는 SIP 디바이스에 대한** 설정을 켜고 **저장** 을 선택합니다.


### <a name="by-using-powershell"></a>PowerShell 사용

PowerShell [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy) cmdlet을 사용하여 SIP 게이트웨이를 사용하도록 설정할 수도 있습니다. SIP 디바이스에 대한 사용자를 사용하도록 설정하려면 정책을 선택하고 특성을 `True`로 설정합니다`-AllowSIPDevicesCalling`. 기본값은 `False`이므로 사용자가 SIP 디바이스를 사용하도록 설정하지 않으면 해당 SIP 디바이스를 사용할 수 없습니다.

> [!NOTE]
> - 정책 전파는 최대 24시간이 걸릴 수 있습니다.

## <a name="set-the-sip-gateway-provisioning-server-url"></a>SIP 게이트웨이 프로비저닝 서버 URL 설정

DHCP(동적 호스트 구성 프로토콜) 서버에서 SIP 게이트웨이 프로비저닝 서버의 URL을 설정할 수 있습니다. 원격으로 작업하는 사용자는 수동으로 구성해야 합니다.

### <a name="using-dhcp"></a>DHCP 사용

각 SIP 디바이스에 대해 다음 SIP 게이트웨이 프로비저닝 서버 URL 중 하나를 설정합니다. 

- Emea: `http://emea.ipp.sdg.teams.microsoft.com`
- 아메리카: `http://noam.ipp.sdg.teams.microsoft.com`
- Apac: `http://apac.ipp.sdg.teams.microsoft.com`

DHCP 서버에서 위의 SIP 게이트웨이 프로비저닝 서버 URL을 구성하여 Teams 조직에 SIP 디바이스를 추가합니다. DHCP 서버에 대한 자세한 내용은 [DHCP 배포 및 관리를 참조하세요](/training/modules/deploy-manage-dynamic-host-configuration-protocol). 또한 DHCP 옵션 42를 사용하여 NTP(네트워크 시간 프로토콜) 서버를 지정하고 DHCP 옵션 2를 사용하여 UTC(협정 세계시)의 오프셋을 초 단위로 지정할 수 있습니다. 조직의 디바이스는 SIP 게이트웨이 프로비저닝 서버로 라우팅됩니다. 성공적으로 프로비전된 SIP 휴대폰은 Teams 로고와 로그인을 위한 소프트 단추를 표시합니다.

SIP 디바이스가 온보딩을 위해 지원되는 최소 펌웨어 버전에 있는지 확인합니다. 온보딩하는 동안 SIP 게이트웨이는 기본 구성 및 인증 사용자 인터페이스를 디바이스에 푸시합니다. SIP 디바이스에 필요한 펌웨어 버전을 확인하려면 [SIP 게이트웨이 계획을 참조하세요](sip-gateway-plan.md).

### <a name="manually"></a>수동으로

원격으로 작업하는 사용자는 다음 단계를 사용하여 SIP 디바이스에 프로비저닝 서버 URL을 수동으로 구성해야 합니다.

1. 디바이스에서 **설정을** 열고 디바이스의 IP 주소를 가져옵니다.

2. 브라우저 창을 열고, 디바이스의 IP 주소를 입력하고, (필요한 경우) 로그인하고, 디바이스의 웹 유틸리티에서 프로비저닝 서버의 URL을 구성합니다.

3. 웹 유틸리티의 **설정** 또는 **고급 설정** 에서 위에 표시된 프로비저닝 서버 URL을 입력합니다.

> [!NOTE]
> - 호환되는 SIP 디바이스만 SIP 게이트웨이에 온보딩할 수 있습니다. 
> - Cisco IP 휴대폰을 온보딩하려면 먼저 멀티플랫폼 펌웨어로 플래시해야 합니다. 방법을 알아보려면 [Cisco 펌웨어 변환 가이드를 참조하세요](https://www.cisco.com/c/en/us/products/collateral/collaboration-endpoints/unified-ip-phone-7800-series/guide-c07-742786.html).
> - Yealink 휴대폰의 경우 옵션 66을 사용합니다.
> - Cisco, Poly 및 AudioCode 휴대폰의 경우 옵션 160을 사용합니다. 
> - Cisco 디바이스의 경우 프로비저닝 서버 URL에 **/$PSN.xml** 추가합니다.


## <a name="configure-conditional-access"></a>조건부 액세스 구성

조건부 액세스는 Microsoft 365 리소스에 액세스하는 디바이스가 제대로 관리되고 안전하게 관리되도록 하는 데 도움이 되는 azure Azure AD(Active Directory) 기능입니다. SIP Gateway는 Azure AD 사용하여 SIP 디바이스를 인증하므로 조직에서 회사 네트워크의 디바이스에 조건부 액세스를 사용하는 경우 다음 IP 주소를 제외해야 합니다.

- 북아메리카:
    - 미국 동부: 52.170.38.140
    - 미국 서부: 40.112.144.212
-   EMEA 지역:
    - 북EU: 40.112.71.149
    - EU 서부: 40.113.112.67
-   APAC 지역:
    - 오스트레일리아 동부: 20.92.120.71
    - 오스트레일리아 남동부: 13.73.115.90

자세한 내용은 [IP 주소 범위를 참조하세요](/azure/active-directory/conditional-access/location-condition#ip-address-ranges).

## <a name="provision-and-enroll-sip-devices-as-common-area-phones"></a>공용 영역 휴대폰으로 SIP 디바이스 프로비전 및 등록

> [!NOTE]
> SIP 디바이스를 등록하려면 먼저 SIP 게이트웨이에 온보딩해야 합니다.

작업을 간소화하기 위해 한 번에 하나씩 또는 일괄 처리로 Teams 관리 센터에 SIP 디바이스를 등록할 수 있습니다. 방법은 다음과 같습니다.

1. [**Teams 관리 센터에 로그인합니다**](https://admin.teams.microsoft.com).

2. **Teams 디바이스** > **SIP 디바이스** 를 선택합니다.

3. 오른쪽 위에서 **디바이스 프로비저닝** **작업을** >  선택하고 다음 단계 중 하나를 수행합니다.

  - **하나의 디바이스를 프로비전하려면 다음을 수행합니다.**

     a. **활성화 대기 중에서** **추가** 를 선택합니다.

     b. **MAC 주소 추가** 창에서 **MAC 주소** 및 디바이스의 **위치를** 입력한 다음 **적용** 을 선택합니다.
     
     C. **활성화 대기 중에서** 방금 추가한 디바이스를 선택한 다음 **확인 코드 생성** 을 선택합니다.
     
     D. **디바이스 프로비전** 창의 **확인 코드** 에서 SIP 디바이스에 대한 확인 코드를 확인합니다.

   - **많은 디바이스를 프로비전하려면 다음을 수행합니다.**

     a. **활성화 대기 중** 의 오른쪽에서 **내보내기**(Microsoft Excel 아이콘)를 선택합니다.
     
     b. **디바이스 프로비전** 창의 **여러 MAC 주소 업로드** 에서 **템플릿 다운로드를** 선택합니다.
     
     C. **컴퓨터에Template_Provisioning.csv** 저장하고 **MAC ID** 및 **위치** 필드를 입력합니다.
    
     D. **디바이스 프로비전** 창에서 **여러 MAC 주소 업로드를** 선택합니다. 

     전자. **MAC 주소 업로드** 창의 오른쪽에서 **파일 선택을** 선택하고 데이터가 포함된 **Template_Provisioning.csv** 파일을 선택합니다.

     F. **디바이스 프로비전** 창의 **활성화 대기 중** 에서 디바이스를 선택한 다음 **확인 코드 생성** 을 선택하여 프로비전된 각 디바이스에 대해 일회성 확인 코드를 생성합니다. 각 SIP 디바이스에 대한 확인 코드를 확인합니다.

4. SIP 디바이스에서 등록 기능 코드 다음에 확인 코드로 전화를 거는 것입니다. SIP 디바이스에서 등록 기능 코드 55*(등록 일회성 확인 코드 \*유효성 검사를 위해 SIP 게이트웨이에서 사용됨)와 이 특정 디바이스에 대한 Teams 관리 센터에서 생성된 확인 코드로 전화를 거는 것입니다. 예를 들어 확인 코드가 123456 경우 55\*번 123456 전화를 걸어 \*디바이스를 등록합니다.

5.  **디바이스 프로비전** 창의 **로그인 대기** 에서 **로그아웃** 을 선택합니다.

6. **사용자 로그인** 대화 상자에서 SIP 디바이스의 페어링 코드를 복사하거나 메모합니다.

7. 로 [https://microsoft.com/devicelogin](https://microsoft.com/devicelogin)이동하고 **코드 입력** 에서 SIP 디바이스의 페어링 코드를 입력한 다음 **, 다음** 을 선택합니다.

8. Microsoft **로그인** 페이지의 **Email 또는 전화** 필드에 SIP 디바이스의 전자 메일 주소를 입력하고 **다음** 을 선택합니다.

9. **암호** 페이지에서 SIP 디바이스의 전자 메일 주소에 대한 암호를 입력한 다음 **로그인을** 선택합니다.

10. **Teams SIP 디바이스 게이트웨이에 로그인하려고 합니까? 페이지에서** **계속** 을 선택합니다.

## <a name="how-to-sign-in-and-sign-out"></a>로그인 및 로그아웃하는 방법

사용자의 개인 디바이스에는 로컬 로그인만 지원됩니다. 관리 센터에서 디바이스를 로그아웃하려면 다음 단계를 수행합니다.

1. [**Teams 관리 센터에 로그인합니다**](https://admin.teams.microsoft.com).

2. **Teams 디바이스** > **SIP 디바이스** 를 선택합니다.

3. 오른쪽에서 SIP 디바이스를 선택한 다음 로그 **아웃을** 선택합니다.


### <a name="user-pairing-and-sign-in"></a>사용자 페어링 및 로그인

사용자가 회사 자격 증명을 사용하여 인증한 후 SIP 디바이스를 페어링하려면 사용자가 다음을 수행해야 합니다.

1. SIP 휴대폰 **에서 로그인** 을 눌러 인증 URL 및 페어링 코드를 표시합니다. 페어링 코드는 시간에 민감합니다. 만료되는 경우 사용자는 휴대폰 **에서 뒤로** 를 누르고 로그인 프로세스를 다시 시작해야 합니다.

2. 사용자의 데스크톱 또는 모바일 브라우저에서 인증 URL로 이동하고 회사 자격 증명을 사용하여 로그인합니다.

3. SIP 휴대폰에 표시되는 페어링 코드를 웹 인증 앱에 입력하여 SIP 휴대폰을 사용자의 계정과 페어링합니다. 로그인에 성공하면 디바이스에서 지원하는 경우 SIP 휴대폰에 전화 번호와 사용자 이름이 표시됩니다.

> [!NOTE]
> Azure Active Directory 웹 인증 앱에 표시되는 디바이스의 위치는 디바이스가 연결된 SIP 게이트웨이 데이터 센터입니다. 범위의 SIP 전화는 OAuth를 사용할 수 없으므로 SIP 게이트웨이는 웹 인증 앱을 통해 사용자를 인증한 다음 디바이스를 사용자의 자격 증명과 페어링합니다. [Microsoft ID 플랫폼 및 OAuth 2.0 디바이스 권한 부여 흐름](/azure/active-directory/develop/v2-oauth2-device-code)에 대해 자세히 알아보세요.

### <a name="sign-out"></a>로그아웃

로그아웃하기 위해 디바이스 사용자는 다음을 수행할 수 있습니다.

- SIP 디바이스에서 **로그아웃** 을 누르고 디바이스에 설명된 단계를 따릅니다. 

Teams 관리 센터에서 디바이스를 로그아웃하려면 다음을 수행합니다.

1. [**Teams 관리 센터에 로그인합니다**](https://admin.teams.microsoft.com).

2. **Teams 디바이스** > **SIP 디바이스** 를 선택합니다.

3. 오른쪽의 **SIP 디바이스** 창에서 디바이스를 선택합니다.

4. 디바이스의 **세부 정보 창** 에서 **세부 정보** 탭을 선택하고 **작업** 메뉴의 오른쪽 위에서 **로그아웃** 을 선택합니다. 

## <a name="view-and-monitor-sip-devices"></a>SIP 디바이스 보기 및 모니터링

디바이스 사용자가 한 번 이상 로그인한 후 Teams 관리 센터에서 SIP 디바이스 인벤토리를 보고 모니터링할 수 있습니다. 방법은 다음과 같습니다.

1. [Teams 관리 센터에 로그인합니다](https://admin.teams.microsoft.com/).

2. **Teams 디바이스** > **SIP 디바이스** 를 선택합니다. 로그인한 모든 SIP 디바이스가 오른쪽에 나열됩니다.

## <a name="restart-a-sip-device"></a>SIP 디바이스 다시 시작

1. [Teams 관리 센터에 로그인합니다](https://admin.teams.microsoft.com).

2. **Teams 디바이스** > **SIP 디바이스** 를 선택합니다. 

3. 오른쪽에서 다시 시작하려는 SIP 디바이스를 선택한 다음 다시 **시작을** 선택합니다.


> [!NOTE]
> - 테넌트에서 SIP 디바이스를 제거하는 것은 현재 Teams 관리 센터에서 사용할 수 없습니다. 
> - 명령 실행은 디바이스 가용성에 따라 달라지며 Teams 관리 센터에 표시된 실행 상태와 일치하지 않을 수 있습니다. SIP 게이트웨이를 지원하지 않는 디바이스에서 사용하도록 설정하려고 하면 명령이 실행되지 않습니다.

## <a name="sync-policy-changes-to-sip-devices-to-enforce-policies"></a>정책을 적용하기 위해 SIP 디바이스에 정책 변경 내용 동기화

사용자가 로그인하면 사용자 세부 정보 및 정책이 SIP 디바이스로 페치됩니다. 로그인한 사용자에 대한 정책 변경 내용은 1시간 이내에 디바이스에 동기화됩니다. 디바이스는 SIP 게이트웨이를 사용하여 등록을 주기적으로 새로 고쳐야 합니다. SIP 전화는 통화 리디렉션에 따라 달라지므로 관리자는 의 특성을 로 `Set-CsTeamsCallingPolicy` `Enabled`설정 `AllowCallRedirect` 해야 합니다.


## <a name="set-a-sip-devices-ui-language"></a>SIP 디바이스의 UI 언어 설정

SIP 디바이스는 일반적으로 여러 언어로 정보를 표시할 수 있습니다. UI 언어를 설정하면 소프트 키 및 로그인/로그아웃 시스템 메시지를 포함하여 인터페이스에 영향을 줍니다. UI 언어 설정은 프로비저닝 서버에서 수행되거나, DHCP 서버를 사용하거나, 다음 예제와 같이 URL에 코드 문자열을 수동으로 추가하여 수행됩니다.

Polycom, AudioCodes 및 Yealink 휴대폰용 독일어를 설정하는 방법:
- `http://emea.ipp.sdg.teams.microsoft.com/lang_de`

Cisco 휴대폰용 일본어 설정 방법:
- `http://emea.ipp.sdg.teams.microsoft.com/lang_ja/$PSN.xml` 


### <a name="supported-languages"></a>지원되는 언어

|언어 이름|언어 코드]
|-------------|-------------|
|영어(기본값)|En       |
|스페인어      |Es           |
|일본어     |Ja           |
|독일어       |드           |
|프랑스어       |Fr           |
|포르투갈어   |Pt           |

> [!Note]
> - 일본어 는 Yealink에서 지원되지 않으며 Polycom VVX에서 부분적으로 지원됩니다.
> - 선택한 언어가 SIP 엔드포인트에서 지원되지 않는 경우 시스템은 기본적으로 영어로 설정됩니다.
> - 프로비저닝 URL을 통해 **lang_xx** 매개 변수를 설정하지 않으면 영어가 기본 언어로 사용됩니다.
> - **긴급 통화 텍스트를 만들기 위해 로그인** 하는 경우 화면화 제한으로 인해 영어의 약어 버전이 다음 IP 전화 모델 **에서 로그인 누름** 에만 표시됩니다.
>   - Poly VVX 150, VVX 201
>   - Cisco CP-6821, CP-7811, CP-7821, CP-7841, CP-7861
>   - 음성 메일 소프트 키 레이블은 문자열 길이 제한으로 인해 Poly VVX의 모든 언어에서 **VM** 텍스트로 하드 코딩됩니다.

## <a name="microsoft-teams-and-ipv6"></a>Microsoft Teams 및 IPv6

SIP 게이트웨이는 IPv4만 지원합니다. Microsoft Teams 서비스 및 클라이언트는 IPv4 및 IPv6을 모두 지원합니다. Microsoft Teams에 대한 통신을 제어하려면 [Microsoft 365 URL 및 IP 주소 범위의 IP 주소 범위를](/microsoft-365/enterprise/urls-and-ip-address-ranges) 사용합니다.

## <a name="emergency-calling"></a>비상 전화

SIP Gateway는 네트워크를 통해 네트워크 특성을 공유하는 호환되는 SIP 디바이스에 대해 동적 긴급 통화(동적 E911)를 지원합니다. 이러한 특성은 Teams 관리 센터에서 프로비전되며 로컬 IP 및 서브넷 길이 또는 섀시 ID 및 네트워크 포트 번호의 조합일 수 있습니다. 위치 특성을 공유하지 않거나 어떤 이유로든 위치가 동적으로 확인되지 않는 디바이스의 경우 SIP Gateway는 등록된 주소를 기반으로 긴급 통화를 계속 지원합니다. 현재 등록된 주소는 직접 라우팅 시나리오에서 지원되지 않습니다. 긴급 통화에 대한 자세한 내용은 [긴급 통화 계획 및 관리를 참조하세요](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing).

## <a name="report-problems-to-microsoft"></a>Microsoft 문제 보고

문제를 보고하려면 [Microsoft 지원](https://support.microsoft.com) 문의하세요.
