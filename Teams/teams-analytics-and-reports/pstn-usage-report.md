---
title: Microsoft Teams PSTN 사용 현황 보고서
author: CarolynRowe
ms.author: crowe
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Microsoft Teams 관리 센터에서 Teams PSTN 사용 현황 보고서를 사용하여 조직의 통화 및 오디오 회의 사용에 대한 개요를 가져오는 방법을 알아봅니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-voice
ms.openlocfilehash: 1539f679225334f71855300a54c4fba950ddd8f8
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267633"
---
# <a name="microsoft-teams-pstn-usage-report"></a>Microsoft Teams PSTN 사용 현황 보고서

Microsoft Teams 관리 센터의 Teams PSTN(공중 전화망) 사용 현황 보고서는 조직의 통화 및 오디오 회의 활동에 대한 개요를 제공합니다. 전화 통신 사업자로 Microsoft를 사용하는 경우 통화 플랜에 대한 자세한 통화 활동을 볼 수 있으며, 자체 전화 통신 사업자를 사용하는 경우 직접 라우팅을 볼 수 있습니다.

**통화 플랜** 탭에는 사용자가 인바운드 및 아웃바운드 PSTN 호출에 소요된 시간(분) 및 이러한 호출 비용을 포함한 정보가 표시됩니다. **직접 라우팅** 탭에는 SIP 주소와 통화 시작 및 종료 시간을 포함한 정보가 표시됩니다. 이 보고서의 정보를 사용하여 조직의 PSTN 사용에 대한 인사이트를 얻고 비즈니스 의사 결정을 조사, 계획 및 결정하는 데 도움을 줍니다.

> [!NOTE]
> 텔스트라 또는 소프트뱅크 통화 플랜이 있는 경우 PSTN 사용 현황 보고서에 통화 세부 정보 레코드가 표시되지 않습니다. 보고 요구 사항은 텔스트라 또는 소프트뱅크에 문의하세요. 

## <a name="view-the-pstn-usage-report"></a>PSTN 사용 현황 보고서 보기

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **분석 & 보고서** > **사용 현황 보고서를** 클릭합니다. **보고서 보기** 탭의 **보고서** 아래에서 **PSTN 사용 현황 보고서를** 선택합니다.
2. **날짜 범위** 에서 미리 정의된 범위 7 또는 28일을 선택하거나 사용자 지정 범위를 설정한 다음 **보고서 실행을** 선택합니다.

## <a name="interpret-the-report"></a>보고서 해석

### <a name="calling-plans"></a>통화 플랜

   ![관리 센터의 통화 플랜 PSTN 사용 보고서 보고서 스크린샷](../media/teams-reports-pstn-usage-calling-plans-with-callouts.png)![번호가 매겨진 설명선이 있는 Microsoft Teams 관리 센터의 PSTN 사용 현황 보고서 스크린샷](../media/teams-reports-pstn-usage-calling-plans-with-callouts.png#lightbox)

|설명선 |설명  |
|--------|-------------|
|**1**   |지난 7일, 28일 동안의 추세 또는 설정한 사용자 지정 날짜 범위에 대한 보고서를 볼 수 있습니다. |
|**2**   |각 보고서에는 생성된 날짜가 있습니다. 보고서는 일반적으로 활동 시간으로부터 24~48시간의 대기 시간을 반영합니다. |
|**3**   |X축은 특정 보고서에 대해 선택한 날짜 범위입니다. Y축은 선택한 기간 동안의 총 호출 수입니다. <br>지정된 날짜의 점 위로 마우스를 가져가서 해당 날짜의 총 호출을 확인합니다.  |
|**4**   |이 테이블에서는 호출당 PSTN 사용량을 분석합니다. <ul><li>**UTC(타임스탬프는** 호출이 시작된 시간입니다.</li><li>**표시 이름은** 사용자의 표시 이름입니다. 표시 이름을 클릭하여 Microsoft Teams 관리 센터의 사용자 설정 페이지로 이동합니다.</li><li>**사용자** 이름은 사용자의 로그인 이름입니다.</li><li>**전화 번호** 는 인바운드 통화에 대한 전화를 받은 번호 또는 아웃바운드 통화에 대해 전화를 건 번호입니다.</li><li>**통화 유형** 은 통화가 PSTN 아웃바운드 또는 인바운드 통화인지 여부와 사용자가 수행한 통화 또는 오디오 회의와 같은 통화 유형입니다. 표시되는 호출 유형은 다음과 같습니다.<br><br>**Teams 사용자 통화 유형**<ul><li>**user_in** - 사용자가 인바운드 PSTN 호출을 받았습니다.</li><li>**user_out** - 사용자가 아웃바운드 PSTN 호출을 수행했습니다.</li><li>**user_out_conf** - 사용자가 3방향 전화 회의와 같은 두 명 이상의 PSTN 참가자를 통화에 추가했습니다.</li><li>**user_out_transfer** - 사용자가 PSTN 번호로 통화를 전송했습니다.</li><li>**user_out_forwarding** - 사용자가 PSTN 번호로 호출을 전달했습니다.</li><li>**conf_in** - 오디오 회의 브리지에 대한 인바운드 호출</li><li>**conf_out** - 일반적으로 회의에 PSTN 번호를 추가하기 위한 오디오 회의 브리지의 아웃바운드 호출</li><li>**unassigned_in** - 통화 플랜을 통해 할당되지 않은 번호로 인바운드 PSTN 호출</li></ul><br>**Teams 봇 호출 유형**<ul><li>**ucap_in** - 자동 전화 교환 또는 통화 큐와 같은 Teams 봇에 대한 인바운드 PSTN 호출</li><li>**ucap_out** - 자동 전화 교환 또는 통화 큐와 같은 Teams 봇의 아웃바운드 PSTN 호출</li></ul><br><li>**호출된** 번호는 전화 번호입니다.</li><li>**국가 또는 지역에** 는 전화 접속된 국가 또는 지역이 있습니다.</li><li>**호출** 된 번호는 호출을 배치한 번호입니다.</li><li>**국가 또는 지역에서** 호출이 발생한 국가 또는 지역입니다.</li><li>**요금은** 계정에 청구되는 통화 금액 또는 비용입니다. </li><li>**통화** 는 호출 비용을 계산하는 데 사용되는 통화 유형입니다. </li><li>**기간** 은 통화가 연결된 시간입니다.</li><li>**국내/국제** 통화는 사용자의 위치에 따라 국내(국가 또는 지역 내) 또는 국제(국가 또는 지역 외부)인지 여부를 알려줍니다.</li><li>**통화 ID** 는 통화에 대한 호출 ID입니다. Microsoft 지원 호출할 때 사용할 수 있는 호출의 식별자입니다.</li><li>**번호 유형** 은 무료 전화 번호 서비스와 같은 사용자의 전화 번호 유형입니다. </li><li>**국가 또는 지역이** 사용 위치입니다. </li> <li>**회의 ID** 는 오디오 회의의 전화 회의 ID입니다. </li><li>**접근 권한 값** 은 호출에 사용되는 라이선스입니다. 표시되는 라이선스 유형은 다음과 같습니다.<ul><li>**MCOEV 또는 MCOEV_VIRTUALUSER 또는 MCOEV_VIRTUALUSER_GOV** - 자동 전화 교환 또는 통화 큐와 같은 음성 애플리케이션</li><li>**FREECALL** - 통화 가격 책정을 방해하는 기술적인 문제가 발생하는 경우 통화는 무료로 제공되며 이 기능과 함께 표시됩니다.</li><li>**MCOPSTN1** - 국내 통화 플랜(3000분 미국/1200분 EU 플랜)</li><li>**MCOPSTN2** - 국제 통화 플랜</li><li>**MCOPSTN5** - 국내 통화 플랜(120분 통화 플랜)</li><li>**MCOPSTN6** - 국내 통화 플랜(240분 통화 플랜)</li><li>**MCOPSTN8** - 사용자당 국내 통화 플랜 120분(다른 통화 플랜과 같이 사용자 간에 풀링되지 않음)</li><li>**MCOPSTN9** - 국제 통화 플랜</li><li>**MCOPSTNCAP** - 공용 영역 전화</li><li>**MCOPSTNPP** - 통신 크레딧</li><li>**MCOMEETADD** - 오디오 회의</li><li>**MCOMEETADD_DIALOUT_US** - 오디오 회의 미국 및 캐나다 전화 접속 계획</li><li>**MCOMEETADD_CN_GLOBAL** - 비중국 사용자를 위한 오디오 회의</li><li>**MCOMEETADD_TATA** - Tata Communications 연결</li><li>**MCOMEETACPEA** - 오디오 회의 분당 종량제 </li><li>**MCOMEETACPEA_GOV** - 정부용 오디오 회의 분당 지불</li></ul></li></ul> 테이블에서 원하는 정보를 보려면 테이블에 열을 추가해야 합니다.|
|**5**   |**열 편집을** 선택하여 테이블에서 열을 추가하거나 제거합니다. |
|**6**   |**필터** 를 선택하여 사용자 이름 또는 호출 유형별로 보고서를 필터링합니다. |
|**7**   |**전체 화면을** 선택하여 전체 화면 모드에서 보고서를 봅니다. |
|**8**   |오프라인 분석을 위해 보고서를 CSV 파일로 내보낼 수 있습니다. **Excel로 내보내기를** 클릭한 다음 **다운로드** 탭에서 **다운로드** 를 클릭하여 준비가 되면 보고서를 다운로드합니다.|

### <a name="direct-routing"></a>직접 라우팅

   ![관리 센터의 직접 라우팅 PSTN 사용 보고서 보고서 스크린샷](../media/teams-reports-pstn-usage-direct-routing-with-callouts.png)![번호가 매겨진 설명선이 있는 Microsoft Teams 관리 센터의 직접 라우팅 PSTN 사용 보고서 스크린샷](../media/teams-reports-pstn-usage-direct-routing-with-callouts.png#lightbox)

|설명선 |설명  |
|--------|-------------|
|**1**   |지난 7일 또는 28일 동안의 추세에 대한 보고서를 볼 수 있습니다. |
|**2**   |각 보고서에는 생성된 날짜가 있습니다. 보고서는 일반적으로 활동 시간으로부터 24~48시간의 대기 시간을 반영합니다. |
|**3**   |X축은 특정 보고서에 대해 선택한 날짜 범위입니다. Y축은 선택한 기간 동안의 총 호출 수입니다.<br>지정된 날짜의 점 위로 마우스를 가져가서 해당 날짜의 총 호출을 확인합니다.  |
|**4**   |이 테이블에서는 호출당 PSTN 사용량을 분석합니다. <ul><li>**UTC(타임스탬프는** 호출이 시작된 시간입니다.</li><li>**표시 이름은** 사용자의 표시 이름입니다. 표시 이름을 클릭하여 Microsoft Teams 관리 센터의 사용자 설정 페이지로 이동합니다. 이 이름은 봇의 이름(예: 통화 큐 또는 클라우드 자동 전화 교환)일 수도 있습니다. </li><li>**SIP 주소** 는 전화를 받거나 호출한 사용자 또는 봇의 SIP 주소입니다.</li><li>**호출자 번호** 는 호출한 사용자 또는 봇의 수입니다. </li><li>**수신자 번호** 는 전화를 받은 사용자 또는 봇의 수입니다. Teams 사용자에 대한 인바운드 호출에서는 Teams 사용자가 되고, Teams 사용자의 아웃바운드 통화에서는 PSTN 사용자가 됩니다. </li><li>**통화 유형** 은 통화가 PSTN 아웃바운드 또는 인바운드 통화인지 여부와 사용자가 수행한 통화 또는 오디오 회의와 같은 통화 유형입니다. 표시되는 호출 유형은 다음과 같습니다.<br><br>**Teams 사용자 통화 유형**<ul><li>**dr_in** - 사용자가 인바운드 PSTN 호출을 받았습니다.</li><li>**dr_out** - 사용자가 아웃바운드 PSTN 호출을 수행했습니다.</li><li>**dr_out_user_conf** - 사용자가 통화에 PSTN 참가자를 추가했습니다.</li><li>**dr_out_user_forwarding** - 사용자가 PSTN 번호로 호출을 전달했습니다.</li><li>**dr_out_user_transfer** - 사용자가 PSTN 번호로 통화를 전송했습니다.</li><li>**dr_emergency_out** - 사용자가 긴급 전화를 걸었습니다.</li><li>**dr_unassigned_in** - 할당되지 않은 번호로 직접 라우팅을 통한 인바운드 PSTN 호출</li></ul><br>**Teams 봇 호출 유형**<ul><li>**dr_in_bot** - 자동 전화 교환 또는 통화 큐와 같은 Teams 봇에 대한 인바운드 PSTN 호출</li><li>**dr_out_bot** - 자동 전화 교환 또는 통화 큐와 같은 Teams 봇의 아웃바운드 PSTN 호출</li></ul><br><li>**호출은** 전화를 받은 사용자의 수입니다.</li><li>**시작 시간(UTC)** 은 SIP 프록시가 아웃바운드 호출(Teams/봇에서 PSTN 사용자에게) SBC에서 최종 응답(SIP 메시지 "200 OK")을 수신하거나 SIP 프록시가 인바운드 호출(PSTN 사용자가 Teams/봇에 대한 PSTN 사용자)에서 Teams 백 엔드 내의 다음 홉으로 초대를 보낸 후의 시간입니다. </li><li>**초대 시간(UTC)** 은 초기 초대가 SBC에 대한 Teams 사용자 또는 봇 호출에서 아웃바운드 호출로 전송되었거나 SBC에서 직접 라우팅의 SIP 프록시 구성 요소에 의해 Teams 또는 봇 호출에 대한 인바운드 호출로 수신된 시간입니다.</li><li>**실패 시간(UTC)** 은 호출이 실패한 시간입니다. 실패한 호출에만 해당합니다. 최종 SIP 코드, 최종 Microsoft 하위 코드 및 최종 SIP 구는 호출이 실패한 이유를 제공하며 문제 해결에 도움이 될 수 있습니다. </li><li>**종료 시간(UTC)** 은 호출이 종료된 시간입니다(성공적인 호출에만 해당).</li><li>**기간** 은 초대에서 호출 종료 또는 실패까지 통화가 연결된 시간입니다. 통화 전달의 경우 기간은 통화 큐의 벨소리를 포함합니다.</li><li>**번호 유형** 은 무료 전화 번호 서비스와 같은 사용자의 전화 번호 유형입니다. </li><li>**미디어 바이패스(media bypass** )는 트렁크가 미디어 바이패스용으로 활성화되었는지 여부를 나타냅니다. </li> <li>**SBC FQDN은 SBC** (세션 테두리 컨트롤러)의 FQDN(정규화된 도메인 이름)입니다. </li><li>**Azure 지역 for Media** 는 바이패스 이외의 호출에서 미디어 경로로 사용된 데이터 센터입니다. </li><li>**Signaling용 Azure 지역은** 바이패스 및 비 우회 호출 모두에 대해 신호를 전송하는 데 사용된 데이터 센터입니다. </li><li>**이벤트 유형** 은 호출의 이벤트 유형입니다. 성공한 호출에 대한 성공과 실패한 호출에 대한 시도가 표시됩니다. </li><li>**최종 SIP 코드** 는 호출이 종료된 코드입니다.</li><li>**최종 Microsoft 하위 코드** 는 발생한 특정 작업을 나타내는 코드입니다.</li><li>**마지막 SIP 구** 는 SIP 코드 및 Microsoft 하위 코드에 대한 설명입니다.</li><li>**상관 관계 ID** 는 Microsoft 지원 호출할 때 사용할 수 있는 호출에 대한 고유 식별자입니다.</li><li>**공유 상관 관계 ID** 는 다운로드 가능한 CSV 파일에만 표시되며 포털에 없습니다. 공유 상관 관계 ID는 관련된 두 개 이상의 호출에 존재합니다. 아래의 자세한 설명을 참조하세요.</li></ul> 테이블에서 원하는 정보를 보려면 테이블에 열을 추가해야 합니다.|
|**5**   |**열 편집을** 선택하여 테이블에서 열을 추가하거나 제거합니다. |
|**6**   |**전체 화면을** 선택하여 전체 화면 모드에서 보고서를 봅니다. |
|**7**   |**Excel로 내보내기를** 선택하여 오프라인 분석을 위해 CSV(쉼표로 구분된 파일)에서 데이터를 다운로드하거나 청구 시스템에 대한 입력으로 사용합니다. |

#### <a name="callercallee-fields-considerations"></a>호출자/호출 수신자 필드 고려 사항

호출 방향에 따라 호출자 또는 수신자 이름에는 E164가 아닌 번호가 포함될 수 있습니다.

이러한 필드는 고객 SBC에서 올 수 있습니다. SBC에서 직접 라우팅에 보낼 수 있는 세 가지 형식은 E.164 숫자, E.164가 아닌 숫자 및 문자열입니다.

- E.164 번호가 있는 사용자부터 E.164 번호가 있는 사용자까지의 E.164 전화 번호입니다. 
- E.164가 아닌 번호에서 호출합니다. 직접 라우팅과 상호 연결된 타사 PBX의 사용자가 Teams 사용자를 호출합니다. 이 경우 호출자 번호는 E.164가 아닌 숫자일 수 있습니다(예: +1001). 
- 스팸은 "내부 수익 서비스"와 같이 숫자를 호출하고 이름만 표시하지 않습니다. 이 문자열은 보고서에 표시됩니다.

#### <a name="phone-number-obfuscation"></a>전화 번호 난독 처리
국가별 개인 정보 보호 요구 사항에는 외부(고객이 소유하지 않음) 전화 번호의 난독 처리가 포함됩니다. 전화 번호의 마지막 숫자 3~4개가 별표(+123 456789***)로 바뀝니다. 

들어오는 호출의 경우 호출자 번호가 난독화되고 발신 호출의 경우 호출 수신자 번호가 난독화됩니다. 이는 테넌트 관리 센터의 PSTN 및 직접 라우팅 보고서, 데이터 내보내기 및 Microsoft Graph를 통해 사용할 수 있는 통화 로그에 적용됩니다.

난독 처리는 조직의 위치(국가)를 기반으로 합니다. 다음 표에 나열되지 않은 국가의 경우 전체 전화 번호가 표시됩니다.

| 국가 | 난독 처리 숫자 수 |
| :-: | :- |
|BE – 벨기에 | 3 |
|CH – 스위스 | 4 |
|DE - 독일 | 3 |
|DK – 덴마크 | 3 |
|ES – 스페인 | 3 |
|FI – 핀란드 | 3 |
|FR – 프랑스 | 4 |
|IT – 이탈리아 | 3 |
|NL - 네덜란드 | 3 |
|NO - 노르웨이 | 3 |
|SE - 스웨덴 | 3 |

#### <a name="about-shared-correlation-id"></a>공유 상관 관계 ID 정보

공유 상관 관계 ID는 다운로드한 내보낸 Excel 파일에만 존재하며 둘 이상의 호출이 관련되어 있음을 나타냅니다. 다음은 다양한 시나리오와 공유 상관 관계 ID가 있는 경우에 대해 설명합니다.

1.    Teams 클라이언트에서 Teams 사용자 1이라는 PSTN 엔드포인트의 PSTN 사용자 1, 통화 유형 Dr_In, 상관 관계 ID 57f28917-42k5-4c0c-9433-79734873f2ac, 공유 상관 관계 ID 없음.
2.    PSTN 엔드포인트에서 PSTN 사용자 1이라는 Teams 클라이언트의 Teams 사용자 1은 공유 상관 관계 ID가 없는 Dr_Out 2c12b8ca-62eb-4c48-b68d-e451f518ff4를 호출합니다.
3.    Teams 클라이언트에서 Teams 사용자 2라고 하는 PSTN 엔드포인트의 PSTN 사용자 1 호출 형식 Dr_In f45e9a25-9f94-46e7-a457-84f5940efde9, 공유 상관 관계 ID f45e9a25-9f94-46e7-a457-84f5940efde9.
4.    상관 관계 ID가 "f45e9a25-9f94-46e7-a457-84f5940efde9"인 기존 호출 3. Teams 사용자 2와의 통화에서 PSTN 사용자 1. Teams 사용자 2 전송(블라인드 또는 상담) Teams 또는 PSTN 사용자에 대한 호출, 호출 형식 Dr_Out_User_Transfer 45a1da7c-9e97-481a-8a05-3fe19a9a77e0, 공유 상관 관계 ID f45e9a25-9f94-46e7-a457-84f5940efde9.

## <a name="exporting-the-reports"></a>보고서 내보내기
**Excel로 내보내기를** 클릭한 다음 **다운로드** 탭에서 **다운로드** 를 클릭하여 준비가 되면 보고서를 다운로드합니다. 내보내기 프로세스는 데이터의 수량에 따라 완료하는 데 몇 초에서 몇 분 정도 걸릴 수 있습니다.

이렇게 하면 모든 사용자의 데이터가 내보내지고 추가 분석을 위해 간단한 정렬 및 필터링을 수행할 수 있습니다. 내보낸 파일에는 온라인 보고서에서 사용할 수 없는 추가 필드가 포함되어 있습니다. 문제 해결 및 자동화된 워크플로에 사용할 수 있습니다.

 "Calls.Export"라는 zip 파일이 표시됩니다 **.`[identifier]`.zip**"입니다. 식별자는 문제 해결에 사용할 수 있는 내보내기 고유 ID입니다.

통화 플랜과 직접 라우팅이 모두 있는 경우 내보낸 파일에 두 제품에 대한 데이터가 포함될 수 있습니다. PSTN 사용 보고서 파일에는 파일 이름이 "**PSTN.calls입니다.`[UTC date]`.csv**" 및 직접 라우팅 "**DirectRouting.calls.`[UTC date]`.csv**".

 PSTN 및 직접 라우팅 파일 외에도 보관 파일에는 선택한 내보내기 시간 범위 및 기능이 있는 "**parameters.json**" 파일이 포함되어 있습니다.

내보낸 파일은 [RFC 4180](https://tools.ietf.org/html/rfc4180) 표준을 준수하는 CSV(쉼표로 구분된 값) 형식입니다. 변환 없이 Excel 또는 다른 표준 규격 편집기에서 파일을 열 수 있습니다.

CSV의 첫 번째 행에는 열 이름이 포함됩니다. 모든 날짜는 UTC이며 [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) 형식입니다.

### <a name="exported-pstn-usage-report"></a>내보낸 PSTN 사용 현황 보고서

 국가별 규정에서 12개월 동안 데이터 보존을 금지하지 않는 한 현재 날짜로부터 최대 1년까지 데이터를 내보낼 수 있습니다.

> [!div class="has-no-wrap"]  
> | # | 이름 | [데이터 형식(SQL Server)](/sql/t-sql/data-types/data-types-transact-sql) | 설명 |
> | :-: | :-: | :-: |:------------------- |
> | 0 | UsageId | `uniqueidentifier` | 고유 호출 식별자 |
> | 1 | 통화 ID | `nvarchar(64)` | 호출 식별자입니다. 고유하지 않음 |
> | 2 | 회의 ID | `nvarchar(64)` | 오디오 회의의 ID |
> | 3 | 사용자 위치 | `nvarchar(2)` | 사용자의 국가 코드, [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 4 | AAD ObjectId | `uniqueidentifier` | Azure Active Directory에서 사용자의 ID를 호출합니다.<br/> 이 사용자 및 기타 사용자 정보는 봇 호출 형식에 대해 null/비어 있습니다(ucap_in, ucap_out). |
> | 5 | Upn | `nvarchar(128)` | Azure Active Directory의 UserPrincipalName(로그인 이름)<br/>이는 일반적으로 사용자의 SIP 주소와 동일하며 사용자의 전자 메일 주소와 같을 수 있습니다. |
> | 6 | 사용자 표시 이름 | `nvarchar(128)` | 사용자의 표시 이름 |
> | 7 | 발신자 ID | `nvarchar(128)` | 인바운드 통화에 대한 호출을 받은 번호 또는 아웃바운드 호출을 위해 전화를 건 번호입니다. [E.164](https://en.wikipedia.org/wiki/E.164) 형식 |
> | 8 | 호출 유형 | `nvarchar(32)` | 통화가 PSTN 아웃바운드 또는 인바운드 통화인지 여부와 사용자가 수행한 통화 또는 오디오 회의와 같은 통화 유형 |
> | 9 | 숫자 형식 | `nvarchar(16)` | 사용자의 전화 번호 유형(예: 무료 전화 번호 서비스) |
> | 10 | 국내/국제 | `nvarchar(16)` | 통화가 사용자의 위치에 따라 국내(국가 또는 지역 내) 또는 국제(국가 또는 지역 외부)인지 여부 |
> | 11 | 대상 전화 걸기 | `nvarchar(64)` | 국가 또는 지역 전화 걸기 |
> | 12 | 대상 번호 | `nvarchar(32)` | [E.164](https://en.wikipedia.org/wiki/E.164) 형식으로 전화 걸기 번호 |
> | 13 | 시작 시간 | `datetimeoffset` | 통화 시작 시간 |
> | 14 | 종료 시간 | `datetimeoffset` | 통화 종료 시간 |
> | 15 | 기간 초 | `int` | 통화가 연결된 기간 |
> | 16 | 연결 요금 | `numeric(16, 2)` | 연결 요금 가격 |
> | 17 | 충전 | `numeric(16, 2)` | 계정에 청구되는 통화 금액 또는 비용 |
> | 18 | 통화 | `nvarchar(3)` | 호출 비용을 계산하는 데 사용되는 통화 유형([ISO 4217](https://en.wikipedia.org/wiki/ISO_4217)) |
> | 19 | 기능 | `nvarchar(32)` | 통화에 사용되는 라이선스 |

### <a name="exported-direct-routing-usage-report"></a>내보낸 직접 라우팅 사용 현황 보고서

국가별 규정에서 해당 기간 동안 데이터 보존을 금지하지 않는 한 현재 날짜로부터 최대 5개월(150일) 동안 데이터를 내보낼 수 있습니다.

> [!div class="has-no-wrap"]  
> | # | 이름 | [데이터 형식(SQL Server)](/sql/t-sql/data-types/data-types-transact-sql) | 설명 |
> | :-: | :-: | :-: |:------------------- |
> | 0 | Correlationid | `uniqueidentifier` | 호출 식별자입니다. 동일한 호출의 여러 다리가 동일한 CorrelationId를 공유할 수 있습니다. |
> | 1 | AAD ObjectId | `uniqueidentifier` | Azure Active Directory에서 사용자의 ID를 호출합니다.<br/> 봇 호출 유형에 대해 이 정보 및 기타 사용자 정보는 null/비어 있을 수 있습니다. |
> | 2 | Upn | `nvarchar(128)` | 전화를 걸거나 받은 사용자 또는 봇의 UserPrincipalName(로그인 이름, Azure Active Directory)입니다.<br/>이는 일반적으로 사용자의 SIP 주소와 동일하며 사용자의 전자 메일 주소와 같을 수 있습니다. |
> | 3 | 표시 이름 | `nvarchar(128)` | Microsoft 365 관리 센터 설정된 사용자 또는 호출 봇의 이름(예: 통화 큐 또는 자동 전화 교환)입니다. |
> | 4 | 사용자 국가 | `nvarchar(2)` | 사용자의 국가 코드, [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 5 | 초대 시간 | `datetimeoffset` | 초기 초대가 Teams 사용자 또는 봇에서 SBC로 아웃바운드로 보내거나 SBC에서 직접 라우팅의 SIP 프록시 구성 요소에서 Teams 또는 봇 호출에 인바운드로 수신된 경우 |
> | 6 | 시작 시간 | `datetimeoffset` | SIP 프록시가 아웃바운드의 SBC(Teams/봇에서 PSTN 사용자에게)에서 최종 답변(SIP 메시지 "200 OK")을 받은 시간 또는 SIP 프록시가 인바운드 호출 시 Teams 백 엔드 내의 다음 홉에 초대를 보낸 후(PSTN 사용자가 Teams/봇에 연결됨)<br/>실패하고 응답이 없는 호출의 경우 초대 또는 실패 시간과 같을 수 있습니다. |
> | 7 | 실패 시간 | `datetimeoffset` | 실패한(완전히 설정되지 않은) 호출에 대해서만 존재합니다. |
> | 8 | 종료 시간 | `datetimeoffset` | 성공적인(완전히 설정된) 호출에 대해서만 존재합니다. 통화가 종료된 시간 |
> | 9 | 기간(초) | `int` | 초대에서 호출 종료 또는 실패까지의 통화 기간입니다. 통화 전달의 경우 기간은 통화 큐의 벨소리를 포함합니다. |
> | 10 | 성공 | `nvarchar(3)` | 예/아니요. 성공 또는 시도 |
> | 11 | 호출자 번호 | `nvarchar(32)` | 호출한 사용자 또는 봇의 수입니다. 팀 사용자 호출에 대한 인바운드에서는 PSTN 사용자가 되고, Teams 사용자 호출의 아웃바운드에서는 Teams 사용자 번호가 됩니다. |
> | 12 | 수신자 번호 | `nvarchar(32)` | 전화를 받은 사용자 또는 봇의 수입니다. 팀 사용자 호출에 대한 인바운드에서는 Teams 사용자가 되고, Teams에서 아웃바운드로 전화를 걸면 PSTN 사용자가 됩니다. |
> | 13 | 호출 유형 | `nvarchar(32)` | 호출 유형 및 방향 |
> | 14 | Azure 지역 for Media | `nvarchar(8)` | 바이패스 이외의 호출에서 미디어 경로에 사용되는 데이터 센터 |
> | 15 | 신호에 대한 Azure 지역 | `nvarchar(8)` | 바이패스 및 비 바이패스 호출 모두에 신호를 전송하는 데 사용되는 데이터 센터 |
> | 16 | 최종 SIP 코드 | `int` | 호출이 종료된 코드, [RFC 3261](https://tools.ietf.org/html/rfc3261) |
> | 17 | 최종 Microsoft 하위 코드 | `int` | SIP 코드 외에도 Microsoft에는 특정 문제를 나타내는 자체 하위 코드가 있습니다. |
> | 18 | 최종 SIP 구 | `nvarchar(256)` | SIP 코드 및 Microsoft 하위 코드에 대한 설명 |
> | 19 | SBC FQDN | `nvarchar(64)` | 세션 테두리 컨트롤러의 정규화된 도메인 이름 |
> | 20 | 미디어 바이패스 | `nvarchar(3)` | 예/아니요. 트렁크가 미디어 바이패스용으로 사용되었는지 여부를 나타냅니다. |
> | 21 | 공유 상관 관계 ID | `uniqueidentifier` | 둘 이상의 호출이 관련되어 있음을 나타냅니다. |


## <a name="related-topics"></a>관련 항목

- [Teams 분석 및 보고](teams-reporting-reference.md)
- [Microsoft Graph의 PSTN 통화 보고서](/graph/api/callrecords-callrecord-getpstncalls?view=graph-rest-1.0&tabs=http)
- [Microsoft Graph의 직접 라우팅 보고서](/graph/api/callrecords-callrecord-getdirectroutingcalls?view=graph-rest-1.0&tabs=http)
