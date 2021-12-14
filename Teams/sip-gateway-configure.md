---
title: SIP Gateway 구성
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/30/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: SIP Gateway를 구성하는 방법에 대해 자세히 알아보도록 합니다.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: a4548ab9abfd96b3945c19c07e08baf1ede05983
ms.sourcegitcommit: 1e83f2c1ed12bcb611eb4eb0a5f1f58496c63147
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/13/2021
ms.locfileid: "61426110"
---
# <a name="configure-sip-gateway"></a>SIP Gateway 구성

이 문서에서는 조직에서 호환되는 SIP 디바이스를 사용할 수 있도록 SIP Gateway를 구성하는 방법을 Microsoft Teams. 조직에 대해 SIP Gateway가 할 수 있는 일과 조직에 필요한 하드웨어, 소프트웨어 및 라이선스를 확인한 후 SIP Gateway 계획을 [읽어보아야 합니다.](sip-gateway-plan.md)

SIP Gateway를 구성하기 전에 다음을 실행합니다.

- **SIP 디바이스를 팩터리 기본 설정으로 다시 설정합니다.** 사용자 또는 조직의 사용자는 SIP Gateway와 함께 사용되는 각 SIP 디바이스를 해당 공장 기본 설정으로 다시 설정해야 합니다. 이 작업을 하는 방법을 확인한 경우 제조업체의 지침을 참조하세요.

- **방화벽을 열고 Microsoft 365 Teams.** URL 및 [IP](/microsoft-365/enterprise/urls-and-ip-address-ranges)주소 범위에 설명된 Microsoft 365 Teams 네트워크의 방화벽을 열고 트래픽을 Office 365 합니다.

- **SIP 디바이스가 프록시 뒤에 있지 않은지 확인합니다.** http/s 트래픽이 회사 http/s 프록시를 무시하는지 확인합니다.

- **UDP 포트를 를** 범위 49152에서 53247까지의 UDP 포트를 를 를 를 을 수 있습니다.

- **TCP 포트를 를 를** IP 범위 52.112.0.0/14~52.120.0.0/14의 경우 TCP 포트 5061을 를 를 갖습니다.

- **다음 https 엔드포인트(IP 주소 및 URL)를 갖습니다.**

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



다음 섹션에서는 SIP Gateway를 구성하기 위해 관리자로서 해야 하는 작업을 설명합니다.

- [조직에서 SIP Gateway를 사용할 수 있는지 확인](#verify-that-sip-gateway-is-available-for-your-organization)

- [조직의 사용자에 대해 SIP Gateway를 사용하도록 설정합니다.](#enable-sip-gateway-for-the-users-in-your-organization)

- [SIP Gateway 프로비전 서버 URL을 설정합니다.](#set-the-sip-gateway-provisioning-server-url)

이 문서에서는 또한 방법을 설명합니다.

- [편의를 위해 SIP 디바이스를](#provision-and-enroll-sip-devices-as-common-area-phones)개별적으로 또는 일괄 처리로 등록합니다.  


- [SIP 디바이스를 보고 모니터링합니다.](#view-and-monitor-sip-devices)

- [다국어 사용자 인터페이스에 대한 지원을 사용하도록 설정합니다.](#set-a-sip-devices-ui-language)

## <a name="verify-that-sip-gateway-is-available-for-your-organization"></a>조직에서 SIP Gateway를 사용할 수 있는지 확인

1. 관리 [센터에 Teams 로그인합니다.](https://admin-teams.microsoft.com/)

2. 왼쪽에서 **Teams** 디바이스 탭이 표시되는지 를 선택합니다.  이 경우 조직에 대해 SIP Gateway 서비스가 활성화됩니다.

## <a name="enable-sip-gateway-for-the-users-in-your-organization"></a>조직의 사용자에 대한 SIP Gateway 사용

조직에 대해 SIP Gateway를 사용하도록 설정하는 방법 중 Teams 관리 센터를 사용하거나 PowerShell cmdlet을 사용하여 설정할 수 있습니다.

### <a name="by-using-teams-admin-center"></a>관리 센터를 Teams 사용하여

관리 센터에서 SIP Gateway를 Teams 다음 단계를 수행합니다.

1. 관리 센터로 [Teams 이동](https://admin.teams.microsoft.com/)

2. 왼쪽의 **음성에서** 통화 **정책 을 선택합니다.**

3. 정책 관리 오른쪽에서 사용자에게 할당된 적절한 호출 정책을 선택하거나 필요한 경우 새 호출 정책을 만들고 필요한 사용자에게 할당합니다.

4. 정책 **관리를 선택하고** 정책을 선택한 다음 **편집을 선택합니다.**

5. **호출에 사용할 수 있는 SIP** 디바이스에 대한 설정을 켜고 저장을 **선택합니다.**


### <a name="by-using-powershell"></a>PowerShell을 사용하여

PowerShell [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps) cmdlet을 사용하여 SIP Gateway를 사용하도록 설정할 수도 있습니다. SIP 디바이스에 대해 사용자를 사용하도록 설정하려면 정책을 선택하고 특성을 `-AllowSIPDevicesCalling` `True` 으로 설정합니다. 기본값은 입니다. 따라서 사용자가 SIP 디바이스를 사용하도록 설정하지 않으면 `False` SIP 디바이스를 사용할 수 없습니다.


> [!NOTE]
> - 정책 전파에는 최대 24시간이 걸릴 수 있습니다.

## <a name="set-the-sip-gateway-provisioning-server-url"></a>SIP Gateway 프로비전 서버 URL 설정

DHCP(동적 호스트 구성 프로토콜) 서버에서 SIP Gateway 프로비전 서버의 URL을 설정할 수 있습니다. 원격으로 작업하는 사용자는 수동으로 구성해야 합니다.

### <a name="using-dhcp"></a>DHCP 사용

각 SIP 디바이스에 대해 다음 SIP Gateway 프로비전 서버 URL 중 하나를 설정합니다. 

- EMEA: `http://emea.ipp.sdg.teams.microsoft.com`
- 아메리카: `http://noam.ipp.sdg.teams.microsoft.com`
- APAC: `http://apac.ipp.sdg.teams.microsoft.com`

DHCP 서버에서 위의 SIP Gateway 프로비전 서버 URL을 Teams 조직에 SIP 디바이스를 추가합니다. DHCP 서버에 대한 자세한 내용은 [DHCP](/learn/modules/deploy-manage-dynamic-host-configuration-protocol)배포 및 관리를 참조합니다. 또한 DHCP 옵션 42를 사용하여 NTP(네트워크 시간 프로토콜) 서버 및 DHCP 옵션 2를 지정하여 조정된 유니버설 시간(UTC)에서 오프셋을 몇 초 만에 지정할 수 있습니다. 조직의 디바이스는 SIP Gateway 프로비전 서버로 라우팅됩니다. 성공적으로 프로비전된 SIP 휴대폰에는 로그인에 Teams 로고와 부드러운 단추가 표시됩니다.

SIP 디바이스가 온보드에 지원되는 최소 펌웨어 버전에 있는지 확인합니다. 온보드하는 동안 SIP Gateway는 기본 구성 및 인증 사용자 인터페이스를 디바이스에 푸시합니다. SIP 디바이스에 필요한 펌웨어 버전을 확인하려면 SIP Gateway 계획 [을 참조합니다.](sip-gateway-plan.md)

### <a name="manually"></a>수동으로

원격으로 작업하는 사용자는 다음 단계를 사용하여 프로비전 서버 URL을 자신의 SIP 디바이스로 수동으로 구성해야 합니다.

1. 장치에서 **설정** 열고 디바이스의 IP 주소를 갖습니다.

2. 브라우저 창을 열고 디바이스의 IP 주소를 입력하고, 로그인(필요한 경우) 디바이스의 웹 유틸리티에서 프로비전 서버의 URL을 구성합니다.

3. 웹 설정 또는 **고급** 설정에서 위에 **표시된** 프로비전 서버 URL을 입력합니다.

> [!NOTE]
> - 호환되는 SIP 디바이스만 SIP Gateway에 온보드할 수 있습니다. 
> - Cisco IP 휴대폰은 온보드되기 전에 다중 플래트폼 펌웨어로 깜박임해야 합니다. 방법에 대한 자세한 내용은 [Cisco 펌웨어 변환 가이드 를 참조하세요.](https://www.cisco.com/c/en/us/products/collateral/collaboration-endpoints/unified-ip-phone-7800-series/guide-c07-742786.html)
> - Yealink 휴대폰의 경우 옵션 66을 사용합니다.
> - Cisco, Poly 및 AudioCode 휴대폰의 경우 옵션 160을 사용합니다. 
> - Cisco 디바이스의 경우 **/$** PSN.xml서버 URL에 추가합니다.


## <a name="configure-conditional-access"></a>조건부 액세스 구성

조건부 액세스는 azure AD(Azure Active Directory) 기능으로, 리소스에 액세스하는 디바이스가 Microsoft 365 올바르게 관리되고 안전하도록 하는 데 도움이 됩니다. SIP Gateway는 Azure AD를 사용하여 SIP 디바이스를 인증하기 때문에 조직에서 회사 네트워크의 디바이스에 대한 조건부 액세스를 사용하는 경우 다음 IP 주소를 제외해야 합니다.

- 북아메리카:
    - 미국 동부: 52.170.38.140
    - 미국 서부: 40.112.144.212
-   EMEA 지역:
    - EU 북부: 40.112.71.149
    - 유럽 서부: 40.113.112.67
-   APAC 지역:
    - 오스트레일리아 동부: 20.92.120.71
    - 오스트레일리아 남동부: 13.73.115.90

자세한 내용은 [IP 주소 범위 를 참조하세요.](/azure/active-directory/conditional-access/location-condition#ip-address-ranges)


## <a name="provision-and-enroll-sip-devices-as-common-area-phones"></a>SIP 디바이스를 공용 영역 휴대폰으로 프로비전 및 등록
> [!NOTE]
> SIP 디바이스를 등록하기 전에 SIP Gateway에 온보드되어야 합니다.

작업을 간소화하려면 한 Teams 관리 센터에 SIP 디바이스를 등록할 수 있습니다. 방법은 다음과 같습니다.

1. Teams 관리 센터에 [**로그인합니다.**](https://admin.teams.microsoft.com)

2. SIP **Teams**  >  **디바이스를 선택합니다.**

3. 오른쪽 위에서 **작업 프로비전** 디바이스를 선택하고 다음 단계 중 하나를  >   따릅니다.

  - **하나의 디바이스를 프로비전하려면:**

     a. 활성화 **대기 중 에서** **추가를 선택합니다.**

     b. MAC 주소 **추가 창에서** **디바이스의 MAC 주소** 및 위치를 입력한 다음 적용을  **선택합니다.**
     
     c. 정품 **인증 대기에서** 방금 추가한 디바이스를 선택한 다음 확인 **코드 생성을 선택합니다.**
     
     d. **프로비전 디바이스** 창의 확인 **코드** 아래에서 SIP 디바이스에 대한 확인 코드를 확인합니다.

   - **여러 디바이스를 프로비전하는 경우:**

     a. 활성화 **대기 중** 에서 오른쪽에서  내보내기(Microsoft Excel 아이콘)를 선택합니다.
     
     b. **프로비전** 디바이스 창의 여러 MAC 업로드 아래에서 템플릿 **다운로드를** **선택합니다.**
     
     c. 컴퓨터에 **Template_Provisioning.csv** **MAC ID** 및 위치 필드를 **입력합니다.**
    
     d. **프로비전 디바이스** 창에서 여러 **MAC 업로드 선택합니다.** 

     e. MAC 주소 업로드  창의 오른쪽에서 파일 선택을 선택하고 데이터가Template_Provisioning.csv 파일을 선택합니다. 

     f. 프로비전 디바이스 창의 정품 인증 대기 중에서  디바이스를 선택한 다음 확인 코드 생성을 선택하여 프로비전된 각 디바이스에 대해 일회성 확인 코드를 생성합니다.  각 SIP 디바이스에 대한 확인 코드를 확인합니다.

4. SIP 디바이스에서 등록 기능 코드에 전화를 걸고 확인 코드에 연결합니다. SIP 디바이스에서 등록 기능 코드 55*(등록 일회성 인증 코드 유효성 검사에 SIP Gateway에서 사용)를 다이얼한 다음, 이 특정 디바이스에 대한 관리 센터에서 Teams 인증 코드로 전화를 \* 니다. 예를 들어 확인 코드가 123456 경우 \* 55 123456 \* 디바이스를 등록합니다.

5.  **프로비전 디바이스** 창의 로그인 대기 중 **에서** 로그인 **을 선택합니다.**

6. 사용자 로그인 **대화** 상자에서 SIP 디바이스의 페어링 코드를 복사하거나 메모합니다.

7. [https://microsoft.com/devicelogin](https://microsoft.com/devicelogin)으로 이동하고 코드 **입력에서** SIP 디바이스의 페어링 코드를 입력한 다음 다음을 **선택합니다.**

8. Microsoft **로그인** 페이지에서 전자 메일  또는 전화 필드에 SIP 디바이스의 전자 메일 주소를 입력한 다음 다음을 **선택합니다.**

9. 암호 **페이지에서** SIP 디바이스의 전자 메일 주소에 대한 암호를 입력한 다음 로그인 **을 선택합니다.**

10. SIP 디바이스 게이트웨이에 로그인하려고 **Teams** 에서 계속을 **선택합니다.**

## <a name="how-to-sign-in-and-sign-out"></a>로그인하고 로그인하는 방법

로컬 로그인만 사용자의 개인 디바이스에 대해 지원됩니다. 관리 센터에서 디바이스를 로그인하려면 다음 단계를 수행합니다.

1. Teams 관리 센터에 [**로그인합니다.**](https://admin.teams.microsoft.com)

2. SIP **Teams**  >  **디바이스를 선택합니다.**

3. 오른쪽에서 SIP 디바이스를 선택한 다음, 로그인 **을 선택합니다.**


### <a name="user-pairing-and-sign-in"></a>사용자 페어링 및 로그인

사용자가 회사 자격 증명을 사용하여 인증한 후 SIP 디바이스를 페어링하려면 다음을 해야 합니다.

1. SIP **휴대폰에서** 로그인을 눌러 인증 URL 및 페어링 코드를 표시합니다. 페어링 코드는 시간이 민감합니다. 만료되면 사용자가 휴대폰에서 **Back을** 누르고 로그인 프로세스를 다시 시작해야 합니다.

2. 사용자의 데스크톱 또는 모바일 브라우저에서 인증 URL로 이동하고 회사 자격 증명을 사용하여 로그인합니다.

3. SIP 휴대폰에 표시된 페어링 코드를 웹 인증 앱에 입력하여 SIP 휴대폰을 사용자의 계정과 페어링합니다. 로그인에 성공하면 시간이 걸릴 수 있습니다. SIP 전화는 디바이스에서 지원하는 경우 전화 번호와 사용자 이름을 표시합니다.

> [!NOTE]
> 웹 인증 앱에 표시된 Azure Active Directory 위치는 디바이스가 연결된 SIP Gateway 데이터 센터입니다. 범위의 SIP 휴대폰은 OAuth를 사용할 수 없습니다. 따라서 SIP Gateway는 웹 인증 앱을 통해 사용자를 인증한 다음 디바이스를 사용자의 자격 증명과 페어링합니다. 자세한 내용은 Microsoft ID 플랫폼 [및 OAuth 2.0 디바이스](/azure/active-directory/develop/v2-oauth2-device-code)권한 부여 흐름 에 대해 자세히 알아보십시오.

### <a name="sign-out"></a>로그인

로그인하려면 디바이스 사용자가 다음을 할 수 있습니다.

- SIP **디바이스에서 Sign-Out을** 누르고 디바이스에 설명된 단계를 따릅니다. 

관리 센터에서 디바이스를 Teams:

1. Teams 관리 센터에 [**로그인합니다.**](https://admin.teams.microsoft.com)

2. SIP **Teams**  >  **디바이스를 선택합니다.**

3. 오른쪽의 **SIP 디바이스** 창에서 디바이스를 선택합니다.

4. 디바이스의 세부 정보 창에서 세부  정보 탭을 선택하고 작업 메뉴의  오른쪽 위에 있는 로그인 **을 선택합니다.** 


## <a name="view-and-monitor-sip-devices"></a>SIP 디바이스 보기 및 모니터링

디바이스의 사용자가 적어도 한 번 로그인한 후 Teams 관리 센터에서 SIP 디바이스 인벤토리를 보고 모니터링할 수 있습니다. 방법은 다음과 같습니다.

1. Teams 관리 센터에 [로그인합니다.](https://admin.teams.microsoft.com/)

2. SIP **Teams**  >  **디바이스를 선택합니다.** 모든 로그인 SIP 디바이스가 오른쪽에 나열됩니다.

## <a name="restart-a-sip-device"></a>SIP 디바이스 다시 시작

1. Teams 관리 센터에 [로그인합니다.](https://admin.teams.microsoft.com)

2. SIP **Teams**  >  **디바이스를 선택합니다.** 

3. 오른쪽에서 다시 시작할 SIP 디바이스를 선택한 다음 다시 **시작을 선택합니다.**

## <a name="sync-policy-changes-to-sip-devices-to-enforce-policies"></a>정책 적용을 위해 SIP 디바이스에 정책 변경 내용을 동기화합니다.

사용자가 로그인할 때 사용자 세부 정보 및 정책이 SIP 디바이스로 페치됩니다. 로그인한 사용자에 대한 정책 변경은 1시간 이내에 디바이스에 동기화됩니다. 디바이스는 SIP Gateway를 통해 정기적으로 등록을 새로 고쳐야 합니다. SIP 휴대폰은 통화 리디렉션에 따라 달라지기 때문에 관리자는 에서 특성을 `AllowCallRedirect` 으로 설정해야 `Set-CsTeamsCallingPolicy` `Enabled` 합니다.


## <a name="set-a-sip-devices-ui-language"></a>SIP 디바이스의 UI 언어 설정

SIP 디바이스는 일반적으로 많은 언어로 정보를 표시할 수 있습니다. UI 언어를 설정하면 소프트키 및 로그인/로그인 시스템 메시지를 포함하여 인터페이스에 영향을 미치게 됩니다. UI 언어 설정은 다음 예제와 같이 DHCP 서버를 사용하여 프로비전 서버에서 수행되거나 URL에 코드 문자열을 추가하여 수동으로 수행됩니다.

Polycom, AudioCodes 및 Yealink 휴대폰에 대해 독일어를 설정하는 방법:
- `http://emea.ipp.sdg.teams.microsoft.com/lang_de`

Cisco 휴대폰에 일본어를 설정하는 방법:
- `http://emea.ipp.sdg.teams.microsoft.com/lang_ja/$PSN.xml` 


### <a name="supported-languages"></a>지원되는 언어

|언어 이름|언어 코드]
|-------------|-------------|
|영어(기본값)|en       |
|스페인어      |es           |
|일본어     |ja           |
|독일어       |de           |
|프랑스어       |fr           |
|포르투갈어   |pt           |

> [!Note]
> - 일본어는 Yealink에서 지원되지 않습니다. Polycom VVX에서 부분적으로 지원됩니다.
> - 선택한 언어가 SIP 엔드포인트에서 지원되지 않는 경우 시스템은 기본적으로 영어로 제공됩니다.
> - **프로비전 URL을 통해** lang_xx 매개 변수가 설정되지 않은 경우 영어가 기본 언어로 사용됩니다.
> - 긴급  통화 텍스트를 다른 언어로 번역하지 않는 경우 화면의 제한으로 인해 다음 IP 전화 모델의 로그인 눌러에서만 영어로 약어 버전이 표시됩니다. 
>   - Poly VVX 150, VVX 201
>   - Cisco CP-6821, CP-7811, CP-7821, CP-7841, CP-7861
>   - 음성 메일 소프트키 레이블은 문자열 길이의 제한으로 인하여 Poly VVX의 모든 언어에서 **VM** 텍스트로 하드코딩됩니다.

## <a name="microsoft-teams-and-ipv6"></a>Microsoft Teams 및 IPv6

SIP Gateway는 IPv4만 지원합니다. Microsoft Teams 및 클라이언트는 IPv4 및 IPv6을 모두 지원합니다. 통신을 제어하려는 Microsoft Teams URL 및 IP 주소 범위의 IP Microsoft 365 [사용하세요.](/microsoft-365/enterprise/urls-and-ip-address-ranges)

## <a name="emergency-calling"></a>비상 전화

SIP Gateway는 정적(등록된 주소라고도 하는 긴급 주소)만 지원합니다. 현재 직접 라우팅 시나리오에서는 등록된 주소가 지원되지 않습니다. 긴급 통화에 대한 자세한 내용은 긴급 통화 계획 [및 관리를 참조하세요.](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)

## <a name="report-problems-to-microsoft"></a>Microsoft에 문제 보고

문제를 보고하기 위해 [Microsoft 지원 에 문의합니다.](https://support.microsoft.com)
