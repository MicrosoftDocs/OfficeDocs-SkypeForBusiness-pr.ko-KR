---
title: 음성 인식(음성 프로필)에 대한 테넌트 관리 Teams 룸
author: cichur
ms.author: v-cichur
ms.reviewer: parisataheri
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 회의실에서 음성 인식(음성 프로필)에 대한 테넌트 Teams 알아보세요.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6b4a8a5d0b866a3eb278ffdba575966f97c549d6
ms.sourcegitcommit: 35ee6946b6f560a268d1313bf51c3cc94d8d52f1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2021
ms.locfileid: "52997771"
---
# <a name="manage-voice-recognition-technology-controls-for-an-intelligent-speaker"></a>지능형 스피커에 대한 음성 인식 기술 컨트롤 관리

지능형 스피커는 음성 프로필 정보를 사용하여 라이브 전사에서 누구를 말한지 인식합니다. 회의실에 Microsoft Teams 룸 Windows 지능형 스피커가 장착되어 있는 경우 모임 중에 라이브 전사를 사용할 수 있습니다. 이 문서에서는 테넌트 관리자인 사용자가 음성 인식에 사용되는 음성 프로파일링을 제어하여 라이브 전사 생성 방법을 설명합니다. 조직에서 음성 인식 및 다음 기능을 사용하는 정도를 제어할 수 있습니다.

- 전사에서 발표자 이름을 편집합니다.
- 대본에서 단일 발화의 발언을 변경하거나 대본의 모든 발화에서 스피커를 변경합니다(하지만 향후 대본에는 제공되지 않습니다).
- 모임에 나열된 사용자에 대한 발표자 ID를 변경합니다.
- 모든 대본에서 해당 스피커로 식별된 하나 이상의 발언의 식별을 제거합니다.

## <a name="review-intelligent-speaker-requirements"></a>지능형 스피커 요구 사항 검토

지능형 스피커에는 특수 7개 마이크 배열이 포함되어 있습니다. 시스템은 음성 프로필 정보를 사용하여 회의실에서 최대 10명까지의 음성을 식별합니다.

다음 항목은 지능형 스피커 요구 사항입니다.

- 고객 테넌트는 미국(북아메리카)에 있어야 합니다. <sup>1</sup>
- 회의실에 최대 10명이 참석해야 합니다.
- 회의실에 최소 7Mbps의 업로드 링크가 있습니다.

 <sup>1</sup> 지능형 스피커 및 관련 음성 프로필 및 사용량은 EN-US 언어 및 미국(NA-미국 지역) 테넌트에서만 사용할 수 있습니다. 테넌트 사용자가 특성 전사에 지능형 스피커를 등록하고 사용하는 경우 두 조건 모두 true가 되어야 합니다.

## <a name="set-up-an-intelligent-speaker"></a>지능형 스피커 설정

지능형 스피커는 USB를 사용하여 본체에 Teams 룸 연결합니다. 최상의 결과를 얻기 위해 Yealink 브랜드 지능형 스피커를 Yealink 브랜드 콘솔과 함께 사용해야 합니다.

> [!NOTE]
> Yealink 지능형 **스피커는** Yealink 콘솔과 함께 사용되어야 합니다.

> [!NOTE]
> Logitech에 연결된 지능형 스피커는 지원하지 Surface Pro Microsoft Teams 룸. 도크를 통해 지능형 Teams 룸 인식할 수 없는 알려진 문제가 있습니다.

지능형 스피커는 벽과 노트북과 같은 큰 개체에서 8인치(20cm) 이상 떨어져 배치해야 합니다. 지능형 스피커 USB 케이블이 설치에 충분하지 않은 경우 케이블 확장 장치를 사용 합니다.

1. 관리자 권한으로 본체에 로그인합니다.
2. 지능형 Teams 마이크 및 스피커와 일치하게 디바이스 설정을 설정합니다.
   또한 룸 콘솔 대신 TAC 포털을 통해 이 작업을 할 수 있습니다.

   이 다이어그램은 디바이스에 데이터 상자가 있는 경우 지능형 스피커가 디바이스에 연결된 방법을 보여줍니다.

   ![스피커, 전원 및 데이터 상자가 있는 지능형 스피커 설정입니다. 한 줄은 본체의 USB 포트로 이동하고 다른 줄은 전원이 공급됩니다. ](../media/intelligent-speakers1.png)

   이 다이어그램은 디바이스에 데이터 상자가 없는 경우 지능형 스피커가 디바이스에 연결되는 방법을 보여줍니다.

   ![스피커가 본체에 직접 연결된 지능형 스피커 설정입니다. ](../media/intelligent-speakers2.png)

> [!Note]
> EPOS 및 Yealink 디바이스에는 "EPOS" 또는 "Yealink" UAC2_RENDER 마이크 이름에 "UAC2_TEAMS"가 포함되어야 합니다. 드롭다운 메뉴에서 이러한 마이크 및 스피커 이름을 찾을 수 없는 경우 Intelligent Speaker 디바이스를 다시 시작합니다.

## <a name="enable-an-intelligent-speaker-user-recognition"></a>지능형 스피커 사용자 인식 사용

지능형 스피커가 있는 모든 모임에서 음성 프로필 데이터를 사용할 수 있습니다. 모임 [Teams](../meeting-policies-in-teams.md#allow-transcription) 정책 및 [PowerShell 모임 cmdlet을](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) 참조하세요.

사용자의 음성 프로필 데이터는 정책이 구분하도록 설정되거나 모임이 아닌 초대자를 모임 중에 볼 때 만들어집니다. 모임이 끝날 때 음성 프로필 데이터가 비우기됩니다.

다음은 지능형 스피커 및 사용자 인식을 설정하는 데 필요한 정책입니다.

|정책|설명|값 및 동작|
|-|-|-|
|enrollUserOverride|테넌트에 대한 음성 프로필 캡처 또는 Teams 설정에 사용합니다. |**사용 안 함**<br><ul><li> 등록하지 않은 사용자는 보기, 등록 또는 다시 등록할 수 없습니다.<li>등록 흐름에 대한 진입점은 숨겨집니다.<li>사용자가 등록 페이지에 대한 링크를 선택하면 해당 조직에서 이 기능을 사용하도록 설정하지 않았다는 메시지가 표시됩니다.  <li>등록한 사용자는 설정에서 음성 프로필을 보고 제거할 Teams 있습니다. 음성 프로필을 제거하면 등록 흐름을 보고, 액세스하거나, 완료할 수 없습니다.</li></ul><br>**사용 가능**<br><ul><li> 사용자는 등록 흐름을 보고, 액세스하고, 완료할 수 있습니다.<li>진입점은 인식 탭의 Teams 설정 페이지에 **표시됩니다.**</li></ul>|
|roomAttributeUserOverride|회의실에서 음성 기반 사용자 ID를 제어합니다. 이 설정은 계정의 Teams 룸 필요합니다.| **해제**<br><ul><li>Teams 룸 디바이스는 방에서 오디오 스트림 저장 대역폭을 보내지 않습니다. <li>회의실 사용자는 기인하거나 구분되지 않습니다. 음성 서명은 검색되거나 사용되지 않습니다.<li>회의실 사용자는 알 수 없습니다.</li></ul> <br>**특성**<br><ul><li>룸 사용자는 등록 상태에 따라 기인됩니다.<li>등록된 사용자는 전사에 해당 이름과 함께 표시됩니다.  <li>등록되지 않은 사용자는 스피커 n으로 표시됩니다.<li>Teams 룸 디바이스는 방에서 7개의 오디오 스트림을 전송합니다.</ul> <br>**구분**<br> *이 설정은 나중에 사용할 수 있습니다.*|
|enabletranscription|사용자 및 Teams 계정에 필요합니다.|**True** 및 **False**|
||||

관리 Teams 관리 센터에서 전사 허용 정책을 **설정합니다.** 설정 **기본적으로 꺼집니다.**

![모임 정책을 강조 표시하고 전사 허용이 선택된 관리 센터](../media/allow-transcription1.png)

## <a name="frequently-asked-questions-faq"></a>자주 묻는 질문 (FAQ)

**음성 프로필 데이터는 어디에 저장하나요?**

음성 프로필 데이터는 사용자 Office 365 클라우드에 저장됩니다.

**보존 시간 표시 막대 및 정책이란?**

일반 보존 정책은 데이터 보존 개요 [에 설명되어 있습니다.](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview) 또한 사용자가 해당 3년 기간 내에 지능형 스피커를 사용하여 모임에 초대되지 않은 경우 사용자의 음성 프로필 데이터가 3년 후에 삭제됩니다. 기존 직원의 모임에는 데이터가 사용되지 않습니다. 직원이 회사를 떠났을 경우 음성 프로필 데이터는 사용자 콘텐츠로 간주되어 데이터 보존 개요에 Office 365 데이터 보존 정책에 따라 [처리됩니다.](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview)

**음성 프로필 데이터가 전체 사용자에 Microsoft 서비스?**

아니요, 음성 프로필 데이터는 사용자가 동의를 제공한 용도로만 사용됩니다. Microsoft는 음성 인식 시나리오 내에서는 음성 프로필 Teams 사용하지 않습니다.

예를 들어 Microsoft는 다음 상황에서 데이터를 사용하지 않습니다.

**다른 조직에서 모임에 참가할 때 내 음성 프로필 데이터가 사용하나요?**

조직의 사용자가 조직한 모임에만 해당하지 않습니다.

**내 음성 프로필을 내보낼 수 있나요?**

IT 관리자는 오디오 데이터를 수시로 내보낼 수 있습니다.

## <a name="related-topics"></a>관련 항목

[지원 문서: 지능형 스피커를 사용하여 객실 내 참가자 식별 ](https://support.microsoft.com/office/use-teams-intelligent-speakers-to-identify-in-room-participants-in-meeting-transcription-a075d6c0-30b3-44b9-b218-556a87fadc00)
