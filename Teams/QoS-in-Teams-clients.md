---
title: Microsoft Teams 클라이언트에서 QoS(서비스 품질) 구현
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: QoS(서비스 품질)를 사용하여 Microsoft Teams 데스크톱 클라이언트에 대한 네트워크 트래픽을 최적화하는 방법을 배워야 합니다.
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
# <a name="implement-quality-of-service-qos-in-microsoft-teams-clients"></a>Microsoft Teams 클라이언트에서 QoS(서비스 품질) 구현

그룹 정책 내에서 QoS(정책 기반 서비스 품질)를 사용하여 Teams 클라이언트에서 미리 정의한 DSCP 값에 대한 원본 포트 범위를 설정할 수 있습니다. 다음 표에 지정된 포트 범위는 각 워크로드에 대한 정책을 만들기 위한 시작점입니다.

*표 1. 권장되는 초기 포트 범위*

|미디어 트래픽 유형| 클라이언트 원본 포트 범위  |프로토콜|DSCP 값|DSCP 클래스|
|:--- |:--- |:--- |:--- |:--- |
|오디오| 50,000~50,019|TCP/UDP|46|Expedited Forwarding(EF)|
|비디오| 50,020~50,039|TCP/UDP|34|Assured Forwarding(AF41)|
|응용 프로그램/화면 공유| 50,040~50,059|TCP/UDP|18|Assured Forwarding(AF21)|
| | | | | |

가능한 경우 그룹 정책 개체 내에서 정책 기반 QoS 설정을 구성합니다. 다음 단계는 비즈니스용  [Skype Server에서](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10)클라이언트에 대한 포트 범위 및 서비스 품질 정책 구성과 매우 유사하며, 이 정책에는 필요하지 않을 수 있는 몇 가지 추가 세부 정보가 있습니다.

도메인에 가입된 Windows 10 컴퓨터에 대한 QoS 오디오 정책을 만들하려면 먼저 그룹 정책 관리가 설치된 컴퓨터에 로그온합니다. 그룹 정책 관리를 열고(시작을 클릭하고 관리 도구를 클릭한 다음 그룹 정책 관리를 클릭) 다음 단계를 완료합니다.

1. 그룹 정책 관리에서 새 정책을 만들어야 하는 컨테이너를 찾습니다. 예를 들어 모든 클라이언트 컴퓨터가 클라이언트라는 OU에 있는 경우 클라이언트 OU에 새 정책을 만들어야 합니다. 

1. 적절한 컨테이너를 마우스 오른쪽 단추로 클릭한 다음 이 도메인에서 GPO 만들기를 **클릭하고 여기에 연결합니다.**

1. 새 **GPO** 대화 상자의 이름 상자에 새 그룹  정책 개체의 이름을 입력한 다음 확인을 **클릭합니다.**

1. 새로 만든 정책을 마우스 오른쪽 단추로 클릭한 다음 편집을 **클릭합니다.**

1. 그룹 정책 관리 편집기에서 **컴퓨터** 구성을 확장하고 **Windows 설정을** 확장하고 정책 기반 **QoS를** 마우스 오른쪽 단추로 클릭한 다음 새 정책 **만들기를 클릭합니다.**

1. 정책 기반 **QoS** 대화 상자의 열기 페이지에서 이름 상자에 새 정책의 이름을 **입력합니다.** **DSCP 값 지정을** 선택하고 값을 **46으로 설정합니다.** 아웃바운드 **스로틀** 속도 지정을 선택하지 않은 그대로 두고 다음을 **클릭합니다.**

1. 다음 페이지에서 이  실행 가능한 이름이 있는 애플리케이션만 **** 선택하고 이름Teams.exe다음을 **클릭합니다.** 이 설정은 Teams 클라이언트에서 일치하는 트래픽의 우선 순위를 지정하는 정책에 지시합니다.

1. 세 번째 페이지에서 원본 **IP** 주소와 대상 **IP** 주소가 모두 선택되어 있는지 확인한 후 다음을 **클릭합니다.** 이러한 두 설정은 패킷을 전송하는 컴퓨터(IP 주소)와 패킷을 받을 컴퓨터(IP 주소)에 관계 없이 패킷을 관리하도록 합니다.

1. 4페이지에서 이 **QoS** 정책이 드롭다운 목록에 적용되는 프로토콜 선택에서 **TCP 및 UDP를** 선택합니다. TCP(Transmission Control Protocol) 및 UDP(User Datagram Protocol)는 가장 일반적으로 사용되는 두 가지 네트워킹 프로토콜입니다.

1. 제목에서 원본 포트 번호를 **지정하고** 이 원본 포트 또는 **범위에서 선택합니다.** 함께 제공되는 텍스트 상자에 오디오 전송을 위해 예약된 포트 범위를 입력합니다. 예를 들어 오디오 트래픽에 대해 포트 50000~포트 50019를 예약한 경우 **50000:50019** 형식을 사용하여 포트 범위를 입력합니다. **마침** 을 클릭합니다.

1. 5-10단계를 반복하여 비디오 및 응용 프로그램/데스크톱 공유에 대한 정책을 만들고 6단계와 10단계에서 적절한 값을 대신합니다.

만든 새 정책은 클라이언트 컴퓨터에서 그룹 정책을 새로 고칠 때까지 적용됩니다. 그룹 정책은 주기적으로 자체적으로 새로 고쳐지지만 다음 단계를 수행하여 즉시 새로 고칠 수 있습니다.

1. 그룹 정책을 새로 고치고자 하는 각 컴퓨터에서 관리자 권한으로 명령 프롬프트를 *여습니다(관리자 권한으로 실행).*

1. 명령 프롬프트에서

   ```console
   gpupdate /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a>그룹 정책 개체에서 DSCP 표시 확인

그룹 정책 개체의 값이 설정되어 있는지 확인한 후 다음 단계를 수행합니다.

1. 관리자 권한으로 명령 프롬프트 *열기(관리자 권한으로 실행).*

1. 명령 프롬프트에서

   ```console
   gpresult /R > gp.txt
   ```

   이렇게 하면 적용된 GPOS에 대한 보고서가 생성되고 이 보고서가 *gp.txt.*

   gp.htm읽기 쉽게 HTML 보고서를 사용하려면 *다음* 명령을 입력합니다.

   ```console
   gpresult /H gp.html
   ```

1. 생성된 파일에서 적용된 그룹  정책 개체 제목을 찾아서 앞에서 만든 그룹 정책 개체의 이름이 적용된 정책 목록에 있는지 확인해야 합니다.

1. 레지스트리 편집기를 열고

   HKEY \_ LOCAL MACHINE 소프트웨어 정책 Microsoft Windows \_ \\ \\ \\ \\ \\ QoS

   표 2에 나열된 레지스트리 항목의 값을 확인해야 합니다.

   *표 2. QoS에 대한 Windows 레지스트리 항목에 대한 값*

   |          이름          |  유형  |    데이터     |
   |         :---:          | :---:  |    :---:    |
   |    애플리케이션 이름    | REG_SZ |  Teams.exe  |
   |       DSCP 값       | REG_SZ |     46      |
   |        로컬 IP        | REG_SZ |     \*      |
   | 로컬 IP Prefix 길이 | REG_SZ |     \*      |
   |       로컬 포트       | REG_SZ | 50000-50019 |
   |        프로토콜        | REG_SZ |     \*      |
   |       원격 IP        | REG_SZ |     \*      |
   |    원격 IP Prefix    | REG_SZ |     \*      |
   |      원격 포트       | REG_SZ |     \*      |
   |     스로틀 속도      | REG_SZ |     -1      |
   | | | |

1. 사용 하는 클라이언트에 대한 애플리케이션 이름 항목의 값이 올바른지 확인하고 DSCP 값 및 로컬 포트 항목 모두 그룹 정책 개체의 설정을 반영하는지 확인합니다.


## <a name="related-topics"></a>관련 항목

[Teams에서 QoS(서비스 품질) 구현](QoS-in-Teams.md)