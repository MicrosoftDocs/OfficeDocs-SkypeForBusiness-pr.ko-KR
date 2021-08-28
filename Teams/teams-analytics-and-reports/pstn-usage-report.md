---
title: Microsoft Teams PSTN 사용 보고서
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
MS.collection:
- M365-voice
description: 관리 센터에서 Teams PSTN 사용 Microsoft Teams 보고를 사용하여 조직의 통화 및 오디오 회의 사용량에 대한 개요를 얻을 수 있는 방법을 알아보습니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8c83605e05e5d28b4ac230487baa5de47dd74aa5
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58631242"
---
# <a name="microsoft-teams-pstn-usage-report"></a>Microsoft Teams PSTN 사용 보고서

Teams 관리 센터의 PSTN(공용 전환 전화 네트워크) Microsoft Teams 보고서는 조직의 통화 및 오디오 회의 활동에 대한 개요를 제공합니다. Microsoft를 전화 통신 사업자로 사용하는 경우 통화 요금제에 대한 자세한 통화 활동을 볼 수 있으며, 자체 전화 통신 통신을 사용하는 경우 직접 라우팅을 사용할 수 있습니다.

통화 **계획 탭에는** 사용자가 인바운드 및 아웃바운드 PSTN 통화에 소요한 분 수와 이러한 호출 비용을 포함한 정보가 표시됩니다. 직접 **라우팅** 탭에는 SIP 주소 및 통화 시작 및 종료 시간을 포함한 정보가 표시됩니다. 이 보고서의 정보를 사용하여 조직의 PSTN 사용량에 대한 인사이트를 얻고 비즈니스 결정을 조사하고 계획하고, 내리는 데 도움이 됩니다.

> [!NOTE]
> Telstra 또는 Softbank 통화 계획이 있는 경우 PSTN 사용 보고서에 통화 세부 정보 레코드가 표시되지 않습니다. 보고 요구 사항을 위해 Telstra 또는 Softbank에 문의하세요. 

## <a name="view-the-pstn-usage-report"></a>PSTN 사용 보고서 보기

1. 관리 센터의 왼쪽 탐색에서 Microsoft Teams 분석 &  >  **보고서 를 클릭합니다.** 보고서 보기 **탭의** **보고서에서** **PSTN** 사용 보고서 를 선택합니다.
2. 날짜 **범위에서** 미리 정의된 범위인 7 또는 28일을 선택하거나 사용자 지정 범위를 설정한 다음 보고서 실행을 **선택합니다.**

## <a name="interpret-the-report"></a>보고서 해석

### <a name="calling-plans"></a>통화 플랜

[![관리 센터의 통화 계획 PSTN](../media/teams-reports-pstn-usage-calling-plans-with-callouts.png "번호 매기기 콜아웃이 있는 Microsoft Teams 관리 센터의 PSTN 사용 보고서 스크린샷") 사용 보고서 스크린샷](../media/teams-reports-pstn-usage-calling-plans-with-callouts.png#lightbox)

|콜아웃 |설명  |
|--------|-------------|
|**1**   |보고서는 지난 7일, 28일 또는 설정한 사용자 지정 날짜 범위의 추세를 볼 수 있습니다. |
|**2**   |각 보고서에는 생성된 날짜가 있습니다. 보고서는 일반적으로 활동 시간으로부터 24~48시간의 대기 시간을 반영합니다. |
|**3**   |X 축은 특정 보고서에 대해 선택한 날짜 범위입니다. Y축은 선택한 기간 동안의 총 호출 수입니다. <br>주어진 날짜에 점 위에 마우스를 대고 그 날짜의 총 호출을 볼 수 있습니다.  |
|**4**   |이 표에서는 호출당 PSTN 사용량을 분석할 수 있습니다. <ul><li>**UTC(타임스탬프)는** 호출이 시작된 시간입니다.</li><li>**표시 이름은** 사용자의 표시 이름입니다. 표시 이름을 클릭하여 관리자 센터의 사용자 설정 페이지로 Microsoft Teams 있습니다.</li><li>**사용자** 이름은 사용자의 로그인 이름입니다.</li><li>**전화** 번호는 인바운드 호출에 대한 호출을 받은 번호 또는 아웃바운드 호출에 대해 전화를 걸 수 있는 번호입니다.</li><li>**호출 유형은** 통화가 PSTN 아웃바운드 호출인지 인바운드 호출인지 여부와 사용자에 의해 배치된 호출 또는 오디오 회의와 같은 호출 유형인지 여부입니다. 볼 수 있는 호출 유형은 다음과 같습니다.<br><br>**Teams 호출 유형**<ul><li>**user_in** - 사용자가 인바운드 PSTN 호출을 수신합니다.</li><li>**user_out** - 사용자가 아웃바운드 PSTN 호출을 배치한 경우</li><li>**user_out_conf** - 사용자가 3가지 전화 회의와 같은 통화에 두 개 이상의 PSTN 참가자를 추가했습니다.</li><li>**user_out_transfer** - 사용자가 PSTN 번호로 호출을 전송</li><li>**user_out_forwarding** - 사용자가 PSTN 번호로 호출을 전달한 경우</li><li>**conf_in** - 오디오 회의 브리지에 대한 인바운드 호출</li><li>**conf_out** - 일반적으로 오디오 회의 브리지의 아웃바운드 호출을 통해 회의에 PSTN 번호를 추가합니다.</li></ul><br>**Teams 봇 호출 형식**<ul><li>**ucap_in** - 자동 Teams 큐와 같은 봇에 대한 인바운드 PSTN 호출</li><li>**ucap_out** - 자동 Teams 큐와 같은 봇의 아웃바운드 PSTN 호출</li></ul><br><li>**에 호출된** 번호입니다.</li><li>**국가 또는 지역으로** 전화 걸기 국가 또는 지역입니다.</li><li>**호출은** 호출을 배치한 번호입니다.</li><li>**국가 또는 지역에서는** 호출이 배치된 국가 또는 지역입니다.</li><li>**요금은** 계정에 청구되는 통화의 금액 또는 비용입니다. </li><li>**통화는** 통화 비용을 계산하는 데 사용되는 통화 유형입니다. </li><li>**기간은** 통화가 연결된 기간입니다.</li><li>**국내/국제는** 통화가 사용자의 위치를 기준으로 국내(국가 또는 지역 내) 또는 국제(국가 또는 지역 외부)인지 여부를 알려 습니다.</li><li>**통화 ID는** 통화에 대한 호출 ID입니다. Microsoft Support를 호출할 때 사용할 수 있는 호출의 식별자입니다.</li><li>**번호 형식은** 무료 번호 서비스와 같은 사용자의 전화 번호 유형입니다. </li><li>**국가 또는 지역은** 사용 위치입니다. </li> <li>**컨퍼런스 ID는** 오디오 회의의 회의 ID입니다. </li><li>**기능은** 호출에 사용되는 라이선스입니다. 볼 수 있는 라이선스 유형은 다음과 같습니다.<ul><li>**MCOEV 또는 MCOEV_VIRTUALUSER 또는** MCOEV_VIRTUALUSER_GOV - 자동 참석자 또는 통화 큐와 같은 음성 애플리케이션</li><li>**FREECALL** - 통화 가격을 책정하지 못하게 하는 기술적 문제가 발생하면 통화가 무료로 제공되어 이 기능으로 표시됩니다.</li><li>**MCOPSTN1** - 국내 통화 계획(미국 3000분/ EU 1200분 요금제)</li><li>**MCOPSTN2** - 국제 통화 계획</li><li>**MCOPSTN5** - 국내 통화 계획(120분 통화 계획)</li><li>**MCOPSTN6** - 국내 통화 계획(240분 통화 계획)</li><li>**MCOPSTN8** - 사용자당 국내 통화 계획 120분(다른 통화 계획과 같은 사용자 전체에 풀링되지 않은 경우)</li><li>**MCOPSTN9** - 국제 통화 계획</li><li>**MCOPSTNCAP** - 공용 영역 전화</li><li>**MCOPSTNPP** - 통신 크레딧</li><li>**MCOMEETADD** - 오디오 회의</li><li>**MCOMEETADD_DIALOUT_US** - 오디오 회의 미국 및 캐나다 전화 접속 계획</li><li>**MCOMEETADD_CN_GLOBAL** - 중국이 아닌 사용자를 위한 오디오 회의</li><li>**MCOMEETADD_TATA** - Tata Communications 연결</li><li>**MCOMEETACPEA** - 오디오 회의 분당 지불 </li><li>**MCOMEETACPEA_GOV** - 정부에 대한 분당 유료 오디오 회의</li></ul></li></ul> 표에서 원하는 정보를 확인하려는 경우 테이블에 열을 추가해야 합니다.|
|**5**   |열 **편집을 선택하여** 표에 열을 추가하거나 제거합니다. |
|**6**   |필터를 **선택하여** 사용자 이름 또는 호출 유형별로 보고서를 필터링합니다. |
|**7**   |전체 **화면을 선택하여** 전체 화면 모드에서 보고서를 볼 수 있습니다. |
|**8**   |오프라인 분석을 위해 보고서를 CSV 파일로 내보낼 수 있습니다. 내보내기를 **Excel** 클릭한 다음 다운로드  탭에서 다운로드를  클릭하여 준비가되면 보고서를 다운로드합니다.|

### <a name="direct-routing"></a>직접 라우팅

[![관리 센터의 직접 라우팅 PSTN](../media/teams-reports-pstn-usage-direct-routing-with-callouts.png "번호 매기기 콜아웃이 있는 Microsoft Teams 관리 센터의 직접 라우팅 PSTN 사용 보고서 스크린샷") 사용 보고서 스크린샷](../media/teams-reports-pstn-usage-direct-routing-with-callouts.png#lightbox)

|콜아웃 |설명  |
|--------|-------------|
|**1**   |보고서는 지난 7일 또는 28일 동안의 추세를 볼 수 있습니다. |
|**2**   |각 보고서에는 생성된 날짜가 있습니다. 보고서는 일반적으로 활동 시간으로부터 24~48시간의 대기 시간을 반영합니다. |
|**3**   |X 축은 특정 보고서에 대해 선택한 날짜 범위입니다. Y축은 선택한 기간 동안의 총 호출 수입니다.<br>주어진 날짜에 점 위에 마우스를 대고 그 날짜의 총 호출을 볼 수 있습니다.  |
|**4**   |이 표에서는 호출당 PSTN 사용량을 분석할 수 있습니다. <ul><li>**UTC(타임스탬프)는** 호출이 시작된 시간입니다.</li><li>**표시 이름은** 사용자의 표시 이름입니다. 표시 이름을 클릭하여 관리자 센터의 사용자 설정 페이지로 Microsoft Teams 있습니다. 이름은 봇의 이름일 수도 있습니다(예: 호출 큐 또는 클라우드 자동 전화 교환. </li><li>**SIP 주소는** 호출을 수신하거나 호출한 봇 또는 사용자 또는 봇의 SIP 주소입니다.</li><li>**발신자** 번호는 호출한 사용자 또는 봇의 수입니다. </li><li>**발신자** 번호는 호출을 받은 사용자 또는 봇의 수입니다. 사용자에 대한 인바운드 Teams 사용자가 Teams 사용자의 아웃바운드 호출에 Teams PSTN 사용자입니다. </li><li>**호출 유형은** 통화가 PSTN 아웃바운드 호출인지 인바운드 호출인지 여부와 사용자에 의해 배치된 호출 또는 오디오 회의와 같은 호출 유형인지 여부입니다. 볼 수 있는 호출 유형은 다음과 같습니다.<br><br>**Teams 호출 유형**<ul><li>**dr_in** - 사용자가 인바운드 PSTN 호출을 수신한 경우</li><li>**dr_out** - 사용자가 아웃바운드 PSTN 호출을 배치한 경우</li><li>**dr_out_user_conf** - 사용자가 호출에 PSTN 참가자를 추가한 경우</li><li>**user_out_transfer** - 사용자가 PSTN 번호로 호출을 전송</li><li>**dr_out_user_forwarding** - 사용자가 PSTN 번호로 호출을 전달한 경우</li><li>**dr_out_user_transfer** - 사용자가 PSTN 번호로 호출을 전송</li><li>**dr_emergency_out** - 사용자가 긴급 전화를 걸었다.</li></ul><br>**Teams 봇 호출 형식**<ul><li>**dr_in_ucap** - 자동 Teams 큐와 같은 봇에 대한 인바운드 PSTN 호출</li><li>**dr_out_ucap** - 자동 Teams 큐와 같은 봇의 아웃바운드 PSTN 호출</li></ul><br><li>**호출은** 호출을 받은 사용자의 수입니다.</li><li>**시작 시간(UTC)은** SIP 프록시가 아웃바운드 호출(Teams/봇)에서 SBC에서 최종 응답(SIP 메시지 "200 확인")을 받았거나, SIP 프록시가 인바운드 호출(PSTN 사용자)의 Teams 백엔드 내에서 다음 홉에 초대를 보내는 시간(PSTN 사용자 Teams/봇)입니다. </li><li>**초대 시간(UTC)은** SBC에 대한 사용자 Teams 봇 호출에서 초기 초대를 보내거나 SBC에서 직접 라우팅의 SIP 프록시 구성 요소에 Teams 또는 봇 호출에 대한 인바운드 호출에 수신된 시간입니다.</li><li>**실패 시간(UTC)은** 호출이 실패한 시간입니다. 실패한 호출의 경우만 해당됩니다. 최종 SIP 코드, 최종 Microsoft 하위 코드 및 최종 SIP 구는 호출이 실패한 이유를 제공하고 문제 해결에 도움이 될 수 있습니다. </li><li>**종료 시간(UTC)은** 호출이 종료된 시간입니다(성공한 호출에만 해당).</li><li>**기간은** 통화가 연결된 기간입니다.</li><li>**번호 형식은** 무료 번호 서비스와 같은 사용자의 전화 번호 유형입니다. </li><li>**미디어 우회는** 트렁크가 미디어 우회에 사용하도록 설정되어 있는지 여부를 나타냅니다. </li> <li>**SBC FQDN은** SBC(세션 테두리 컨트롤러)의 완전히 자격을 갖춘 도메인 이름(FQDN)입니다. </li><li>**미디어용 Azure 지역은** 비우회 호출에서 미디어 경로로 사용된 데이터 센터입니다. </li><li>**시그널링용 Azure 지역은** 우회 및 비우회 호출 모두에 대한 신호 전송에 사용된 데이터 센터입니다. </li><li>**이벤트 형식은** 호출의 이벤트 유형입니다. 성공적인 호출에 대한 성공 및 실패한 호출에 대한 시도가 표시됩니다. </li><li>**최종 SIP 코드는** 호출이 종료된 코드입니다.</li><li>**최종 Microsoft 하위 코드는** 발생한 특정 작업을 나타내는 코드입니다.</li><li>**최종 SIP 구는** SIP 코드 및 Microsoft 하위 코드에 대한 설명입니다.</li><li>**상관 관계 ID는** Microsoft 지원을 호출할 때 사용할 수 있는 호출에 대한 고유 식별자입니다.</li><li>**공유 상관 관계 ID는** 다운로드 가능한 CSV 파일에만 표시하며 포털에 존재하지 않습니다. 공유 상관 관계 ID는 관련이 있는 두 개 이상의 호출에 있습니다. 아래에서 자세한 설명을 참조하세요.</li></ul> 표에서 원하는 정보를 확인하려는 경우 테이블에 열을 추가해야 합니다.|
|**5**   |열 **편집을 선택하여** 표에 열을 추가하거나 제거합니다. |
|**6**   |전체 **화면을 선택하여** 전체 화면 모드에서 보고서를 볼 수 있습니다. |
|**7**   |오프라인 **Excel** CSV(콤마로 구분된 파일)에서 데이터를 다운로드하거나 청구 시스템에 대한 입력으로 사용하려면 내보내기 를 선택합니다. |

#### <a name="callercallee-fields-considerations"></a>호출자/호출자 필드 고려 사항

호출 방향에 따라 발신자 또는 발신자 이름에는 E164가 아닌 숫자가 포함될 수 있습니다.

이러한 필드는 고객 SBC에서 올 수 있습니다. SBC가 직접 라우팅에 보낼 수 있는 세 가지 형식은 E.164 숫자, 비 E.164 숫자 및 문자열입니다.

- E.164 번호가 있는 사용자로부터 E.164 번호가 있는 사용자에 대한 E.164 전화 번호입니다. 
- 비 E.164 번호에서 호출합니다. 직접 라우팅과 상호 연결된 타사 PBX의 사용자가 사용자에 대한 Teams 합니다. 이 경우 호출자 번호는 E.164가 아닌 번호(예: +1001)일 수 있습니다. 
- 스팸 발송자는 전화로 전화를 걸고 숫자( 예: "내부 수익 서비스")의 이름만 제시하지 않습니다. 이 문자열은 보고서에 표시됩니다.

#### <a name="about-shared-correlation-id"></a>공유 상관 관계 ID에 대해

공유 상관 관계 ID는 다운로드한 내보낼 Excel 파일에만 존재하며 두 개 이상의 호출이 관련되어 있습니다. 다음에서는 서로 다른 시나리오와 공유 상관 관계 ID가 있는 경우를 설명합니다.

1.    클라이언트의 Teams 사용자 1이라는 PSTN 엔드포인트의 PSTN Teams, 전화 유형 Dr_In, 상관 관계 ID 57f28917-42k5-4c0c-9433-79734873f2ac, 공유 상관 관계 ID가 없습니다.
2.    Teams PST Dr_Out N Teams PSTN 사용자 1이라는 클라이언트의 사용자 1은 2c12b8ca-62eb-4c48-b68d-e451f518ff4, 공유 상관 관계 ID가 없습니다.
3.    클라이언트에서 Teams 사용자 2라는 PSTN 엔드포인트의 PSTN Teams Dr_In f45e9a25-9f94-46e7-a457-84f5940efde9, 공유 상관 관계 ID f45e9a25-9f94-46e7-a457-84f5940efde9
4.    상관 관계 ID가 있는 기존 호출 3 "f45e9a25-9f94-46e7-a457-84f5940efde9". 사용자 2가 있는 Teams PSTN 사용자 1입니다. Teams 사용자 2 또는 PSTN 사용자에 대한 Teams(블라인드 또는 협의) 호출 유형 Dr_Out_User_Transfer 45a1da7c-9e97-481a-8a05-3fe19a9a770, 공유 상관 관계 ID f45e9a25-9f94-46e7-a457-84f5940efde9.

## <a name="exporting-the-reports"></a>보고서 내보내기
내보내기를 **Excel** 클릭한 다음 다운로드  탭에서 다운로드를  클릭하여 준비가되면 보고서를 다운로드합니다. 내보내기 프로세스는 데이터의 수량에 따라 완료하는 데 몇 초에서 몇 분 정도 걸릴 수 있습니다.

이렇게 하면 모든 사용자의 데이터를 내보내고 추가 분석을 위해 간단한 정렬 및 필터링을 할 수 있습니다. 내보낼 파일에는 온라인 보고서에서 사용할 수 없는 추가 필드가 포함되어 있습니다. 이러한 방법은 문제 해결 및 자동화된 워크플로에 사용할 수 있습니다.

 **"Calls.Export"라는 zip 파일이 표시됩니다. `[identifier]`.zip**"은 문제 해결에 사용할 수 있는 내보내기에 대한 고유 ID가 되는 식별자입니다.

통화 계획과 직접 라우팅이 모두 있는 경우 내보낼 파일에 두 제품에 대한 데이터가 포함될 수 있습니다. PSTN 사용 보고서 파일에 파일 이름 "**PSTN.calls이 있습니다. `[UTC date]`.csv**" 및 직접 라우팅 "**DirectRouting.calls. `[UTC date]`.csv**".

 PSTN 및 직접 라우팅 파일 외에도 보관 파일에는 "parameters.js"에 있는 **파일"이** 포함되어 있으며, 선택한 내보내기 시간 범위 및 기능이 있습니다.

내보낼 파일은 [RFC 4180](https://tools.ietf.org/html/rfc4180) 표준을 준수하는 CSV(콤마 구분 값) 형식으로 제공됩니다. 파일을 변환할 필요 없이 Excel 또는 기타 표준 준수 편집기에서 열 수 있습니다.

CSV의 첫 번째 행에는 열 이름이 포함되어 있습니다. 모든 날짜는 UTC 및 [ISO 8601 형식입니다.](https://en.wikipedia.org/wiki/ISO_8601)

### <a name="exported-pstn-usage-report"></a>내보낼 PSTN 사용 보고서

 국가별 규정에서 12개월 동안 데이터의 보존을 금지하지 않는 한 현재 날짜에서 최대 1년까지 데이터를 내보낼 수 있습니다.

> [!div class="has-no-wrap"]  
> | # | 이름 | [데이터 형식(SQL Server)](/sql/t-sql/data-types/data-types-transact-sql) | 설명 |
> | :-: | :-: | :-: |:------------------- |
> | 0 | UsageId | `uniqueidentifier` | 고유 호출 식별자 |
> | 1 | 통화 ID | `nvarchar(64)` | 호출 식별자입니다. 고유하게 보장되지 않습니다. |
> | 2 | 회의 ID | `nvarchar(64)` | 오디오 회의의 ID |
> | 3 | 사용자 위치 | `nvarchar(2)` | 사용자 국가 코드, [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 4 | AAD ObjectId | `uniqueidentifier` | 사용자 ID를 Azure Active Directory.<br/> 이 및 기타 사용자 정보는 봇 호출 형식에 대해 null/비어 있습니다(ucap_in, ucap_out) |
> | 5 | UPN | `nvarchar(128)` | 에서 UserPrincipalName(로그인 이름)을 Azure Active Directory.<br/>일반적으로 사용자의 SIP 주소와 동일하며 사용자의 전자 메일 주소와 같을 수 있습니다. |
> | 6 | 사용자 표시 이름 | `nvarchar(128)` | 사용자의 표시 이름 |
> | 7 | 발신자 ID | `nvarchar(128)` | 인바운드 호출에 대한 호출을 받은 번호 또는 아웃바운드 호출에 대해 전화를 걸 수 있는 번호입니다. [E.164 형식](https://en.wikipedia.org/wiki/E.164) |
> | 8 | 통화 유형 | `nvarchar(32)` | 통화가 PSTN 아웃바운드 호출인지 인바운드 호출인지 여부와 사용자에 의해 배치된 호출 또는 오디오 회의와 같은 호출 유형 |
> | 9 | 숫자 형식 | `nvarchar(16)` | 사용자 전화 번호 유형(예: 무료 전화 번호 서비스)입니다. |
> | 10 | 국내/국제 | `nvarchar(16)` | 통화가 국내(국가 또는 지역 내) 또는 국제(국가 또는 지역 외부)에 따라 사용자의 위치를 기준으로 하는지 여부 |
> | 11 | 대상 전화 걸기 | `nvarchar(64)` | 전화 걸기 국가 또는 지역 |
> | 12 | 대상 번호 | `nvarchar(32)` | [E.164](https://en.wikipedia.org/wiki/E.164) 형식으로 전화 걸기 번호 |
> | 13 | 시작 시간 | `datetimeoffset` | 통화 시작 시간 |
> | 14 | 종료 시간 | `datetimeoffset` | 통화 종료 시간 |
> | 15 | 기간 초 | `int` | 통화가 연결된 시간 |
> | 16 | 연결 요금 | `numeric(16, 2)` | 연결 요금 가격 |
> | 17 | 요금 | `numeric(16, 2)` | 계정에 청구되는 통화 비용 또는 금액 |
> | 18 | 통화 | `nvarchar(3)` | 통화 비용을 계산하는 데 사용되는 통화[유형(ISO 4217)](https://en.wikipedia.org/wiki/ISO_4217) |
> | 19 | 기능 | `nvarchar(32)` | 통화에 사용되는 라이선스 |

### <a name="exported-direct-routing-usage-report"></a>내보내진 직접 라우팅 사용 현황 보고서

국가별 규정이 해당 기간 동안 데이터의 보존을 금지하지 않는 한 현재 날짜에서 최대 5개월(150일)까지 데이터를 내보낼 수 있습니다.

> [!div class="has-no-wrap"]  
> | # | 이름 | [데이터 형식(SQL Server)](/sql/t-sql/data-types/data-types-transact-sql) | 설명 |
> | :-: | :-: | :-: |:------------------- |
> | 0 | CorrelationId | `uniqueidentifier` | 고유 호출 식별자 |
> | 1 | SIP 주소 | `nvarchar(128)` | 전화를 걸거나 받은 사용자 또는 봇의 주소입니다.<br/>이는 일반적으로 SIP 주소와 동일한 Azure Active Directory 사용자PrincipalName(UPN, 로그인 이름)입니다. |
> | 2 | 표시 이름 | `nvarchar(128)` | 사용자 또는 호출 봇의 이름(예: 큐 또는 호출 자동 전화 교환)은 Microsoft 365 관리 센터 |
> | 3 | 사용자 국가 | `nvarchar(2)` | 사용자 국가 코드, [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 4 | 초대 시간 | `datetimeoffset` | 초기 초대가 SBC로 Teams 또는 봇 호출에서 아웃바운드를 보내거나 SBC에서 직접 라우팅의 SIP 프록시 Teams 또는 봇 호출로 인바운드를 받은 경우 |
> | 5 | 시작 시간 | `datetimeoffset` | SIP 프록시가 아웃바운드(Teams/봇에서 SIP 메시지 "200 확인")를 받았거나, SIP 프록시가 인바운드 통화의 백엔드 내에서 다음 홉에 초대를 Teams(PSTN 사용자를 Teams/봇에) 전송한 시간입니다.<br/>실패한 호출 및 변경되지 않은 호출의 경우 초대 또는 실패 시간과 같을 수 있습니다. |
> | 6 | 실패 시간 | `datetimeoffset` | 실패한 호출(완전히 설정되지 않은) 호출에만 존재합니다. |
> | 7 | 종료 시간 | `datetimeoffset` | 성공(완전히 설정된) 호출에만 존재합니다. 통화가 종료된 시간 |
> | 8 | 기간(초) | `int` | 통화 기간 |
> | 9 | 성공 | `nvarchar(3)` | 예/아니요. 성공 또는 시도 |
> | 10 | 발신자 번호 | `nvarchar(32)` | 호출한 사용자 또는 봇의 수입니다. Team 사용자 호출에 대한 인바운드에서 PSTN 사용자로, Teams 사용자 호출의 아웃바운드에 사용자 번호가 Teams 됩니다. |
> | 12 | 발신자 번호 | `nvarchar(32)` | 호출을 받은 사용자 또는 봇의 수입니다. Team 사용자 호출에 대한 인바운드에서 해당 사용자가 Teams 사용자가 됩니다. Teams 사용자 호출에서 아웃바운드가 PSTN 사용자입니다. |
> | 13 | 통화 유형 | `nvarchar(32)` | 통화 유형 및 방향 |
> | 14 | 미디어용 Azure 지역 | `nvarchar(8)` | 비우회 호출의 미디어 경로에 사용되는 데이터 센터 |
> | 15 | 신호에 대한 Azure 지역 | `nvarchar(8)` | 우회 호출 및 비우회 호출 모두에 대한 신호 전송에 사용되는 데이터 센터 |
> | 16 | 최종 SIP 코드 | `int` | 호출이 종료된 코드, [RFC 3261](https://tools.ietf.org/html/rfc3261) |
> | 17 | 최종 Microsoft 하위 코드 | `int` | SIP 코드 외에도 Microsoft에는 특정 문제를 나타내는 자체 하위 코드가 있습니다. |
> | 18 | 최종 SIP 구 | `nvarchar(256)` | SIP 코드 및 Microsoft 하위 코드에 대한 설명 |
> | 19 | SBC FQDN | `nvarchar(64)` | 세션 테두리 컨트롤러의 완전 자격을 갖춘 도메인 이름 |
> | 20 | 미디어 바이패스 | `nvarchar(3)` | 예/아니요. 미디어 우회에 대해 트렁크를 사용하도록 설정되어 있는지 또는 그렇지 않은지 나타냅니다. |
> | 21 | 공유 상관 관계 ID | `uniqueidentifier` | 두 개 이상의 호출이 관련이 있는지 나타냅니다. |


## <a name="related-topics"></a>관련 항목

- [Teams 분석 및 보고](teams-reporting-reference.md)