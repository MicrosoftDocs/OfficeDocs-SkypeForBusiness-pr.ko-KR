---
title: 데이터 수집 방법
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, allancar
ms.topic: reference
ms.assetid: c17e8ea6-b83b-4345-9401-47a6c8b13aad
ms.tgt.pltfrm: cloud
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Legal
hideEdit: true
description: Microsoft는 비즈니스용 Skype를 사용 하는 방법과 사용자에 게 문제가 발생 하는 방식을 이해 하기 위해 인구 조사, 사용, 오류 데이터를 수집 합니다. 데이터는 제품 개선을 계획 하는 데 사용 됩니다.
ms.openlocfilehash: 532cfe380a9f61043e38768c4c5d7d9c9fa8e9a6
ms.sourcegitcommit: b92b673e718e34b6ebda6de57ad69eb6651faa98
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2019
ms.locfileid: "36183692"
---
# <a name="skype-for-business-and-microsoft-teams-data-collection-practices"></a>비즈니스용 Skype 및 Microsoft 팀 데이터 수집 방법

비즈니스용 skype 서버 및 비즈니스용 skype Online 및 Microsoft 팀 용 skype 앱, Microsoft에서 이러한 제품을 사용 하는 방법과 로그인 오류 등의 오류 종류에 대 한 데이터를 수집 하는 데 도움이 됩니다. 이 정보는 사용 패턴을 이해 하 고, 새 기능을 계획 하며, 문제 영역을 해결 하 고 해결 하는 데 도움이 됩니다.

일부 사용 데이터는 자동으로 수집 되지만, 관리자 및/또는 사용자가 허용 하도록 선택한 경우에만 다른 데이터를 수집할 수 있습니다. 데이터 수집은 다음 세 가지 범주로 나뉩니다.

- 인구 조사 데이터

- 사용 현황 데이터

- 오류 보고 데이터

## <a name="census-data"></a>인구 조사 데이터

인구 조사 데이터는 비즈니스용 Skype를 제공, 지원 및 개선 하는 용도로만 확보 됩니다. Microsoft 팀 및 비즈니스용 Skype Online. 여기에는 장치, 운영 체제 버전, 국가 및 언어 설정 등의 환경 정보가 포함 됩니다. 또한 로그인 시도 및 실패에 대 한 카운터도 포함 합니다. 다음은 수집 되는 인구 조사 데이터의 몇 가지 구체적인 예입니다.

|**데이터 형식**|**예**|**상속자**|
|:-----|:-----|:-----|
|AppName  <br/> |iPhoneSkype  <br/> ||
|DeviceModel  <br/> |iPhone  <br/> ||
|OSName  <br/> |iPhoneiOS  <br/> ||
|OSVersion  <br/> |8.3  <br/> ||
|UserLanguage  <br/> |EN-US  <br/> ||
|UserID  <br/> |E296D735-4F36-4E18-7C3B-52E1A02A0164  <br/> |ID는 클라이언트에서 한 번, 원격 분석 서비스에서 두 번 해시 됩니다. 해시를 사용 하면 ID를 특정 사용자에 게 연결할 수 없습니다.  <br/> |
|DeviceID  <br/> |5E872200-F546-4CCD-8F23-AF5F507AA2DD  <br/> |장치 ID는 장치에서 임의로 생성 되 고 원격 분석 서비스로 전송 되는 GUID입니다.  <br/> |

인구 조사 데이터에는 조직이 나 사용자를 식별 하는 정보가 포함 되어 있지 않습니다. 자세한 내용은 [비즈니스용 Skype 개인 정보 취급 방침](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) 을 참조 하세요.

인구 조사 data는 기본적으로 설정 되어 있으며 관리자 또는 최종 사용자가 해제할 수 없습니다.

## <a name="usage-data"></a>사용 현황 데이터

사용 현황 데이터에는 통화 수, 보내거나 받은 메신저 대화, 참가 한 모임 수, 사용 하는 기능 빈도, 안정성 문제 등의 정보가 포함 됩니다.

사용 현황 데이터에는 contoso.com 같은 조직을 식별 하는 정보가 포함 될 가능성이 있습니다. 다음은 수집 되는 사용 현황 데이터의 몇 가지 구체적인 예입니다.

|**데이터 형식**|**예**|**상속자**|
|:-----|:-----|:-----|
|보낸 메신저 대화  <br/> |까지  <br/> ||
|수신 된 메신저 대화  <br/> |5mb  <br/> ||
|모임 참가 (시도)  <br/> |5mb  <br/> ||
|모임 참가 (성공)  <br/> |4(tcp/ipv4)  <br/> ||
|통화/회의 시간 (분)  <br/> |30 분  <br/> ||
|FederationPartner  <br/> |Microsoft.com  <br/> |이것은 Office 365에 등록 된 조직의 이름이 며 일반 텍스트로 전송 되므로 난독 처리 되지 않습니다.  <br/> |

사용 현황 데이터에는 사용자를 식별 하는 정보가 포함 되어 있지 않습니다.

사용 현황 데이터 수집은 기본적으로 설정 되어 있지만 온-프레미스 관리자는 비즈니스용 Skype 서버의 Disable자동 Sendtracing 그룹 정책 설정을 사용 하 여 해제할 수 있습니다. 이 설정을 끄면 조직의 모든 사용자에 게 영향을 줍니다. 자세한 내용은 [클라이언트 부트스트랩 정책 구성을](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) 참조 하세요.

최종 사용자는 사용 현황 데이터 수집을 설정 하거나 해제할 수 없습니다.

Skype 모임 앱 및 참가 시작 관리자 웹 페이지의 경우이 정책을 통해 원격 분석을 제어 하는 방법이 있습니다.

`Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True`

이 정책의 기본값은 false 이므로 원격 분석 수집은 기본적으로 해제 되어 있습니다. 이 설정은 풀 단위이 고 Skype 모임 앱에 연결 하는 모든 사용자를 해당 서버에서 호스트 하는 모임에 제어 합니다.

## <a name="error-reporting-data"></a>오류 보고 데이터

오류 보고 데이터에는 성능 및 안정성, 장치 구성, 네트워크 연결 품질, 오류 코드, 오류 로그 및 예외에 대 한 정보가 포함 될 수 있습니다. 다음은 수집 되는 오류 보고 데이터의 몇 가지 구체적인 예입니다.

|**데이터 형식**|**예**|**상속자**|
|:-----|:-----|:-----|
|메시지 방향  <br/> |들어옴  <br/> ||
|대화 상태  <br/> |이면  <br/> ||
|대화 스레드 ID  <br/> |AdDO8hsJqilU93hQHC3OZaPR2saEA = =  <br/> ||
|UserID  <br/> |amosmarble <br/> |ID는 저장 하기 전에 원격 분석 서비스가 해시 하는 일반 텍스트로 전송 됩니다.  <br/> |

오류 보고 데이터에는 사용자의 IP 주소 및 세션 초기화 프로토콜 Uniform Resource Identifier (SIP URI)와 같은 개인 식별 가능한 정보도 포함 될 수 있습니다. 수집 된 내용에 대 한 자세한 설명은 비즈니스용 [Skype 개인 정보 취급 방침](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) 을 참조 하세요.

오류 보고에는 두 가지 사항이 필요 합니다.

- Disable자동 Sendtracing 그룹 정책 설정이 서버나 테 넌 트 관리 센터 (기본 상태인 경우)에서 False로 설정 되어 있습니다. 자세한 내용은 [클라이언트 부트스트랩 정책 구성을](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) 참조 하세요.
    
- 최종 사용자 ![의 일반 탭 (기어 아이콘을 클릭 하면 기어를 ](media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) 나타내는 아이콘에는 비즈니스용 Skype 클라이언트에서 **일반** 탭이 표시 됨)의 **옵션** 대화 상자가 열립니다.
    
 
![옵션 대화 상자의 데이터 수집 확인란 스크린샷](media/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
Skype 모임 앱의 경우 MeetingUxEnableTelemetry는 또한 오류 보고 기능을 제어 하며, Windows에서의 충돌은 물론, Watson 설정이 크래시 정보를 업로드 하는 것을 제어 합니다. 데스크톱 클라이언트 대화 상자에 표시 되는 것과 같은 Skype 모임 앱에 대 한 사용자 설정은 없습니다.

자세한 내용은 비즈니스용 [Skype에서 일반 옵션 설정을](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439) 참조 하세요.

네트워크 설정을 위해 [비즈니스용 Skype Online에 대 한 네트워크 설정을](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66) 볼 수 있습니다.

중국에서 21Vianet에서 운영 하는 Office 365를 사용 하는 경우 [21vianet에서 운영 하는 비즈니스용 Skype Online을 위한 네트워크 설정을](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf)참조 하세요.

## <a name="related-topics"></a>관련 항목
[사용자 환경 개선 프로그램](https://www.microsoft.com/products/ceip/default.mspx)

[오디오 회의 및 통화 요금제의 국가 및 지역 사용 가능 여부](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
