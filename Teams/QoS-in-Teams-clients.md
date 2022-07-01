---
title: Microsoft Teams 클라이언트에서 QoS(서비스 품질) 구현
ms.author: mikeplum
author: MikePlumleyMSFT
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: QoS(서비스 품질)를 사용하여 Microsoft Teams 데스크톱 클라이언트의 네트워크 트래픽을 최적화하는 방법을 알아봅니다.
ms.localizationpriority: medium
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
ms.openlocfilehash: 70dbc5794fe64a1afed86bc82d0005ad7d510c5f
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2022
ms.locfileid: "66563926"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams-clients"></a>Microsoft Teams 클라이언트에서 QoS(서비스 품질) 구현

그룹 정책 내에서 정책 기반 QoS(서비스 품질)를 사용하여 Teams 클라이언트에서 미리 정의된 DSCP 값의 원본 포트 범위를 설정할 수 있습니다. 다음 표에 지정된 포트 범위는 각 워크로드에 대한 정책을 만들기 위한 시작점입니다.

*표 1. 권장되는 초기 포트 범위*

|미디어 트래픽 유형| 클라이언트 원본 포트 범위  |프로토콜|DSCP 값|DSCP 클래스|
|:--- |:--- |:--- |:--- |:--- |
|오디오| 50,000~50,019|TCP/UDP|46|Expedited Forwarding(EF)|
|비디오| 50,020~50,039|TCP/UDP|34|Assured Forwarding(AF41)|
|응용 프로그램/화면 공유| 50,040~50,059|TCP/UDP|18|Assured Forwarding(AF21)|
| | | | | |

가능하면 그룹 정책 개체 내에서 정책 기반 QoS 설정을 구성합니다. 다음 단계는 포트 [범위를 구성하고 비즈니스용 Skype 서버 클라이언트에 대한 서비스 품질 정책을 구성하는](/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10) 것과 매우 유사합니다. 여기에는 필요하지 않을 수 있는 몇 가지 추가 세부 정보가 있습니다.

도메인에 가입된 Windows 10 컴퓨터에 대한 QoS 오디오 정책을 만들려면 먼저 그룹 정책 관리가 설치된 컴퓨터에 로그온합니다. 그룹 정책 관리를 열고(시작을 클릭하고 관리 도구를 가리킨 다음 그룹 정책 관리 클릭) 다음 단계를 완료합니다.

1. 그룹 정책 관리에서 새 정책을 만들어야 하는 컨테이너를 찾습니다. 예를 들어 모든 클라이언트 컴퓨터가 **Clients** 라는 OU에 있는 경우 클라이언트 OU에서 새 정책을 만들어야 합니다.

1. 적절한 컨테이너를 마우스 오른쪽 단추로 클릭한 다음 **이 도메인에서 GPO 만들기를 클릭하고 여기에 연결합니다**.

1. **새 GPO** 대화 상자의 **이름 상자에 새** 그룹 정책 개체의 이름을 입력하고 **확인을** 클릭합니다.

1. 새로 만든 정책을 마우스 오른쪽 단추로 클릭한 다음 **편집** 을 클릭합니다.

1. 그룹 정책 관리 편집기에서 **컴퓨터 구성** 을 확장하고 **Windows 설정을** 확장하고 **정책 기반 QoS** 를 마우스 오른쪽 단추로 클릭한 다음 **새 정책 만들기** 를 클릭합니다.

1. **정책 기반 QoS** 대화 상자의 여는 페이지에서 **이름** 상자에 새 정책의 이름을 입력합니다. **DSCP 값 지정** 을 선택하고 값을 **46** 으로 설정합니다. **아웃바운드 제한 속도 지정** 을 선택하지 않은 상태로 두고 **다음** 을 클릭합니다.

1. 다음 페이지에서 **이 실행 파일이 있는 애플리케이션만** 선택하고 **Teams.exe** 이름을 입력한 다음 **다음을 클릭합니다**. 이 설정은 정책에서 Teams 클라이언트에서 일치하는 트래픽의 우선 순위만 지정하도록 지시합니다.

1. 세 번째 페이지에서 **모든 원본 IP 주소** 와 **모든 대상 IP 주소** 가 모두 선택되어 있는지 확인한 다음 **다음** 을 클릭합니다. 이러한 두 설정은 패킷을 보낸 컴퓨터(IP 주소)와 패킷을 받을 컴퓨터(IP 주소)에 관계없이 패킷이 관리되도록 합니다.

1. 4페이지의 드롭다운 목록에 **이 QoS 정책이 적용되는 프로토콜 선택** 에서 **TCP 및 UDP** 를 선택합니다. TCP(전송 제어 프로토콜) 및 UDP(사용자 데이터그램 프로토콜)는 가장 일반적으로 사용되는 두 네트워킹 프로토콜입니다.

1. 제목 아래에서 **원본 포트 번호를 지정** 하고 **이 원본 포트 또는 범위에서** 선택합니다. 함께 제공되는 텍스트 상자에 오디오 전송을 위해 예약된 포트 범위를 입력합니다. 예를 들어 오디오 트래픽을 위해 포트 50000~포트 50019를 예약한 경우 다음 형식인 **50000:50019** 를 사용하여 포트 범위를 입력합니다. **마침** 을 클릭합니다.

1. 5-10단계를 반복하여 비디오 및 애플리케이션/데스크톱 공유에 대한 정책을 만들고 6단계와 10단계에서 적절한 값을 대체합니다.

만든 새 정책은 클라이언트 컴퓨터에서 그룹 정책 새로 고칠 때까지 적용되지 않습니다. 그룹 정책 주기적으로 자체적으로 새로 고쳐지지만 다음 단계에 따라 즉시 새로 고침을 강제 적용할 수 있습니다.

1. 그룹 정책 새로 고치려는 각 컴퓨터에서 관리자 권한으로 명령 프롬프트를 엽니다(*관리자 권한으로 실행*).

1. 명령 프롬프트에서 를 입력합니다.

   ```console
   gpupdate /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a>그룹 정책 개체에서 DSCP 표시 확인

그룹 정책 개체의 값이 설정되었는지 확인하려면 다음 단계를 수행합니다.

1. 관리자 권한으로 명령 프롬프트를 엽니다(*관리자 권한으로 실행*).

1. 명령 프롬프트에서 를 입력합니다.

   ```console
   gpresult /R > gp.txt
   ```

   이렇게 하면 적용된 GPO의 보고서가 생성되고 *gp.txt* 텍스트 파일로 전송됩니다.

   *gp.html* 더 읽기 쉬운 HTML 보고서를 보려면 다음 명령을 입력합니다.

   ```console
   gpresult /H gp.html
   ```

1. 생성된 파일에서 **적용된 그룹 정책 개체** 제목을 찾고 이전에 만든 그룹 정책 개체의 이름이 적용된 정책 목록에 있는지 확인합니다.

1. 레지스트리 편집기를 열고

   HKEY\_LOCAL\_MACHINE\\소프트웨어\\정책\\Microsoft\\Windows\\QoS

   표 2에 나열된 레지스트리 항목의 값을 확인합니다.

   *표 2. QoS에 대한 Windows 레지스트리 항목의 값*

   |          이름          |  유형  |    데이터     |
   |         :---:          | :---:  |    :---:    |
   |    애플리케이션 이름    | REG_SZ |  Teams.exe  |
   |       DSCP 값       | REG_SZ |     46      |
   |        로컬 IP        | REG_SZ |     \*      |
   | 로컬 IP 접두사 길이 | REG_SZ |     \*      |
   |       로컬 포트       | REG_SZ | 50000-50019 |
   |        프로토콜        | REG_SZ |     \*      |
   |       원격 IP        | REG_SZ |     \*      |
   |    원격 IP 접두사    | REG_SZ |     \*      |
   |      원격 포트       | REG_SZ |     \*      |
   |     제한 속도      | REG_SZ |     -1      |
   | | | |

1. 사용 중인 클라이언트에 대해 애플리케이션 이름 항목의 값이 올바른지 확인하고 DSCP 값과 로컬 포트 항목이 모두 그룹 정책 개체의 설정을 반영하는지 확인합니다.


## <a name="related-topics"></a>관련 항목

[Teams에서 QoS(서비스 품질) 구현](QoS-in-Teams.md)