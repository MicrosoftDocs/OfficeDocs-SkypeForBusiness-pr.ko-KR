---
title: Microsoft Teams에서 공원 호출 및 검색
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.callparkpolicies.overview
- seo-marvel-apr2020
description: 통화 공원을 사용하여 Microsoft Teams에서 통화를 보류하는 방법을 알아보고 검색합니다.
ms.openlocfilehash: e64d9dafec0f3a4b65abc532ecfa60583fe6da84
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424596"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>Microsoft Teams에서 공원 호출 및 검색

통화 공원 및 검색은 사용자가 통화를 보류할 수 있는 기능입니다. 호출이 파크된 경우 서비스는 호출 검색을 위한 고유한 코드를 생성합니다. 통화를 저장한 사용자 또는 다른 사용자가 지원되는 앱 또는 장치에서 해당 코드를 사용하여 통화를 검색할 수 있습니다. (자세한 내용은 [Teams에서 Park 통화를](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) 참조합니다.)

호출 공원 사용에 대한 몇 가지 일반적인 시나리오는 다음과 같습니다.

- 안내원이 공장에서 근무하는 사람을 위해 전화를 걸고 있습니다. 그런 다음, 안내원이 공용 주소 시스템을 통해 전화 및 코드 번호를 발표합니다. 그런 다음 전화를 걸고 있는 사용자는 공장 층에서 Teams 전화를 선택하고 통화를 검색하는 코드를 입력할 수 있습니다.
- 디바이스 배터리가 전원이 부족하기 때문에 사용자가 모바일 디바이스에 통화를 걸 수 있습니다. 그러면 사용자는 Teams 데스크 전화에서 통화를 검색하는 코드를 입력할 수 있습니다.
- 지원 담당자는 고객 통화를 저장하고 전문가가 전화를 검색하고 고객을 지원하기 위해 Teams 채널에 공지 사항을 전송합니다. 전문가가 Teams 클라이언트에서 코드를 입력하여 호출을 검색합니다.

통화를 정비하고 검색하려면 사용자는 Enterprise Voice 사용자일 수 있으며 호출 공원 정책에 포함되어야 합니다.

> [!NOTE]
> 통화 공원 및 검색은 [Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md) 전용 배포 모드에서만 사용할 수 있으며 비즈니스용 Skype IP 전화에서는 지원되지 않습니다.

## <a name="configure-call-park-and-retrieve"></a>호출 공원 구성 및 검색

통화 공원을 구성하고 검색하려면 Teams 관리자 되어야 합니다. 기본적으로 사용하지 않도록 설정되어 있습니다. 호출 공원 정책을 사용하여 사용자에 대해 사용하도록 설정하고 사용자 그룹을 만들 수 있습니다. 사용자 집합에 동일한 정책을 적용하면 사용자들 사이에서 호출을 저장하고 검색할 수 있습니다.

통화 공원 정책을 사용하도록 설정하려면

1. Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 음성 통화 **공원**  >  **정책으로 이동하세요.**
2. 정책 **관리 탭에서** 추가를 **클릭합니다.**
3. 정책에 이름을 지정한 다음 호출 허용을 **켜기로** **전환합니다.**

    ![호출 공원 정책 설정 스크린샷](media/call-park-add-policy.png)

4. 저장을 **선택합니다.**

목록에서 정책을 선택하고 편집을 클릭하여 정책을 편집할 **수 있습니다.**

정책이 작동하려면 사용자에게 할당되어야 합니다. 사용자에게 [개별적으로 정책을](assign-policies.md) 할당하거나 그룹에 할당할 수 있습니다.

그룹에 통화 파트 정책을 할당하는 경우

1. 통화 공원 **정책 페이지의** 그룹 정책 **할당 탭에서** 그룹 **추가를 클릭합니다.**
2. 사용할 그룹을 검색한 다음 추가를 **클릭합니다.**
3. 다른 그룹 할당과 비교하여 순위를 선택 합니다.
4. 정책 **선택에서** 이 그룹을 할당하려는 정책을 선택합니다.

    ![](media/call-park-assign-policy-to-group.png)

5. 적용을 **클릭합니다.**

## <a name="related-topics"></a>관련 항목

[Teams에서 전화 걸기](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[Teams에서 사용자에게 정책 할당](assign-policies.md)

[New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)