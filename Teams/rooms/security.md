---
title: Microsoft Teams 회의실 보안
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: sohailta
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Microsoft Teams 회의실 장치를 보호하는 방법을 배워야 합니다.
ms.openlocfilehash: d9968af4f386ed68d9a931d834082ba5362c5c33
ms.sourcegitcommit: 380cd74c08cd34e1c3f73f5c0f51da4ae2674f6f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2021
ms.locfileid: "49880880"
---
# <a name="microsoft-teams-rooms-security"></a>Microsoft Teams 회의실 보안

Microsoft는 파트너와 협력하여 Microsoft Teams 회의실을 보호하는 추가 작업이 필요하지 않은 안전한 솔루션을 제공합니다. 이 문서에서는 Teams 회의실에 있는 많은 보안 기능에 대해 논의합니다.

> [!NOTE]
> Microsoft Teams 회의실은 일반적인 최종 사용자 작업 공간처럼 취급하면 안 됩니다. 사용 사례는 크게 다를 뿐 아니라 기본 보안 프로필도 훨씬 다릅니다.

제한된 최종 사용자 데이터는 Teams 회의실에 저장됩니다. 최종 사용자 데이터는 문제 해결 및 지원 전용 로그 파일에 저장될 수 있습니다. Teams 회의실을 사용하는 모임 참석자도 파일을 하드 드라이브에 복사하거나 직접 로그인할 수 있습니다. 최종 사용자 데이터는 Microsoft Teams 회의실 디바이스로 전송되거나 액세스할 수 없습니다.

최종 사용자가 Teams 회의실 하드 드라이브에 파일을 넣을 수 없는 경우에도 Microsoft Defender는 계속 사용할 수 있습니다. Teams 회의실 성능은 Microsoft Defender를 통해 테스트됩니다. 이 기능을 사용 안 하거나 엔드포인트 보안 소프트웨어를 추가하면 예측할 수 없는 결과가 발생하고 시스템 성능이 저하될 수 있습니다.

## <a name="hardware-security"></a>하드웨어 보안

Teams 회의실 환경에는 Windows 10 IoT Enterprise Edition을 실행하는 중앙 컴퓨팅 모듈이 있습니다. 인증된 모든 컴퓨팅 모듈에는 보안 탑재 솔루션, 보안 잠금 슬롯(예: Kensington Lock) 및 I/O 포트 액세스 보안 조치가 있어야 권한이 없는 디바이스의 연결을 방지할 수 있습니다. UEFI(Unified Extensible Firmware Interface) 구성을 통해 특정 포트를 사용하지 않도록 설정할 수도 있습니다.

모든 인증된 컴퓨팅 모듈은 기본적으로 사용하도록 설정된 TPM(신뢰할 수 있는 플랫폼 모듈) 2.0 규격 기술과 함께 제공되어야 합니다. TPM은 Teams 회의실 리소스 계정에 대한 로그인 정보를 암호화하는 데 사용됩니다.

보안 부팅은 기본적으로 사용하도록 설정되어 있습니다. 보안 부팅은 OEM(원래 장비 제조업체)에서 신뢰할 수 있는 소프트웨어만 사용하여 디바이스가 부팅하는지 확인하기 위해 PC 업계의 구성원이 개발한 보안 표준입니다. PC가 시작되면 펌웨어는 UEFI 펌웨어 드라이버(옵션 ROM이라고도 하는), EFI 애플리케이션 및 운영 체제를 포함하여 부팅 소프트웨어의 각 조각의 서명을 검사합니다. 서명이 유효하면 PC가 부팅하고 펌웨어가 운영 체제에 대한 제어를 제공합니다. 자세한 내용은 보안 [부팅을 참조하세요.](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot)

UEFI 설정에 대한 액세스는 물리적 키보드와 마우스를 연결해야만 가능합니다. 이렇게 하면 Teams 회의실 터치 사용 콘솔뿐만 아니라 Teams 회의실에 연결된 다른 터치 가능 디스플레이를 통해 UEFI에 액세스할 수 없습니다.

커널 DMA(직접 메모리 액세스) 보호는 Teams 회의실에서 사용하도록 설정된 Windows 10 설정입니다. 이 기능을 사용하여 OS 및 시스템 펌웨어는 모든 DMA 지원 디바이스에 대한 악성 및 의도하지 않은 DMA 공격으로부터 시스템을 보호합니다.

- 부팅 프로세스 중에.

- OS 런타임 중에 M.2 PCIe 슬롯 및 Thunderbolt 3과 같은 내부/외부 DMA 지원 포트에 쉽게 액세스할 수 있도록 연결된 디바이스의 악성 DMA에 대해.

Teams 회의실을 사용하면 HVCI(하이퍼바이서로 보호된 코드 무결성)도 사용할 수 있습니다. HVCI에서 제공하는 기능 중 하나는 Credential Guard입니다. Credential Guard는 다음과 같은 이점을 제공합니다.

- **하드웨어 보안** NTLM, Kerberos 및 Credential Manager는 보안 부팅 및 가상화를 비롯한 플랫폼 보안 기능을 사용하여 자격 증명을 보호합니다.

- **가상화 기반 보안** Windows NTLM 및 Kerberos 파생 자격 증명 및 기타 비밀은 실행 중인 운영 체제와 격리된 보호된 환경에서 실행됩니다.

- **고급 영구적 위협으로부터 향상된 보호** 자격 증명 관리자 도메인 자격 증명, NTLM 및 Kerberos 파생 자격 증명이 가상화 기반 보안을 사용하여 보호되는 경우 다수의 대상 공격에 사용되는 자격 증명 도난 공격 기술 및 도구가 차단됩니다. 관리 권한으로 운영 체제에서 실행되는 맬웨어는 가상화 기반 보안으로 보호되는 비밀을 추출할 수 없습니다.

## <a name="software-security"></a>소프트웨어 보안

Microsoft Windows가 부팅된 후 Teams 회의실은 Skype라는 로컬 Windows 사용자 계정에 자동으로 로그인됩니다. Skype 계정에 암호가 없습니다. Skype 계정 세션을 안전하게 보호하려면 다음 단계를 수행합니다.

> [!IMPORTANT]
> 암호를 변경하거나 로컬 Skype 사용자 계정을 편집하지 않습니다. 이렇게 하면 Teams 회의실이 자동으로 로그인되지 않도록 할 수 있습니다.

Microsoft Teams 회의실 앱은 Windows 10 1903 이상에서 찾은 할당된 액세스 기능을 사용하여 실행됩니다. 할당된 액세스는 사용자에게 노출되는 애플리케이션 진입점을 제한하는 Windows 10의 기능입니다. 이를 통해 단일 앱 키오스크 모드를 사용할 수 있습니다. 셸 시작 프로그램을 사용하여 Teams 회의실은 Windows 데스크톱 애플리케이션을 사용자 인터페이스로 실행되는 키오스크 디바이스로 구성됩니다. Microsoft Teams 회의실 앱은 사용자가 로그온할 때 일반적으로 explorer.exe 기본 셸(explorer.exe)을 대체합니다. 즉, 기존 탐색기 셸은 시작되지 않습니다. 이렇게 하면 Windows 내에서 Microsoft Teams 회의실 취약성 표면이 크게 감소합니다. 자세한 내용은 Windows 데스크톱 버전에서 키오스크 및 디지털 [기호 구성을 참조하세요.](https://docs.microsoft.com/windows/configuration/kiosk-methods)

Teams 회의실에서 보안 검사 또는 CIS(인터넷 보안 센터) 벤치마크를 실행하기로 결정한 경우 Skype 사용자 계정이 Teams 회의실 앱 외의 응용 프로그램 실행을 지원하지 않는 경우 로컬 관리자 계정의 컨텍스트에서만 검사가 실행될 수 있습니다. Skype 사용자 컨텍스트에 적용된 대부분의 보안 기능은 다른 로컬 사용자에게 적용되지 않습니다. 따라서 이러한 보안 검사는 Skype 계정에 적용되는 전체 보안 잠금을 표면화하지 않습니다. 따라서 Teams 회의실에서 로컬 검색을 실행하지 않는 것이 좋습니다. 그러나 원하는 경우 외부 침투 테스트를 실행할 수 있습니다. 이 때문에 로컬 검사를 실행하는 대신 Teams Rooms 디바이스에 대해 외부 침투 테스트를 실행하는 것이 좋습니다.

또한 관리되지 않는 기능이 사용되지 못하게 제한하기 위해 잠금 정책이 적용됩니다. 키보드 필터는 할당된 액세스 정책에서 다루지 않는 잠재적으로 불안정한 키보드 조합을 가로채고 차단할 수 있습니다. 로컬 또는 도메인 관리 권한을 가지는 사용자만 Windows에 로그인하여 Teams 회의실을 관리할 수 있습니다. Microsoft Teams 회의실 장치에서 Windows에 적용되는 이러한 정책 및 기타 정책은 제품 수명 주기 동안 지속적으로 평가 및 테스트됩니다.

## <a name="account-security"></a>계정 보안

Teams 회의실 장치에는 기본 암호가 있는 "Admin"이라는 관리 계정이 포함됩니다. 설정을 완료한 후 가능한 한 빨리 기본 암호를 변경하는 것이 좋습니다.

Teams 회의실 장치를 제대로 작동하기 위해 관리자 계정이 필요하지는 않습니다. 이름을 변경하거나 삭제할 수도 있습니다. 그러나 관리자 계정을 삭제하기 전에 Teams 회의실 장치와 함께 배송되는 계정을 제거하기 전에 구성된 대체 로컬 관리자 계정을 설정해야 합니다. 기본 제공 Windows 도구 또는 PowerShell을 사용하여 로컬 Windows 계정의 암호를 변경하는 방법에 대한 자세한 내용은 다음을 참조하세요.

- [Windows 암호 변경 또는 재설정](https://support.microsoft.com/windows/change-or-reset-your-windows-password-8271d17c-9f9e-443f-835a-8318c8f68b9c)
- [Set-LocalUser](https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/set-localuser?view=powershell-5.1#example-2--change-the-password-on-an-account)

도메인 계정을 로컬 Windows 관리자 그룹으로 가져올 수도 있습니다. Intune을 사용하여 Azure AD 계정에 대해 이 작업을 할 수 있습니다. 자세한 내용은 [정책 CSP – RestrictedGroups를 참조하세요.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-restrictedgroups)

> [!CAUTION]
> 다른 로컬 또는 도메인 계정에 로컬 관리자 권한을 부여하기 전에 관리자 계정을 삭제하거나 사용하지 않도록 설정하면 Teams 회의실 장치를 관리하는 기능을 잃을 수 있습니다. 이 경우 디바이스를 원래 설정으로 다시 설정하고 설정 프로세스를 다시 완료해야 합니다.
>
> Skype 사용자 계정에 로컬 관리자 권한을 부여하지 않습니다.

Windows 구성 디자이너를 사용하여 Windows 10 프로비전 패키지를 만들 수 있습니다. 로컬 관리자 암호를 변경하는 것과 함께 컴퓨터 이름을 변경하고 Azure Active Directory에 등록하는 등 작업을 할 수도 있습니다. Windows 구성 디자이너 프로비전 패키지 만들기에 대한 자세한 내용은 Windows 10용 프로비전 [패키지를 참조하세요.](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages)

Teams에 로그인할 수 있도록 각 Teams 회의실 장치에 대한 리소스 계정을 만들어야 합니다. 이 계정에서는 2단계 또는 다단계 인증을 사용할 수 없습니다. 두 번째 요소를 요구하면 계정이 재부팅 후 Teams 회의실 앱에 자동으로 로그인하지 못하게 됩니다. 그러나 이 계정에 대한 추가 보안을 위해 최신 인증을 사용하도록 설정할 수 있습니다. 또한 리소스 계정에 대해 위치 기반 조건부 액세스 정책을 배포하여 승인되지 않은 위치에서 계정에 로그인하지 못하게 할 수 있습니다. 자세한 내용은 조건부 액세스 정책에서 위치 조건 [사용 참조](https://docs.microsoft.com/azure/active-directory/conditional-access/location-condition)

가능한 경우 Azure AD에서 리소스 계정을 만드는 것이 좋습니다. 동기화된 계정은 하이브리드 배포에서 Teams 회의실과 함께 작동할 수 있는 반면 이러한 동기화된 계정은 Teams 회의실에 로그인하는 데 어려움이 있으며 문제 해결이 어려울 수 있습니다. 타사 페더전 서비스를 사용하여 리소스 계정에 대한 자격 증명을 인증하도록 선택한 경우 타사 IDP가 특성으로 `wsTrustResponse` 응답하는지 확인 `urn:oasis:names:tc:SAML:1.0:assertion`

## <a name="network-security"></a>네트워크 보안

일반적으로 Teams 회의실에는 Microsoft Teams 클라이언트와 동일한 네트워크 요구 사항이 있습니다. 방화벽 및 기타 보안 장치를 통한 액세스는 Teams 회의실의 경우 다른 Microsoft Teams 클라이언트와 동일합니다. Teams 회의실과 관련되어 있으며, Teams에 대해 "필수"로 나열된 범주는 방화벽에서 열려 있어야 합니다. Teams 회의실은 Windows 업데이트, Microsoft Store 및 Microsoft Intune에 대한 액세스도 필요합니다(Microsoft Intune을 사용하여 장치를 관리하는 경우). Microsoft Teams 회의실에 필요한 전체 IPS 및 URL 목록은 다음을 참조하세요.

- **Microsoft Teams** [Office 365 URL 및 IP 주소 범위](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide#skype-for-business-online-and-microsoft-teams)
- **Windows 업데이트** [WSUS 구성](https://docs.microsoft.com/windows-server/administration/windows-server-update-services/deploy/2-configure-wsus#211-connection-from-the-wsus-server-to-the-internet)
- **비즈니스** 및 교육용 Microsoft Store에 대한 [Microsoft Store의 전제적 준비](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business#proxy-configuration)
- **Microsoft Intune용 Microsoft Intune** [네트워크 Enpoints](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)

Microsoft Teams Rooms Premium의 Microsoft Teams Rooms 관리 서비스 구성 요소를 사용하는 경우 Teams 회의실이 다음 URL에 액세스할 수 있는지도 확인해야 합니다.

- global.azure-devices-provisioning.net
- gj3ftstorage.blob.core.windows.net
- gj3ft-hub.azure-devices.net
- iothubsgagwt5wgvwg6.azure-devices.net
- blobssgagwt5wgvwg6.blob.core.windows.net
- prod-48.westus.logic.azure.com
- prod-08.westus.logic.azure.com
- prod-62.westus.logic.azure.com
- prod-65.westus.logic.azure.com
- prod-05.westus.logic.azure.com

Teams 회의실은 보안 업데이트를 포함하여 최신 Windows 업데이트에 자동으로 패치를 적용하도록 구성됩니다. Teams 회의실은 미리 설정된 로컬 정책을 사용하여 매일 오전 2시부터 보류 중인 업데이트를 설치합니다. Windows 업데이트를 배포하고 적용하는 데 추가 도구를 사용할 필요가 없습니다. 추가 도구를 사용하여 업데이트를 배포하고 적용하면 Windows 패치 설치가 지연될 수 있으며 따라서 배포가 덜 안전하지 않습니다. Teams Rooms 앱은 Microsoft Store를 사용하여 배포됩니다. 디바이스에 Microsoft Teams Rooms Standard 라이선스가 있는 경우 새 버전의 앱이 야간 패치 프로세스 중에 자동으로 설치됩니다. 디바이스에 Microsoft Teams Rooms Premium 라이선스가 부여되고 Microsoft Managed Service에 등록된 경우 정의된 롤아웃 계획에 따라 새 버전의 Teams Rooms 앱이 설치됩니다.

Teams Rooms 디바이스는 대부분의 802.1X 또는 기타 네트워크 기반 보안 프로토콜에서 작동합니다. 그러나 가능한 모든 네트워크 보안 구성에 대해 Teams 회의실을 테스트할 수 없습니다. 따라서 네트워크 성능 문제로 추적할 수 있는 성능 문제가 발생하는 경우 조직에서 구성한 경우 이러한 프로토콜을 사용하지 않도록 설정해야 할 수 있습니다.

실시간 미디어의 최적의 성능을 위해 프록시 서버 및 기타 네트워크 보안 디바이스를 우회하도록 Teams 미디어 트래픽을 구성하는 것이 좋습니다. 실시간 미디어는 대기 시간이 매우 길고 프록시 서버와 네트워크 보안 디바이스는 사용자의 비디오 및 오디오 품질을 크게 저하할 수 있습니다. 또한 Teams 미디어가 이미 암호화되어 있기 때문에 프록시 서버를 통해 트래픽을 전달할 경우 어떤 이점도 없습니다. 자세한 내용은 Microsoft [](https://docs.microsoft.com/microsoft-365/solutions/networking-design-principles?view=o365-worldwide) Teams 및 Microsoft Teams 회의실을 통해 미디어의 성능을 개선하기 위한 네트워크 권장 사항을 설명하는 설계자 관점인 클라우드에 대한 네트워킹을 참조하세요.

> [!IMPORTANT]
> Teams 회의실은 인증된 프록시 서버를 지원하지 않습니다.

Teams 회의실 장치는 내부 LAN에 연결할 필요가 없습니다. 직접 인터넷에 액세스할 수 있는 안전한 네트워크 세그먼트에 Teams 회의실을 배치하는 것이 좋은지 고려합니다. 내부 LAN이 손상되면 Teams 회의실에 대한 공격 벡터 기회가 감소합니다.

Teams 회의실 장치를 유선 네트워크에 연결하는 것이 좋습니다. Teams Rooms 장치에서 무선 네트워크를 사용하는 것은 권장되거나 인증되지 않습니다. Wi-Fi Sense와 같은 일부 연결 기능은 기본적으로 사용하지 않도록 설정됩니다.

근접 참가 및 기타 Teams 회의실 기능은 이 기능을 Bluetooth. 그러나 Teams Bluetooth 디바이스의 네트워크 구현은 Teams 회의실 장치에 대한 외부 장치 연결을 허용하지 않습니다. Bluetooth 기술 사용은 현재 광고 표시 장치 및 프롬프트된 프롬프트된 기본 연결로 제한됩니다. `ADV_NONCONN_INT`PDU(프로토콜 데이터 단위) 형식은 광고 비콘에 사용됩니다. 이 PDU 유형은 수신 장치에 정보를 광고하는 연결할 수 없는 디바이스용입니다. 이러한 기능의 일부로 Bluetooth 디바이스 페어링은 없습니다. Bluetooth 프로토콜에 대한 자세한 내용은 Bluetooth SIG 웹 사이트에서 [확인할 수 있습니다.](https://www.bluetooth.com/blog/bluetooth-low-energy-it-starts-with-advertising/)
