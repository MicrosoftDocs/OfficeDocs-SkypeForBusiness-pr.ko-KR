---
title: 클라이언트에 대 한 포트 범위 및 서비스 품질 정책 구성
ms.reviewer: ''
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 이 문서에서는 Windows 10에서 실행 되는 클라이언트에 대 한 비즈니스용 Skype 서버에서 클라이언트에 대 한 포트 범위를 구성 하 고 서비스 품질 정책을 구성 하는 방법에 대해 설명 합니다.
ms.openlocfilehash: 95fe768333a01aff165e74eec334f14bf23d69dc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045891"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 클라이언트에 대 한 포트 범위 및 서비스 품질 정책 구성

이 문서에서는 Windows 10에서 실행 되는 클라이언트에 대 한 비즈니스용 Skype 서버에서 클라이언트에 대 한 포트 범위를 구성 하 고 서비스 품질 정책을 구성 하는 방법에 대해 설명 합니다.

## <a name="configure-port-ranges"></a>포트 범위 구성

기본적으로 비즈니스용 Skype 클라이언트 응용 프로그램은 통신 세션에 포함 된 경우 포트 1024과 65535 사이의 모든 포트를 사용할 수 있습니다. 이는 특정 포트 범위가 클라이언트에 대해 자동으로 사용 하지 않도록 설정 되었기 때문입니다. 그러나 서비스 품질을 사용 하려면 다양 한 트래픽 유형 (오디오, 비디오, 미디어, 응용 프로그램 공유 및 파일 전송)을 일련의 고유한 포트 범위에 다시 할당 해야 합니다. 이 작업은 Get-csconferencingconfiguration cmdlet을 사용 하 여 수행할 수 있습니다.

> [!NOTE]  
> 최종 사용자는 이러한 변경 작업을 직접 수행할 수 없습니다. 포트 변경 내용은 Get-csconferencingconfiguration cmdlet을 사용 하는 관리자만 수행할 수 있습니다.


비즈니스용 Skype 서버 관리 셸에서 다음 명령을 실행 하 여 현재 통신 세션에 사용 되는 포트 범위를 확인할 수 있습니다.

    Get-CsConferencingConfiguration

비즈니스용 Skype 서버를 설치한 후 회의 설정을 변경 하지 않은 경우 다음 속성 값이 포함 된 정보를 반환 해야 합니다.

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

위의 출력을 자세히 보면 두 가지 중요한 사항을 확인할 수 있습니다. 먼저, ClientMediaPortRangeEnabled 속성이 False로 설정되어 있습니다.

    ClientMediaPortRangeEnabled : False

이 속성을 False로 설정 하면 비즈니스용 Skype 클라이언트는 통신 세션에 포함 될 때 포트 1024과 65535 사이에 사용 가능한 포트를 사용 하기 때문에 중요 합니다. 이는 다른 포트 설정 (예: ClientMediaPort 또는 ClientVideoPort)에 관계 없이 적용 됩니다. 지정 된 포트 집합으로 사용을 제한 하려는 경우 (서비스 품질을 구현 하려는 경우에는이 작업을 수행 하려는 경우) 먼저 클라이언트 미디어 포트 범위를 사용 하도록 설정 해야 합니다. 다음 Windows PowerShell 명령을 사용 하 여이 작업을 수행할 수 있습니다.

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

위의 명령은 회의 구성 설정의 전역 컬렉션에 대해 클라이언트 미디어 포트 범위를 사용하도록 설정합니다. 그러나 이러한 설정은 사이트 범위 및/또는 서비스 범위(회의 서버 서비스에 한함)에도 적용할 수 있습니다. 특정 사이트 또는 서버에 대해 클라이언트 미디어 포트 범위를 사용하도록 설정하려면 Set-CsConferencingConfiguration을 호출할 때 해당 사이트 또는 서버의 Identity를 지정합니다.

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

또는 이 명령을 사용하여 모든 회의 구성 설정에 대해 포트 범위를 동시에 사용하도록 설정할 수도 있습니다.

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

위의 출력에서 두 번째로 중요한 사항은 예제 출력에서 기본적으로 각 네트워크 트래픽 유형에 대해 설정된 미디어 포트 범위가 동일하다는 점입니다.

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

QoS를 구현하려면 이러한 각 포트 범위가 고유해야 합니다. 예를 들어 포트 범위를 다음과 같이 구성할 수 있습니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>클라이언트 트래픽 유형</th>
<th>포트 시작</th>
<th>포트 범위</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>오디오만</p></td>
<td><p>50020</p></td>
<td><p>20cm(8</p></td>
</tr>
<tr class="even">
<td><p>비디오</p></td>
<td><p>58000</p></td>
<td><p>20cm(8</p></td>
</tr>
<tr class="odd">
<td><p>응용 프로그램 공유</p></td>
<td><p>42000</p></td>
<td><p>20cm(8</p></td>
</tr>
<tr class="even">
<td><p>파일 전송</p></td>
<td><p>42020</p></td>
<td><p>20cm(8</p></td>
</tr>
</tbody>
</table>


위 표에서 클라이언트 포트 범위는 서버에 대해 구성 된 포트 범위의 하위 집합을 나타냅니다. 예를 들어 서버에서 응용 프로그램 공유가 포트 40803 ~ 49151를 사용 하도록 구성 되었습니다. 클라이언트 컴퓨터에서 응용 프로그램 공유는 포트 42000 ~ 42019를 사용 하도록 구성 됩니다. 이 역시 QoS를 보다 쉽게 관리할 수 있도록 하는 것입니다. 클라이언트 포트는 서버에서 사용 되는 포트의 하위 집합을 표시할 필요가 없습니다. 예를 들어 클라이언트 컴퓨터에서 응용 프로그램 공유를 구성 하는 데 사용할 수 있는, 즉 포트 1만 ~ 10019을 가정해 봅니다. 그러나 클라이언트 포트 범위를 서버 포트 범위의 하위 집합으로 만드는 것이 좋습니다.

또한 서버에서 응용 프로그램을 공유 하기 위해 포트를 별도로 설정 했지만 클라이언트에서 응용 프로그램을 공유할 8348 수 있도록 20 개의 포트만 설정 했습니다. 이 역시 아주 간단 하지만 그다지 빠르지는 않습니다. 일반적으로, 포트 범위에서 사용할 수 있는 100 포트가 있는 경우에는 사용 가능한 각 포트를 고려할 수 있으며,이는 해당 컴퓨터가 주어진 시간에 최대 100의 통신 세션에 참가할 수 있다는 것을 의미 합니다. 서버는 클라이언트 보다 더 많은 대화에 참여 하므로 클라이언트 보다 더 많은 포트를 서버에서 여는 것이 좋습니다. 클라이언트에서 응용 프로그램을 공유 하기 위해 20 개의 포트를 별도로 설정 하면 사용자가 지정 된 장치에서 20 개의 응용 프로그램 공유 세션에 참가 하 고 동시에 모두 사용할 수 있습니다. 이는 대다수의 사용자에 게 충분 하다 고 입증 해야 합니다.

위의 포트 범위를 회의 구성 설정의 전역 컬렉션에 할당 하려면 다음 비즈니스용 Skype 서버 관리 셸 명령을 사용 하면 됩니다.

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

또는 다음 명령을 사용하여 모든 회의 구성 설정에 대해 동일한 포트 범위를 할당합니다.

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

개별 사용자는 비즈니스용 Skype에서 로그 오프 한 다음 변경 내용을 실제로 적용 하기 전에 다시 로그온 해야 합니다.

> [!NOTE]  
> 명령 하나를 사용하여 클라이언트 미디어 포트 범위를 사용하도록 설정한 다음 해당 포트 범위를 할당할 수도 있습니다. 예를 들면 다음과 같습니다.<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a>Windows 10에서 실행 되는 클라이언트에 대 한 서비스 품질 정책 구성

비즈니스용 Skype 클라이언트에서 사용할 포트 범위를 지정 하는 것 외에도 클라이언트 컴퓨터에 적용 되는 별도의 서비스 정책 품질을 만들어야 합니다. 회의, 응용 프로그램 및 중재 서버에 대해 만들어지는 서비스 정책의 품질 정책은 클라이언트 컴퓨터에 적용 되지 않아야 합니다. 이 정보는 비즈니스용 Skype 클라이언트 및 Windows 10을 실행 하는 컴퓨터에만 적용 됩니다.

다음 예에서는이 포트 범위 집합을 사용 하 여 오디오 정책과 비디오 정책을 만듭니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>클라이언트 트래픽 유형</th>
<th>포트 시작</th>
<th>포트 범위</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>오디오만</p></td>
<td><p>50020</p></td>
<td><p>20cm(8</p></td>
</tr>
<tr class="even">
<td><p>비디오</p></td>
<td><p>58000</p></td>
<td><p>20cm(8</p></td>
</tr>
<tr class="odd">
<td><p>응용 프로그램 공유</p></td>
<td><p>42000</p></td>
<td><p>20cm(8</p></td>
</tr>
<tr class="even">
<td><p>파일 전송</p></td>
<td><p>42020</p></td>
<td><p>20cm(8</p></td>
</tr>
</tbody>
</table>

Windows 10 컴퓨터에 대 한 서비스 품질 오디오 정책을 만들려면 먼저 그룹 정책 관리를 설치한 컴퓨터에 로그온 합니다. **시작**을 클릭 하 고 **관리 도구**를 가리킨 다음 **그룹 정책 관리**를 클릭 하 여 그룹 정책 관리를 열고 다음 절차를 완료 합니다.

1.  그룹 정책 관리에서 새 정책을 만들 컨테이너를 찾습니다. 예를 들어 모든 클라이언트 컴퓨터가 Clients 라는 OU에 있는 경우 클라이언트 OU에 새 정책이 생성 됩니다.

2.  적절 한 컨테이너를 마우스 오른쪽 단추로 클릭 한 다음 **이 도메인에서 GPO를 만들어 여기에 연결**을 클릭 합니다.

3.  **새 GPO** 대화 상자에서 **이름** 상자에 새 그룹 정책 개체의 이름을 입력 하 고 **확인**을 클릭 합니다.

4.  새로 만든 정책을 마우스 오른쪽 단추로 클릭 한 다음 **편집**을 클릭 합니다.

5.  그룹 정책 관리 편집기에서 **컴퓨터 구성**, **Windows 설정을**차례로 확장 하 고 **정책 기반 QoS**를 마우스 오른쪽 단추로 클릭 한 후에 **새 정책 만들기**를 클릭 합니다.

6.  **정책 기반 QoS** 대화 상자의 열기 페이지에서 **이름** 상자에 새 정책의 이름을 입력 합니다. **DSCP 값 지정**을 선택하고 값을 **46**으로 설정합니다. **아웃바운드 스로틀 속도 지정**은 선택되지 않은 상태로 두고 **다음**을 클릭합니다.

7.  다음 페이지에서 **이 실행 파일 이름의 응용 프로그램만**선택 하 고 이름으로 **sc.exe** 를 입력 한 후 **다음**을 클릭 합니다. 이 설정은 비즈니스용 Skype 클라이언트에서 일치 하는 트래픽의 우선 순위를 지정 하는 것만 정책에 지시 합니다.

8.  세 번째 페이지에서 **원본 ip 주소** 와 **대상 ip 주소가** 모두 선택 되어 있는지 확인 하 고 **다음**을 클릭 합니다. 이러한 두 설정은 해당 패킷을 전송하는 컴퓨터(IP 주소) 및 패킷을 수신하는 컴퓨터(IP 주소)에 관계없이 패킷이 관리되도록 보장합니다.

9.  4페이지에서는 **이 QoS 정책이 적용되는 프로토콜 선택** 드롭다운 목록에서 **TCP 및 UDP**를 선택합니다. TCP (전송 제어 프로토콜) 및 UDP (사용자 데이터 그램 프로토콜)는 비즈니스용 Skype 서버 및 해당 클라이언트 응용 프로그램에서 가장 일반적으로 사용 하는 두 가지 네트워킹 프로토콜입니다.

10. **원본 포트 번호 지정** 제목 아래에서 **이 원본 포트 또는 범위부터**를 선택합니다. 포함된 텍스트 상자에는 오디오 전송에 예약된 포트 범위를 입력합니다. 예를 들어 포트 50020을 사용 하 여 오디오 트래픽에 대해 포트 50039을 예약한 경우이 형식으로 포트 범위를 입력 합니다 **50020:50039**. **마침**을 클릭합니다.

오디오에 대 한 QoS 정책을 만든 후에는 비디오에 대 한 두 번째 정책을 만들어야 합니다. 비디오용 정책을 만들려면 오디오 정책을 만들 때 수행한 것과 기본적으로는 같은 절차를 따르되 다음 항목을 대체합니다.

  - 다른 고유 정책 이름을 사용 합니다.

  - DSCP 값을 46이 아닌 **34**로 설정합니다. 이전에 설명 했 듯이, DSCP 값 34를 사용 하지 않아도 되는 경우에는 오디오에 사용 되는 것과 다른 DSCP 값을 할당 하기만 하면 됩니다.

  - 비디오 트래픽에 이전에 구성 된 포트 범위를 사용 합니다. 예를 들어 비디오용으로 58000에서 58019 까지의 포트를 예약한 경우 포트 범위를 this: **58000:58019**로 설정 합니다.

응용 프로그램 공유 트래픽을 관리 하기 위한 정책을 만들려는 경우 다음을 수행 합니다.

  - 다른 고유한 정책 이름 (예: **비즈니스용 Skype 서버 응용 프로그램 공유**)을 사용 합니다.

  - DSCP 값을 46이 아닌 **24**로 설정합니다. 다시 말해서,이 값은 24 일 필요는 없으며 오디오 및 비디오에 사용 되는 DSCP 값과는 다릅니다.

  - 비디오 트래픽에 이전에 구성 된 포트 범위를 사용 합니다. 예를 들어 응용 프로그램 공유를 위해 42000 ~ 42019 포트를 예약한 경우 포트 범위를 this: **42000:42019**로 설정 합니다.

파일 전송 정책의 경우:

  - 다른 고유한 정책 이름 (예: **비즈니스용 Skype 서버 파일 전송**)을 사용 합니다.

  - DSCP 값을 **14**로 설정 합니다. 다시 말하지만이 값은 14 일 필요는 없으며 단순히 고유한 DSCP 코드 여야 합니다.

  - 이전에 구성 된 응용 프로그램에 대 한 포트 범위를 사용 합니다. 예를 들어 응용 프로그램 공유를 위해 42020 ~ 42039 포트를 예약한 경우 포트 범위를 this: **42020:42039**로 설정 합니다.

새로 만든 정책은 클라이언트 컴퓨터에서 그룹 정책을 새로 고칠 때까지 적용 되지 않습니다. 그룹 정책은 일정한 간격에 따라 자체적으로 새로 고쳐지기는 하지만, 그룹 정책을 새로 고쳐야 하는 각 컴퓨터에서 다음 명령을 실행하면 그룹 정책을 강제로 즉시 새로 고칠 수 있습니다.

    Gpupdate.exe /force

이 명령은 관리자 자격 증명으로 실행 되는 모든 명령 창에서 실행할 수 있습니다. 관리자 자격 증명을 사용한 명령 창을 실행하려면 **시작**을 클릭하고 **명령 프롬프트**를 마우스 오른쪽 단추로 클릭한 후 **관리자 권한으로 실행**을 클릭합니다.

이러한 정책은 클라이언트 컴퓨터에 대 한 대상으로 지정 해야 합니다. 비즈니스용 Skype 서버를 실행 하는 서버에는 적용 되지 않아야 합니다.

네트워크 패킷이 적절한 DSCP 값으로 표시되도록 하려면 다음 절차를 완료하여 각 컴퓨터에서 새 레지스트리 항목도 만들어야 합니다.

1.  **시작**, **실행**을 차례로 클릭합니다.

2.  **실행** 대화 상자에 **regedit**를 입력 하 고 enter 키를 누릅니다.

3.  레지스트리 편집기에서 **\_HKEY\_로컬 컴퓨터**를 확장 하 고 **시스템**, **CurrentControlSet**, **서비스**를 차례로 확장 한 다음 **Tcpip**를 확장 합니다.

4.  **Tcpip**를 마우스 오른쪽 단추로 클릭하고 **새로 만들기**를 가리킨 다음 **키**를 클릭합니다. 새 레지스트리 키를 만든 후 **QoS**를 입력 하 고 enter 키를 눌러 키의 이름을 바꿉니다.

5.  **QoS**를 마우스 오른쪽 단추로 클릭하고 **새로 만들기**를 가리킨 다음 **문자열 값**을 클릭합니다. 새 레지스트리 값을 만든 후에는 **NLA 사용 안 함**을 입력 한 다음 enter 키를 눌러 값의 이름을 바꿉니다.

6.  **NLA 사용 안 함**을 두 번 클릭 합니다. **문자열 편집** 대화 상자에서 **값 데이터** 상자에 **1** 을 입력 하 고 **확인**을 클릭 합니다.

7.  레지스트리 편집기를 닫고 컴퓨터를 eboot.

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a>여러 네트워크 어댑터가 장착 된 컴퓨터에서 서비스 품질 구성

컴퓨터에 여러 네트워크 어댑터가 있는 경우 DSCP 값이 구성 된 값이 아닌 0x00으로 표시 되는 문제에 가끔씩 실행 될 수 있습니다. 이 문제는 일반적으로 하나 이상의 네트워크 어댑터에서 Active Directory 도메인에 액세스할 수 없는 컴퓨터에서 발생 합니다 (예: 이러한 어댑터가 개인 네트워크에 사용 되는 경우). 이와 같은 경우, DSCP 값은 도메인에 액세스할 수 있는 어댑터에 태그를 지정 하지만 도메인에 액세스할 수 없는 어댑터에 대해서는 태그를 지정 하지 않습니다.

도메인에 대 한 액세스 권한이 없는 어댑터를 포함 하 여 컴퓨터에 있는 모든 네트워크 어댑터의 DSCP 값에 태그를 설정 하려면 레지스트리에 값을 추가 하 고 구성 해야 합니다. 이 작업은 다음 절차에 따라 수행할 수 있습니다.

1.  **시작**, **실행**을 차례로 클릭합니다.

2.  **실행** 대화 상자에 **regedit**를 입력 하 고 enter 키를 누릅니다.

3.  레지스트리 편집기에서 **\_HKEY\_로컬 컴퓨터**를 확장 하 고 **시스템**, **CurrentControlSet**, **서비스**를 차례로 확장 한 다음 **Tcpip**를 확장 합니다.

4.  **QoS** 라는 이름의 레지스트리 키가 표시 되지 않으면 **Tcpip**를 마우스 오른쪽 단추로 클릭 하 고 **새로 만들기**를 가리킨 다음 **키**를 클릭 합니다. 새 키를 만든 후 **QoS**를 입력 하 고 enter 키를 눌러 키의 이름을 바꿉니다.

5.  **QoS**를 마우스 오른쪽 단추로 클릭하고 **새로 만들기**를 가리킨 다음 **문자열 값**을 클릭합니다. 새 레지스트리 값을 만든 후에는 **NLA 사용 안 함**을 입력 한 다음 enter 키를 눌러 값의 이름을 바꿉니다.

6.  **NLA 사용 안 함**을 두 번 클릭 합니다. **문자열 편집** 대화 상자에서 **값 데이터** 상자에 **1** 을 입력 하 고 **확인**을 클릭 합니다.

새 레지스트리 값을 만들고 구성한 후에는 컴퓨터를 다시 부팅 해야 변경 내용이 적용 됩니다.

## <a name="see-also"></a>참고 항목

[Windows 10에서 그룹 정책 개체 만들기](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
