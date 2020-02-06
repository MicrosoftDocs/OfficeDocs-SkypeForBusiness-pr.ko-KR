---
title: Lync Server 2013에서 선택적 소프트웨어 설치
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 비즈니스용 Skype Server 2015 계획 도구를 사용 하 여 비즈니스용 Skype Server 2015 인프라 디자인 및 계획을 시작 하기 전에 먼저 계획 도구를 설치 해야 합니다. 비즈니스 서버 2015에 대 한 Skype를 설치 하려는 도메인 또는 인프라의 일부인 워크스테이션 또는 서버에 계획 도구를 배포할 필요는 없습니다. 계획 도구와 함께 제공 되는 Readme 파일은 도구 설치 및 사용에 대 한 중요 한 정보를 자세히 설명 합니다. 이해를 돕기 위해 Readme 파일의 일부 정보가 여기에 중복 됩니다.
ms.openlocfilehash: 29cadae219faadb68a8a027de11309efc8e3f10b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816387"
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a>Lync Server 2013에서 선택적 소프트웨어 설치

비즈니스용 Skype Server 2015 계획 도구를 사용 하 여 비즈니스용 Skype Server 2015 인프라 디자인 및 계획을 시작 하기 전에 먼저 계획 도구를 설치 해야 합니다. 비즈니스 서버 2015에 대 한 Skype를 설치 하려는 도메인 또는 인프라의 일부인 워크스테이션 또는 서버에 계획 도구를 배포할 필요는 없습니다. 계획 도구와 함께 제공 되는 Readme 파일은 도구 설치 및 사용에 대 한 중요 한 정보를 자세히 설명 합니다. 이해를 돕기 위해 Readme 파일의 일부 정보가 여기에 중복 됩니다.

> [!IMPORTANT]
> 계획 도구는 관리자 권한이 있는 사용자가 설치 하 고 도구를 설치할 컴퓨터에 대 한 사용 권한을 필요로 합니다.

계획 도구의 설치 및 작동을 위해 지원 되는 운영 체제는 다음과 같습니다.

- Windows 10

- Windows 8

- Windows 8.1

- Windows Server 2012

- Windows Server 2012 R2

- Windows 7, 32 비트 버전

- Windows 7, 64 비트 edition (w)에서 Windows를 사용 하는 경우

- Windows Server 2008 R2, WOW 사용

또한 계획 도구에는 Microsoft .NET Framework 4.5이 필요 합니다.

사전 설치 요구 사항이 충족 되 면 계획 도구를 설치할 수 있습니다.



## <a name="to-install-the-planning-tool"></a>계획 도구를 설치 하려면

1. 로컬 컴퓨터에 관리자 그룹의 구성원으로 로그온 합니다.

2. Windows 탐색기나 명령 창을 사용 하 여 계획 도구 설치 파일을 다운로드 한 디렉터리를 찾습니다.

3. SkypeForBusinessPlanningTool를 찾습니다. Windows 탐색기에서 파일을 두 번 클릭 합니다. 명령 창에 파일 이름을 입력 한 다음 **enter 키를 눌러 파일을 실행** 합니다.

4. **비즈니스용 Skype 서버 2015의 시작 페이지에서 계획 도구 설정 마법사**의 **다음**을 클릭 합니다.

5. 라이선스 계약의 사용 약관에 동의 하기로 선택한 경우 **최종 사용자 사용권 계약**을 확인 하 고 **사용권 계약에** 동의 함을 선택한 후 **다음**을 클릭 합니다.

6. 계획 도구 파일을 설치할 위치를 선택 합니다. 기본 위치는 C:\Program Files (x86) \Skype Skype Server 2015 \ 계획 도구입니다. 설치 위치를 변경 하려면 **변경을**클릭 합니다. **대상 폴더 변경**에서 파일을 설치할 위치를 찾아보거나 입력 하 고 **확인**을 클릭 한 후 **다음**을 클릭 합니다.

7. 이제 설치 관리자가 계획 도구를 설치할 준비가 되었습니다. 설치 **를 클릭 하** 여 설치 프로세스를 시작 합니다.

8. 설치가 시작 되 고 진행률이 표시 됩니다. 설치가 성공적으로 완료 되 면 **마침을**클릭 합니다.

9. 계획 도구를 사용할 준비가 되었습니다.

## <a name="optional-software"></a>선택적 소프트웨어
<a name="Optional_Software"> </a>

비즈니스용 Skype 서버 2015 계획 도구는 Microsoft Excel 및 Microsoft Visio로 내보내기 하도록 디자인 되었습니다. 이러한 응용 프로그램은 계획 도구 작동에 필요 하지 않지만 디자인의 배포 및 문서에 중요 한 가치를 갖습니다.

### <a name="microsoft-excel"></a>Microsoft Excel

Microsoft Excel로 디자인을 내보내면 스프레드시트에 일곱 개의 탭이 표시 되는 보고서가 만들어집니다.

- 요약-사이트 구성에 대 한 정보 (사용자 수, 용량 설정, 서버 프로필 정보 등)를 표시 합니다.

- 하드웨어 프로필-토폴로지에 지정 된 서버에 대 한 권장 하드웨어 구성 (CPU, 메모리, 디스크, 네트워크 인터페이스 등)에 대 한 보고서를 표시 합니다. 서버 구성 요소에 대 한 수량 및 권장 사양이 포함 됩니다. 또한 각 서버는 사이트별로 서버 요구 사항에 대 한 완전 한 표현을 제공 하도록 사이트에 정의 됩니다.

- 포트 요구 사항-사용 하도록 설정 된 모든 포트의 보고서와 DNS LB (도메인 이름 시스템 부하 분산) 및 HLB (하드웨어 부하 분산 장치)에 대 한 연결을 표시 합니다. 이 보고서를 사용 하 여 방화벽과 DNS LB 및 HLB 구성을 계획 해야 합니다.

- 요약 보고서-Edge Server 네트워크를 설정 하는 데 필요한 설정에 대 한 일반적인 요약 정보를 표시 합니다.

- 인증서 보고서-Edge 서버를 실행 하는 데 필요한 인증서에 필요한 주체 이름 및 주체 대체 이름을 표시 합니다.

- 방화벽 보고서-원본 및 대상 포트와 외부 및 내부 인터페이스에 대 한 IP 주소를 표시 합니다.

- DNS Report-사용자가 만든 각 DNS 항목에 필요한 FQDN (정규화 된 도메인 이름) 및 IP/VIP 주소를 표시 합니다.

### <a name="microsoft-visio"></a>Microsoft Visio

Microsoft Visio로 디자인을 내보내면 구성 된 토폴로지와 인프라의 설명서에 사용할 수 있는 다이어그램이 만들어집니다. 문서에 대 한 요구 사항을 충족 하기 위해 가져온 다이어그램을 편집 하 고 다시 정렬할 수 있습니다. 일반적인 Visio 다이어그램에는 다음이 포함 됩니다.

> [!NOTE]
> 세 개 이상의 프런트 엔드 서버를 필요로 하는 설계가 충분히 큰 경우 프런트 엔드 풀, 프런트 엔드 서버, SQL Server를 실행 하는 컴퓨터, IP 주소, Fqdn에 대 한 추가 페이지가 만들어집니다.

- 전역 토폴로지-구성 된 비즈니스용 Skype 서버 2015 사이트의 다이어그램입니다.

- 사이트 이름 탭-Edge Server, 방화벽, 공공 교환 통신 네트워크 (PSTN) 및 게이트웨이가 있는 사이트 구성 토폴로지가 표시 되며 내부 서버 배포 내부 배포는 프런트 엔드 풀, SQL Server 기반 서버, Active Directory 도메인 서비스, 디렉터, Exchange UM (통합 메시징) 서버, Exchange 사서함 서버, Office Web Apps 서버를 포함 하 여 구성 된 서버와 풀로 구성 됩니다. 중재 서버와 영구 채팅 서버.

- Edge 네트워크 다이어그램-연결 된 IP 주소와 Fqdn을 사용 하 여 Edge 서버 구성을 자세히 설명 하는 다이어그램입니다. DNS 부하 분산 및 하드웨어 부하 분산 장치도 포함 됩니다. 또한 디렉터 및 프런트 엔드 서버 또는 프런트 엔드 풀은 연결 된 DNS LB 또는 HLB와 할당 된 IP 주소 (계획 도구는 IPv4 및 IPv6 주소 모두 지원) 및 FQDN으로 표시 됩니다.

## <a name="see-also"></a>참고 항목
<a name="Optional_Software"> </a>

[계획 도구 설치](https://technet.microsoft.com/library/ebdc9e26-4b22-4b02-85b9-7462bcfe7c93.aspx)
