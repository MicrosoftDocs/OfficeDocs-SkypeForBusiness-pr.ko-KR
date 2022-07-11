---
title: Teams 모임에서 Q&A 관리
author: wlibebe
ms.author: wlibebe
ms.reviewer: sameer.sitaram
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.localizationpriority: medium
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
description: IT 관리자가 질문 수집, 토론 구성, 개별 메시지 삭제, 사용 가능한 언어 사용, 데이터 보존 및 삭제 정책 이해에 대한 구조화된 접근 방식을 위해 Teams Q&A에서 Q&A를 설정, 사용 및 관리하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 387f66967a4448ff15374d6765e10ae25a72d7c0
ms.sourcegitcommit: 8d7a926758971bee491d24f23b1ad14f5e5c6f7f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2022
ms.locfileid: "66713446"
---
# <a name="manage-qa-in-teams-meetings"></a>Teams 모임에서 Q&A 관리

Q&A를 사용하면 발표자가 참석자의 질문을 받아 실시간으로 답변할 수 있습니다. 이 기능은 타운 홀, 웨비나, 모든 손, 교육 등 구조화된 대규모 모임에 가장 적합합니다.

이 문서에서는 이끌이가 모임에서 Teams Q&A를 사용하도록 설정할 수 있는지 여부를 결정하는 Q&A 및 사용자 수준 정책을 관리하는 방법을 설명합니다.

> [!NOTE]
> 이 기능은 현재 프라이빗 미리 보기로 제공되며 공개적으로 액세스할 수 없습니다. 프라이빗 미리 보기 프로그램에 참여하려면 [여기에서 등록하세요.](https://m365crmedu.powerappsportals.com/LMSSignup/)


## <a name="prerequisites"></a>필수 구성 요소

- [Yammer의 IP 및 URL](/microsoft-365/enterprise/urls-and-ip-address-ranges)에 대한 액세스를 차단하지 않았는지 확인합니다.
- 조직의 사용자가 Teams 모임에 Q&A를 추가할 수 있도록 하려면 Office 365 Yammer 서비스에 대한 로그인이 Azure Active Directory에서 사용하도록 설정되어 있는지 확인해야 합니다. 아래 단계에 따라 로그인이 사용하도록 설정되어 있는지 확인합니다.
  - **Azure AD 관리 센터** > **모든 서비스** > **엔터프라이즈 애플리케이션** > **Office 365 Yammer** > **속성** 으로 이동합니다.
  - **사용자가 로그인할 수 있도록 설정하려면** 필요한 경우 **[예**]를 선택합니다.

## <a name="who-can-use-qa"></a>Q&A를 사용할 수 있는 사용자

Q&A는 다음 사용자 유형에서 사용할 수 있습니다.

- 일반 사용자 - 테넌트에 Microsoft 365 자격 증명이 있는 사용자입니다.
- 페더레이션된 사용자 - 다른 테넌트에 대한 Microsoft 365 자격 증명을 사용하는 사용자입니다.
- 게스트 사용자 - Microsoft Teams, SharePoint 또는 Azure Active Directory에 추가하는 모든 게스트입니다.

관리자가 Q&A를 사용하도록 설정하면 이끌이 역할이 있는 사용자는 모임을 만들거나 업데이트할 때 Q&A를 켤 수 있습니다. Teams 및 Outlook 모임 옵션을 통해 이끌이는 이전에 추가된 모임에서 Q&A를 제거하여 참석자가 이 기능을 사용하지 못하도록 할 수도 있습니다.

## <a name="use-the-teams-admin-center-to-manage-qa"></a>Teams 관리 센터를 사용하여 Q&A 관리

> [!NOTE]
> 관리 센터에서 Q&A 관리는 공개 미리 보기에서 사용할 수 없습니다. PowerShell을 사용하여 사용자에 대한 Q&A를 설정하고 관리합니다.

조직에 Q&A를 설정할 수 있는 이끌이를 제한하기 위한 요구 사항이 있을 수 있습니다. Teams 관리 센터를 사용하여 대규모 모임에서 Q&A를 설정할 수 있는 이끌이를 관리할 수 있습니다.
다음 단계에 따라 Q&A를 사용할 수 있는 이끌이를 제어합니다.

1. Teams 관리 센터에서 **모임 모임** > [**정책**](/meeting-policies-participants-and-guests)으로 이동합니다.
2. 기존 정책을 선택하거나 새 정책을 만들고 "이러한 이끌이에 대한 Q&A 없음"과 같은 이름을 지정합니다.
3. **"참가자 & 게스트"** 라는 섹션으로 스크롤하여 **"질문 & 답변 환경"** 설정에 대해 사용하지 않도록 설정하고 정책을 저장합니다.
4. Q&A를 설정하지 못하게 하려는 특정 M365 그룹, 최종 사용자 또는 구독에 정책을 할당합니다.

## <a name="use-powershell-to-manage-qa"></a>PowerShell을 사용하여 Q&A 관리

조직에 Q&A를 설정할 수 있는 이끌이를 제한하기 위한 요구 사항이 있을 수 있습니다. PowerShell을 사용하여 대규모 모임에서 Q&A를 설정할 수 있는 이끌이를 관리할 수 있습니다.

Q&A를 사용하도록 설정하는 PowerShell 명령 예제:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -QnAEngagementMode Enabled
```

## <a name="delete-an-individual-message-from-qa-in-teams"></a>Teams의 Q&A에서 개별 메시지 삭제

Q&A 애플리케이션에 게시된 질문 또는 답변을 삭제하려면 다음 단계를 수행합니다.

1. Exchange 관리 센터에 전역 관리자로 로그인합니다.
2. **받는 사람** > **사서함** 으로 이동하여 모임을 구성한 사용자의 이름으로 검색합니다.
3. 모임 이끌이를 선택하고 **사서함 위임 관리를** 클릭합니다. **읽기 및 관리** 섹션에서 **추가 권한** **편집** > 을 선택합니다.
4. 자신을 모임 이끌이의 대리인으로 추가하고 저장을 선택합니다.
5. 바탕 화면이 아닌 Outlook Web App Outlook 일정 열고 **일정 추가** 를 선택한 다음 **디렉터리에서 추가를** 선택합니다.
6. 모임 이끌이를 검색하고 일정을 **내 일정** 에 추가합니다. 이제 선택한 사용자의 모임이 일정에 표시됩니다.
7. 일정에서 콘텐츠를 삭제할 모임을 찾고, 모임 레코드를 열고, **참가자와 채팅** 을 선택합니다. 참가자와의 채팅을 선택하면 Teams에서 모임 채팅이 열립니다.
8. Teams 앱 바에서 Q&A 애플리케이션으로 이동합니다.
9. 삭제하려는 질문이나 답변을 찾아 삭제를 선택합니다.
10. 콘텐츠 삭제가 완료되면 Exchange 관리 센터로 돌아가서 모임 이끌이의 대리인으로 자신을 제거합니다.

> [!NOTE]
> 답변을 제거하기 전에 질문을 삭제하면 질문에 대한 첫 번째 대답이 질문이 됩니다.
>
> 이를 방지하려면 다음 단계를 순서대로 수행합니다.
>
> 1. 삭제하려는 질문 식별
> 2. 질문에 대한 답변 삭제
> 3. 질문 삭제

## <a name="available-languages-for-yammer-versus-teams"></a>Yammer 및 Teams에 사용 가능한 언어

Q&A는 기본적으로 Teams에 대한 사용자의 언어로 설정됩니다. Teams와 Yammer에 사용할 수 있는 언어에 차이가 있는 경우 다음 언어 기본값이 발생합니다.

- 가장 가까운 기본 언어 - Yammer는 사용 가능한 경우 가장 가까운 기본 언어로 기본 설정됩니다. 예를 들어 Yammer는 프랑스어 캐나다어(fr-CA) 버전을 제공하지 않으므로 대신 프랑스어(fr-FR)로 콘텐츠를 표시합니다.
- 지원되지 않는 언어 - Yammer에서 언어를 전혀 제공하지 않으면 Yammer는 기본적으로 미국 영어(en-US)로 설정됩니다.

## <a name="ediscovery"></a>eDiscovery

q&A용 eDiscovery는 다른 Yammer 콘텐츠에 대한 eDiscovery와 동일하게 작동합니다.

- 테넌트의 Teams 애플리케이션에서 Teams Q&A를 사용하는 경우 이 콘텐츠는 Yammer 네트워크의 구성 또는 존재 여부에 관계없이 eDiscovery에서 사용할 수 있습니다. 표준 Yammer 콘텐츠에 eDiscovery를 사용하려면 Yammer 네트워크가 [기본 모드](/yammer/configure-your-yammer-network/overview-native-mode)여야 합니다.
- eDiscovery를 수행할 때 Yammer에서 또는 Teams의 Q&A를 통해 메시지가 생성되었는지 여부를 확인할 수 있습니다. 파일 메타데이터 섹션에서 항목 클래스 필드에서 해당 정보를 찾을 수 있습니다.
- 조직에서 Yammer에서 제공하는 Teams Q&A를 사용하는 경우 Q&A에서 생성된 콘텐츠는 Yammer 콘텐츠로 간주되며 검색할 수 있습니다. Microsoft 365 앱의 eDiscovery에 대한 자세한 내용은 [Microsoft 365의 eDiscovery 솔루션을](/microsoft-365/compliance/ediscovery) 참조하세요.
- 모임 이끌이가 익명 게시를 사용하도록 설정하면 참석자가 게시하는 질문이 eDiscovery에 대한 이끌이의 사서함에 수집됩니다.

## <a name="data-storage"></a>데이터 스토리지

Q&모임의 일부로 만든 메시지는 Yammer 메시지로 저장됩니다. 이러한 메시지는 Yammer에 저장되고 eDiscovery용으로 수집됩니다.
파일은 항상 모든 데이터 미사용 정책 및 위치를 처리하는 SharePoint에 저장됩니다.

다음 지침에서는 메시징 데이터가 저장되는 방법을 설명합니다.

- Q&사용자 수준에서 eDiscovery 및 Advanced eDiscovery 통해 콘텐츠를 검색할 수 있습니다.
- 메시지 데이터(메시지 콘텐츠 포함)는 기본적으로 고객의 Yammer 네트워크 위치에 따라 북아메리카 또는 EU에 저장됩니다.
- 기존 Yammer 네트워크가 없는 테넌트의 경우 미국 Yammer 지역에 Q&Yammer 네트워크가 만들어집니다. Q&A에 대한 조직의 메시지는 항상 미국에 저장됩니다.
- OneNote 탭과 마찬가지로 모임에서 Q&A를 제거해도 모임 데이터는 삭제되지 않습니다. 모임에서 Q&A를 제거하면 모임의 데이터에 대한 액세스 권한만 제거됩니다. Q&A 탭을 다시 추가하면 모든 모임 대화가 다시 표시됩니다.

## <a name="gdpr-for-qa-in-teams"></a>Teams의 Q&A에 대한 GDPR

Microsoft 365 관리 센터를 통해 데이터 주체 요청을 완료하면 Q&A의 모든 콘텐츠에서 사용자의 연락처 정보가 자동으로 제거됩니다.

## <a name="data-lifecycle-for-qa-in-teams"></a>Teams에서 Q&A에 대한 데이터 수명 주기

Teams의 Q&A에서 생성된 데이터의 수명 주기는 규정 준수 센터의 Yammer 데이터 보존 설정에 따라 달라집니다. Azure Active Directory를 통해 해당 기판 분할된 데이터베이스의 Q&A 메시지 복사본을 받은 모임의 모든 사용자를 하드 삭제하는 경우 Yammer는 사용자 삭제 후 30일 이내에 해당 모임에 대한 Q&A 콘텐츠의 복사본을 삭제합니다.

## <a name="retention-and-deletion"></a>보존 및 삭제

콘텐츠 보존은 Yammer 및 Teams에 대해 서로 다른 정책을 설정했는지 여부에 관계없이 Yammer에 대해 설정된 보존 정책을 따릅니다.

> [!NOTE]
> Yammer Network가 기본 모드가 아닌 경우 여기에서 만든 정책은 Teams Q&A 데이터에만 적용됩니다. 기본 모드에서 모든 Yammer 사용자는 azure Active Directory(Azure AD)에 있고, 모든 그룹은 Microsoft 365 그룹이며, 모든 파일은 SharePoint Online에 저장됩니다.

## <a name="faq"></a>FAQ

**Q: Q&콘텐츠를 내보낼 어떻게 할까요? 있나요?**

**A:** Q&콘텐츠는 Microsoft 365 규정 준수 센터 저장되고 eDiscovery를 통해 액세스됩니다. 향후 반복에는 모임 이끌이를 위한 모임 하이라이트 보고서 및 내보내기 기능이 포함됩니다.

**Q: Q&A는 Microsoft 365 Multi-Geo 기능을 지원하나요?**

**A:** Q&A는 현재 Microsoft 365 Multi-Geo 기능을 지원하지 않습니다. Q&데이터는 고객의 Yammer 네트워크 위치에 따라 기본적으로 북아메리카 또는 EU에 저장됩니다.

**Q: 구조화된 모임에 대해 자세히 알아볼 수 있는 위치는 어디인가요?**

**A:** Microsoft Teams에서 성공적인 대규모 모임을 호스트하기 위한 모범 [사례를](/MicrosoftTeams/quick-start-meetings-live-events) 따릅니다.

**Q: Teams 앱 스토어를 통해 Q&A를 설정하는 것과 모임 옵션을 사용하는 것의 차이점은 무엇인가요?**

**A:** 참석자 및 중재자 사용자 환경에는 차이가 없지만 앞으로 Q&A는 모임 옵션을 사용하여 설정해야 합니다. Teams 앱 스토어의 Q&A 앱은 2022년 말까지 더 이상 사용되지 않으므로 모임 옵션을 사용하여 모임에서 Q&A를 설정하는 것이 가장 좋습니다.
