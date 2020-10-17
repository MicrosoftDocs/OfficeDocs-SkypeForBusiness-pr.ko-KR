---
title: Microsoft 팀 클라이언트에서 QoS (서비스 품질) 구현
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: QoS (서비스 품질)를 사용 하 여 Microsoft 팀 데스크톱 클라이언트에 대 한 네트워크 트래픽을 최적화 하는 방법을 알아봅니다.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: bc352303cf63ea966927aece0aef36854a0ace1b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526405"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams-clients"></a>Microsoft 팀 클라이언트에서 QoS (서비스 품질) 구현

그룹 정책 내에서 정책 기반 QoS (서비스 품질)를 사용 하 여 팀 클라이언트에서 미리 정의 된 DSCP 값에 대 한 원본 포트 범위를 설정할 수 있습니다. 다음 표에 지정 된 포트 범위는 각 작업 부하에 대 한 정책을 만들기 위한 출발점입니다.

*표 1 권장 되는 초기 포트 범위*

|미디어 트래픽 유형| 클라이언트 원본 포트 범위  |프로토콜|DSCP 값|DSCP 클래스|
|:--- |:--- |:--- |:--- |:--- |
|오디오| 50,000~50,019|TCP/UDP|46|Expedited Forwarding(EF)|
|비디오| 50,020~50,039|TCP/UDP|34|Assured Forwarding(AF41)|
|응용 프로그램/화면 공유| 50,040~50,059|TCP/UDP|awg|Assured Forwarding(AF21)|
| | | | | |

가능 하면 그룹 정책 개체 내에서 정책 기반 QoS 설정을 구성 합니다. 다음 단계는  [비즈니스용 Skype Server에서 클라이언트에 대 한 포트 범위와 서비스 품질 정책을 구성](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10)하는 것과 매우 유사 하며, 필요 하지 않을 수도 있는 추가 세부 사항이 있습니다.

도메인에 가입한 Windows 10 컴퓨터에 대해 QoS 오디오 정책을 만들려면 먼저 그룹 정책 관리가 설치 된 컴퓨터에 로그온 합니다. 그룹 정책 관리 (시작을 클릭 하 고 관리 도구를 가리킨 다음 그룹 정책 관리 클릭)를 열고 다음 단계를 완료 합니다.

1. 그룹 정책 관리에서 새 정책을 만들 컨테이너를 찾습니다. 예를 들어 모든 클라이언트 컴퓨터가 **클라이언트**라는 OU에 있는 경우 클라이언트 ou에서 새 정책을 만들어야 합니다.

1. 적절 한 컨테이너를 마우스 오른쪽 단추로 클릭 한 다음 **이 도메인에서 GPO 만들기를 클릭 하 고 여기에 연결**합니다.

1. **새 GPO** 대화 상자의 **이름** 상자에 새 그룹 정책 개체의 이름을 입력 하 고 **확인**을 클릭 합니다.

1. 새로 만든 정책을 마우스 오른쪽 단추로 클릭 한 다음 **편집**을 클릭 합니다.

1. 그룹 정책 관리 편집기에서 **컴퓨터 구성**, **Windows 설정을**차례로 확장 하 고 **정책 기반 QoS**를 마우스 오른쪽 단추로 클릭 한 다음 **새 정책 만들기**를 클릭 합니다.

1. **정책 기반 QoS** 대화 상자의 열기 페이지에 있는 **이름** 상자에 새 정책의 이름을 입력 합니다. **DSCP 값 지정** 을 선택 하 고 값을 **46**로 설정 합니다. **아웃 바운드 스로틀 속도 지정** 을 선택 하지 않은 상태로 두고 **다음**을 클릭 합니다.

1. 다음 페이지에서 **이 실행 파일 이름의 응용** 프로그램만 선택 하 고 **Teams.exe**이름을 입력 한 후 **다음**을 클릭 합니다. 이 설정은 팀 클라이언트에서 일치 하는 트래픽에만 우선 순위를 지정 하도록 정책에 지시 합니다.

1. 세 번째 페이지에서 **원본 ip 주소** 와 **대상 ip 주소가** 모두 선택 되어 있는지 확인 하 고 **다음**을 클릭 합니다. 이러한 두 가지 설정은 패킷을 보낸 컴퓨터 (IP 주소)와 패킷을 받을 컴퓨터 (IP 주소)에 관계 없이 패킷이 관리 됨을 보장 합니다.

1. 4 페이지에서 **이 QoS 정책이 적용 되는 프로토콜 선택** 드롭다운 목록에서 **TCP 및 UDP** 를 선택 합니다. TCP (전송 제어 프로토콜) 및 UDP (사용자 데이터 그램 프로토콜)는 가장 일반적으로 사용 되는 두 가지 네트워킹 프로토콜입니다.

1. **원본 포트 번호를 지정 하는**제목 아래에서 **이 원본 포트 또는 범위를**선택 합니다. 해당 텍스트 상자에 오디오 전송용으로 예약 된 포트 범위를 입력 합니다. 예를 들어 오디오 트래픽용 포트 50019를 통해 포트 5만를 예약한 경우이 형식을 사용 하 여 포트 범위를 입력 합니다 ( **50000:50019**). **마침**을 클릭합니다.

1. 6 ~ 10 단계의 적절 한 값으로 대체 하 여 비디오 및 응용 프로그램/데스크톱 공유에 대 한 정책을 만들려면 5-10 단계를 반복 합니다.

만든 새 정책은 클라이언트 컴퓨터에서 그룹 정책이 새로 고쳐질 때까지 적용 되지 않습니다. 그룹 정책은 주기적으로 자체적으로 새로 고쳐지고, 다음 단계에 따라 즉시 새로 고칠 수 있습니다.

1. 그룹 정책을 새로 고칠 각 컴퓨터에서 관리자 권한으로 명령 프롬프트를 엽니다 (*관리자 권한으로 실행*).

1. 명령 프롬프트에서 다음을 입력 합니다.

   ```console
   gpupdate /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a>그룹 정책 개체에서 DSCP 표시 확인

그룹 정책 개체의 값이 설정 되어 있는지 확인 하려면 다음 단계를 수행 합니다.

1. 관리자 권한으로 명령 프롬프트를 엽니다 (*관리자 권한으로 실행*).

1. 명령 프롬프트에서 다음을 입력 합니다.

   ```console
   gpresult /R > gp.txt
   ```

   이렇게 하면 적용 된 Gpo에 대 한 보고서가 생성 되 고이를 *gp.txt*이라는 텍스트 파일에 보냅니다.

   *gp.html*이라는 보다 읽기 쉬운 HTML 보고서를 보려면 다음 명령을 입력 합니다.

   ```console
   gpresult /H gp.html
   ```

1. 생성 된 파일에서 **적용 된 그룹 정책 개체** 의 머리글을 찾아 이전에 만든 그룹 정책 개체의 이름이 적용 된 정책 목록에 있는지 확인 합니다.

1. 레지스트리 편집기를 열고 다음으로 이동 합니다.

   HKEY \_ 로컬 \_ 컴퓨터 \\ 소프트웨어 \\ 정책 \\ Microsoft \\ Windows \\ QoS

   표 2에 나열 된 레지스트리 항목의 값을 확인 합니다.

   *표 2. QoS에 대 한 Windows 레지스트리 항목의 값*

   |          이름          |  유형  |    데이터     |
   |         :---:          | :---:  |    :---:    |
   |    응용 프로그램 이름    | REG_SZ |  Teams.exe  |
   |       DSCP 값       | REG_SZ |     46      |
   |        로컬 IP        | REG_SZ |     \*      |
   | 로컬 IP 접두사 길이 | REG_SZ |     \*      |
   |       로컬 포트       | REG_SZ | 50000-50019 |
   |        프로토콜        | REG_SZ |     \*      |
   |       원격 IP        | REG_SZ |     \*      |
   |    원격 IP 접두사    | REG_SZ |     \*      |
   |      원격 포트       | REG_SZ |     \*      |
   |     스로틀 속도      | REG_SZ |     -1      |
   | | | |

1. 사용 중인 클라이언트에 대 한 응용 프로그램 이름 항목의 값이 올바른지 확인 하 고 DSCP 값과 로컬 포트 항목에 그룹 정책 개체의 설정이 반영 되는지 확인 합니다.


## <a name="related-topics"></a>관련 주제

[팀에서 QoS (서비스 품질) 구현](QoS-in-Teams.md)