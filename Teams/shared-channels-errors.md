---
title: Microsoft Teams의 공유 채널 오류
author: MikePlumleyMSFT
ms.author: mikeplum
manager: serdars
ms.reviewer: jasonlewis
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: normal
search.appverid: MET150
description: Microsoft Teams의 공유 채널에서 오류 수정을 사용하는 방법을 알아봅니다.
ms.openlocfilehash: ecd05f1593817ed03d6e516e8915cd15694b6315
ms.sourcegitcommit: 3266fde54b92a18865d666b98e4e7e8322b9dedc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/26/2022
ms.locfileid: "67024165"
---
# <a name="shared-channels-errors-in-microsoft-teams"></a>Microsoft Teams의 공유 채널 오류

조직 외부의 사용자를 공유 채널에 추가하려고 할 때 사용자에게 오류 메시지가 표시되는 경우 이 문서의 설정을 확인합니다. 

## <a name="due-to-admin-policy-you-cant-add-external-people-to-the-channel-for-more-info-talk-to-your-admin"></a>관리 정책으로 인해 외부 사용자를 채널에 추가할 수 없습니다. 자세한 내용은 관리자에게 문의하세요.

Teams는 팀 멤버 자격에 Microsoft 365 그룹 사용합니다. 조직 외부의 사용자가 공유 채널에 추가되려면 Microsoft 365 그룹 게스트 설정을 설정해야 합니다. 사용자에게 이 오류가 표시되면 조직 외부 사용자에 대한 Microsoft 365 그룹 설정을 확인합니다.

조직 외부 사용자에 대한 Microsoft 365 그룹 설정을 지정하려면
1. Microsoft 365 관리 센터 왼쪽 탐색 창에서 **설정을 확장합니다**.
1. **조직 설정을** 클릭합니다.
1. 목록에서 **Microsoft 365 그룹** 클릭합니다.
1. **Let 그룹 소유자가 게스트로 Microsoft 365 그룹 조직 외부의 사용자를 추가하고** **게스트 그룹 구성원이 그룹 콘텐츠에 액세스하도록 허용** 확인란이 모두 선택되어 있는지 확인합니다.
1. 변경한 경우 **변경 내용 저장** 을 클릭합니다.

## <a name="due-to-admin-policy-you-cant-add-external-people-to-the-channel"></a>관리자 정책으로 인해 채널에 외부 사용자를 추가할 수 없습니다.

Teams 채널 정책은 사용자가 공유 채널과 상호 작용하는 방법을 결정합니다. 사용자에게 이 오류 메시지가 표시되면 해당 사용자의 채널 정책을 확인합니다.

조직 외부 사용자를 공유 채널에 초대하는 정책을 설정하려면
1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 Teams > Teams 정책으로 이동합니다.
1. 사용자에게 할당된 정책을 선택합니다.
1. **공유 채널에 외부 사용자를 초대할 수** 있는지 확인합니다 **.**
1. 변경한 경우 **적용** 을 선택합니다.

Teams 채널 정책에 대한 자세한 내용은 [Microsoft Teams의 채널 정책 관리를 참조하세요](teams-policies.md).

## <a name="you-cant-share-this-channel-with-people-from-this-org"></a>이 조직의 사용자와 이 채널을 공유할 수 없습니다.

사용자에게 이 오류가 표시되면 Azure Active Directory 테넌트 간 액세스 설정을 통해 다른 조직의 사용자와 채널을 공유할 수 없습니다. 이는 조직의 인바운드 설정 또는 다른 조직의 아웃바운드 설정 때문일 수 있습니다.

조직의 인바운드 설정을 확인하려면
1. [Azure Active Directory](https://aad.portal.azure.com)에서 **외부 ID** 를 선택한 다음 테 **넌트 간 액세스 설정을** 선택합니다.
1. 확인하려는 조직의 인바운드 액세스 링크를 선택합니다.
1. **B2B 직접 연결** 탭에서 **설정 사용자 지정을** 선택합니다.
1. **외부 사용자 및 그룹** 탭에서 **액세스 허용** 및 **모든 외부 사용자 및 그룹이** 선택되었는지 확인하거나 **외부 사용자 및 그룹 선택을** 선택한 경우 초대되는 사용자가 선택한 그룹의 구성원인지 확인합니다.
1. 변경한 경우 **저장** 을 선택하고 **인바운드 액세스 설정** 블레이드를 닫습니다.

사용자가 오류를 계속 볼 경우 공동 작업 중인 조직을 확인합니다. 해당 조직의 아웃바운드 설정은 조직과의 공유를 허용하지 않을 수 있습니다. 조직 간에 공유 채널을 설정하는 방법에 대한 자세한 내용은 [공유 채널에서 외부 참가자와 공동 작업을 참조하세요](/microsoft-365/solutions/collaborate-teams-direct-connect).

## <a name="we-couldnt-find-any-matches-make-sure-the-email-address-is-correct-or-talk-to-your-admin"></a>일치하는 항목을 찾을 수 없습니다. 전자 메일 주소가 올바른지 확인하거나 관리자에게 문의하세요.

사용자에게 이 오류가 표시되면 Microsoft 365는 외부 조직에서 지정된 전자 메일 주소를 찾을 수 없습니다. 외부 조직에서 주소를 확인해야 합니다.

