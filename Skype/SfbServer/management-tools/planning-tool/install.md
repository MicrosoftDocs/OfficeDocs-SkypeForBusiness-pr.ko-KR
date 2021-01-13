---
title: 비즈니스용 Skype 서버에서 계획 도구 설치
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
description: 비즈니스용 Skype 서버 2015 계획 도구를 사용하여 비즈니스용 Skype 서버 2015 인프라를 디자인하고 계획하기 전에 먼저 계획 도구를 설치해야 합니다. 비즈니스용 Skype 서버 2015를 설치할 도메인 또는 인프라의 일부인 작업소나 서버에 계획 도구를 배포할 필요는 없습니다. 계획 도구와 함께 제공된 Readme 파일에는 도구 설치 및 사용에 대한 중요한 정보가 자세히 설명됩니다. 여기에서는 명확성을 위해 Readme 파일의 일부 정보가 복제됩니다.
ms.openlocfilehash: 902249e042694a37594c6dc0b753b0c1388c0729
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834728"
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버에서 계획 도구 설치

비즈니스용 Skype 서버 2015 계획 도구를 사용하여 비즈니스용 Skype 서버 2015 인프라를 디자인하고 계획하기 전에 먼저 계획 도구를 설치해야 합니다. 비즈니스용 Skype 서버 2015를 설치할 도메인 또는 인프라의 일부인 작업소나 서버에 계획 도구를 배포할 필요는 없습니다. 계획 도구와 함께 제공된 Readme 파일에는 도구 설치 및 사용에 대한 중요한 정보가 자세히 설명됩니다. 여기에서는 명확한 설명을 위해 Readme 파일의 일부 정보가 복제됩니다.

> [!IMPORTANT]
> 계획 도구를 사용하려면 도구를 설치할 컴퓨터에 대한 관리자 권한 및 사용 권한이 있는 사용자가 설치해야 합니다.

계획 도구의 설치 및 작동에 지원되는 운영 체제는 다음입니다.

- Windows 10

- Windows 8

- Windows 8.1

- Windows Server 2012

- Windows Server 2012 R2

- Windows 7, 32비트 버전

- WOW(Win32)에서 Windows를 사용하는 Windows 7, 64비트 버전

- WOW를 사용하는 Windows Server 2008 R2

또한 계획 도구에는 Microsoft .NET Framework 4.5가 필요합니다.

사전 설치 요구 사항이 충족된 후 계획 도구를 설치할 수 있습니다.



## <a name="to-install-the-planning-tool"></a>계획 도구를 설치하려면

1. Administrators 그룹의 구성원으로 로컬 컴퓨터에 로그온합니다.

2. Windows 탐색기 또는 명령 창을 사용하여 계획 도구 설치 파일을 다운로드한 디렉터리를 찾습니다.

3. 위치를 SkypeForBusinessPlanningTool.msi. Windows 탐색기에서 파일을 두 번 클릭합니다. 명령 창에 파일의 이름을 입력한 다음 **Enter를** 눌러 파일을 실행합니다.

4. 비즈니스용 Skype 서버 **2015의** 시작 페이지에서 계획 도구 설치 마법사에서 다음을 **클릭합니다.**

5. 최종 **사용자** 사용권 계약을  검토하고 사용권 계약에 동의하도록 선택한 경우 사용권 계약의 약관에 동의한 후 다음을 **클릭합니다.**

6. 계획 도구 파일을 설치할 위치를 선택하십시오. 기본 위치는 C:\Program Files (x86)\Skype for Business Server 2015\Planning Tool입니다. 설치 위치를 변경하려면 변경을 **클릭합니다.** 대상 **폴더 변경에서** 파일을 설치할 위치를 찾아보거나 입력하고 확인을 클릭한 후 다음을 **클릭합니다.**

7. 이제 설치 관리자에서 계획 도구를 설치할 준비가 완료되었습니다. 설치를 **클릭하여** 설치 프로세스를 시작할 수 있습니다.

8. 설치가 시작되고 진행률이 표시됩니다. 설치가 완료된 후 **마쳤습니다.**

9. 계획 도구를 사용할 준비가 완료되었습니다.

## <a name="optional-software"></a>선택적 소프트웨어
<a name="Optional_Software"> </a>

비즈니스용 Skype 서버 2015 계획 도구는 Microsoft Excel 및 Microsoft Visio로 내보낼 수 있도록 디자인됩니다. 이러한 응용 프로그램은 계획 도구의 작업에 필요하지는 하지만 디자인의 배포 및 설명서에 중요한 가치를 제공합니다.

### <a name="microsoft-excel"></a>Microsoft Excel

디자인을 Microsoft Excel로 내보내면 스프레드시트에 7개의 탭이 표시되는 보고서가 생성됩니다.

- 요약 - 사용자 수, 용량 설정 및 서버 프로필 정보를 포함하여 사이트 구성에 대한 정보를 표시됩니다.

- 하드웨어 프로필 - CPU, 메모리, 디스크 및 네트워크 인터페이스를 포함하여 토폴로지에서 지정된 서버에 대한 권장 하드웨어 구성에 대한 보고서를 표시합니다. 서버 구성 요소의 수량 및 권장 사양도 포함됩니다. 또한 각 서버는 사이트별로 서버 요구 사항을 완전한 표현하기 위해 사이트별로 정의됩니다.

- 포트 요구 사항 - 사용하도록 설정된 모든 포트에 대한 보고서와 DNS LB(Domain Name System Load Balancing) 및 HLB(하드웨어 부하 분산)와의 연결 보고서를 표시합니다. 이 보고서를 사용하여 방화벽과 DNS LB 및 HLB 구성을 계획해야 합니다.

- 요약 보고서 - 에지 서버 네트워크를 설정하는 데 필요한 설정의 일반 요약을 제공합니다.

- 인증서 보고서 - 에지 서버를 실행하는 데 필요한 인증서에 필요한 주체 이름 및 주체 대체 이름을 표시됩니다.

- 방화벽 보고서 - 외부 및 내부 인터페이스 둘 다에 대한 원본 및 대상 포트와 IP 주소를 표시됩니다.

- DNS 보고서 - 만드는 각 DNS 항목에 필요한 FQDN(FQDN) 및 IP/VIP 주소를 표시됩니다.

### <a name="microsoft-visio"></a>Microsoft Visio

설계를 Microsoft Visio로 내보내면 구성된 토폴로지 및 인프라에 대한 설명서에서 사용할 다이어그램이 만들어집니다. 가져온 다이어그램은 설명서 요구 사항에 맞게 편집하고 재정렬할 수 있습니다. 일반적인 Visio 다이어그램에 포함되는 항목은 다음과 같습니다.

> [!NOTE]
> 디자인에 프런트 엔드 서버가 3대 이상 필요할 정도로 큰 경우 프런트 엔드 풀, 프런트 엔드 서버, 실행되는 컴퓨터SQL Server IP 주소 및 FQDNS에 대해 페이지가 추가로 만들어집니다.

- 전역 토폴로지 - 구성된 비즈니스용 Skype 서버 2015 사이트의 다이어그램입니다.

- 사이트 이름 탭 - 에지 서버, 방화벽, 게이트웨이가 있는 PSTN(Public Switched Telephone Network) 및 내부 서버 배포가 있는 사이트 구성 토폴로지 표시 내부 배포는 프런트 엔드 풀, SQL Server 기반 서버, Active Directory 도메인 서비스, 디렉터, Exchange UM(통합 메시징) 서버, Exchange 사서함 서버, Office Web Apps 서버, 중재 서버 및 영구 채팅 서버를 포함하여 구성된 서버 및 풀로 구성됩니다.

- 에지 네트워크 다이어그램 - 연결된 IP 주소 및 FQDNS를 사용하여 에지 서버 구성을 자세히 설명하는 다이어그램입니다. DNS 부하 분산 및 하드웨어 부하 분산 장치도 포함됩니다. 또한 연결된 DNS LB 또는 HLB 및 할당된 IP 주소(계획 도구에서 IPv4 및 IPv6 주소 모두 지원) 및 FQDN과 함께 Director 및 프런트 엔드 서버 또는 프런트 엔드 풀이 표시됩니다.

## <a name="see-also"></a>참고 항목
<a name="Optional_Software"> </a>

[계획 도구 설치](https://technet.microsoft.com/library/ebdc9e26-4b22-4b02-85b9-7462bcfe7c93.aspx)
