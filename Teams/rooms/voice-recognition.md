---
title: Teams 룸 음성 인식(음성 프로필)에 대한 테넌트 관리 제어
author: cazawideh
ms.author: czawideh
ms.reviewer: parisataheri
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Teams 회의실에서 음성 인식(음성 프로필)에 대한 테넌트 관리 제어에 대해 알아봅니다.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6afd8cbf6a62665dbdb4c472df9620d623011452
ms.sourcegitcommit: 3beef904411a9d5787a73678464003a868630649
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2022
ms.locfileid: "64817709"
---
# <a name="manage-voice-recognition-technology-controls-for-an-intelligent-speaker"></a>지능형 스피커에 대한 음성 인식 기술 컨트롤 관리

지능형 스피커는 음성 프로필 정보를 사용하여 라이브 전사에서 누가 말한지 인식합니다. Windows 회의실 Microsoft Teams 룸 인텔리전트 스피커가 장착된 경우 모임 중에 라이브 전사를 사용할 수 있습니다. 이 문서에서는 테넌트 관리자가 음성 인식에 사용되는 음성 프로파일링을 제어하여 라이브 전사를 생성하는 방법을 설명합니다. 조직에서 음성 인식 및 다음 기능을 사용하는 정도를 제어할 수 있습니다.

- 대본에서 화자의 이름을 편집합니다.
- 대본에서 단일 발화의 화자를 변경하거나 대본의 모든 발화에서 화자를 변경합니다(이후의 대본에는 적용되지 않음).
- 모임에 나열된 사용자의 화자 ID를 변경합니다.
- 모든 대본에서 해당 화자로 식별된 하나 이상의 발화 식별을 제거합니다.

## <a name="review-intelligent-speaker-requirements"></a>인텔리전트 스피커 요구 사항 검토

인텔리전트 스피커에는 특수한 7개의 마이크 배열이 포함되어 있습니다. 이 시스템은 음성 프로필 정보를 사용하여 회의실에서 최대 10명의 음성을 식별합니다.

인텔리전트 스피커 요구 사항은 다음과 같습니다.

- 회의실에는 최대 10명이 직접 참석해야 합니다.
- 회의실의 업로드 링크는 최소 7Mbps입니다.

Epos, Sennheiser 및 Yealink 인텔리전트 스피커가 지원됩니다.

> [!NOTE]
> 인텔리전트 스피커는 아직 지원되지 않는 인도를 제외한 모든 국가 및 지역에서 사용할 수 있습니다. 현재 생체 인식 등록 및 모임 내 전사에 지원되는 로캘 목록은 [지원되는 로캘](#supported-locales) 을 참조하세요.

## <a name="set-up-an-intelligent-speaker"></a>지능형 스피커 설정

인텔리전트 스피커는 USB를 사용하여 Teams 룸 콘솔에 직접 연결합니다.

> [!NOTE]
> Yealink Intelligent Speaker는 Yealink 콘솔과 함께 사용해야 **합니다** .

> [!NOTE]
> Logitech Surface Pro Microsoft Teams 룸 연결된 인텔리전트 스피커는 지원되지 않습니다. Teams 룸 도크를 통해 지능형 스피커를 인식할 수 없는 알려진 문제가 있습니다.

인텔리전트 스피커는 벽과 노트북과 같은 대형 물체에서 8인치(20cm) 이상 떨어져 있어야 합니다. 인텔리전트 스피커 USB 케이블이 설치하기에 충분하지 않은 경우 케이블 확장기를 사용합니다.

1. 관리자 권한으로 콘솔에 로그인합니다.
2. 인텔리전트 스피커 마이크 및 스피커와 일치하도록 Teams 디바이스 설정을 지정합니다.
   회의실 콘솔 대신 TAC 포털을 통해 이 작업을 수행할 수도 있습니다.

   이 다이어그램은 디바이스에 데이터 상자가 포함된 경우 지능형 스피커가 디바이스에 연결되는 방법을 보여줍니다.

   ![스피커, 전원 및 데이터 상자가 있는 인텔리전트 스피커 설정 한 줄은 콘솔의 USB 포트로 이동하고 다른 줄은 전원으로 이동합니다.](../media/intelligent-speakers1.png)

   이 다이어그램은 디바이스에 데이터 상자가 없는 경우 인텔리전트 스피커가 디바이스에 연결되는 방법을 보여줍니다.

   ![스피커가 콘솔에 직접 연결되는 인텔리전트 스피커 설정입니다.](../media/intelligent-speakers2.png)

> [!Note]
> EPOS 및 Yealink 디바이스에는 "EPOS" 또는 "Yealink" 접두사 및 스피커 이름에 "UAC2_RENDER", 마이크 이름에 "UAC2_TEAMS"이 포함되어야 합니다. 드롭다운 메뉴에서 이러한 마이크 및 스피커 이름을 찾을 수 없는 경우 인텔리전트 스피커 장치를 다시 시작합니다.

## <a name="enable-an-intelligent-speaker-user-recognition"></a>인텔리전트 스피커 사용자 인식 사용

음성 프로필 데이터는 인텔리전트 스피커와의 모든 모임에서 사용할 수 있습니다. 모임 설정에 대한 자세한 내용은 [Teams 모임 정책](../meetings-policies-recording-and-transcription.md#allow-transcription) 및 [PowerShell 모임 cmdlet](/powershell/module/skype/set-csteamsmeetingpolicy)을 참조하세요.

사용자의 음성 프로필 데이터는 정책을 구분하도록 설정되거나 모임 중에 모임이 아닌 초대 대상자가 들어갈 때 만들어집니다. 음성 프로필 데이터는 모임이 끝날 때 해제됩니다.

다음은 지능형 스피커 및 사용자 인식을 설정하는 데 필요한 정책입니다.

|정책|설명|값 및 동작|
|-|-|-|
|enrollUserOverride|테넌트에 대한 Teams 설정에서 음성 프로필 캡처 또는 등록을 설정하는 데 사용합니다. |**사용 안 함**<br><ul><li> 등록한 적이 없는 사용자는 보거나 등록하거나 다시 등록할 수 없습니다.<li>등록 흐름의 진입점은 숨겨집니다.<li>사용자가 등록 페이지에 대한 링크를 선택하면 조직에 대해 이 기능이 사용하도록 설정되지 않음을 나타내는 메시지가 표시됩니다.  <li>등록한 사용자는 Teams 설정에서 음성 프로필을 보고 제거할 수 있습니다. 음성 프로필을 제거하면 등록 흐름을 보거나 액세스하거나 완료할 수 없습니다.</li></ul><br>**사용**<br><ul><li> 사용자는 등록 흐름을 보고, 액세스하고, 완료할 수 있습니다.<li>진입점은 **인식** 탭 아래의 Teams 설정 페이지에 표시됩니다.</li></ul>|
|roomAttributeUserOverride|회의실에서 음성 기반 사용자 ID를 제어합니다. 이 설정은 Teams 룸 계정에 필요합니다.| **해제**<br><ul><li>Teams 룸 장치는 회의실에서 오디오 스트림 절약 대역폭을 보내지 않습니다. <li>회의실 사용자는 특성이 지정되거나 구별되지 않으며 음성 서명은 전혀 검색되거나 사용되지 않습니다.<li>회의실 사용자를 알 수 없습니다.</li></ul> <br>**특성**<br><ul><li>룸 사용자는 등록 상태에 따라 특성이 지정됩니다.<li>등록된 사용자는 전사에 자신의 이름으로 표시됩니다.  <li>등록되지 않은 사용자는 Speaker \<n>로 표시됩니다.<li>Teams 룸 장치는 방에서 7개의 오디오 스트림을 보냅니다.</ul> <br>**구별**<br> <ul><li>회의실 사용자는 화자 1, 스피커 2, .... 전사의 발표자 \<n> 입니다.</li><li>사용자의 등록 상태에 관계없이 해당 이름은 전사에 표시되지 않습니다.</li><li>Teams 룸 장치는 방에서 7개의 오디오 스트림을 보냅니다.</li></ul>
|AllowTranscription|사용자 및 Teams 룸 계정에 필요합니다.|**True** 및 **False**|
||||

Teams 관리 센터에서 **전사** 정책을 설정합니다. 설정 기본적으로 **꺼져** 있습니다.

![모임 정책이 강조 표시된 관리 센터에서 전사 허용이 선택되었습니다.](../media/allow-transcription1.png)
  
> [!NOTE]
> 정책이 할당된 후 적용되는 데 최대 48시간이 걸릴 수 있습니다. 정책을 더 빨리 적용하려면 계정을 로그아웃하고 다시 로그인해야 합니다.

## <a name="frequently-asked-questions-faq"></a>자주 묻는 질문 (FAQ)

**음성 프로필 데이터는 어디에 저장되어 있나요?**

음성 프로필 데이터는 사용자 콘텐츠와 함께 Office 365 클라우드에 저장됩니다.

**보존 타임라인 및 정책은 무엇인가요?**

일반 보존 정책은 [데이터 보존 개요](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview)에 설명되어 있습니다. 또한 사용자가 해당 1년 기간 내에 지능형 스피커를 사용하는 모임에 초대되지 않은 경우 사용자의 음성 프로필 데이터는 1년 후에 삭제됩니다. 데이터는 기존 직원의 모임에서 사용되지 않습니다. 직원이 퇴사한 경우 음성 프로필 데이터는 사용자 콘텐츠로 간주되며 데이터 [보존 개요](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview)에 설명된 Office 365 데이터 보존 정책에 따라 처리됩니다.

**음성 프로필 데이터는 Microsoft 서비스 걸쳐 사용합니까?**

아니요, 음성 프로필 데이터는 사용자가 동의한 용도로만 사용됩니다. Microsoft는 Teams 음성 인식 시나리오 내에서만 음성 프로필 데이터를 사용하지 않습니다.

예를 들어 Microsoft는 다음과 같은 상황에서 데이터를 사용하지 않습니다.

**다른 조직에서 모임에 참가할 때 내 음성 프로필 데이터가 사용되나요?**

조직의 사용자가 구성한 모임에만 해당되지 않습니다.

**내 음성 프로필을 내보내는 방법**

IT 관리자는 언제든지 오디오 데이터를 내보낼 수 있습니다.

## <a name="supported-locales"></a>지원되는 로캘

다음 등록 및 모임 내 전사 로캘은 모든 국가 및 지역에서 지원됩니다.

### <a name="enrollment-locales"></a>등록 로캘

최종 사용자는 다음 로캘에서 인식을 위해 음성을 등록할 수 있습니다.

|**언어**|**국가/지역**|**문화권 ID**|
|:-----|:-----|:-----|
|영어  <br/> |오스트레일리아 <br/> |en-AU  <br/> |
|영어  <br/> |캐나다  <br/> |en-CA <br/> |
|영어  <br/> |인도  <br/> |en-IN  <br/> |
|영어  <br/> |뉴질랜드  <br/> |en-NZ  <br/> |
|영어  <br/> |영국  <br/> |en-GB  <br/> |
|영어  <br/> |미국  <br/> |en-US  <br/> |


### <a name="in-meeting-transcription-locales"></a>모임 내 전사 로캘

최종 사용자가 등록되면 모임 중에 음성을 인식할 수 있으며 모임이 다음 로캘 중 하나로 설정된 경우 전사에서 식별할 수 있습니다.

|**언어**|**국가/지역**|**문화권 ID**|
|:-----|:-----|:-----|
|중국어(간체)  <br/> |중국  <br/> |zh-CN  <br/> |
|영어  <br/> |오스트레일리아 <br/> |en-AU  <br/> |
|영어  <br/> |캐나다  <br/> |en-CA <br/> |
|영어  <br/> |인도  <br/> |en-IN  <br/> |
|영어  <br/> |뉴질랜드  <br/> |en-NZ  <br/> |
|영어  <br/> |영국  <br/> |en-GB  <br/> |
|영어  <br/> |미국  <br/> |en-US  <br/> |
|프랑스어  <br/> |캐나다  <br/> |fr-CA  <br/> |
|프랑스어  <br/> |프랑스  <br/> |fr-FR  <br/> |
|독일어  <br/> |독일  <br/> |de-DE  <br/> |
|이탈리아어  <br/> |이탈리아  <br/> | it-IT <br/> |
|일본어  <br/> |일본  <br/> |ja-JP  <br/> |
|한국어  <br/> |대한민국  <br/> |ko-KR  <br/> |
|포르투갈어  <br/> |브라질  <br/> |pt-BR  <br/> |
|스페인어  <br/> |멕시코  <br/> |es-MX  <br/> |
|스페인어  <br/> |스페인  <br/> |es-ES  <br/> |

## <a name="related-topics"></a>관련 항목

[지원 문서: 인텔리전트 스피커를 사용하여 회의실 내 참가자 식별 ](https://support.microsoft.com/office/use-teams-intelligent-speakers-to-identify-in-room-participants-in-meeting-transcription-a075d6c0-30b3-44b9-b218-556a87fadc00)
