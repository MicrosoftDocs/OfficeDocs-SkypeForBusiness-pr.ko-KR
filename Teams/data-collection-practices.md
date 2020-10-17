---
title: 데이터 수집 사례
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, allancar
ms.topic: reference
ms.assetid: c17e8ea6-b83b-4345-9401-47a6c8b13aad
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Legal
- seo-marvel-mar2020
hideEdit: true
description: 제품 개선을 계획하는데 Teams 및 비즈니스용 Skype 사용과 문제점들을 이해하기 위해 어떻게 Microsoft에서 인구 조사, 사용 및 오류 데이터를 수집하는지 알아봅니다.
ms.openlocfilehash: b7f1f7b63645adfb0cfa0c492a680059ef383402
ms.sourcegitcommit: f5ad0fc5be7201b71da4f13586972831c9961e51
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2020
ms.locfileid: "47651234"
---
# <a name="skype-for-business-and-microsoft-teams-data-collection-practices"></a>비즈니스용 Skype 및 Microsoft Teams의 데이터 수집 사례

비즈니스용 Skype 서버 및 비즈니스용 Skype Online, 비즈니스용 skype 및 Microsoft Teams 앱은 해당 제품이 어떻게 사용되는지 이해하고 로그인 오류 등 발생하는 오류의 종류를 Microsoft가 이해하는데 도움이 되도록 데이터를 수집합니다. 이 정보는 사용 패턴을 이해하고, 새로운 기능을 계획하며, 문제를 해결하 는데 도움이 됩니다.

몇가지 사용 현황 데이터의 경우 자동으로 수집되지만, 다른 데이터는 관리자 및/또는 사용자가 수집을 허용한 경우에만 수집됩니다. 데이터 수집은 다음 세 가지 범주로 나뉩니다.

- 인구 조사 데이터

- 사용 현황 데이터

- 오류 보고 데이터

## <a name="census-data"></a>인구 조사 데이터

인구 조사 데이터는 비즈니스용 Skype를 제공, 지원 및 개선하기 위해서만 사용됩니다. Microsoft Teams 및 비즈니스용 Skype Online 여기에는 장치 및 운영 체제 버전과 같은 환경 정보와 지역 및 언어 설정이 포함됩니다. 로그인 시도와 실패에대 한 카운터도 포함합니다. 다음은 수집되는 인구 조사 데이터의 몇 가지 예입니다.

|**데이터 형식**|**예**|**참고**|
|:-----|:-----|:-----|
|AppName  <br/> |iPhoneSkype  <br/> ||
|DeviceModel  <br/> |iPhone  <br/> ||
|OSName  <br/> |iPhoneiOS  <br/> ||
|OSVersion  <br/> |8.3  <br/> ||
|UserLanguage  <br/> |EN-US  <br/> ||
|UserID  <br/> |E296D735-4F36-4E18-7C3B-52E1A02A0164  <br/> |ID가 클라이언트에서 한번, 원격 분석 서비스에서 다시 한번 해시됩니다. 해시는 ID가 특정 사용자에게 연결될 수 없도록 합니다.  <br/> |
|DeviceID  <br/> |5E872200-F546-4CCD-8F23-AF5F507AA2DD  <br/> |장치 ID는 장치에서 임의로 생성되어 원격 분석 서비스로 전송되는 GUID입니다.  <br/> |

인구 조사 데이터에는 사용자의 조직이나 사용자를 식별하는 정보가 포함 되어 있지 않습니다. 자세한 내용은 [비즈니스용 Skype의 개인정보취급방침](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx)을 참조하세요.

인구 조사 데이터는 기본적으로 켜져 있으며 관리자 또는 최종 사용자에 의해 해제될 수 없습니다.

## <a name="usage-data"></a>사용 현황 데이터

사용 현황 데이터에는 통화 횟수, 보내거나 받은 메시지 수, 참가한 모임 수, 사용한 기능의 빈도 그리고 안정성 문제와 같은 정보를 포함하고 있습니다.

사용 현황 데이터는 contoso.com과 같은 조직의 식별 정보를 포함할 수 있습니다. 다음은 수집되는 사용 현황 데이터의 몇 가지 예입니다.

|**데이터 형식**|**예**|**참고**|
|:-----|:-----|:-----|
|보낸 메시지  <br/> |12  <br/> ||
|받은 메시지  <br/> |5  <br/> ||
|모임 참가(시도)  <br/> |5  <br/> ||
|모임 참가(성공)  <br/> |4  <br/> ||
|통화/모임 시간  <br/> |30분  <br/> ||
|FederationPartner  <br/> |Microsoft.com  <br/> |이것은 Office 365에 등록된 조직의 이름이며, 애매하게 만들지 않은 일반 텍스트로 전송됩니다.  <br/> |

사용 현황 데이터에는 사용자를 식별하는 정보가 포함 되어 있지 않습니다.

사용 현황 데이터 수집은 기본적으로 켜져 있지만 온-프레미스 관리자는 비즈니스용 Skype 서버에서 DisableAutomaticSendTracing 그룹 정책 설정을 이용하여 해당 기능을 해제할 수 있습니다. 이 설정을 끄면 조직의 모든 사용자에게 적용됩니다. 자세한 내용은 [클라이언트 부트스트랩 정책 구성](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies)을 참조하세요.

최종 사용자는 사용 현황 데이터 수집을 설정하거나 해제할 수 없습니다.

Skype 모임 앱과 조인 시작 관리자 웹 페이지에서 원격 분석을 제어하는 방법은 다음 정책을 통해 확인할 수 있습니다.

`Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True`

이 정책은 기본값이 False이므로 원격 분석 수집은 기본적으로 해제되어 있습니다. 해당 설정은 풀 단위로 설정되어 있고 Skype 모임 앱을 통해 해당 서버에 호스트 되어 있는 모임에 연결하는 모든 사용자를 제어합니다.

## <a name="error-reporting-data"></a>오류 보고 데이터

오류 보고 데이터에는 성능 및 안정성에 대한 정보, 장치 구성, 네트워크 연결 품질, 오류 코드, 오류 로그 및 예외가 포함될 수 있습니다. 다음은 수집되는 오류 보고 데이터의 몇 가지 예입니다.

|**데이터 형식**|**예**|**참고**|
|:-----|:-----|:-----|
|메시지 방향  <br/> |수신  <br/> ||
|대화 상태  <br/> |유휴  <br/> ||
|대화 스레드 ID  <br/> |AdDO8hsJqilU93hQHC3OZaPR2saEA==  <br/> ||
|UserID  <br/> |amosmarble <br/> |ID는 저장하기 전 원격 분석 서비스가 해시하여 암호화 되지 않은 일반 텍스트로 전송됩니다.  <br/> |

오류 보고 데이터에는 사용자의 IP 주소 및 세션 초기화 프로토콜인 SIP URI(Uniform Resource Identifier)와 같은 개인 식별 정보를 포함할 수도 있습니다. 수집되는 항목에 대한 자세한 내용은 [비즈니스용 Skype 개인정보취급 방침](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx)을 참조하세요.

오류 보고에는 두 가지 작업을 요구합니다.

- DisableAutomaticSendTracing 그룹 정책 설정은 서버 또는 테넌트 관리 센터에서 False로 설정됩니다.(기본 상태) 자세한 내용은 [클라이언트 부트스트랩 정책 구성](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies)을 참조하세요.
    
- 최종 사용자는 개별적으로 비즈니스용 Skype 클라이언트의 일반 탭에서 옵트인합니다.(기어 아이콘 ![기어를 나타내는 아이콘](media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png)을 클릭하면 표시된 **일반** 탭으로 **옵션** 대화 상자가 열립니다.) 
    
 
![옵션 대화 상자의 데이터 수집 확인란 스크린샷](media/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
Skype 모임 앱의 경우 MeetingUxEnableTelemetry가 오류 보고도 제어합니다. Windows의 크래시가 발생하더라도 Watson 설정이 크래시 정보 업로드를 제어합니다. 데스크톱 클라이언트 대화 상자에 표시 되는 것과 같은 사용자 설정은 Skype 모임 앱에 없습니다.

자세한 내용은 [비즈니스용 Skype의 일반 옵션 설정](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439)을 참조하세요.

[비즈니스용 Skype Online을 위한 네트워크 설정](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66)을 참조하여 네트워크를 설정할 수 있습니다.

중국에서 21vianet이 운영하는 Microsoft 365 또는 Office 365를 사용하는 경우 [21Vianet이 운영하는 비즈니스용 Skype Online 네트워크 설정](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf)을 참조하세요.

## <a name="related-topics"></a>관련 항목
[오디오 회의 및 통화 요금제 국가 및 지역 가용성](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
