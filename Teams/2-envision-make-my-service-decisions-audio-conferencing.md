---
title: 오디오 회의 서비스를 결정할 수 있도록 설정-Microsoft 팀
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 12/28/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 모임, 라이선스 및 사용 가능성, 회의 브리지 설정 구성, 전화 번호 취득 또는 전송, 테 넌 트 다이얼 플랜 선택에 대해 알아보세요.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6f7c36904aadf19802511979fa5e069b3c91035e
ms.sourcegitcommit: 2f8b9c7c8d20f2605d09cae4bbaeb10667f2ddea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/21/2019
ms.locfileid: "36182741"
---
# <a name="make-my-service-decisions"></a>내 서비스 결정 하기

오디오 회의의 기술 구현을 계획 하려면, 정의 된 비즈니스 요구 사항을 충족 하는 솔루션을 구현 하기 위해 조직 준비를 더 잘 하는 일련의 서비스 의사 결정을 미리 만들어야 합니다.

## <a name="audio-conferencing-in-teams"></a>팀의 오디오 회의

Microsoft 팀에서 필요한 오디오 회의 기능을 정의 하는 과정에서 첫 번째 단계는 최신 공개 로드맵을 평가 하 여 다음을 결정 하는 것입니다.

-   범위 내에서 사용자에 게 배포할 팀의 오디오 회의 기능입니다.

-   팀에서 오디오 회의에 대 한 사용자 기능 요구 사항이 필요 합니다.

-   최신 공개 로드맵에서 설명한 팀의 오디오 회의 기능이 배포의 시간 표시 막대 내에서 사용자, 기능 및 범위 요구 사항을 충족 하는지 확인 합니다.

> [!NOTE]
> 팀을 식별 하기 위한 최신 팀 로드맵입니다. 배포의 범위에 있는 오디오 회의 기능은에 <https://aka.ms/O365Roadmap>나와 있습니다.

## <a name="meetings-in-teams"></a>팀의 모임

팀에서는 HD 비디오, VoIP (voice over IP), PSTN 전화 접속 회의 옵션을 사용 하 여 온라인 모임을 예약 하 고 참가할 수 있는 기능을 제공 합니다.

회의는 비공개 모임 (초대 당사자만 참가할 수 있음) 또는 채널 모임 (해당 채널에 대 한 액세스 권한이 있는 모든 사용자에 대해 열림)으로 예약할 수 있으며, 사용자는 채널 내에서 즉석 모임을 시작할 수도 있습니다.

> [!NOTE]
> 팀에서 모임의 기능에 대 한 자세한 내용은 [Microsoft 365 로드맵을](https://aka.ms/O365Roadmap)참조 하세요.

모임 참가자는 유선전화 또는 휴대폰을 통해 유료 또는 무료 전화 접속 회의 브리지 전화 번호로 전화를 걸어 팀 모임에 참가할 수 있습니다. 또한 사용자는 음성 회의 서비스에서 "전화 걸기" 기능을 시작 하도록 하 여 전화 회의 브리지가 전화를 걸거나 (데이터 연결이 안정적이 지 않은 경우 유용) 모임 이끌이가 모임을 초대 하도록 할 수 있습니다. 참가자에 게 전화를 걸어 보세요.

> [!IMPORTANT]
> 팀의 오디오 회의는 타사의 ACPs (오디오 회의 공급자)를 지원 하지 않습니다.

<!--ENDOFSECTION-->

## <a name="availability-of-audio-conferencing"></a>오디오 회의 사용 가능 여부

팀에서 오디오 회의를 구현 하기 전에 오디오 회의 서비스의 사용 가능성을 [국가 및 지역 및 통화 요금제에 대해](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)자세히 검토 해야 합니다.

> [!IMPORTANT]
> 지역 조직에서 오디오 회의를 사용할 수 있도록 법률 제약 조건으로 인해, Office 365 구독에 대 한 계약은 오디오 회의 서비스가 상업적으로 사용할 수 있는 국가 및 지역에서 시작 해야 합니다.

조직이 음성 회의 서비스를 받을 자격이 있는지 확인 한 후에는 사용 가능한 국가 및 지역 목록에 따라 오디오 회의 서비스를 구현할 사용자 위치 또는 사무실의 목록을 컴파일해야 합니다.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|결정 사항|<ul><li>오디오 회의 서비스를 구현할 사용자 위치 또는 사무실을 결정 합니다.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|다음 단계|<ul><li>오디오 회의 서비스에 사용할 사용자 위치 또는 사무실을 문서화 합니다.</li></ul>|

> [!TIP]
> 다음은 오디오 회의 사이트 활용 목록 서식 파일의 예입니다.
> 
> |지사   |위치 |PSTN 컨퍼런스 서비스  |
> |---------|---------|---------|
> |하나의 Epping도로|오스트레일리아|오디오 회의|
> |100 Cyberport도로|홍콩 특별 행정구|레거시 PSTN 회의|
> |One Marina Royal|싱가포르|오디오 회의|
> |32 런던 다리의 거리|영국|오디오 회의|
> |39 Roosevelt Président du|프랑스|오디오 회의|

<!--ENDOFSECTION-->

## <a name="licensing-for-audio-conferencing"></a>오디오 회의 라이선스

[오디오 회의 라이선스](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) 는 Office 365 E5 구독 계획의 일부로 또는 Office 365 E1 또는 Office 365 E3 구독 계획에 대 한 추가 기능 서비스로 사용할 수 있습니다.

> [!NOTE]
> 팀의 PSTN 또는 전화 접속 회의는 타사의 ACPs (오디오 회의 공급자)를 지원 하지 않습니다.
> <br>지금 비즈니스용 Skype Online PSTN 회의를 사용 하 고 있는 경우 팀에서 오디오 회의를 즉시 활용할 수 있습니다.

무료 회의 브리지 전화 번호를 제공 하 고 국제 전화 번호로 회의 전화 걸기를 지원 하려면 조직의 [통신 크레딧을](what-are-communications-credits.md) 설정 해야 합니다.

> [!IMPORTANT]
> 일부 국가는 무료 회의 브리지 전화 번호로만 서비스를 제공 합니다. 이러한 국가에서 전화 접속을 지원 하려면 통신 크레딧을 사용 해야 합니다.

통신 크레딧을 구현할 때 첫 번째로 고려해 야 할 사항은 구매 하고자 하는 초기 자금의 양을 결정 하는 것입니다. 조직에서 자동 충전을 사용 하기로 선택한 경우에는 트리거 금액 (최저 금액)과 자동 충전 금액을 결정 해야 합니다. 실제 사용에 따라 자동 충전 금액이 결정 됩니다. 시간에 따른 통신 크레딧 사용량을 모니터링 하 고 필요에 따라 충전 금액을 조정 해야 합니다.

[여기](what-are-communications-credits.md)에서는 통신 크레딧에 대해 자세히 알아볼 수 있습니다.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|결정 사항|<ul><li>조직에서 이미 필요한 오디오 회의 라이선스를 구입 하지 않은 경우 기존 Office 365 구독을 단계별로 진행 하거나 오디오 회의 추가 기능 라이선스를 구입 하 여 오디오 회의 라이선스를 취득할 것인지 여부를 결정 합니다.</li><li>오디오 회의 구현에 대 한 통신 크레딧이 필요한 지 여부를 결정 합니다. 그렇다면 구매할 초기 금액을 결정 합니다. 해당 되는 경우 트리거 금액 및 자동 충전 금액을 결정 합니다.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|다음 단계|<ul><li>오디오 회의 라이선스를 할당할 사용자를 문서화 합니다.</li><li>커뮤니케이션 크레딧 계획 문서화 (초기 금액, 트리거 금액, 자동 충전 금액)</li></ul>|

> [!TIP]
> 다음 예제를 사용 하 여 오디오 회의 사용자에 대 한 라이선스 할당 목록을 문서화할 수 있습니다.
> 
> |클릭할  |지사  |Office 365 라이선스  |
> |---------|---------|---------|
> |Adele Vance|하나의 Epping도로|Office 365 E5|
> |정 Wilber|하나의 Epping도로|Office 365 E3, 오디오 회의 추가 기능|
> |이혜준 씨 Walters|하나의 Epping도로|Office 365 E3, 오디오 회의 추가 기능|
> |Christie cl|One Marina Royal|Office 365 E3, 오디오 회의 추가 기능|
> |Debra Berger|One Marina Royal|Office 365 E5|
> |정영일 Gu-in&platform|One Marina Royal|Office 365 E5|
> |Emily Braun|32 런던 다리의 거리|Office 365 E5|
> |Lidia Holloway|32 런던 다리의 거리|Office 365 E5|
> |세인트루이스의 Lahr|32 런던 다리의 거리|Office 365 E5|
> |Marcel Beauchamp|39 Roosevelt Président du|Office 365 E3, 오디오 회의 추가 기능|
> |Rachelle Cormier|39 Roosevelt Président du|Office 365 E5|
> |Isabell Potvin|39 Roosevelt Président du|Office 365 E3, 오디오 회의 추가 기능|

<br>

> [!TIP]
> 통신 제작진 계획 번호는 다음과 같이 문서화할 수 있습니다.
>
> |         |         |
> |---------|---------|
> |초기 금액|$1000|
> |트리거 금액|$400|
> |자동 충전 금액|TBA|
> 
<!--ENDOFSECTION-->

## <a name="conference-bridge-phone-numbers"></a>컨퍼런스 브리지 전화 번호

Office 365의 오디오 회의 서비스에는 다음이 포함 됩니다.

-   여러 회의 브리지 전화 번호 유형 (유료 및 무료)

-   여러 회의 브리지 전화 번호 범주 (전용 및 공유)

-   회의 브리지에 대 한 여러 언어 지원 (기본 및 보조)

-   테 넌 트의 기본 전화 번호

> [!NOTE]
> 전용 회의 브리지 전화 번호는 해당 라이선스의 수에 따라 테 넌 트 당 가져올 수 있는 전화 번호의 한계를 계산 합니다. 무료 회의 브리지 전화 번호에는 통신 크레딧이 필요 합니다.

기존 컨퍼런스 브리지 전화 번호를 오디오 회의 서비스에 이전 해야 하는 경우, 예를 들어 국가 관련 요구 사항이 충족 되는 경우 기존 컨퍼런스 브리지 전화 번호를 Microsoft에 양도할 수 있습니다.

> [!NOTE]
> 전화 번호를 Microsoft로 전송 하는 것의 복잡도는 국가 또는 지역, 통신 회사, 관련 회로 수 및 기타 다양 한 요인에 따라 크게 달라 집니다. 현재 공급자와 협력 하 여 일정을 충족 시킬 수 있을 만큼 일찍 프로세스를 시작 하는 데 걸리는 시간을 조사 하세요.

회의 브리지 전화 번호에 대 한 자세한 내용을 보려면 다음 문서를 검토 하세요.

-   [Microsoft 팀을 위한 오디오 회의 설정](set-up-audio-conferencing-in-teams.md)

-   [오디오 회의를 위한 전화 번호](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/phone-numbers-for-audio-conferencing)

-   [서비스 전화 번호 가져오기](getting-service-phone-numbers.md)

-   [Office 365에 전화 번호 전송](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|결정 사항|<ul><li>조직에 전용 회의 브리지 전화 번호가 필요한 지 여부를 결정 합니다.</li><li>오디오 회의 구현을 위해 범위 내에서 사용자 위치 또는 사무실에 대해 전용 회의 브리지 전화 번호를 구하는 방법을 결정 합니다 (즉, Microsoft에서 얻거나 기존 전화 번호를 전송 하는 경우).</li><li>Microsoft에서이를 받도록 선택 하는 경우 오디오 회의 구현의 범위 내에서 사용자 위치 또는 사무실에 대해 사용할 방법을 결정 합니다 (양식 제출 또는 자동).</li><li>각 전용 회의 브리지 전화 번호에 대해 설정할 언어 기본 설정을 결정 합니다.</li><li>테 넌 트 기본 회의 브리지 전화 번호를 결정 합니다.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|다음 단계|<ul><li>전화 번호 획득을 위한 마스터 요금제를 사용 하 여 오디오 회의 구현 범위에서 각 사용자 위치 또는 사무실에 대 한 전화 번호를 구하는 방법을 자세히 설명 합니다.</li><li>해당 하는 경우, 각 위치 또는 사무실에 대 한 하나의 양식으로 새 전화 번호 요청 양식을 작성 합니다.</li><li>자세한 회의 브리지 전화 번호 구성 (공유 및 전용 회의 브리지 전화 번호, 각 전용 회의 브리지 전화 번호에 대 한 언어 기본 설정, 테 넌 트 기본 회의 브리지 전화 번호)을 문서화 합니다.</li></ul>|

아래에는 회의 브리지 세부 정보를 수집 하는 데 사용할 수 있는 서식 파일의 예가 나와 있습니다.

> [!TIP]
> 다음은 회의 브리지 세부 정보를 수집 하는 서식 파일의 예입니다.
> 
> |지사   |브리지 번호 획득 및 브리지 종류 |다리 번호  |브리지 언어|
> |---------|---------|---------|---------|
> |하나의 Epping도로|신규, 전용 취득|TBA|영어 (오스트레일리아)|
> |One Marina Royal|새로운 공유 취득|TBA|영어 (미국), 중국어 (간체, PRC)|
> |32 런던 다리의 거리|포트 기존 전용|+ 44 20 7946 0001|영어 (영국)|
> |39 Roosevelt Président du|신규, 전용 취득|TBA|프랑스어 (프랑스), 영어 (영국)|

<!--ENDOFSECTION-->

## <a name="conference-bridge-settings"></a>회의 브리지 설정

사용자 환경을 더욱 세밀 하 게 조정 하기 위해 오디오 회의 모임 참가 (모임 입력 및 종료 알림과 발신자 이름 기록), 모임 이끌이의 PIN 길이, 전자 메일 알림:에 대 한 조직 전체 옵션을 구성할 수 있습니다.

-   모임 입력 및 종료 알림은 기록 된 이름, 전화 번호, 톤 형식으로 제공 됩니다.

-   PIN 길이는 기본적으로 5 자리 PIN을 사용 하 여 4 ~ 12 자리 숫자로 구성할 수 있습니다.

-   오디오 회의 라이선스의 사용 또는 기타 관리 기반 변경 사항에 따라 전송 되는 알림 전자 메일은 기본적으로 사용 하도록 설정 됩니다. 이 기능을 사용 하지 않도록 설정 하 고 조직의 사용자 통신을 제어할 수 있습니다.

오디오 회의 라이선스를 할당 한 사용자의 경우 오디오 회의 좌표에 표시 되는 기본 유료/무료 번호를 사용 하도록 구성할 수 있습니다.

-   테 넌 트 수준 기본값입니다.

-   자동으로 지정 된 회의 브리지 전화 번호입니다.

-   각 사용자에 대해 수동으로 구성한 회의 브리지 전화 번호입니다.

사용자 특정 회의 브리지 전화 번호는 일반적으로 사용자가 배포 되는 글로벌 또는 전국 조직에 유용 하며, 모임 초대에 기본 회의 브리지 전화 번호로 현지 번호를 제공 해야 합니다.

다른 도시 또는 해외에 참가 하는 참가자는 테 넌 트 수준에서 구성 된 추가 번호를 조회할 수 있지만, 이러한 번호는 모임 초대에 직접 표시 되지 않습니다. 모임 초대는 참가자를 **팀 전화 접속 번호** 페이지로 받아서 해당 위치에 가장 가까운 회의 브리지 전화 번호를 조회 하는 링크를 제공 합니다.

또한 인증 되지 않은 발신자를 허용 하기 전에 모임 이끌이가 모임을 시작 하도록 요청 하거나 인증 되지 않은 호출자가 모임을 시작 하도록 허용할 것인지 여부에 관계 없이 각 개별 모임 이끌이가 인증 되지 않은 호출자를 처리 하는 방식을 구성할 수 있습니다. .

또한 각 사용자에 게 추가 구성을 적용 하 여 무료 회의 브리지 전화 번호 사용을 제어 하 고 회의에서 전화를 걸 수 있습니다.

> [!NOTE]
> 이러한 비용 관련 컨트롤은 현재 미리 보기 고객만 사용할 수 있습니다. 미리 보기 프로그램에서 조직을 등록할 수 있습니다 https://www.skypepreview.com.

이러한 컨트롤을 사용 하면 모임 이끌이가 구성한 모임에 대해 무료 전화 회의 브리지 전화 번호를 제공할 수 있는지 여부와 참가자가 자신이 구성한 모임에서 전화를 걸 수 있는지 여부를 결정할 수 있습니다. 전화 걸기 제어 수준은 전체 전화 걸기를 차단 하 여 국내 번호에 대 한 전화 걸기를 허용 하 고 국내 번호와 국제 전화를 모두 사용할 수 있습니다.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|결정 사항|<ul><li>조직에 입력 및 종료 알림이 필요한 지 여부를 결정 하 고, 구현 될 알림의 유형 (예, 톤, 전화 번호 또는 기록 된 이름)을 선택 합니다.</li><li>조직의 보안 요구 사항을 충족 하는 오디오 회의 PIN 길이를 결정 합니다.</li><li>조직에서 오디오 회의 서비스와 관련 된 사용자 통신을 제어 하려는 지 여부를 결정 합니다.</li><li>각 모임 이끌이에게 할당할 회의 브리지 전화 번호를 결정 합니다.</li><li>일부 모임 이끌이가 모임에 대해 무료 전화 회의 브리지 전화 번호를 사용 해야 하는지 여부를 결정 합니다.</li><li>일부 모임 이끌이가 인증 되지 않은 호출자가 모임을 시작 하도록 허용 해야 하는지 여부를 결정 합니다.</li><li>일부 모임 이끌이가 회의 전화 걸기를 제어 해야 하는지 여부를 결정 합니다.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|다음 단계|<ul><li>세부 회의 브리지 설정 (입력 및 종료 알림, PIN 길이, 구성 변경 전자 메일 알림) 문서화</li><li>각 모임 이끌이에게 할당할 회의 브리지 전화 번호와 인증 되지 않은 발신자에 대 한 정책, 무료 및 전화 걸기 컨트롤에 대 한 정책을 제어 하는 해당 설정을 문서화 합니다.</li></ul>|

> [!TIP]
> 다음 예제와 같이 회의 브리지 설정을 문서화할 수 있습니다.
> 
> |         |         |
> |---------|---------|
> |모임 입력 및 종료 알림 사용|수|
> |입력/종료 알림 유형|신호음이|
> |모임에 참가 하기 전에 호출자에 게 자신의 이름을 기록 하도록 요청|비활성화|
> |핀 길이|5mb|
> |전화 접속 설정이 변경 되 면 자동으로 사용자에 게 전자 메일 보내기|비활성화|

<br>

> [!TIP]
> 다음 예제를 사용 하 여 오디오 회의 사용자에 대 한 회의 브리지 설정 할당 목록을 문서화할 수 있습니다.
>
> |클릭할  |지사  |기본 유료 전화 번호  |기본 무료 전화 번호  |무료 통화 허용  |인증 되지 않은 호출자가 대기실 건너뛰기  |전화 회의 종료  |
> |---------|---------|---------|---------|---------|---------|---------|
> |Adele Vance|하나의 Epping도로|TBA|TBA|'|수|국제 및 국내|
> |정 Wilber|하나의 Epping도로|TBA|TBA|아니요|비활성화|허용 되지 않음|
> |이혜준 씨 Walters|하나의 Epping도로|TBA|TBA|아니요|비활성화|허용 되지 않음|
> |Christie cl|One Marina Royal|TBA|TBA|'|비활성화|국내|
> |Debra Berger|One Marina Royal|TBA|TBA|'|수|국내|
> |정영일 Gu-in&platform|One Marina Royal|TBA|TBA|'|수|국내|
> |Emily Braun|32 런던 다리의 거리|+ 44 20 7946 0001|TBA|'|수|허용 되지 않음|
> |Lidia Holloway|32 런던 다리의 거리|+ 44 20 7946 0001|TBA|'|비활성화|허용 되지 않음|
> |세인트루이스의 Lahr|32 런던 다리의 거리|+ 44 20 7946 0001|TBA|'|비활성화|허용 되지 않음|
> |Marcel Beauchamp|39 Roosevelt Président du|TBA|TBA|아니요|비활성화|국내|
> |Rachelle Cormier|39 Roosevelt Président du|TBA|TBA|'|수|국제 및 국내|
> |Isabell Potvin|39 Roosevelt Président du|TBA|TBA|아니요|비활성화|국내|

<!--ENDOFSECTION-->

## <a name="manage-cloud-voice-telephone-numbers"></a>클라우드 음성 전화 번호 관리

오디오 회의 구현의 경우 새 전화 번호를 취득 하거나 기존 전화 번호를 양도/이식 하도록 선택할 수 있습니다.

사용자가 익숙한 방법으로 전화를 걸 수 있도록 허용 (예: 시내 통화를 위해 지역 코드를 생략 하거나, 국내 통화에 대 한 국가 코드를 생략 하거나), 전화 회의를 할 때 시외 전화 걸기를 사용 하는 경우 사용자 지정 다이얼 플랜을 구성할 수 있습니다. 사용자에 게 할당 합니다.

## <a name="acquire-new-telephone-numbers"></a>새 전화 번호 취득

Microsoft 클라우드 음성 솔루션 내의 두 가지 전화 번호 유형은 다음과 같습니다.

-   조직의 사용자에 게 할당할 수 있는 구독자 (사용자) 번호입니다.

-   유료 및 무료 서비스 번호로 사용할 수 있는 서비스 번호로, 가입자 번호 보다 높은 동시 통화 용량을 가지 며 오디오 회의, 자동 전화 교환 또는 통화 대기열 등의 서비스에 할당할 수 있습니다.

이러한 유형의 전화 번호에 대 한 자세한 내용은 [통화 요금제에 사용 되는 다른 종류의 전화 번호](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/different-kinds-of-phone-numbers-used-for-calling-plans)를 참조 하세요.

얻을 수 있는 총 전화 번호 수는 전화 번호 유형 및 사용자에 게 할당 된 라이선스 수에 따라 달라 집니다.

서비스 번호와 함께 제공 되는 경우 오디오 회의 구현을 신중 하 게 계획 해야 합니다. 비즈니스에 전용 회의 브리지 전화 번호가 필요한 지 평가 합니다. 그렇지 않은 경우 조직에서 공유 컨퍼런스 브리지 전화 번호를 사용 하도록 선택할 수 있습니다.

구할 수 있는 총 전화 번호 수에 대 한 자세한 내용은 [받을 수 있는 전화 번호](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/how-many-phone-numbers-can-you-get) 수를 참조 하세요.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|결정 사항|<ul><li>Microsoft에서 새 전화 번호를 취득할 사용자 위치 또는 사무실을 결정 합니다.</li><li>Microsoft에서 가져올 전화 번호 유형을 결정 합니다.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|다음 단계|<ul><li>Microsoft에서 새 전화 번호를 얻을 수 있는 사용자 위치 또는 사무실을 문서화 합니다.</li><li>Microsoft에서 얻을 수 있는 전화 번호 유형을 문서화 합니다.</li></ul>|

## <a name="transfer-existing-telephone-numbers"></a>기존 전화 번호 전송

조직에서 Microsoft에 기존 전화 번호를 전송 (또는 포트) 하려는 경우 Microsoft에 포트 주문 요청을 제출 하 여이 작업을 수행할 수 있습니다.

모든 기존 전화 번호를 한 번에 (전체 포트) 전송할 수 있으며, 일부 지역에서는 기존 전화 번호의 하위 집합을 전송할 수 있습니다 (부분 포트). 일부 포트는 전화 접속 회의 브리지를 오디오 회의 서비스로만 이동 하려는 경우에 유용할 수 있습니다.

단일 포트 주문은 전화 번호만 단일 전화 번호 유형 으로만 전송할 수 있습니다. 일부 전화 번호를 구독자 번호와 서비스 번호로 전송 해야 하는 경우 먼저 Microsoft에 전송을 완료 한 다음 숫자가 Microsoft의 제어권 내에서 바로 변환을 수행 하는 것이 좋습니다.

다른 방법으로 부분 포트가 지원 되는 경우 한 번에 하나의 포트 요청을 여러 포트 요청에 제출할 수 있습니다. 그러나이 대체 접근 방법은 기존 통신 서비스 공급자와 계약을 연장 합니다.

전화 번호 포팅는 복잡 한 주제 이며, 관계자의 기대치를 철저 하 게 관리 하 고 적절 한 계획을 수립 해야 합니다. 자세히 알아보려면 다음 문서를 참조 하세요.

-   [Office 365로 전화 번호 전송](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)

-   [전화 번호 전송 일반적인 질문](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transferring-phone-numbers-common-questions)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|결정 사항|<ul><li>기존 전화 번호가 Microsoft에 전송 되는 사용자 위치 또는 사무실을 결정 합니다.</li><li>Microsoft로 전송할 전화 번호 유형을 결정 합니다.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|다음 단계|<ul><li>기존 전화 번호가 Microsoft에 전송 되는 사용자 위치 또는 사무실을 문서화 합니다.</li><li>Microsoft로 전송할 전화 번호 유형을 문서화 합니다.</li></ul>|

<!--ENDOFSECTION-->

## <a name="dial-plans"></a>다이얼 플랜

Office 365의 전화 시스템 기능에 있는 다이얼 플랜은 전화 걸기 전화 번호를 대체 형식 (일반적으로 E. \ 164 형식)으로 변환 하는 표준화 규칙 집합으로, 통화 승인 및 통화 라우팅을 위해 사용할 수 있습니다. 오디오 회의 서비스는 전화 시스템에서 사용 하는 것과 같은 기능을 활용 하 여 컨퍼런스 전화 걸기 시나리오에서 해당 전화 번호를 번역 합니다 (예: PSTN을 통해 참가자를 초대 하 고 "전화 걸기" 기능).

Office 365의 전화 시스템 기능에는 다음과 같은 두 가지 유형의 다이얼 플랜이 있습니다.

-   **서비스 다이얼 플랜:** Office 365 사용 위치를 기반으로 사용자에 게 적용 되는 기본 다이얼 플랜으로, 수정할 수 없습니다.

-   **테 넌 트 다이얼 플랜:** 이는 테 넌 트 내에서 사용자 지정 가능한 다이얼 플랜으로, 다음 두 가지 형식으로 구분 됩니다.

    -   **테 넌 트-글로벌 다이얼 플랜:** 테 넌 트의 모든 사용자에 게 적용 되는 다이얼 플랜입니다.

    -   **테 넌 트-사용자 다이얼 플랜:** 특정 사용자 에게만 적용 되는 다이얼 플랜입니다.

사용자에 게 할당 된 유효 다이얼 플랜은 서비스 다이얼 플랜 (사용자의 Office 365 사용 위치에 기반) 및 테 넌 트 다이얼 플랜 (테 넌 트 전역 다이얼 플랜 또는 테 넌 트-사용자 다이얼 플랜 중 하나가 될 수 있음)의 조합입니다.

![표에는 서비스 및 테 넌 트 다이얼 플랜의 세 가지 조합이 나와 있습니다.] (media/audio_conferencing_image8.png "표에는 서비스 및 테 넌 트 다이얼 플랜의 세 가지 조합이 나와 있습니다.")

> [!Important]
> 각 테 넌 트 다이얼 플랜에는 최대 25 개의 정규화 규칙이 있을 수 있습니다. 따라서 서비스 다이얼 플랜의 일부로 이미 사용할 수 있는 정규화 규칙을 복제 하지 않는 것이 중요 합니다.

다이얼 플랜에 대 한 자세한 내용은 [다이얼 플랜 이란?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans) 를 참조 하세요.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|결정 사항|<ul><li>조직에 사용자 지정 다이얼 플랜 (비즈니스 요구 사항, 채택 요구 사항 등)이 필요한 지 여부를 결정 합니다.</li><li>해당 하는 경우 사용자 지정 다이얼 플랜에 대 한 요구 사항을 지원 하도록 테 넌 트 다이얼 플랜 (테 넌 트 전역 또는 테 넌 트 사용자)의 범위를 결정 합니다.</li><li>해당 하는 경우 클라우드 음성 구현의 범위 내에서 사용자 위치 또는 사무실을 지원 하기 위해 만들 테 넌 트 다이얼 플랜을 결정 합니다.</li><li>해당 하는 경우, 각 사용자에 대해 사용자 지정 다이얼 플랜 및 테 넌 트 다이얼 플랜을 할당 해야 하는지 결정 합니다.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|다음 단계|<ul><li>클라우드 음성 구현의 일부로 구성할 사용자 지정 다이얼 플랜 및 관련 정규화 규칙을 문서화 합니다.</li><li>각 사용자에 대해 사용자 지정 다이얼 플랜 및 테 넌 트 다이얼 플랜을 할당할 사용자를 문서화 합니다.</li></ul>|

> [!TIP]
> 프로젝트에 해당 되는 경우 다음 서식 파일을 사용 하 여 테 넌 트 다이얼 플랜 구성을 문서화할 수 있습니다.
> 
> |테 넌 트 다이얼 플랜 이름<br>_설명_  |정규화 규칙 이름<br>_설명_  |패턴이<br>변환용<br>IsInternalExtension  |
> |---------|---------|---------|
> |**AU-NSW-NorthRyde-OER**<br>_하나의 Epping도로 북쪽 Ryde, NSW, AU 다이얼 플랜_|**AU-NSW-NorthRyde-OER-내부**<br>_하나의 Epping도로 된 사무실, 북쪽 Ryde, NSW, 오스트레일리아의 내부 번호 (x7000-x7999)_|^ (7 \ d{3}) $<br>+ 6125550 $1<br>False|
> ||**AU-NSW-로컬**<br>_NSW의 현지 번호 정규화 (오스트레일리아)_|^ ([2-9] \d{7}) $<br>+ 612 $1<br>해제|
> ||**AU-TollFree**<br>_오스트레일리아에 대 한 무료 전화 번호 정규화_|^ (1 [38] \d{4,8}) \d * $<br>+ 61 $1<br>해제|
> ||**AU-서비스**<br>_오스트레일리아에 대 한 서비스 번호 정규화_|^ (000\|1 [0125] \d{1,8}) $<br>$1<br>해제|
> |**SG-싱가포르-OMB**<br>_OMB 싱가포르, SG 다이얼 플랜_|**SG-OMB-내부**<br>_OMB office, 싱가포르의 내부 번호 (x8000 a € "x8999)_|^ (8 \ d{3}) $<br>+ 656888 $1<br>False|
> ||**SG-TollFree**<br>_싱가포르의 무료 번호 정규화_|^ (1? 800 \ d{7}) \d * $<br>+ 65 $1<br>해제|
> ||**SG-서비스**<br>_싱가포르의 서비스 번호 정규화_|^ (1 \ d{3,4}\|9 \ d{2}) $<br>$1<br>해제|
> |**FR-FR-Issy-39qdPR**<br>_39 Président Roosevelt Issy-les-Moulineaux, 프랑스 다이얼 플랜_|**FR-39qdPR-내부**<br>_39 x7999 Président Roosevelt office, Issy-x7000-Moulineaux, 프랑스에 대 한 내부 번호 (a €)_|^ (7 \ d{3}) $<br>+ 3319999 $1<br>False|
> ||**FR-FR-TollFree**<br>_프랑스에 대 한 무료 전화 번호 정규화_|^ 0? (80 \ d{7}) \d * $<br>+ 33 $1<br>해제|
> ||**FR-서비스**<br>_프랑스에 대 한 서비스 번호 정규화_|^ (1 \ d{1,2}\|11 [68] \d{3}\|10 \ d{2}\|3 \ d{3}) $<br>$1<br>해제|

<br>

> [!TIP]
> 다음 예제 서식 파일을 활용 하 여 프로젝트를 지원 하기 위해 다이얼 플랜 배정을 문서화할 수 있습니다.
>
> |클릭할  |지사  |다이얼 플랜 유형  |다이얼 플랜 이름  |
> |---------|---------|---------|---------|
> |Adele Vance|하나의 Epping도로|테 넌 트 다이얼 플랜|AU-NSW-NorthRyde-OER|
> |정 Wilber|하나의 Epping도로|테 넌 트 다이얼 플랜|AU-NSW-NorthRyde-OER|
> |이혜준 씨 Walters|하나의 Epping도로|테 넌 트 다이얼 플랜|AU-NSW-NorthRyde-OER|
> |Christie cl|One Marina Royal|테 넌 트 다이얼 플랜|SG-싱가포르-OMB|
> |Debra Berger|One Marina Royal|테 넌 트 다이얼 플랜|SG-싱가포르-OMB|
> |정영일 Gu-in&platform|One Marina Royal|테 넌 트 다이얼 플랜|SG-싱가포르-OMB|
> |Emily Braun|32 런던 다리의 거리|서비스 다이얼 플랜|해당 없음|
> |Lidia Holloway|32 런던 다리의 거리|서비스 다이얼 플랜|해당 없음|
> |세인트루이스의 Lahr|32 런던 다리의 거리|서비스 다이얼 플랜|해당 없음|
> |Marcel Beauchamp|39 Roosevelt Président du|테 넌 트 다이얼 플랜|FR-FR-Issy-30qdPR|
> |Rachelle Cormier|39 Roosevelt Président du|테 넌 트 다이얼 플랜|FR-FR-Issy-30qdPR|
> |Isabell Potvin|39 Roosevelt Président du|테 넌 트 다이얼 플랜|FR-FR-Issy-30qdPR|

<!--ENDOFSECTION-->

## <a name="document-service-decisions"></a>문서 서비스 결정 

이 문서의 이전 섹션에 나와 있는 정보를 사용 하 여 서비스 의사 결정을 문서화할 수 있습니다. 일반적으로이 설명서에는 다음과 같은 주요 섹션이 포함 됩니다.

-   오디오 회의 서비스 사이트 지원 목록

-   오디오 회의 모임 이끌이의 라이선스 할당 목록

-   통신 제작진 번호 계획

-   회의 브리지 세부 정보

-   회의 브리지 설정

-   회의 브리지 설정 지정

-   전화 번호 취득 계획

-   테 넌 트 다이얼 플랜

-   다이얼 플랜 배정

<!--ENDOFSECTION-->