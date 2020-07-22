---
title: PSTN 사용 현황 보고서
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 74eda791-c41f-4fd9-ae0b-913342e7ab04
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
description: 새로운 비즈니스용 Skype 관리 센터 보고서 영역에 조직의 통화 및 오디오 회의 활동이 표시 됩니다. 이 기능을 사용 하면 보고서를 자세히 분석 하 여 각 사용자의 활동에 대 한 세부적인 통찰력을 제공할 수 있습니다. 예를 들어 비즈니스용 Skype PSTN 사용 정보 보고서를 사용 하 여 인바운드/아웃 바운드 통화와 이러한 통화 비용에 소요 된 시간을 확인할 수 있습니다. 통화 비용을 포함 하 여 오디오 회의 PSTN 사용 정보를 보고, 사용 현황 및 통화 대금 청구 세부 정보를 파악 하 여 조직 내 사용량을 확인할 수 있습니다.
ms.openlocfilehash: 09d372f6526d14a65e878271a1b277fc19d7d3e4
ms.sourcegitcommit: bdf6cea0face74809ad3b8b935bc14ad60b3bb35
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/21/2020
ms.locfileid: "45201172"
---
# <a name="pstn-usage-report"></a>PSTN 사용 현황 보고서

새로운 비즈니스용 Skype 관리 센터 **보고서** 영역에 조직의 통화 및 오디오 회의 활동이 표시 됩니다. 이 기능을 사용 하면 보고서를 자세히 분석 하 여 각 사용자의 활동에 대 한 세부적인 통찰력을 제공할 수 있습니다. 예를 들어 **비즈니스용 SKYPE PSTN 사용 정보** 보고서를 사용 하 여 인바운드/아웃 바운드 통화와 이러한 통화 비용에 소요 된 시간을 확인할 수 있습니다. 통화 비용을 포함 하 여 오디오 회의 PSTN 사용 정보를 보고, 사용 현황 및 통화 대금 청구 세부 정보를 파악 하 여 조직 내 사용량을 확인할 수 있습니다.
  
사용할 수 있는 보고서에 대 한 자세한 내용은 [보고서 개요](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) 를 확인 하세요.
  
이 보고서는 다른 비즈니스용 Skype 보고서와 함께 조직 전체의 통화 사용을 포함 하는 활동에 대 한 세부 정보를 제공 합니다. 이러한 세부 정보는 조직에 대 한 기타 비즈니스 의사 결정과 [통신 크레딧을](/microsoftteams/what-are-communications-credits)설정 하는 데 매우 유용 합니다.
  
> [!NOTE]
> Microsoft 365 관리 센터에 관리자로 로그온 하면 모든 비즈니스용 Skype 보고서를 볼 수 있습니다. 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-usage-details-report"></a>비즈니스용 Skype PSTN 사용 정보 보고서에 액세스 하는 방법

![비즈니스용 skype 로고를 나타내는 아이콘](../images/sfb-logo-30x30.png) **비즈니스용 Skype 관리 센터 사용**

- 관리 센터로 이동 합니다. **관리**센터  >  **비즈니스용 Skype 관리 센터**에서  >  **Reports**  >  **PSTN 사용 정보**를 보고 >.
    
    > [!NOTE]
    > 사용 중인 Microsoft 365 또는 Office 365 구독에 따라 여기에 표시 된 모든 제품 및 보고서가 표시 되지 않을 수 있습니다.
  
## <a name="interpret-the-skype-for-business-pstn-usage-report"></a>비즈니스용 Skype PSTN 사용 보고서 해석

표시 되는 각 열을 확인 하 여 사용자의 비즈니스용 Skype PSTN 사용에 대 한 보기를 얻을 수 있습니다.
  
보고서의 모양은 다음과 같습니다.
  
[![비즈니스용 SKYPE PSTN 사용 보고서 ](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png)](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png#lightbox)

***
![번호 1](../images/sfbcallout1.png)<br/>이 표에서는 사용자 당 모든 PSTN 사용을 분석 한 결과를 보여 줍니다. 비즈니스용 Skype에 할당 된 모든 사용자와 해당 PSTN 사용이 표시 됩니다. 표에 열을 추가 하거나 제거할 수 있습니다.
*    통화 **id** 는 통화에 대 한 통화 id입니다. Microsoft 서비스 지원을 호출할 때 사용 되는 통화의 식별자입니다.
*    **사용자 ID** 는 사용자의 로그인 이름입니다.
*    **전화 번호** 는 통화를 수신 하는 비즈니스용 Skype 전화 번호 이거나, 발신 전화를 거는 번호입니다.
*    **사용자 위치** 는 사용자가 위치한 국가/지역입니다.
*    **발신자 id** 는 수신 전화에 대 한 발신자의 전화 번호 (발신자 id)로, 통화를 발생 시킨 번호 또는 통화가 발신 전화를 위해 시작 된 비즈니스용 Skype 번호입니다.
*    **통화 유형은** 호출이 PSTN 발신 또는 수신 전화이 고 사용자 또는 오디오 회의와 같은 통화 유형에 해당 하는지 여부입니다. 표시 될 수 있는 통화 종류는 다음과 같습니다. 

     **통화 요금제 호출 형식** 
     *    **user_in** (사용자가 인바운드 PSTN 통화 받음) 
     *    **user_out** (사용자가 아웃 바운드 PSTN 통화를 배치 하였습니다) 
     *    **user_out_conf** (사용자가 2 명 이상의 PSTN 참가자를 3 방향 전화 회의 통화와 같은 통화에 추가) 
     *    **user_out_transfer** (사용자가 PSTN 번호로 통화를 전송 했습니다) 
     *    **user_out_forwarding** (사용자가 PSTN 번호로 착신 전환 됨)

     **오디오 회의 통화 유형**
     *    **conf_in** (오디오 회의 브리지에 대 한 인바운드 전화). 이 통화 유형의 레코드에 대해 **사용자 ID** 열에 지정 된 사용자가 모임의 이끌이에 해당 합니다.
     *    **conf_out** (일반적으로 전화에 PSTN 번호를 추가 하는 오디오 회의 브리지의 발신 전화). 이 통화 유형의 레코드에 대해 **사용자 ID** 열에 지정 된 사용자가 모임의 이끌이에 해당 합니다.

     **통합 커뮤니케이션 애플리케이션 (c-AP)** 
     *    **ucap_in** (자동 전화 교환 또는 통화 대기열 등의 UC 응용 프로그램에 대 한 인바운드 PSTN 통화) 
     *    **ucap_out** (자동 전화 교환 또는 통화 대기열 등의 UC 응용 프로그램에서 보낸 아웃 바운드 PSTN 통화)
         > [!NOTE]
         > 자동 전화 교환 또는 통화 대기열 등의 사용자에 게 전송 된 통화는이 호출 다리는 P2P (피어 투 피어) 음성 통화를 통해 PSTN 사용 보고서에 표시 되지 않습니다. 비즈니스용 Skype 관리 센터에서 "비즈니스용 skype 통화 분석" > 도구 아래에 있는 P2P 호출에 액세스할 수 있으며, 사용자 이름 또는 SIP 주소로 검색 하 여 날짜/시간 및/또는 원래 CLID (통화 라인 ID)를 기준으로 통화를 연관 시킬 수도 있습니다. 

     **국내/국제** 전화는 사용자 위치에 따라 거주 하는 통화가 국내 (국가/지역 내) 또는 국제 (국가/지역 외부)로 간주 되었는지 알려줍니다. 
*    **대상 전화 거** 는 국가/지역에서 프랑스, 독일 또는 미국 (미국) 등으로 거는 대상의 이름입니다. 
*    **Number type** 은 사용자의 전화 번호, 서비스 또는 무료 번호에서 가져온 전화 번호 유형입니다.  
*    **시작 시간 (UTC)** 은 통화를 시작 하거나 배치한 시간입니다. 
*    **기간은** 통화가 연결 된 시간입니다.  
*    **ConfID** 는 오디오 회의의 전화 회의 ID입니다. 
*    **청구** 는 계좌에 부과 되는 통화의 금액 또는 비용입니다. 
*    **통화** 는 통화 비용을 계산 하는 데 사용 되는 통화 유형입니다. 
*    **접근 권한** 값은 통화에 사용 되는 라이선스입니다. 표시 될 수 있는 라이선스 종류는 다음과 같습니다. 
     *    **MCOPSTNPP** -통신 크레딧 <br/> **MCOPSTN1** -국내 통화 요금제 (3000 min US/1200 최소 EU 요금제) 
     *    **MCOPSTN2** -국제 통화 요금제 
     *    **MCOPSTN5** -국내 통화 요금제 (120 분 통화 요금제) 
     *    **MCOPSTN6** -국내 통화 요금제 (240 분 통화 요금제) 참고: 제한 된 가용성
     *    **Mcomeetadd** 오디오 회의
     *    **MCOMEETACPEA** -분 당 오디오 회의 결제
     
> [!NOTE]
> 통화 또는 회의 구독에 포함 되지 않은 통화/시간 당 요금만 포함 하도록 보고서를 실행 하려면 "MCOPSTNPP" 기능을 사용 하 여 보고서를 필터링 합니다. 이렇게 하면 분당 모든 지불에 대 한 서비스를 제공할 수 있습니다.  분 단위 오디오 회의에는 "MCOPSTNPP" 대신 "MCOMEETACPEA"를 기준으로 필터링 합니다.  

> [!NOTE]
> 일부 필드에 "데이터 없음"이 표시 될 수도 있습니다. "데이터 없음"은 통화 유형이 나 접근 권한 값에 해당 필드를 적용할 수 없음을 의미 합니다. 

> [!NOTE]
> Telstra 또는 소프트 은행 통화 요금제가 있는 경우 PSTN 사용 보고서에 통화 정보 레코드가 표시 되지 않습니다. 보고 요구 사항에 대해 Telstra 또는 소프트 은행에 문의 하세요. 
***
![번호 2](../images/sfbcallout2.png)<br/>특정 열을 기준으로 그룹화 하려면 열을 클릭 하 여 하나 이상의 열에 있는 모든 데이터를 그룹화 하는 보기를 만들려는 경우 **열 머리글을 여기로 끌어** 놓습니다.
 ***

## <a name="exporting-pstn-usage-report"></a>PSTN 사용 보고서 내보내기

**Excel로 내보내기** 단추를 클릭 하거나 탭 하면 PSTN 사용 보고서를 다운로드할 수 있습니다. 국가 관련 규정이 12 개월 동안 데이터의 보존을 금지 하지 않는 한, 현재 날짜부터 1 년 까지의 데이터를 내보낼 수 있습니다.

이렇게 하면 모든 사용자의 데이터가 내보내며 추가 분석을 위해 간단한 정렬 및 필터링이 가능 합니다.

내보내기 프로세스는 완료 하는 데 몇 초에서 몇 분 정도 소요 될 수 있습니다 (데이터 수량에 따라 다름). 서버에서 내보내기가 완료 되 면 "**Calls. []" 라는 zip 파일을 받게 됩니다. `identifier` zip**",이 식별자는 문제 해결에 사용할 수 있는 내보내기의 고유 ID입니다.

전화 요금제와 직접 라우팅이 모두 있는 경우 내보낸 파일에는 두 제품 모두에 대 한 데이터가 포함 될 수 있습니다. PSTN 사용 보고서 파일의 파일 이름에는 "**PSTN. * 통화. `UTC date` csv**". PSTN 및 다이렉트 라우팅 파일 외에도,이 아카이브에는 "**parameters.json**" 파일이 포함 되어 있으며, 선택한 내보내기 시간 범위와 기능 (있는 경우)이 있습니다.

내보낸 파일은 [RFC 4180](https://tools.ietf.org/html/rfc4180) 표준과 호환 되는 CSV (쉼표로 구분 된 값) 파일입니다. 파일은 Excel 또는 다른 표준 규격 편집기에서 변환을 요구 하지 않고 열 수 있습니다.

CSV의 첫 번째 행에 열 이름이 포함 됩니다.

### <a name="fields-in-the-export"></a>내보내기의 필드

내보낸 파일에는 온라인 보고서에서 사용할 수 없는 추가 필드가 포함 되어 있습니다. 문제 해결 및 자동화 워크플로를 위해 사용 될 수 있습니다.

> [!div class="has-no-wrap"]  
> | #  | 이름 | [데이터 형식 (SQL Server)](https://docs.microsoft.com/sql/t-sql/data-types/data-types-transact-sql) | 설명 |
> | :-: | :-: | :-: |:------------------- |
> | 0 | UsageId | `uniqueidentifier` | 고유한 통화 식별자 |
> | 1 | 통화 ID | `nvarchar(64)` | 통화 식별자입니다. 고유 하지 않을 수 있습니다. |
> | 2 | 전화 회의 ID | `nvarchar(64)` | 오디오 회의의 ID입니다. |
> | 3 | 사용자 위치 | `nvarchar(2)` | 사용자의 국가 코드, [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 4(tcp/ipv4) | AAD ObjectId | `uniqueidentifier` | Azure Active Directory에서 사용자의 ID를 호출 하는 중입니다.<br/> 이 및 기타 사용자 정보는 봇 통화 형식 (ucap_in, ucap_out)에 대해 null/비어 있습니다. |
> | 5mb | UPN | `nvarchar(128)` | Azure Active Directory에서 UserPrincipalName (로그인 이름).<br/>이것은 일반적으로 사용자의 SIP 주소와 같으며 사용자의 전자 메일 주소와 같을 수 있습니다. |
> | 26 | 사용자 표시 이름 | `nvarchar(128)` | 사용자의 표시 이름 |
> | 7 | 발신자 ID | `nvarchar(128)` | 인바운드 통화에 대 한 통화 또는 발신 전화를 거는 번호를 수신 하는 번호입니다. [E 164](https://en.wikipedia.org/wiki/E.164) 형식 |
> | 20cm(8 | 통화 종류 | `nvarchar(32)` | 통화가 PSTN 아웃 바운드 통화 인지, 통화 유형 (예: 사용자 또는 음성 컨퍼런스)과 같은 통화 유형에 관계 됨 |
> | 되었는지 | 숫자 형식 | `nvarchar(16)` | 무료 번호 서비스와 같은 사용자의 전화 번호 유형 |
> | 1천만 | 국내/국제 | `nvarchar(16)` | 사용자의 위치에 따라 국가 또는 지역에 거주 하는 국가 또는 지역 외부 통화 인지 여부 |
> | mb | 대상 전화 | `nvarchar(64)` | 국가 또는 지역 전화 걸기 |
> | 까지 | 대상 번호 | `nvarchar(32)` | [E. \ 164](https://en.wikipedia.org/wiki/E.164) 형식으로 거는 번호 |
> | 일자 | 시작 시간 | `datetimeoffset` | 통화 시작 시간 (UTC, [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601)) |
> | 13 | 종료 시간 | `datetimeoffset` | 통화 종료 시간 (UTC, [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601)) |
> | ~ | 기간 (초) | `int` | 통화가 연결 된 기간 |
> | 16 | 연결 수수료 | `numeric(16, 2)` | 연결 수수료 금액 |
> | 17@@ | 부과 | `numeric(16, 2)` | 계좌에 부과 되는 통화 또는 비용의 금액입니다. |
> | awg | 통화 | `nvarchar(3)` | 통화 비용을 계산 하는 데 사용 되는 통화 유형입니다 ([ISO 4217](https://en.wikipedia.org/wiki/ISO_4217)). |
> | 인치 | 기능 | `nvarchar(32)` | 통화에 사용 된 라이선스 |

    
## <a name="want-to-see-other-skype-for-business-reports"></a>다른 비즈니스용 Skype 보고서를 보 시겠습니까?

- [비즈니스용 Skype 활동 보고서](activity-report.md) 사용자가 피어 투 피어를 사용 하는 시간과 회의 세션에서 참여 한 시간을 확인할 수 있습니다.
    
- [비즈니스용 Skype 장치 사용 현황 보고서](device-usage-report.md) 비즈니스용 Skype 앱이 설치 되어 있고 메신저 및 모임에 사용 되 고 있는 Windows 기반 운영 체제와 모바일 장치를 포함 하는 장치를 볼 수 있습니다.
    
- [비즈니스용 Skype 컨퍼런스 이끌이 활동 보고서](conference-organizer-activity-report.md) 사용자가 메신저 대화, 오디오/비디오, 응용 프로그램 공유, 웹, 다이얼 아웃, 타사, 제 3 자, 전화 걸기-Microsoft를 사용 하는 회의를 구성 하는 시간을 확인할 수 있습니다.
    
- [비즈니스용 Skype 컨퍼런스 참가자 활동 보고서](conference-participant-activity-report.md) 참가 하 고 있는 메신저, 오디오/비디오, 응용 프로그램 공유, 웹 및 전화 접속 오디오 회의가 얼마나 많은 지 확인할 수 있습니다.
    
- [비즈니스용 Skype 피어 투 피어 활동 보고서](peer-to-peer-activity-report.md) 사용자 들이 메신저 대화, 오디오/비디오, 응용 프로그램 공유, 파일 전송 중 어느 것을 사용 하 고 있는지 확인할 수 있습니다.
    
- [비즈니스용 Skype 사용자 차단 보고서](users-blocked-report.md) 조직의 사용자에 게 PSTN 통화를 차단 하는 것을 볼 수 있습니다.

- [비즈니스용 SKYPE PSTN 분 풀 보고서](pstn-minute-pools-report.md) 조직 내 현재 달 중 사용 된 시간 (분)을 확인할 수 있습니다.

- [비즈니스용 Skype 세션 정보 보고서](session-details-report.md) 개인 사용자의 통화 환경에 대 한 세부 정보를 확인할 수 있습니다.
    
## <a name="related-topics"></a>관련 항목
[관리 센터의 활동 보고서](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
  
  
 
