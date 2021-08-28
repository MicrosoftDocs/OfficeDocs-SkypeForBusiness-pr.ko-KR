---
title: Microsoft Teams 룸 보안
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
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
description: 디바이스를 보호하는 Microsoft Teams 룸 대해 자세히 알아보습니다.
ms.openlocfilehash: d3b0f244f36ed30376fbe72e9669b6f84f9f9629
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58627290"
---
# <a name="microsoft-teams-rooms-security"></a>Microsoft Teams 룸 보안

Microsoft는 파트너와 협력하여 보안이 유지되는 솔루션을 제공하며 보안 유지를 위해 추가 작업이 필요하지 Microsoft Teams 룸. 이 문서에서는 여러 보안 기능에 대해 Teams 룸.

> [!NOTE]
> Microsoft Teams 룸 일반적인 최종 사용자 작업대와 같이 처리하면 안 됩니다. 사용 사례는 크게 다르지만 기본 보안 프로필도 훨씬 다릅니다.
> 이 문서는 Microsoft Teams 룸 실행 중인 디바이스에 Windows.

제한된 최종 사용자 데이터는 사용자에 Teams 룸. 최종 사용자 데이터는 문제 해결 및 지원 전용 로그 파일에 저장될 수 있습니다. 어떤 시점에서도 하드 드라이브에 파일을 복사하거나 Teams 룸 자체로 로그인하는 방법을 사용하여 모임의 참석자도 할 수 없습니다. 최종 사용자 데이터는 디바이스에 전송되거나 액세스하지 Microsoft Teams 룸 없습니다.

최종 사용자가 하드 드라이브에 파일을 넣을 수 Teams 룸 Microsoft Defender는 여전히 사용하도록 설정되어 있습니다. Teams 룸 성능은 Microsoft Defender에서 테스트됩니다. 이 기능을 사용 안 하거나 엔드포인트 보안 소프트웨어를 추가하면 예측할 수 없는 결과가 발생하고 시스템 성능이 저하될 수 있습니다.

## <a name="hardware-security"></a>하드웨어 보안

이 Teams 룸 버전에서 실행되는 중앙 계산 모듈이 Windows 10 IoT Enterprise 있습니다. 인증된 모든 계산 모듈에는 보안 탑재 솔루션, 보안 잠금 슬롯(예: Kensington Lock), 인증되지 않은 디바이스의 연결을 방지하기 위한 I/O 포트 액세스 보안 조치가 있어야 합니다. UEFI(통합된 Extensible 펌웨어 인터페이스) 구성을 통해 특정 포트를 사용하지 않도록 설정할 수도 있습니다.

인증된 모든 계산 모듈은 기본적으로 사용하도록 설정된 TPM(신뢰할 수 있는 플랫폼 모듈) 2.0 준수 기술을 제공해야 합니다. TPM은 리소스 계정에 대한 로그인 정보를 Teams 룸 사용됩니다.

보안 부팅은 기본적으로 사용하도록 설정되어 있습니다. 보안 부팅은 PC 업계 구성원이 OEM(원래 장비 제조업체)에서 신뢰할 수 있는 소프트웨어만 사용하여 디바이스가 부팅되는지 확인하기 위해 개발된 보안 표준입니다. PC가 시작되면 펌웨어는 UEFI 펌웨어 드라이버(옵션 ROM), EFI 애플리케이션 및 운영 체제를 포함하여 각 부팅 소프트웨어의 서명을 검사합니다. 서명이 유효한 경우 PC가 부팅하고 펌웨어가 운영 체제에 대한 제어를 제공합니다. 자세한 내용은 보안 부팅 [을 참조하세요.](/windows-hardware/design/device-experiences/oem-secure-boot)

UEFI 설정에 대한 액세스는 물리적 키보드 및 마우스를 연결하여만 가능합니다. 이렇게 하면 터치 지원 콘솔과 Teams 룸 연결된 다른 터치 지원 디스플레이를 통해 UEFI에 액세스할 수 Teams 룸.

DMA(직접 메모리 액세스) 보호는 Windows 10 설정에서 사용하도록 설정된 Teams 룸. 이 기능을 사용하여 OS 및 시스템 펌웨어는 모든 DMA 지원 디바이스에 대해 악의적이지 않은 DMA 공격으로부터 시스템을 보호합니다.

- 부팅 프로세스 중에.

- OS 런타임 동안 M.2 PCIe 슬롯 및 Thunderbolt 3과 같은 내부/외부 DMA 지원 포트에 쉽게 액세스할 수 있는 디바이스에 연결된 악의적인 DMA에 대해.

Teams 룸 HVCI(Hypervisor 보호 코드 무결성)를 사용할 수 있습니다. HVCI에서 제공하는 기능 중 하나는 자격 증명 보호입니다. 자격 증명 보호는 다음과 같은 이점을 제공합니다.

- **하드웨어 보안** NTLM, Kerberos 및 자격 증명 관리자는 보안 부팅 및 가상화를 비롯한 플랫폼 보안 기능을 사용하여 자격 증명을 보호합니다.

- **가상화 기반** Windows NTLM 및 Kerberos 파생 자격 증명 및 기타 비밀은 실행 중인 운영 체제와 격리된 보호된 환경에서 실행됩니다.

- **고급 영구 위협으로부터** 더 나은 보호 자격 증명 관리자 도메인 자격 증명, NTLM 및 Kerberos 파생 자격 증명이 가상화 기반 보안을 사용하여 보호되는 경우, 대상 공격에 사용되는 자격 증명 도용 공격 기술과 도구가 차단됩니다. 관리 권한이 있는 운영 체제에서 실행되는 맬웨어는 가상화 기반 보안으로 보호되는 비밀을 추출할 수 없습니다.

## <a name="software-security"></a>소프트웨어 보안

Microsoft Windows 부팅한 후 Teams 룸 로컬 Windows 사용자 계정에 자동으로 Skype. Skype 계정에 암호가 없습니다. 계정 세션을 Skype 보안을 유지하려면 다음 단계를 수행합니다.

> [!IMPORTANT]
> 암호를 변경하거나 로컬 사용자 계정을 Skype 않습니다. 이렇게 하면 사용자가 자동으로 Teams 룸 수 없습니다.

Microsoft Teams 룸 앱은 1903년 이후의 Windows 10 할당된 액세스 기능을 사용하여 실행됩니다. 할당된 액세스는 사용자에게 Windows 10 애플리케이션 진입점을 제한하는 기능입니다. 이를 통해 단일 앱 키오스크 모드를 사용할 수 있습니다. Shell 시작 관리자 Teams 룸 데스크톱 애플리케이션을 사용자 인터페이스로 Windows 키오스크 디바이스로 구성됩니다. Microsoft Teams 룸 앱은 사용자가 로그온할 때 일반적으로 explorer.exe 기본 셸(explorer.exe)을 대체합니다. 즉, 기존 탐색기 셸은 시작되지 않습니다. 이렇게 하면 Microsoft Teams 룸 취약성 표면이 크게 Windows. 자세한 내용은 데스크톱 버전에서 키오스크 및 디지털 기호 [구성을 Windows 참조하세요.](/windows/configuration/kiosk-methods)

보안 검사 또는 CIS(인터넷 보안 센터) 벤치마크를 실행하기로 결정한 Teams 룸 사용자 계정이 다른 애플리케이션 실행을 지원하지 Skype 로컬 관리자 계정의 컨텍스트에서만 Teams 룸 있습니다. 사용자 컨텍스트에 Skype 대부분의 보안 기능은 다른 로컬 사용자에게 적용되지 않습니다. 따라서 이러한 보안 검사는 해당 계정에 적용되는 전체 보안 잠금을 Skype 않습니다. 따라서 로컬 검색을 실행하지 않는 것이 Teams 룸. 그러나 원하는 경우 외부 침투 테스트를 실행할 수 있습니다. 이 때문에 로컬 검사를 실행하는 대신 Teams 룸 디바이스에 대해 외부 침투 테스트를 실행하는 것이 좋습니다.

또한 관리되지 않는 기능을 사용할 수 있도록 제한하기 위해 잠금 정책이 적용됩니다. 키보드 필터는 할당된 액세스 정책에서 다루지 않는 잠재적으로 불안정한 키보드 조합을 가로채고 차단할 수 있습니다. 로컬 또는 도메인 관리 권한을 가지는 사용자만 로그인할 수 Windows 권한을 Teams 룸. 제품 수명 주기 동안 Windows Microsoft Teams 룸 디바이스에 적용되는 이러한 정책 및 기타 정책은 지속적으로 평가되고 테스트됩니다.

## <a name="account-security"></a>계정 보안

Teams 룸 디바이스에는 기본 암호가 포함된 "Admin"이라는 관리 계정이 포함됩니다. 설정을 완료한 후 가능한 한 빨리 기본 암호를 변경하는 것이 좋습니다.

관리자 계정은 디바이스의 적절한 Teams 룸 필요하지 않습니다. 이름을 변경하거나 삭제할 수도 있습니다. 그러나 관리자 계정을 삭제하기 전에 디바이스와 함께 배송되는 관리자 계정을 제거하기 전에 구성된 대체 로컬 관리자 계정을 Teams 룸 합니다. 기본 제공 도구 또는 PowerShell을 사용하여 로컬 Windows 계정에 대한 암호를 변경하는 Windows 방법에 대한 자세한 내용은 다음을 참조하세요.

- [암호 변경 또는 Windows 재설정](https://support.microsoft.com/windows/change-or-reset-your-windows-password-8271d17c-9f9e-443f-835a-8318c8f68b9c)
- [Set-LocalUser](/powershell/module/microsoft.powershell.localaccounts/set-localuser?view=powershell-5.1#example-2--change-the-password-on-an-account)

도메인 계정을 로컬 관리자 그룹으로 Windows 수 있습니다. Intune을 사용하여 Azure AD 계정에 대해 이 작업을 할 수 있습니다. 자세한 내용은 [정책 CSP – RestrictedGroups를 참조하세요.](/windows/client-management/mdm/policy-csp-restrictedgroups).

> [!CAUTION]
> 다른 로컬 또는 도메인 계정에 로컬 관리자 권한을 부여하기 전에 관리자 계정을 삭제하거나 사용하지 않도록 설정하면 해당 디바이스를 관리할 수 Teams 룸 수 있습니다. 이 경우 디바이스를 원래 설정으로 다시 재설정하고 설정 프로세스를 다시 완료해야 합니다.
>
> 사용자 계정에 로컬 관리자 권한을 Skype 않습니다.

Windows 구성 디자이너를 사용하여 프로비전 패키지를 Windows 10 수 있습니다. 로컬 관리자 암호를 변경하는 것과 함께 컴퓨터 이름을 변경하고 사용자에 등록하는 Azure Active Directory. 구성 디자이너 프로비전 패키지를 만드는 Windows 자세한 내용은 에 대한 프로비전 [패키지를 Windows 10.](/windows/configuration/provisioning-packages/provisioning-packages)

각 디바이스에 대한 리소스 계정을 Teams 룸 로그인할 수 있도록 Teams. 이 계정에서는 2단계 또는 다단계 인증을 사용할 수 없습니다. 두 번째 요소가 필요하면 계정이 재부팅한 후 Teams 룸 앱에 자동으로 로그인할 수 없습니다. 그러나 이 계정에 대한 추가 보안을 위해 최신 인증을 사용하도록 설정할 수 있습니다. 또한 리소스 계정에 대해 위치 기반 조건부 액세스 정책을 배포하여 승인되지 않은 위치에서 계정에 로그인하지 못하게 할 수 있습니다. 자세한 내용은 조건부 액세스 정책에서 위치 조건 사용을 [참조하세요.](/azure/active-directory/conditional-access/location-condition)

가능한 경우 Azure AD에서 리소스 계정을 만드는 것이 좋습니다. 동기화된 계정은 하이브리드 배포에서 Teams 룸 사용할 수 있는 반면, 이러한 동기화된 계정은 로그인하기가 Teams 룸 문제 해결이 어려울 수 있습니다. 타사 페더전 서비스를 사용하여 리소스 계정에 대한 자격 증명을 인증하는 경우 타사 IDP가 으로 설정된 특성으로 응답하도록 `wsTrustResponse` `urn:oasis:names:tc:SAML:1.0:assertion` 합니다.

## <a name="network-security"></a>네트워크 보안

일반적으로 Teams 룸 클라이언트와 동일한 네트워크 요구 사항이 Microsoft Teams 있습니다. 방화벽 및 기타 보안 디바이스를 통한 액세스는 다른 Teams 룸 클라이언트와 Microsoft Teams 동일합니다. 특정 Teams 룸 방화벽에 대해 "필수"로 나열된 Teams 열려 있어야 합니다. Teams 룸 업데이트, Windows, Microsoft Store 및 Microsoft Intune 액세스해야 합니다(Microsoft Intune 장치를 관리하는 경우). 다음에 필요한 전체 IPS 및 URL 목록은 Microsoft Teams 룸 참조하세요.

- **Microsoft Teams** Office 365 URL 및 [IP 주소 범위](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide#skype-for-business-online-and-microsoft-teams)
- **Windows** [WSUS 구성 업데이트](/windows-server/administration/windows-server-update-services/deploy/2-configure-wsus#211-connection-from-the-wsus-server-to-the-internet)
- **Microsoft Store** 및 교육에 대한 비즈니스용 Microsoft Store [전제](/microsoft-store/prerequisites-microsoft-store-for-business#proxy-configuration)
- **Microsoft Intune** [네트워크 엔포인트를 Microsoft Intune](/mem/intune/fundamentals/intune-endpoints)

관리되는 Microsoft Teams 룸 구성 요소를 사용하는 Microsoft Teams 룸 Premium 다음 URL에 액세스할 수 Teams 룸 있는지도 확인해야 합니다.

- agent.rooms.microsoft.com
- global.azure-devices-provisioning.net
- gj3ftstorage.blob.core.windows.net
- iothubsgagwt5wgvwg6.azure-devices.net
- blobssgagwt5wgvwg6.blob.core.windows.net
- mmrstgnoamiot.azure-devices.net
- mmrstgnoamstor.blob.core.windows.net
- mmrprodapaciot.azure-devices.net
- mmrprodapacstor.blob.core.windows.net
- mmrprodemeaiot.azure-devices.net
- mmrprodemeastor.blob.core.windows.net
- mmrprodnoamiot.azure-devices.net
- mmrprodnoamstor.blob.core.windows.net

Teams 룸 업데이트를 포함하여 최신 Windows 자동으로 패치를 유지하도록 구성됩니다. Teams 룸 미리 설정된 로컬 정책을 사용하여 매일 2:00am부터 보류 중인 업데이트를 설치합니다. 업데이트를 배포하고 적용하기 위해 추가 도구를 Windows 없습니다. 추가 도구를 사용하여 업데이트를 배포하고 적용하면 패치 Windows 배포가 지연될 수 있습니다. Teams 룸 앱을 사용하여 Microsoft Store. 디바이스에 표준이 Microsoft Teams 룸 경우 새 버전의 앱이 야간 패치 프로세스 중에 자동으로 설치됩니다. 디바이스에 라이선스가 Microsoft Teams 룸 Premium Microsoft Managed Service에 등록된 경우 새 버전의 Teams 룸 배포 계획에 따라 설치됩니다.

Teams 룸 디바이스는 대부분의 802.1X 또는 기타 네트워크 기반 보안 프로토콜과 함께 작동합니다. 그러나 가능한 모든 네트워크 보안 구성에 Teams 룸 테스트할 수 없습니다. 따라서 네트워크 성능 문제로 추적할 수 있는 성능 문제가 발생하는 경우 조직에서 구성한 경우 이러한 프로토콜을 사용하지 않도록 설정해야 할 수 있습니다.

실시간 미디어의 최적의 성능을 위해 프록시 서버 및 기타 네트워크 보안 디바이스를 Teams 미디어 트래픽을 구성하는 것이 좋습니다. 실시간 미디어는 대기 시간이 매우 중요하며 프록시 서버와 네트워크 보안 디바이스는 사용자의 비디오 및 오디오 품질을 크게 저하할 수 있습니다. 또한 미디어가 Teams 암호화되어 있기 때문에 프록시 서버를 통해 트래픽을 전달할 수 있는 가시적 이점은 없습니다. 자세한 내용은 네트워크 권장 사항을 논의하는 네트워크 구성(클라우드에 [대한) 네트워킹을](/microsoft-365/solutions/networking-design-principles?view=o365-worldwide) Microsoft Teams 및 Microsoft Teams 룸.

> [!IMPORTANT]
> Teams 룸 프록시 서버를 지원하지 않습니다.

Teams 룸 디바이스는 내부 LAN에 연결할 필요가 없습니다. 인터넷에 직접 Teams 룸 보안 네트워크 세그먼트에 데이터를 배치하는 것이 고려됩니다. 내부 LAN이 손상되면 공격 벡터가 Teams 룸 감소합니다.

유선 네트워크에 Teams 룸 디바이스를 연결하는 것이 좋습니다. 디바이스에서 무선 Teams 룸 사용하는 것이 권장되거나 인증되지 않습니다. 일부 연결 기능(예: Wi-Fi Sense)은 기본적으로 비활성화됩니다.

근접 조인 및 기타 Teams 룸 기능은 Bluetooth. 그러나 Bluetooth 디바이스의 Teams 룸 디바이스에 대한 외부 디바이스 연결을 허용하지 Teams 룸 않습니다. Bluetooth 디바이스에서 Teams 룸 기술은 현재 광고 비콘 및 프롬프트된 원시 연결로 제한됩니다. `ADV_NONCONN_INT`PDU(프로토콜 데이터 단위) 형식은 광고 비콘에 사용됩니다. 이 PDU 유형은 수신기 장치에 정보를 광고하는 연결할 수 없는 디바이스용입니다. 이러한 기능의 일부로 Bluetooth 디바이스 페어링이 없습니다. 프로토콜에 대한 Bluetooth 자세한 내용은 SIG 웹 사이트 [에서 Bluetooth 있습니다.](https://www.bluetooth.com/blog/bluetooth-low-energy-it-starts-with-advertising/)
